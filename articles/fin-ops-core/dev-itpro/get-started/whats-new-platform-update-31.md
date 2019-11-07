---
title: Finance and Operations アプリのプラットフォーム更新プログラム 31 (2020 年 1 月) の機能のプレビュー
description: このトピックでは、Finance and Operations アプリのプラットフォーム更新プログラム 31 でプレビューされる機能について説明します。
author: tonyafehr
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: tfehr
ms.search.scope: Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Platform update 31
ms.openlocfilehash: 38d4d40499a5df697107366124de0a47efb76e3b
ms.sourcegitcommit: 654aaff001402397009148dad51f39af7e0cc114
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "2672997"
---
# <a name="preview-features-in-platform-update-31-for-finance-and-operations-apps-january-2020"></a>Finance and Operations アプリのプラットフォーム更新プログラム 31 (2020 年 1 月) の機能のプレビュー

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

このトピックでは、Finance and Operations アプリのプラットフォーム更新プログラム 31 の新機能または変更されたプレビュー機能について説明します。 このバージョンのビルド番号は 7.0.5457 です。 一般提供開始日は 2020 年 1 月ですが、新機能は 2019 年 10 月の初期リリースで使用できます。 プラットフォーム更新プログラム 31 の詳細については [追加リソース](whats-new-platform-update-31.md#additional-resources) を参照してください。

## <a name="turn-on-the-new-preview-grid-control-through-feature-management"></a>機能管理を通じて、新しい (プレビュー) グリッド コントロールをオンにする
以前は、「&debug=reactGrid」を環境 URL に追加することによって、新しいグリッド コントロールは使用可能になりました。 プラットフォーム 更新プログラム 31 では、新しいグリッド コントロールは、機能管理ワークスペースを使用する的確な環境に対して有効にすることができるようになりました (フライトを有効にする方法に関する指示については、次のステップを参照してください)。 新しいグリッド コントロールに関する詳細については、[ユーザーの生産性 - 新しいグリッド](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/finance-operations/user-productivity-new-grid) を参照してください。

この機能のプレビュー中に新しいグリッドを有効にするには、これらのステップに従います。

1.   次の SQL ステートメントを使用してフライトを有効にします。

      INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);

2.    IIS をリセットして、静的なフライティング キャッシュをフラッシュします。

3.    Finance and Operations アプリの**機能管理**ワークスペースに移動します。 

4.    機能のリストから**新しいグリッド コントロール**機能を選択し、詳細ウィンドウの**直ちに有効化**を選択します。

      機能のリストに**新しいグリッド コントロール**が表示されない場合、**更新プログラムの確認**を選択します。

後続のすべてのユーザー セッションは、新しいグリッドを有効にして開始されます。


## <a name="updates-to-saved-views"></a>保存されたビューに更新
保存されたビュー機能は、プラットフォーム更新プログラム 31 により進化し続けます。 このリリースには、ビューおよび個人用設定の管理用の管理者の個人用設定ページのオーバーホール、ビューの一括インポート/エクスポート機能、および特定の法人のユーザーにビューを公開する機能が含まれています。 保存されたビューに関する詳細については、[保存されたビュー](../../fin-ops/get-started/saved-views.md) を参照してください。  

## <a name="new-controls-available-for-developers"></a>開発者が使用可能な新しいコントロール
Web サイトのホスト コントロールが追加され、開発者はサードパーティのアプリを iFrames 内で Finance and Operations に直接埋め込むことができるようになりました。 これは、特定の権限を持つユーザーが個人用設定を介してアプリを埋め込むことができるようにするための最初のステップで、埋め込み PowerApps の既存のシナリオに似ています。

開発者は新しい星評価コントロールを使用することもできます。 このコントロールは、1 から 5 個の星のスケール上で 4 分の 1 ずつの評価を表示します。

## <a name="updated-icon-for-finance-and-operations-apps"></a>更新された Finance and Operations アプリのアイコン
Finance and Operations アプリ用の新しいアイコンは、Dynamics 365 の最新のアイコン スタイリングに沿っていて、Web クライアントに表示されるようになりました。

## <a name="optimization-of-loading-the-data-management-workspace"></a>データ管理ワークスペース読み込みの最適化
特定の条件下では、データ管理ワークスペースの読み込みに時間がかかります。 ワークスペースの読み込みにかかる時間を減らすために、新しい最適化が実施されています。 この変更は、フライト DMFWorkspaceLoadPerformance を介して有効化できます。

## <a name="inefficient-memory-usage-by-data-management-exportimport-jobs"></a>データ管理のエクスポート/インポート ジョブによるメモリ不足
データ管理のエクスポート/インポート ジョブによるメモリ消費が、パフォーマンスの問題を引き起こすほど十分に高い場合、複数の問題が報告されています。 SSIS パッケージ実行ロジックは、この問題を解決するために最適化されています。 この変更は、フライト DMFExecuteSSISOutOfProc によって保護されているため、既定ではオフになっています。 この変更は、以降のプラットフォームの更新プログラムでは既定で有効になります。

## <a name="extensibility-enhancements"></a>拡張性の強化
プラットフォーム更新プログラム 31 では、次の拡張機能が追加されました。

