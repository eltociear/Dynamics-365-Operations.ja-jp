---
title: "クラウド環境へ更新プログラムを適用"
description: "このトピックでは、Lifecycle Services (LCS) を使用して、バイナリ更新プログラムまたはアプリケーション (AOT) 展開可能なパッケージをクラウド環境に適用する方法について説明します。"
author: manalidongre
manager: AnnBe
ms.date: 10/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations, Retail
ms.assetid: 341a229f-d9c3-4678-b353-d08d5b2c1caf
ms.search.region: Global
ms.author: manado
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: Platform update 1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: 86d6bab2916966ff0baed2665ed7fecc47db72b3
ms.contentlocale: ja-jp
ms.lasthandoff: 11/01/2018

---

# <a name="apply-updates-to-cloud-environments"></a>クラウド環境へ更新プログラムを適用

[!include [banner](../includes/banner.md)]

このトピックでは、Microsoft Dynamics Lifecycle Services (LCS) を使用して、Microsoft Dynamics 365 for Finance and Operations 環境または Microsoft Dynamics 365 for Retail 環境に更新プログラムを自動的に適用する方法について説明します。 展開可能なパッケージを使用して更新が適用されます。

> [!IMPORTANT]
> パッケージを適用するとシステムのダウンタイムが発生します。 すべて関連するサービスを停止、およびパッケージを適用中のときには環境を使用できなくなります。 それに応じた計画を立てる必要があります。

## <a name="supported-environments"></a>サポートされる環境

次のトポロジは、LCS で自動化されたフローを使用するパッケージ配置をサポートします。
- **LCS 実装プロジェクト** – すべての環境のタイプがサポートされています。 自動化されたパッケージ アプリケーションとは、実稼働環境を除くすべての環境のセルフサービス操作です。 実稼働環境については、顧客は、適用パッケージを要求を送信するため LCS を使用する必要があります。
- **LCS パートナーと試用プロジェクト** – マルチボックス開発/テスト トポロジを除く、すべての環境のタイプがサポートされています。

> [!NOTE]
> プロジェクトのタイプに関係なく、ビルド環境があれば、LCS のみを使用してバイナリ更新プログラムとデータ アップグレード パッケージを適用します。 LCS を使用してアプリケーション配置可能パッケージを適用することはできません。

他のトポロジ (以下) については、リモート デスクトップ プロトコル (RDP) を使用して環境に接続し、コマンドラインからインストールする必要があります。 手動のパッケージ配置の詳細については、[コマンド ラインからの配置可能パッケージのインストール](install-deployable-package.md) を参照してください。

- ローカルの開発環境 (仮想ハード ディスク [VHD] からダウンロード可能)
- Microsoft Azure (パートナーおよび試用プロジェクト) でのマルチボックス開発/テスト環境

## <a name="key-concepts"></a>重要な概念

