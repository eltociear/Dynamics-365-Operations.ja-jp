---
title: Commerce Data Exchange とコマース チャネルのコミュニケーション
description: このトピックでは、Commerce Data Exchange とその要素の概要を示します。 ここでは、Microsoft Dynamics 365 Commerce バックオフィスとチャネルとの間でのデータの転送で各コンポーネントが果たす役割について説明します。
author: athinesh99
manager: AnnBe
ms.date: 11/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations, Retail
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9dce413f378edbc5203d7ccca3f8cc6e0ca7dab4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004584"
---
# <a name="commerce-data-exchange-and-commerce-channel-communications"></a>Commerce Data Exchange とコマース チャネルのコミュニケーション

[!include [banner](../includes/banner.md)]

このトピックでは、Commerce Data Exchange とその要素の概要を示します。 ここでは、Microsoft Dynamics 365 Commerce バックオフィスとチャネルとの間でのデータの転送で各コンポーネントが果たす役割について説明します。

<a name="overview"></a>概要
--------

Commerce Data Exchange は、オンライン ストアまたは従来型の店舗などの、バックオフィスとチャネル間でデータを転送するシステムです。 チャネルのデータを格納するデータベースは、コマース データベースとは別にあります。 チャネルのデータベースは、トランザクションに必要なデータのみ格納します。 マスター データがバックオフィスでコンフィギュレーションされ、チャネルに配分されます。 トランザクション データは販売時点管理 (POS) システムまたはオンライン店舗で作成され、バックオフィスにアップロードされます。 データ配送は非同期です。 つまり、データを収集してソースでパッケージングするプロセスは、データを取得して適用するプロセスとは別に行われます。 価格および在庫検索などのシナリオの場合、データはリアルタイムに取得する必要があります。 これらのシナリオをサポートするために、Commerce Data Exchange には、バックオフィスとチャネル間のリアルタイム通信を可能にするサービスが含まれます。 

## <a name="async-service"></a>非同期サービス
Commerce データベースの Microsoft SQL Server 変更追跡は、チャネルに送信する必要のあるデータの変更内容を特定するのに使用されます。 配送スケジュールに基づいて、バックオフィスはそのデータをパッケージングして中央の保存場所 (Azure Blob Storage) に保存します。 別のバッチ処理は、このデータ パッケージをチャネルのデータベースに挿入するために Commerce Data Exchange: Async Client ライブラリを使用します。 

[![非同期サービス](./media/async-300x239.png)](./media/async.png)

### <a name="commerce-scheduler"></a>コマース スケジューラ

スケジューラ ジョブとは、データを配送場所へ (から) 配送するためのメカニズムです。 ジョブは、配分するデータを含むテーブルおよびテーブル フィールドを指定するサブジョブで構成されます。 バックオフィスには、ほとんどの組織のレプリケーションの要件を満たすサブジョブと定義済スケジューラ ジョブが含まれます。 次のタイプの定義済ジョブが作成されます。

-   **ダウンロード ジョブ** – ダウンロード ジョブは、バックオフィスからチャネル データベースに変更されたデータを送信します。 レコードへの変更は、SQL Server 変更履歴によって追跡されます。
-   **アップロード ジョブ (P ジョブ)** – アップロード ジョブは、チャンネルからコマース データベースへの販売トランザクションをプルします。 P ジョブは、データを漸増的にアップロードします。 P ジョブが実行されると、Async Client ライブラリが場所から既に受け取ったレコードに対するレプリケーション カウンターをチェックします。 レコードは、レプリケーション カウンターが検出された最大値を超える場合のみアップロードされます。 P ジョブは以前にアップロードされたデータを更新しません。

配送スケジュールは、手動またはバックオフィスでスケジューリングされたバッチ ジョブによるデータ転送の実行に使用されます。 配送スケジュールには、1 つ以上のチャンネル データ グループと 1 つ以上のスケジューラ ジョブを含めることができます。 スケジューラー・ジョブが円滑に実行されていることを確認するには、インスタンス用に構成された「既定の」データベース名を変更せず、2 番目のデータベースを作成しないでください。 Commerce Scale Unit ではないすべてのデータベースは Microsoft により管理され、1 つの既定のデータベースのみが必要です。 

## <a name="realtime-service"></a>リアルタイム サービス
Commerce Data Exchange: リアルタイム サービスは、バックオフィスと小売チャネル間のリアルタイム通信を提供する統合サービスです。 リアルタイム サービスにより、個々の POS コンピューターとオンライン ストアがバックオフィスから特定のデータをリアル タイムで取得できるようになります。 ほとんどのキー操作はローカルのチャンネル データベースで実行できますが、次のシナリオはバックオフィスに格納されているデータへの直接アクセスが必要です。

-   ギフトカードの発行および引換え
-   ロイヤルティ ポイントを引き換え
-   クレジット メモの発行および引換え
-   顧客レコードを作成または更新します
-   販売注文を作成、更新、完了しています
-   発注書または移動オーダーに対する在庫を入荷
-   棚卸資産会計の実行
-   店舗間から販売トランザクションを取得し、返品トランザクションを完了します

[![Real-time Service](./media/rts.png)](./media/rts.png) 

定義済の Real-time Service プロファイルが作成されます。
