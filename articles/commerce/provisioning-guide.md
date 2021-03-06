---
title: Dynamics 365 Commerce プレビュー環境のプロビジョニング
description: このトピックでは、Microsoft Dynamics 365 Commerce のプレビュー環境をプロビジョニングする方法について説明します。
author: psimolin
manager: annbe
ms.date: 01/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: cbd4c118de2e91c8849461b20a01403049a07e66
ms.sourcegitcommit: 4ed1d8ad8a0206a4172dbb41cc43f7d95073059c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "3024639"
---
# <a name="provision-a-dynamics-365-commerce-preview-environment"></a>Dynamics 365 Commerce プレビュー環境のプロビジョニング


[!include [banner](includes/banner.md)]

このトピックでは、Dynamics 365 Commerce のプレビュー環境をプロビジョニングする方法について説明します。

開始する前に、このトピックにざっと目を通して、プロセスに必要な内容を把握することをお勧めします。

> [!NOTE]
> Dynamics 365 Commerce プレビューへのアクセス許可がまだ与えられていない場合、[Dynamics 365 Commerce Web サイト](https://aka.ms/Dynamics365CommerceWebsite) からプレビューのアクセス許可を要求できます。

## <a name="overview"></a>概要

Commerce プレビュー環境を正常にプロビジョニングするには、特定の製品名とタイプを持つプロジェクトを作成する必要があります。 Commerce scale unit (CSU) には、後で E コマースをプロビジョニングするために使用する必要がある特定のパラメーターもあります。 このトピックの手順では、プロビジョニングを完了する必要があるすべての手順と、使用する必要があるパラメーターについて説明します。

Commerce プレビュー環境のプロビジョニングが正常に完了した後、いくつかのプロビジョニング後の手順を完了して準備する必要があります。 一部の手順は、システムのどの側面を評価するかに応じて使用するオプションです。 オプションの手順は、後からいつでも完了できます。

プロビジョニング後に Commerce プレビュー環境を構成する方法については、[Commerce プレビュー環境のコンフィギュレーション](cpe-post-provisioning.md)を参照してください。 Commerce プレビュー環境のオプション機能を構成する方法については、[Commerce プレビュー環境のオプション機能のコンフィギュレーション](cpe-optional-features.md)を参照してください。

プロビジョニングの手順について質問がある場合、または問題が発生した場合は、[Microsoft Dynamics 365 Commerce プレビュー Yammer グループ](https://aka.ms/Dynamics365CommercePreviewYammer)から Microsoft にご連絡ください。

## <a name="prerequisites"></a>必要条件

Commerce プレビュー環境をプロビジョニングする前に、次の前提条件が整っている必要があります。

- Microsoft Dynamics Lifecycle Services (LCS) ポータルへのアクセス許可があります。
- 既存の Microsoft Dynamics 365 のパートナーまたは顧客は、Dynamics 365 Commerce プロジェクトを作成できます。
- Dynamics 365 Commerce プレビュー プログラムを承諾しました。
- **移行、ソリューションの作成、および学習**のためにプロジェクトを作成するのに必要なアクセス許可があります。
- 環境のプロビジョニングを行うプロジェクトで、**環境管理者**または**プロジェクト所有者**ロールのメンバーになっています。
- Microsoft Azure サブスクリプションへの管理者アクセス許可があるか、または代理として管理者アクセス許可が必要な 2 つの手順を完了することができるサブスクリプション管理者の連絡先があります。
- Azure Active Directory (Azure AD) テナント ID が使用可能です。
- E コマース システムの管理者グループとして使用される  Azure AD セキュリティ グループが作成され、その ID が使用可能になりました。
- 評価とレビューのモデレーター グループとして使用される  Azure AD セキュリティ グループが作成され、その ID が使用可能になりました。 (このセキュリティ グループは、E コマースのシステム管理グループと同じにすることができます。)

## <a name="provision-your-commerce-preview-environment"></a>Commerce プレビュー環境のプロビジョニング

これらの手順は、Commerce プレビュー環境をプロビジョニングする方法を説明しています。 それらを正常に完了すると、Commerce プレビュー環境を構成する準備が整います。 ここで説明するすべての活動は、LCS ポータルで発生します。

> [!IMPORTANT]
> プレビューのアクセス許可は、コマース プレビュー アプリケーションで指定した LCS アカウントと組織に関連付けられています。 Commerce プレビュー環境をプロビジョニングするには、同じアカウントを使用する必要があります。 コマース プレビュー環境で別の LCS アカウントまたはテナントを使用する必要がある場合は、それらの詳細を Microsoft に提供する必要があります。 連絡先情報については、このトピック後半の [Commerce プレビュー環境のサポート](#commerce-preview-environment-support)セクションを参照してください。

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a>LCS でプレビュー機能が使用可能で有効になっていることを確認する

LCS でプレビュー機能が使用可能で有効になっていることを確認するには、次の手順を実行します。

1. プレビューへのアクセス権を要求するために使用したのと同じ LCS アカウントを使用して、[LCS ポータル](https://lcs.dynamics.com)にサインインします。
1. LCS ホーム ページで右にスクロールし、**プレビュー機能の管理**タイルを選択します。

    ![プレビュー管理タイル](./media/preview1.png)

1. **プライベート プレビュー機能**までスクロールし、次の機能が使用可能で有効になっていることを確認します。

    - E コマースの評価
    - Commerce Preview プログラムの環境

    ![プライベート プレビューの機能](./media/preview2.png)

1. これらの機能がリストに表示されない場合は、Microsoft に連絡して、職場の電子メール アドレス、LCS アカウント、およびテナントの詳細を提供します。 連絡先情報については、[Commerce プレビュー環境のサポート](#commerce-preview-environment-support) セクションを参照してください。

### <a name="create-a-new-project"></a>新しいプロジェクトの作成

LCS に新しいプロジェクトを作成するには、次の手順を実行します。

1. LCS のホーム ページで、プラス記号 (**+**) を選択してプロジェクトを作成します。
1. 右側のウィンドウで、次のいずれかのステップを実行します。

    - パートナーである場合、**移行、ソリューションの作成、および学習**を選択します。
    - 顧客の場合、**見込みプリセールス**を選択します。

1. 名前と説明、および業種を入力します。
1. **製品名**フィールドで、**Dynamics 365 Retail** を選択します。
1. **製品バージョン** フィールドで、**Dynamics 365 Retail** を選択します。
1. **方法**フィールドで、**Dynamics Retail の実装方法**を選択します。
1. オプション: ロールとユーザーを既存のプロジェクトからインポートできます。
1. **作成**を選択します。 プロジェクト ビューが表示されます。

### <a name="add-the-azure-connector"></a>Azure コネクタの追加

LCS プロジェクトに Azure コネクタを追加するには、次の手順を実行します。

1. 次の手順のいずれかを実行します。

    - パートナーである場合は、右端で**プロジェクト設定**タイルを選択します。
    - 顧客の場合は、トップ メニューで**プロジェクト設定**を選択します。

1. **Azure コネクタ**を選択します。
1. Azure コネクタを追加するには、**追加**を選択します。
1. 名前を入力します。
1. Azure サブスクリプション ID を入力します。
1. **Azure Resource Manager (ARM) を使用するようにコンフィギュレーションする**のオプションをオンにします。
1. **Azure サブスクリプション AAD テナント ドメイン (または ID)** の値が正しいことを確認します。 必要に応じて、Azure サブスクリプション管理者に問い合わせてください。
1. **次へ** を選択します。
1. ページの指示に従って、サブスクリプションに必要なアプリケーションのアクセス許可を与えます。 必要に応じて、Azure サブスクリプション管理者に問い合わせてください。

    1. [Azure ポータル](https://portal.azure.com/)にサインインします。
    1. 適切なディレクトリが選択されていることを確認し、左側のメニューで**サブスクリプション**を選択します。
    1. リストから正しいサブスクリプションを検索し、選択します。 必要に応じて検索機能を使用します。
    1. メニューから、**アクセス制御 (IAM)** を選択します。
    1. 右側の**ロール割り当ての追加**で、**追加**を選択します。 **ロール割り当ての追加**ウィンドウが開きます。
    1. **ロール** フィールドで、**貢献者**を選択します。
    1. **アクセス権の割り当て先**について、既定値を **Azure AD ユーザー、グループ、またはサービス プリンシパル**のままにします。
    1. **選択**の下で、**b96b7e94-b82e-4e71-99a0-cf7fb188acea** を入力します。
    1. リストから**Dynamics 配置サービス \[wsfed 有効\]** を選択します。
    1. **保存** を選択します。

1. **次へ** を選択します。
1. ページの指示に従って、サブスクリプションに必要なアプリケーションのアクセス許可を与えます。 必要に応じて、Azure サブスクリプション管理者に問い合わせてください。
1. **次へ** を選択します。
1. **Azure リージョン** フィールドで、**米国東部**、**米国東部 2**、**米国西部**、または**米国西部 2** のいずれかを選択します。
1. **接続** を選択します。 Azure コネクタがリストに表示されます。

### <a name="import-the-commerce-preview-demo-base-extension"></a>コマース プレビュー デモ ベース拡張機能のインポート

コマース プレビュー デモ ベース拡張機能をプロジェクトにインポートするには、次の手順を実行します。

1. 上部にあるプロジェクト名を選択して、プロジェクトのホーム ページを開きます。
1. 次の手順のいずれかを実行します。

    - パートナーである場合は、右端の**資産ライブラリ** タイルを選択します。
    - 顧客の場合は、トップ メニューで**資産ライブラリ**を選択します。

1. 左のリストから、**ソフトウェア配置可能パッケージ**を選択します。
1. **インポート** を選択します。
1. **共有アセット ライブラリ**で、資産のリストから**コマース プレビュー デモ ベース拡張機能**を選択します。
1. **ピック**を選択します。 資産ライブラリに戻ると、リストに拡張機能が表示されます。

次の図は、LCS **資産ライブラリ** ページで実行する必要があるアクションを示しています。

![コマース プレビュー デモ ベース拡張機能のインポート](./media/import.png)

### <a name="deploy-the-environment"></a>環境の配置

環境を配置するには、次の手順に従います。

> [!NOTE]
> オプションが 1 つしかないページはスキップされるため、手順 6、7、または 8 を完了する必要はありません。 **環境パラメーター** ビューで、**Dynamics 365 Commerce - デモ (10.0.* x* プラットフォーム更新プログラム *xx*)** が**環境名**フィールドのすぐ上に表示されていることを確認します。 詳細については、手順 8 の後に表示されているイラストを参照してください。

1. トップ メニューで、**クラウド ホスト環境**を選択します。
1. 環境を追加するために**追加**を選択します。
1. **アプリケーション バージョン** フィールドで、最新のバージョンを選択します。 最新バージョン以外のアプリケーション バージョンを特定する必要がある場合は、**10.0.8** より前のバージョンを選択しないでください。
1. **プラットフォーム バージョン** フィールドで、選択したアプリケーション バージョンに対して自動的に選択されたプラットフォーム バージョンを使用します。 

    ![アプリケーションとプラットフォーム バージョンを選択する](./media/project1.png)

1. **次へ** を選択します。
1. 環境のトポロジとして**デモ**を選択します。

    ![環境トポロジ 1 を選択する](./media/project2.png)

1. 環境のトポロジとして **Dynamics 365 Commerce - デモ**を選択します。 以前に 1 つの Azure コネクタをコンフィギュレーションしている場合、この環境に対して使用されます。 複数の Azure コネクタをコンフィギュレーションした場合は、**米国東部**、**米国東部 2**、**米国西部**、または**米国西部 2** から、使用するコネクタを選択できます。 (最適なエンド ツー エンドのパフォーマンスのために、**米国西部 2** を選択することをお勧めします)。

    ![環境トポロジ 2 を選択する](./media/project3.png)

1. **環境の配置**のページで、環境名を入力します。 詳細設定はそのままにしておきます。

    ![環境の配置のページ](./media/project4.png)

1. VM サイズを必要に応じて調整します。 (VM 最小在庫管理単位をお勧めします \[SKU\] **D13 v2**。)
1. 価格決定およびライセンス条件を確認、チェック ボックスをオンにして同意したことを示します。
1. **次へ** を選択します。
1. 配置の確認ページで、詳細が正しいことを確認した後、**配置**を選択します。 **クラウド ホスト環境**ビューに戻り、環境がリストに表示されます。

    要求した環境はキューに格納され、その後配置されます。 環境ワークフローは完了までに少し時間がかかることがあります。 そのため、約 6 ~ 9 時間後に再度確認してください。

1. 続行する前に、環境の状態が**配置済み**になっていることを確認してください。

### <a name="initialize-the-commerce-scale-unit-csu"></a>Commerce Scale Unit (CSU) を初期化する

CSU を初期化するためには、次の手順に従います。

1. **クラウド ホスト環境**ビュー内で、リストから環境を選択します。
1. 右側の環境ビューで、**完全な詳細**を選択します。 環境の詳細のビューが表示されます。
1. **環境機能**の下で、**管理**を選択します。
1. **コマース** タブで、**初期化**を選択します。 CSU 初期化パラメーター ビューが表示されます。
1. **地域**フィールドで、**米国東部**、**米国東部 2**、**米国西部**、または**米国西部 2** のいずれかを選択します。
1. **バージョン** フィールドで、リストから**バージョンを指定する**を選択し、表示されるフィールドに **9.18.20014.4** を指定します。 ここで示されている正確なバージョンを指定してください。 それ以外の場合は、RCSU を後で正しいバージョンに更新する必要があります。
1. **拡張機能の適用**オプションをオンにします。
1. 拡張機能のリストから、**コマース プレビュー デモ ベース拡張機能**を選択します。
1. **初期化**を選択します。
1. 配置の確認ページで、詳細が正しいことを確認した後、**はい**を選択します。 **コマース** タブが選択されているところでは、**コマースの管理**ビューが再度表示されます。 CSU がプロビジョニング用にキューに格納されました。
1. 続行する前に、CSU の状態が**成功**となっていることを確認します。 初期化には約 2 ~ 5 時間かかります。

### <a name="initialize-e-commerce"></a>E コマースの初期化

E コマースを初期化するためには、次の手順に従います。

1. **E コマース** タブで、プレビューの同意を確認し、**設定**を選択します。
1. **E コマース テナント名**フィールドに名前を入力します。 ただし、この名前は E コマース インスタンスを指す URL の一部に表示されることに注意してください。
1. **Commerce scale unit の名前**フィールドで、リストから CSU を選択します。 (リストには 1 つのオプションのみが必要です。)

    **E コマースの地域**フィールドは自動的に設定され、値を変更することはできません。

1. **次へ** を選択して続行します。
1. **サポートされているホスト名**フィールドに、`www.fabrikam.com` などの有効なドメインを入力します。
1.  **システム管理者の ADD セキュリティ グループ** フィールドに、使用するセキュリティ グループの名前の最初の数文字を入力します。 検索結果を表示するには、拡大クラス アイコンを選択します。 リストから正しいセキュリティ グループを選択します。
2.  **評価とレビュー モデレーター用 ADD セキュリティ グループ** フィールドに、使用するセキュリティ グループの名前の最初の数文字を入力します。 検索結果を表示するには、拡大クラス アイコンを選択します。 リストから正しいセキュリティ グループを選択します。
1. **評価とレビュー サービスを有効にする**オプションを、有効のままにします。
1. **初期化**を選択します。 **E コマース** タブが選択されているところでは、**コマースの管理**ビューが再度表示されます。 E コマースの初期化を開始しました。
1. 続行する前に、E コマースの初期化状態が**初期化成功**になるまでお待ちください。
1. 右下の**リンク**で、次のリンクの URL をメモします。

    * **E コマース サイト** – E コマース サイトのルートへのリンク。
    * **E コマース サイト管理ツール** – サイト管理ツールへのリンク。

## <a name="commerce-preview-environment-support"></a>Commerce プレビュー環境のサポート

プロビジョニング手順の完了中に問題が発生した場合は、[Microsoft Dynamics 365 Commerce プレビュー Yammer グループ](https://aka.ms/Dynamics365CommercePreviewYammer)を参照してください。

Yammer グループにアクセスしようとして問題が発生した場合は、<Dynamics365Commerce@microsoft.com> から電子メールで Microsoft にお問い合わせください。 この電子メール アドレスはアクティブに監視されていません。 したがって、応答に遅延が予想されます。

## <a name="next-steps"></a>次のステップ

Commerce プレビュー環境のプロビジョニングと構成のプロセスを続行するには、[Commerce プレビュー環境のコンフィギュレーション](cpe-post-provisioning.md)を参照してください。

## <a name="additional-resources"></a>追加リソース

[Dynamics 365 Commerce プレビュー環境の概要](cpe-overview.md)

[Dynamics 365 Commerce レビュー環境のコンフィギュレーション](cpe-post-provisioning.md)

[Dynamics 365 Commerce プレビュー環境のオプション機能のコンフィギュレーション](cpe-optional-features.md)

[Dynamics 365 Commerce プレビュー環境に関するよく寄せられる質問](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Retail Cloud Scale Unit (RCSU)](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Microsoft Azure ポータル](https://azure.microsoft.com/features/azure-portal)

[Dynamics 365 Commerce Web サイト](https://aka.ms/Dynamics365CommerceWebsite)

