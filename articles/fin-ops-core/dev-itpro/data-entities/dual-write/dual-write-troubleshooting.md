---
title: データ統合のトラブルシューティング ガイド
description: このトピックでは、Finance and Operations アプリと Common Data Service 間のデータ統合に関するトラブルシューティングの情報を提供します。
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 87bdb72024c1c3844ff61e832a92f7edcc77c5d6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019881"
---
# <a name="troubleshooting-guide-for-data-integration"></a>データ統合のトラブルシューティング ガイド

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

## <a name="enable-plug-in-trace-logs-in-common-data-service-and-inspect-the-dual-write-plug-in-error-details"></a>Common Data Service のプラグイン トレース ログを有効にし、デュアル書き込みプラグイン エラーの詳細を検査

デュアル書き込み同期中に問題またはエラーが発生した場合は、これらの手順に従って追跡ログのエラーを検査します。

1. エラーを検査する前に、プラグイン トレース ログを有効にする必要があります。 手順については、[チュートリアル: プラグインの書き込みおよび登録](https://docs.microsoft.com/powerapps/developer/common-data-service/tutorial-write-plug-in#view-trace-logs) の "トレースログの表示" を参照してください。

    これでエラーを検査できるようになります。

2. Microsoft Dynamics 365 Sales にサインインします。
3. **設定**ボタン (ギヤ記号) を選択してから、**詳細設定**を選択します。
4. **設定**メニューで、**カスタマイズ \> プラグイン トレース ログ**を選択します。
5. タイプ名として **Microsoft.Dynamics.Integrator.CrmPlugins.Plugin** を選択して、エラー詳細を表示します。

## <a name="inspect-dual-write-synchronization-errors"></a>デュアル書き込み同期エラーの調査

テスト中のエラーを検査するには、次の手順に従います。

1. Microsoft Dynamics Lifecycle Services (LCS) にログインします。
2. LCS プロジェクトを開いて、デュアル書き込みテストを実行します。
3. **クラウド ホスト環境**を選択します。
4. LCS に表示されるローカル アカウントを使用して、アプリケーション バーチャル マシン (VM) へのリモート デスクトップ接続を実行します。
5. イベント ビューアーを開きます。 
6. **アプリケーションとサービス ログ \> Microsoft \> Dynamics \> AX-DualWriteSync \> オペレーション**の順に移動します。 エラーと詳細が表示されます。

## <a name="unlink-one-common-data-service-environment-from-the-application-and-link-another-environment"></a>1 つの Common Data Service 環境をアプリケーションからリンク解除し、別の環境をリンクする

リンクを更新するには、以下の手順を実行します。

1. アプリケーション環境に移動します。
2. データ管理を開きます。
3. **アプリ用 CDS** を選択します。
4. 実行しているすべてのマッピングを選択してから、**停止**を選択します。
5. すべてのマッピングを選択してから、**削除**を選択します。

    > [!NOTE]
    > **CustomerV3-Account** テンプレートが選択されている場合、**削除**オプションは利用できません。 必要に応じて、このテンプレートの選択をクリアします。 **CustomerV3-Account** は古いプロビジョニングされたテンプレートであり、見込み客から現金化ソリューションで動作します。 グローバルにリリースされているため、すべてのテンプレートの下に表示されます。

6. **リンク解除の環境**を選択します。
7. **はい**を選択して操作を確認します。
8. 新しい環境をリンクするには、[インストール ガイド](https://aka.ms/dualwrite-docs) の手順に従います。