開始する前に、*配置可能パッケージ*、*runbooks*、および *AXInstaller* を理解する必要があります。 デプロイ可能なパッケージは、どのような環境でも利用可能なデプロイメントの単位です。 デプロイ可能なパッケージは、プラットフォームまたは他のランタイム コンポーネント、更新されたアプリケーション (AOT) パッケージ、または新しいアプリケーション (AOT) パッケージのバイナリ更新です。 AXInstaller は、パッケージのインストールを可能にする runbook を作成します。 詳細については、このトピックの最後で [パッケージ、Runbook、および AXUpdateInstaller の詳細](apply-deployable-package-system.md#packages-runbooks-and-the-axupdateinstaller-in-depth) を参照してください。

## <a name="supported-package-types"></a>サポートされているパッケージの種類

- **AOT の配置可能パッケージ** - アプリケーション メタデータおよびソース コードから生成される配置可能なパッケージ。 この展開可能なパッケージは、開発環境またはビルド環境で作成されます。
- **バイナリ更新プログラム パッケージ** - ダイナミックリンク ライブラリ (DLL)と、プラットフォームとアプリケーションが依存するその他のバイナリとメタデータを含む配置可能パッケージ。 これは、Microsoft によってリリースされたパッケージです。
- **配置可能小売パッケージ** - 小売コードが結合された後に生成されるさまざまな小売パッケージの組み合わせ。
- **マージ済パッケージ** – 各タイプの 1 つのパッケージを組み合わせて作成されたパッケージ。 たとえば、1 つのバイナリ更新パッケージと 1 つの AOT パッケージ、または 1 つの AOT パッケージと 1 つの小売展開可能パッケージを結合することができます。 パッケージは、LCS のプロジェクトのアセット ライブラリでマージされます。
> [!NOTE] 
> バイナリ パッケージおよび小売展開可能パッケージは、同じ結合済パッケージにまとめることはできません。

## <a name="prerequisite-steps"></a>前提条件のステップ

- **適用するパッケージが有効であることを確認してください。** パッケージがアセット ライブラリにアップロードされるとき、そのパッケージは分析されません。 パッケージを選択すると、右側のペインにパッケージ ステータスが **未検証** として表示されます。 パッケージは、環境に適用する前に、次の手順を使用して検証に合格する必要があります。 パッケージの状態は、パッケージが有効かどうかを示すために、資産ライブラリで更新されます。 ガイドラインを満たしていないパッケージによって実稼働環境が影響を受けていなことを保証する手助けのために検証が必要です。

    検証には次の 3 つのタイプがあります。

    - 基本パッケージの形式検証
    - プラットフォーム バージョンのチェック
    - パッケージのタイプ

- **実稼動環境でパッケージを適用する前に、パッケージがサンド ボックス環境に適用されていることを確認してください。** 実稼働環境が常に良好な状態に保たれるように、実稼働環境に適用される前にパッケージがサンドボックス環境でテストされていることを確認する必要があります。 したがって、パッケージが実稼働環境で適用されるように要求する前に、自動フローを使用してパッケージがサンドボックス環境に適用されていることを確認してください。
- **複数のパッケージを適用する場合は、マージ済パッケージを作成します。このパッケージは、まずサンドボックス環境で、次に実稼働環境で適用できます。** 平均環境で単一パッケージのアプリケーションは、約 5 時間のダウンタイムが必要です。 複数のパッケージを適用する必要がある場合にダウンタイムが発生しないように、各タイプのパッケージを 1 つずつ含む単一のパッケージを作成することができます。 資産ライブラリでバイナリ パッケージとアプリケーション配置可能パッケージを選択した場合、**マージ** ボタンは、ツールバー上で利用可能になります。 このボタンをクリックすると、2 つのパッケージを単一のパッケージにマージできるため、合計のダウンタイムを半分に減らすことができます。
- **サンド ボックスと製造環境に適用する前に、アプリケーション バイナリ更新プログラムのパッケージが開発/ビルド環境に適用されていることを確認してください** - アプリケーション バイナリ パッケージが階層 2+ サンドボックス環境に直接適用されているが、開発/ビルド環境に適用されてない場合、次に AOT パッケージを開発/ビルド ボックス (サンドボックス環境と同じアプリケーション バイナリを持たない) からサンド ボックスに移動すると、アプリケーション バイナリの一部は開発/ビルド環境で上書きされます。 これにより、サンドボックス環境のバージョンが後退する可能性があります。 

## <a name="apply-a-package-to-a-non-production-environment-by-using-lcs"></a>LCS を使用して非運用環境にパッケージを適用します

> [!IMPORTANT]
> パッケージを適用するとシステムのダウンタイムが発生します。 すべて関連するサービスを停止、およびパッケージを適用中のときには環境を使用できなくなります。

開始する前に、配置可能パッケージが LCS のアセット ライブラリにアップロードされていることを確認します。

1. バイナリ更新プログラムで、資産ライブラリに直接パッケージをアップロードします。 LCS から更新プログラムをダウンロードする方法の詳細については、[Lifecycle Services から更新プログラムをダウンロード](../migration-upgrade/download-hotfix-lcs.md) を参照してください。

    X++ 修正プログラムまたはアプリケーション カスタマイズおよび拡張機能からの結果であるアプリケーション (AOT) 配置可能パッケージについては、開発またはビルド環境で配置可能パッケージを作成し、資産ライブラリにアップロードします。
2. パッケージを適用する環境の**環境の詳細**ビューを開きます。
3. **メンテナンス** &gt; **更新プログラムの適用**をクリックし、更新プログラムを適用します。
4. パッケージを選択して適用します。 上部にあるフィルターを使用してパッケージを探します。
5. **適用** をクリックします。 **環境の詳細**ビューの右上隅にある状態が**キュー**に変わり、**環境の更新**セクションにパッケージの進捗状況が表示されていることを確認します。

    [![キュー ステータス](./media/parallelexecutionsandbox_queuedstate.jpg)](./media/parallelexecutionsandbox_queuedstate.jpg)
    
6. ページを更新し、パッケージ アプリケーションの進行状況を参照してください。 サービス ステータスが**進行中**であり、環境ステータスが**サービス**となっていることを確認します。

    [![サービスの状態](./media/parallelexecutionsandbox_servicingstate.png)](./media/parallelexecutionsandbox_servicingstate.png)
    
7. ページを更新して、パッケージ アプリケーション要求のステータス更新を確認します。 このパッケージが適用されると、環境ステータスは **配置済み** に変わり、サービスのステータスは **完了** に変わります。

    [![配置済み状態](./media/parallelexecutionsandbox_signedoffstate.png)](./media/parallelexecutionsandbox_signedoffstate.png)
    
8. パッケージ アプリケーションでサインオフするには、問題がなければ **サインオフ** をクリックします。 パッケージを適用するときに問題が発生した場合**払出サイン オフ**をクリックします。

### <a name="troubleshooting"></a>トラブルシューティング

#### <a name="general-troubleshootingdiagnostics"></a>一般的なトラブルシューティング/診断

パッケージ アプリケーションが正常に行われない場合は、ログまたは詳細なログを確認する runbook のいずれかをダウンロードすることができます。 また、RDP を使用して、問題を修正するために環境に接続することができます。 Microsoft に問題を報告する必要がある場合、**環境更新**セクションに報告される活動 ID を含めるようにします。

![ログのダウンロードおよび runbook ボタンのダウンロード](./media/applypackage_sandbox_10.png)


![トラブルシューティング](./media/parallelexecutionsandbox_troubleshooting.jpg)

#### <a name="using-the-logs"></a>ログの使用

1. ログをダウンロードします。
2. ログ ファイルを解凍します。
3. **AOS** や **BI** など、ステップが失敗したロールを選択します。
4. ステップが失敗した VM を選択します。 この情報は **環境の更新** セクションの **コンピューター名** 列に表示されます。
5. VM のログで、問題が発生したステップに対応するフォルダーを選択します。 フォルダー名は、各フォルダーが対応するステップを識別します。 たとえば、ステップの実行で問題が発生した場合、<strong>ExecuteRunbook\</strong>* フォルダーを選択します。

    たとえば、フォルダー名が ExecuteRunbook-b0c5c413-dae3-4a7a-a0c4-d558614f7e98-1\_I0\_R0 である場合、ステップ番号が強調表示され、グローバル一意識別子 (GUID) の後の番号になります。

#### <a name="package-failure"></a>パッケージの失敗

パッケージ アプリケーションが正常に行われていない場合は、2 つのオプションがあります。

- 失敗した操作を再試行するには、**再開**をクリックします。

    ![失敗した状態](./media/parallelexecutionsandbox_failedstate.jpg)
    
- パッケージ アプリケーションを停止するには、**中止**をクリックします。

    > [!Note]
    > **中止**をクリックすると、環境に既に作成されている変更はロールバックされません。 続行するには、問題を修正する必要があります。
    
    [![パッケージ アプリケーションを中止すると表示されるメッセージ ボックス](./media/applypackage_sandbox_13-1024x274.png)](./media/applypackage_sandbox_13.png)

## <a name="apply-a-package-to-a-production-environment-by-using-lcs"></a>LCS を使用して運用環境にパッケージを適用します

実稼動環境では、サンドボックス環境または他のタイプの環境とは異なり、LCS 経由のパッケージ アプリケーションはセルフ サービスではありません。 顧客とパートナーは、お客様がダウンタイムの準備が整ったときにパッケージを適用するために Microsoft に要求を送信する必要があります。 

1. 更新プログラムを LCS からダウンロードします。 LCS から更新プログラムをダウンロードする方法の詳細については、[Lifecycle Services から更新プログラムをダウンロード](../migration-upgrade/download-hotfix-lcs.md) を参照してください。

    - バイナリ更新プログラムで、更新プログラムの配置可能パッケージを直接資産ライブラリにアップロードします。
    - アプリケーション/X++ 更新プログラムについては、開発環境でパッケージを適用します。 すべての競合を解決した後、Visual Studio で配置可能パッケージを生成し、アセット ライブラリにパッケージをアップロードします。 アセット ライブラリにアップロードおよび配置可能なパッケージを作成する方法の詳細については、[モデルの配置可能パッケージの作成](create-apply-deployable-package.md) を参照してください。

2. LCS の**資産ライブラリ**ページの、対応する資産のタイプのタブで(**ソフトウェア可能パッケージ**)、パッケージを選択し、**リリース候補**をクリックします。
3. このトピックの前半の手順を使用して、サンドボックス環境でパッケージを適用します。
4. パッケージが正常に適用された後、サンドボックス環境でサイン オフし、アセット ライブラリを開いて、パッケージを**リリース候補**とマークします。
5. パッケージを適用する実稼働環境の**環境の詳細**ビューを開きます。
6. **メンテナンス** &gt; **更新プログラムの適用**をクリックし、パッケージを適用します。
7. 適用するパッケージのタイプを選択します。
8. 実稼働環境に適用するパッケージを選択し、**スケジュール** をクリックして適用要求を送信します。

    > [!NOTE]
    > パッケージのリストには、サンドボックス環境で正常に署名され、リリース候補としてマークされているパッケージのみが含まれています。

9. パッケージ アプリケーションをスケジュールする日時を指定して **送信** をクリックし、**OK** をクリックして確認します。 パッケージを適用している間、お客様の環境はダウンして業務を遂行できないことに注意してください。
10. ページを更新します。 ページの 2 つのフィールドは、要求の状態を示します。

    - **要求ステータス** – このフィールドには、Microsoft に送信した要求のステータスが示されます。
    - **操作可能なユーザー** - このフィールドは、アクションを実行するユーザーを示します。

    ![要求のステータスとフィールドによって操作可能](./media/applypackage_prod_7-1024x269.png)
    
11. Microsoft が要求を受け入れるか、拒否します。

    - 要求が承認されると、Microsoft は環境の更新を開始します。
    
    ![承認依頼: 要求状態 = 要求受入済、操作可能なユーザー = Microsoft](./media/applypackage_prod_9-1024x384.png)
    
    - 要求が却下された場合は、Microsoft は却下理由と顧客がとる必要があるアクションを顧客を通知します。 顧客は、要求の再スケジュール、パッケージの変更、要求の取り消しを行うことができます。
    
    ![拒否された要求: 要求の状態 = 要求が拒否、アクション可能 = 顧客/パートナー](./media/applypackage_prod_8-1024x322.png)

    顧客はいつでも**コメント** フィールドを使用してリクエストにコメントを投稿できます。
    
    ![要求に転記されるコメント例](./media/applypackage_prod_10-1024x336.png)
    
12. 環境がサービスされた後、ステータスを監視することができます。 **ステータスのサービス** フィールドは、パッケージ アプリケーションのステータスを示します。

    [![サービス ステータスおよびステータス フィールドの要求](./media/applypackage_prod_11-1024x399.png)](./media/applypackage_prod_11.png)
    
    また、進捗状況インジケーターは、利用可能な手順の総数のうち、実行された手順の数を表示します。
    
    ![進捗状況インジケーター](./media/applypackage_prod_12-1024x414.png)

### <a name="successful-package-application"></a>アプリケーションのパッケージに成功

- 配置が正常に完了すると、**サービスの状態**フィールドは**完了**に設定されていますが、要求がまだ終了していないため、**要求状態**フィールドは**処理中**に設定されます。

    ![配置の成功: サービスのステータス = 完了、要求のステータス = 実行中](./media/applypackage_prod_13-1024x392.png)
    
- Microsoft が要求の適用を完了した後、**サービス要求の終了**をクリックして要求を閉じる必要があります。
- 成功した要求を閉じるときは、**作業項目の詳細を編集** ダイアログ ボックスで、**サービス要求の状態** フィールドを **成功** に設定し、**送信** をクリックします。

### <a name="unsuccessful-package-application"></a>アプリケーションのパッケージに失敗

- パッケージ アプリケーションが正常に終了されていない場合、Microsoft は問題を調査します。 **ステータスのサービス** フィールドは、パッケージ アプリケーションが失敗したことを示します。

    ![パッケージ展開に失敗: サービス状態 = 失敗](./media/applypackage_prod_17.png)
    
- 配置に失敗すると、Microsoft はパッケージを途中で停止して、環境を適正な状態に元に戻し、顧客に要求を送信します。これにより、顧客は、環境を検証して、要求を完了させることができます。 パッケージに問題がある場合は、顧客は新しいパッケージを含む新しい要求を送信する必要があります。

    ![変更が元に戻され、顧客が環境を検証しなければならないとの Microsoft からのコメント](./media/applypackage_prod_18-1024x346.png)
    
- 失敗した要求を閉じるときは、**作業項目の詳細を編集** ダイアログ ボックスで、**サービス要求の状態** フィールドを **"中止"** に設定します。

## <a name="deploying-packages-in-retail-environments"></a>小売環境でのパッケージの展開

環境内の配置可能パッケージを適用した後に、小売コンポーネント (Retail Modern POS など) を使用している場合、店舗内コンポーネントも更新する必要があります。 詳細については、[Retail Modern POS (MPOS) の構成、インストール、有効化](../../retail/retail-modern-pos-device-activation.md)を参照してください。

## <a name="packages-runbooks-and-the-axupdateinstaller-in-depth"></a>パッケージ、Runbook、および AXUpdateInstaller の詳細

配置可能パッケージ、runbooks、および AXUpdateInstaller は、更新プログラムの適用に使用するツールです。 

**配置可能パッケージ** - 配置可能パッケージとは、任意の Finance and Operations または Retail 環境に適用できる配置の単位です。 デプロイ可能なパッケージは、プラットフォームまたは他のランタイム コンポーネント、更新されたアプリケーション (AOT) パッケージ、または新しいアプリケーション (AOT) パッケージのバイナリ更新です。 LCS からダウンロードした、または開発環境で作成した配置可能なパッケージは、製品タイプ間では適用できません。 つまり、Finance and Operations の展開可能なパッケージは Retail 環境に適用することができず、その逆も同様です。 Retail と互換性のある Finance and Operations の既存のカスタマイズを持ち、それを Retail 環境に適用する場合は、Retail 開発環境でソース コードを再パッケージし、逆の方向に移動している場合は逆コンパイルします。   

[![配置可能なパッケージの例](./media/applypackage_deployablepackage.jpg)](./media/applypackage_deployablepackage.jpg)

**Runbook** – 展開ランブックは展開可能なパッケージを対象となる環境に適用させるために生成される一連の手順です。 一部のステップは自動化され、一部のステップは手動です。 AXUpdateInstaller は、これらの手順を一度に 1 つずつ正しい順序で実行できます。

[![展開ランブック の例](./media/applypackage_runbook-1024x528.jpg)](./media/applypackage_runbook.jpg)

**AXUpdateInstaller** - Microsoft Visual Studio または Microsoft バイナリ更新プログラムからカスタマイズ パッケージを作成すると、インストーラの実行可能ファイルが配置可能パッケージと共にバンドルされます。 インストーラーは、指定したトポロジの Runbook を生成します。 インストーラーは、特定のトポロジの Runbook に従って、手順を順番に実行することもできます。

## <a name="additional-resources"></a>その他のリソース

[配置可能なパッケージのコマンドラインからのインストール](install-deployable-package.md)