- メソッド WorkflowDocumentField.substitutePlaceholderAsUser の区切り記号をセミコロンから区分線に調整することにより、エクスポートされたデータとの競合がなくなります (Ref# 299129)。
- メソッド SysWorkflowParticipantProvider.SysWorkflowParticipantProvider をリファクターすることにより、解決されたユーザーのリストへアクセスを提供します (Ref# 310122)。
- 拡張機能によって追加されたテーブル表示メソッドが、cacheCalculateMethod API によりキャッシュされます (Ref# 341431)。
- SysExtensionAppClassFactory.getClassFromSysExtAttribute のロック アプローチの改善により、ブロック問題を削減します (Ref# 338254)。
- 拡張機能を介して Grid.DataGroup プロパティの消去を有効化することにより、異なるフィールド グループを持つグループを追加できるようになります (Ref# 303030)。
- DataEntity.PrimaryCompanyContext の拡張機能を許可します (Ref# 292575)。

## <a name="excel-add-in-authentication-and-authorization-enhancements"></a>Excel アドインの認証および承認の機能拡張
Excel アドインに複数の認証および承認の機能拡張があり、特定のケースの処理が改善されます。
- **認証トークンの有効期限がサイレント** - プロセスは既存の認証トークンを検証し、ユーザーが既存の認証コンテキストを継続して使用できるか、または再度サインインする必要があるかを特定します。 以前は、認証トークンが期限切れになっている場合は、Excel アドインによってユーザーに通知されました。 ユーザーには標準のサインイン画面でのみ表示され、情報メッセージによって、デバッグ目的のために認証トークンの有効期限が報告されるようになりました。
- **認証タイムアウト** - 認証プロセスが時間内に完了しなかったために、場合によっては、ユーザーは**サインアウト** ボタンのあるエラー メッセージを受信していました。 エラーを無視し、再度**サインイン**を選択することにより認証が成功していましたが、ユーザーが**サインアウト**を選択した場合、無限ループになる可能性がありました。
- **ADFS サインアウトのサポートの改善** - サインアウトのメカニズムがダイアログボックスの中になりました。 これにより、Excel アドインから ADFS サーバーへの通信は別のダイアログ ボックスにおいてのみ許可されるので、Active Directory Federation Services (ADFS) を使用している顧客へのサポートが改善されました。
- **認証失敗に関する情報が提供される** - 以前は、ユーザー認証に成功したにもかかわらず、サーバーと通信するための承認されたアクセス許可を持っていない場合、アプレットの読み込みが失敗するので、Excel アドインは「アプレットの読み込み」を表示していました。 これは、承認されたアクセス許可に関する暗黙的な失敗でした。 承認のアクセス許可の失敗について明示的に詳細がユーザーに表示されるので、何が起こったかを知ることができ、正しいサーバーに正しいユーザーでサインインしていることを確認できるようになりました。

## <a name="skipautoorderby-api"></a>skipAutoOrderBy API
ORDER BY 句を含めないよう明示的に指定することにより、AX クエリ オブジェクトを使用している場合、カーネルによって主キーが ORDER BY 句に追加されます。 この API は ORDER BY 句をスキップし、クエリには追加されません。 詳細については、[Q クラス](../dev-ref/q-classes.md) を参照してください。


## <a name="additional-resources"></a>追加リソース

### <a name="platform-update-31-bug-fixes"></a>プラットフォーム アップデート 31 のバグ修正プログラム
プラットフォーム更新 31 の一部である更新プログラムのそれぞれに含まれるバグ修正については、Lifecycle Services (LCS) にログインし、この [KB 資料](https://fix.lcs.dynamics.com/Issue/Details?bugId=386525&dbType=3&qc=e03ced97fa18dc4439f36de17b00da7257dc15869a72e5b2435fec0acec0c493)を参照してください。

### <a name="dynamics-365-2019-release-wave-2-plan"></a>Dynamics 365: 2019 リリースのウェーブ 2 プラン
当社のビジネス アプリやプラットフォームの次回および最近リリースされた機能について検討中ですか?

[Dynamics 365: 2019 リリース ウェーブ 2 プラン](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/) をご確認ください。 あらゆる詳細情報を端から端まで徹底的に捕捉して一元化しました。計画を策定する際に 1 つのドキュメントでそれらの情報を参照できます。

### <a name="removed-and-deprecated-features"></a>削除済みおよび非推奨の機能
[削除済みまたは非推奨の機能](../../dev-itpro/migration-upgrade/deprecated-features.md) のトピックでは、削除済みまたは非推奨の機能について説明します。

- *削除された*機能は製品では使用できません。
- *削除予定*の機能は現在開発中ではなく、将来の更新で削除される可能性があります。

製品から機能が削除される前に、非推奨の通知が削除の 12 ヶ月前に [削除済みまたは非推奨の機能](../../dev-itpro/migration-upgrade/deprecated-features.md) のトピックに発表されます。

コンパイル時に影響する重大な変更が、サンドボックス環境および実稼働環境と互換性のあるバイナリの場合、廃止時間は 12 か月以内になります。 通常、これらはコンパイラに加える必要がある機能の更新です。