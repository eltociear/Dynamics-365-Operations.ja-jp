---
title: 新しい E コマース テナントの配置
description: このトピックでは、Microsoft Dynamics Lifecycle Services (LCS) を使用して新しい E コマース テナントを配置する方法について説明します。
author: psimolin
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6d7dfcaf244260de5f39a1201ec1ea78e94351e7
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001786"
---
# <a name="deploy-a-new-e-commerce-tenant"></a>新しい E コマース テナントの配置


[!include [banner](includes/banner.md)]

このトピックでは、Microsoft Dynamics Lifecycle Services (LCS) を使用して新しい E コマース テナントを配置する方法について説明します。

## <a name="overview"></a>概要

Microsoft Dynamics Lifecycle Services (LCS) は、パートナーや顧客がプロジェクト環境を管理したり、Microsoft Dynamics 製品や機能に関する最新情報を表示したり、サポート インシデントを作成、追跡、参照したりするために使用できる、クラウドベースのコラボレーション ワークスペースです。 E コマースの管理機能は LCS に統合されています。

LCS の詳細については、[Lifecycle Services ユーザー ガイド](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)を参照してください。
    
## <a name="get-started"></a>はじめに

E コマースを初期化する前に、プロジェクト、環境、および Retail Cloud Scale Unit (RCSU) を初期化する必要があります。 LCS で初期化を行うには、プロジェクト所有者ロールまたは環境マネージャ ロールのいずれかのアクセス許可が必要です。 実稼働環境とサンドボックス環境のトポロジがサポートされています。

環境に関する詳細については、[環境計画](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning)を参照してください。 RCSU の詳細については、[Retail Cloud Scale Unit の初期化](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels)を参照してください。

## <a name="initialize-e-commerce"></a>E コマースの初期化

この手順を使用して、既存環境で E コマースを初期化します。

開始する前に、次の必要な情報があることを確認してください。

- 使用される RCSU。
- E コマース システムで使用される Microsoft Azure Active Directory セキュリティ グループ。
- 評価およびレビュー モデレーターで使用される Microsoft Azure Active Directory セキュリティ グループ。
- 環境に関連付けられるドメイン。

さらに、次のオプション情報を収集できます。

- Azure AD 企業と顧客間 (B2C) 情報:

    - テナント名。
    - クライアント ID。
    - ログイン カスタム ドメイン。
    - 返信 URL。
    - ポリシー ID のサインアップ サインイン。
    - リセット パスワード ポリシー ID。
    - プロファイル ポリシー 編集 ID。

[!NOTE]
この情報は、サービス要求を介して後から追加できます。

必要な情報を収集したら、次の手順に従って E コマースを初期化します。

1. [LCS](https://lcs.dynamics.com) にサインインします。
1. E コマースを初期化する環境を含むプロジェクトを開きます。
1. **環境**セクションで、環境を選択します。
1. **環境機能**で、**小売管理**のリンクを選択します。
1. **E コマース** タブで、**設定**を選択します。 ダイアログ ボックスが表示されるので、プロビジョニングに必要な情報を入力します。
1. 必要な情報を入力し、次のページに進みます。
1. 次のページで必要な情報を入力し、フォームを送信します。 **E コマース** タブに戻り、初期化が開始されていることを確認します。
1. 初期化の状態を表示するには、**更新**もしくは後で **E コマース** タブに戻ります。
    
E コマースが LCS から初期化されると、システムは E コマースに必要な複数のコンポーネントをプロビジョニングし、それらを環境に関連付けます。 プロビジョニングが完了すると、**小売管理**ページの **E コマース** タブが更新されて、プロビジョニングが反映されます。 このページには、最新のカスタマイズ配置と、進行中の他の配置状態が表示されます。 また、E コマース サイトおよび作成されるサイトの E コマース サイト ビルダーへのリンクも含まれています。

## <a name="access-site-builder"></a>サイト ビルダーへのアクセス

サイト ビルダーにアクセスするには、LCS の**小売管理**ウィンドウの **E コマース** タブに移動し、**E コマース サイトの管理ツール**のリンクを選択します。 サイト ビルダー ランディング ページには、テナント レベルのビューが表示されます。 このページから次の操作を実行できます。

- テナント レベルの設定を変更します。
- 作成したサイトで、表示するためのアクセス許可を持っているサイトに移動します。 
- 管理および報告などのレビュー機能にアクセスします。
- 新しいサイトを作成します。 新しいサイトを作成する方法の詳細については、[新しい E コマース サイトの作成](create-ecommerce-site.md) を参照してください。 

## <a name="additional-resources"></a>追加リソース

[ドメイン名のコンフィギュレーション](configure-your-domain-name.md)

[E コマース サイトの作成](create-ecommerce-site.md)

[チャンネルとオンライン サイトの関連付け](associate-site-online-store.md)

[robots.txt ファイルの管理](manage-robots-txt-files.md)

[ユーザー ログイン用のカスタム ページの設定](custom-pages-user-logins.md)

[コンテンツ配信ネットワーク (CDN) のサポートの追加](add-cdn-support.md)

[場所に基づく店舗検出の有効化](enable-store-detection.md)
