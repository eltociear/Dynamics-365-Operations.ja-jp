---
title: "注文処理オプションの設定"
description: "このトピックでは、方法をアクション]、Microsoft Dynamics 365を使用してコール センターの注文を処理する方法を説明します。"
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78973
ms.assetid: 09fca083-ac0d-4f30-baf2-bb00a626be12
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: eb62073fdfa50576d2c613594f3d85cbc0b322f6
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-order-processing-options"></a>注文処理オプションの設定

このトピックでは、方法をアクション]、Microsoft Dynamics 365を使用してコール センターの注文を処理する方法を説明します。 

Dynamics 365 for Operationsの[小売りとコマースは、オンライン店舗、リアルタイム店舗とコール センターなど、複数の小売チャンネルをサポートします。 コール センターでは、作業者は電話で顧客の注文をとり販売注文を作成します。 このトピックでは、コール センターを作成およびコール センターのオプションをコンフィギュレーションする方法を説明します。 各コール センターは、独自のユーザー、支払方法、価格グループ、財務分析コード、配達のモードを使用できます。 コール センターを作成するとき、これらのオプションをコンフィギュレーションできます。 **重要:** 現在の Dynamics AX ユーザーが販売注文を作成する場合、コール センターのワークフローを使用する前に、コール センター ユーザーとしてコール センターに割り当てられている必要があります。 **コール センター**ページは、コール センターに固有の機能グループを有効または無効にするために使用できます。 次の機能グループを有効にできます。

-   [**注文完了**] – このグループには [**販売注文**] ページの支払いおよび注文完了に関連する機能が含まれます。
-   [**主導販売**] – このグループにはソース コード、スクリプト、カタログ要求に関連する機能が含まれます。 

コール センターの設定でこれらの機能を有効にすると、コール センターに関連付けられたユーザーは**販売注文**ページを使用できます。 これらの機能の多くは、使用する前に追加の設定が必要です。 画像およびスクリプトは、特定のコール センターのインデックス化された販売設定の一部として有効になります。 これらの機能が有効な場合、スクリプトおよび製品画像は**販売注文**ページの情報ボックス ウィンドウに表示されます。 製品に対して設定されている既定の画像が表示されます。 スクリプトは、品目、カタログ、顧客、またはカタログのコンテキストの品目に対してコンフィギュレーションできます。 コール センター注文で、特定の注文明細行の価格の設定に関する追加情報を表示できます。 たとえば、注文はどの割引が適用されるかを示します。 **売掛金勘定** **設定で**この &gt; 機能を使用 &gt; して**売掛金勘定パラメータ** &gt; **価格** &gt; **価格の詳細**。 **販売注文明細行**ボックスの一覧から**価格の詳細**ページにアクセスできます。 注文イベント追跡は監査の目的で使用すると、注文の有効期間中に注文に対して実行されるアクションを確認、または特定のユーザーのアクションを追跡することができます。 たとえば、ユーザーが販売注文を作成、注文を保留に設定、請求金額を変更、注文明細行を更新するたびに、アクションを記録できます。 特定のユーザー、ユーザーのグループ、または特定の期間内のすべてのユーザーを追跡するアクションに対し、注文イベントを設定できます。 そのドキュメントのページのアクション ウィンドウから**注文イベント**ページをオープンして、ドキュメントに対して実行されたアクションを表示できます。 **販売およびマーケティング** **設定で**注文の &gt; イベントを設定できます &gt;。**イベント** &gt; **注文のイベント**。 顧客の注文を期限までに出荷できない場合、会社は顧客に通知のための電子メール メッセージを自動的に送信して、注文の状態を説明し、顧客に注文キャンセルの機会を与えることができます。 遅延が指定したしきい値を超えた場合、注文は自動的にキャンセルできます。 最大 3 個の電子メール メッセージを指定した間隔で送信できます。

1.  **最初の取消通知** – 顧客が注文をキャンセルできます。
2.  **最初の取消通知** – 顧客が注文をキャンセルできます。
3.  **最終取消通知** – システムが注文をキャンセルし、顧客にキャンセルが通知されます。

個別の顧客および製品に対して、自動通知および取消プロセスを除外できます。 利益幅警告は品目を注文に追加するときに発生します。 警告には、価格の利益幅と品目の収益性など、品目に関する重要な情報が含まれます。 販売注文に品目を追加するときに価格変更が適切かどうかを判断するには、この情報を使用できます。 たとえば、ある品目に対してコストの 40 パーセント以上のしきい値が許容され、コストの 20 から 39 パーセントが疑わしいと指定する、取引利益幅のしきい値を設定します。 この場合、20 から 39 パーセントのしきい値を持つ品目は警告をトリガーします。 コストの 20 パーセント未満のしきい値を持つ品目は販売できず、品目価格の調整ができません。 **売掛金勘定** **設定で**利益 &gt; 幅の警告を設定できます &gt;。**売掛金勘定パラメータ** &gt; **利益幅の警告**。 既定のルールに基づいて売上税の割り当てを設定するとき、住所要素に対する照合の優先順位を指定できます。 たとえば、郵便番号による売上税グループの照合が、州による売上税グループの照合よりも優先順位が高くなるように指定できます。 新しい顧客住所レコードを入力するとき、顧客の住所が既定のルールとどのように一致するか、および定義した優先順位照合に基づいて、売上税グループが自動的に割り当てられます。 **総勘定元帳のパラメータ**ページでこの機能をコンフィギュレーションできます。

