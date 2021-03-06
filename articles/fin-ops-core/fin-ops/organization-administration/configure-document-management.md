---
title: ドキュメント管理のコンフィギュレーション
description: このトピックでは、添付ファイルおよびレコードのメモを格納するように、ドキュメント管理 (ドキュメント処理) を構成する方法について説明します。
author: ChrisGarty
manager: AnnBe
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 240185e174b0e1f64ced9453fdd940d434cb8932
ms.sourcegitcommit: 759325234a763e14071348a6f5399999a92f8264
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2020
ms.locfileid: "2983777"
---
# <a name="configure-document-management"></a>ドキュメント管理のコンフィギュレーション

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


このトピックでは、添付ファイルおよびレコードのメモを格納するように、ドキュメント管理 (ドキュメント処理) を構成する方法について説明します。 これには、この機能に関連する概念および機能に関する情報が含まれています。

ドキュメントの管理の詳細については、簡単なビデオ [ドキュメント管理](https://www.youtube.com/watch?v=p4rl1CkiLN4&feature=youtu.be) をご視聴ください。

## <a name="configure-document-types"></a>ドキュメント タイプのコンフィギュレーション

ドキュメント タイプは、レコードに添付したドキュメント、または作成するテンプレートを分類するために使用します。 各ドキュメント タイプは、固有の場所に格納されることができます。

ドキュメント タイプの既定のセットが用意されています。 これらのドキュメント タイプを使用すると、ファイル、イメージ、メモ、または URL として添付ファイルを分類できます。 **ファイル** および **画像** の既定のドキュメント タイプは、場所として **Azure ストレージ**を使用するよう構成されます。

新しいドキュメント タイプを作成するには、次の手順に従います。

1. **ドキュメント タイプ**ページに移動します。
2. **新規** をクリックします。
3. **タイプ** フィールドに、**SharePoint** または **HR** ドキュメントなどの新しいドキュメント タイプの短縮名を入力します。
4. **名前**フィールドに、**SharePoint ファイル**または **HR ドキュメント**などの長い名前を入力します。
5. **クラス** フィールドで、ドキュメント タイプの動作を定義するクラスを指定します。

    - **ファイルの添付** - ユーザーはファイルを要求されます。
    - **URL の添付** - ユーザーは、`https://www.microsoft.com` のように、**メモ**フィールドに URL を入力することができます。 **添付ファイル** ページの **開く** ボタンをクリックすると [参照] タブに URL が開きます。
    - **簡易メモ** – ユーザーは **メモ** フィールドに簡易メモを追加できます。

6. **クラス** フィールドで**ファイルの添付**を指定した場合、**場所**フィールドで使用する記憶域メカニズムを指定します。
7. **場所** フィールドで **SharePoint** を指定した場合、**SharePoint アドレス** フィールドで Microsoft SharePoint アドレスを指定します。 これを行うには、**編集** ボタン (鉛筆シンボル) をクリックし、**フォルダー選択** ダイアログ ボックスをオンにします。

## <a name="configure-sharepoint-storage"></a>SharePoint 記憶域のコンフィギュレーション

Microsoft SharePoint Online は、ネイティブでサポートされる保存場所の 1 つです。 現在、SharePoint Online だけがサポートされています。 オンプレミス SharePoint (ローカル SharePoint サーバー) のサポートは将来追加される可能性があります。

SharePoint ストレージを使用するには、ドキュメント タイプの**場所**フィールドを **SharePoint** に設定します。 その後、**SharePoint アドレス** フィールドに、有効な SharePoint アドレスを入力します。

SharePoint 記憶域を構成するには、次の手順を実行します。

1. **ドキュメント管理パラメータ**ページに移動します。
2. **SharePoint** タブの**既定の SharePoint サーバー**フィールドで、contosoax7.sharepoint.com など、SharePoint サイトに対して自動的に検出されたホスト名を確認します。 通常、SharePoint ホスト名は tenantname.sharepoint.com の形式で、そのテナントのアカウントは `user1@tenantname.onmicrosoft.com` の形式で示されます。

    既定の SharePoint サーバーが指定されていない場合は、通常、テナントの SharePoint サイトが存在しないか、有効な Microsoft Office 365 ライセンスが現在のユーザー (管理者) に関連付けられていません。

4. オプション: **SharePoint 接続**のテスト をクリックし、指定された SharePoint ホスト名をテストします。 これでセキュリティとライセンスが正しく機能していることを確認します。 
5. オプション: **SharePoint を開く**をクリックし、指定された SharePoint ホスト名をブラウザーで開きます。 これはセキュリティを検証せず、ブラウザのタブで SharePoint パスを開くだけの簡単に検索であることに注意してください。

### <a name="troubleshooting-sharepoint-communication"></a>SharePoint 通信のトラブルシューティング

SharePoint 通信は、次の条件が満たされた場合にのみ、現在のユーザーに対して機能します。

- Office 365 ライセンスが、ユーザーのアカウントに関連付けられています。
- ユーザーは、外部ユーザーではなくテナントの一般的なユーザーです (別のテナントのユーザーなど)。
- テナント用の SharePoint サイト (たとえば、Contoso.SharePoint.com など) が存在します。

## <a name="configure-file-types"></a>ファイルの種類のコンフィギュレーション

許可されているファイル拡張子のリストを変更することで、ユーザーがレコードに添付できるファイルの種類を制御できます。

ファイル タイプを指定するには、次の手順に従います。

1. **ドキュメント管理パラメータ**ページに移動します。
2. **ファイル タイプ**タブで、既定のファイル タイプを確認します。
3. ユーザーがレコードに添付できないファイル タイプを削除し、ユーザーがレコードに添付できるファイル タイプを追加します。

## <a name="configure-document-preview"></a>ドキュメント プレビューのコンフィギュレーション

添付ファイルのプレビューには、Microsoft Office Online Server で提供される Web アプリ オープン プラットフォーム インターフェイス (WOPI) を使用します。 **ドキュメント管理パラメーター** ページの**全般**タブの **Office Web Apps サーバー** フィールドで、添付ファイルのプレビューに使用する Office Online サーバー インスタンスを指定します。 既定値は [`https://onenote.officeapps.live.com`] です。 この値は、クラウド ベースの WOPI サーバーを指しています。

### <a name="for-a-microsoft-dynamics-365-finance--operations-on-premises-environment"></a>Microsoft Dynamics 365 Finance + Operations (オンプレミス) 環境の場合

財務 + 運営の規定のクラウドベース WOPI サーバーが、プレビューを提供する添付ファイルを読み込みできません。 プレビューが必要な場合は、[オンプレミス Office Online サーバー インスタンスをインストールし](https://technet.microsoft.com/library/jj219455.aspx)、それを環境内で構成する必要あります。 **Office Web アプリケーション サーバー** フィールドを、インストールされている Office Online Server インスタンスのホスト名に設定し、**保存**をクリックします。

プレビューが必要な場合は、**Office Web アプリケーション サーバー** フィールドを `https://localhost` に設定します。 プレビューは、その後は、エラー メッセージではなく、「プレビューを利用できません」というメッセージを表示します。

### <a name="document-preview-wopi-will-not-work-in-environments-with-ip-whitelisting-enabled"></a>ドキュメント プレビュー (WOPI) は、IP ホワイトリストが有効になっている環境では機能しません。

プレビューを提供する WOPI サービスは、ファイルのレンダリングを取得するためのファイル サービスへと接続し返すことができないため、ドキュメント プレビュー (WOPI) は、IP ホワイトリストが有効になっている環境では機能しません。

## <a name="other-configuration"></a>他のコンフィギュレーション

これらのオプションが使用されることはほとんどありませんが、考慮すべきその他のコンフィギュレーション オプションを次に示します。

- **ドキュメント管理パラメーター**ページの、**一般**タブで、**ドキュメント テーブルの使用**オプションを使用して、**アクティブ ドキュメント テーブル**許可リストを有効にすることができます。 このオプションを**はい**に設定すると、他のすべてのテーブルの添付ファイルが無効になります。 したがって、必要なときにのみこのオプションをオンにしてください。
- **ドキュメント管理パラメーター**ページの、**全般**タブで、**最大ファイル サイズ(単位: メガバイト)** フィールドを使用して、添付ファイルの最大ファイル サイズを設定できます。 ユーザーがファイルを提供する機能は、構成ファイルで環境に対して設定されているファイル サイズ制限でも制限されることに注意してください。 これらの設定ファイルは、クライアント ページから変更することはできません。
- **オプション** ページ (**設定** \> **ユーザー オプション**) では、**基本設定** タブで、**ドキュメント処理の有効化** オプションを使用して、ドキュメント処理を無効にします (ドキュメント管理)。

## <a name="accessing-document-management-attachments"></a>ドキュメント管理添付ファイルへのアクセス 

ドキュメント管理は、データ ソースを含む殆どのフォームのトップにある**添付**ボタン (キーボード ショートカット: **Ctrl**+**Shift**+**A**) として、ユーザーに表示されます。 **添付**ボタンをクリックすると、フォーム上で現在選択されているコントロールのデータ ソースのコンテキストで**添付ファイル** フォームが開きます。

**添付** ボタンには、現在選択されているレコードの添付ファイルの数も表示されるため、ユーザーはそのフォームを開かなくても、現在のレコードに添付ファイルがあるかどうかを確認することができます。 カウントには 0 ～ 9、次に 9+ が表示され、パフォーマンスの影響と大きなカウントの決定と表示の視覚的ノイズが制限されます。

## <a name="attachment-recovery"></a>添付ファイルの回復

プラットフォーム更新プログラム 29 では、添付ファイルの回復機能が追加され、設定された期間内に回復されるレコードの添付ファイルのごみ箱が提供されます。

### <a name="configuration-of-attachment-recovery"></a>添付ファイルの復元のコンフィギュレーション

**ドキュメント管理パラメータ** > **一般** >  **遅延削除** > **遅延削除の有効化** に移動して添付ファイルの回復を有効にできます。 **削除を延期する日数** のデフォルトは 30 日ですが、必要に応じて変更できます。 **削除を延期する日数** 値がゼロの場合、削除された添付ファイルが無期限に回復可能であることを意味します。 

添付ファイルの回復を有効にすると、この名前のバッチジョブが作成されます: "保存期間の終了に達した削除済み参照のスキャン"。 このバッチ ジョブは **削除を延期する日数** を使用して、**削除されたデータと時間** に基づいて削除された添付ファイルを保持する期間を決定します。

### <a name="deleting-attachments-when-attachment-recovery-is-active"></a>添付ファイルの回復がアクティブな場合の添付ファイルの削除

ユーザーが添付ファイルを削除すると通知がメッセージ センターに追加され、削除の確認と削除が意図されていない場合にアクションを取り消すオプションが提供されます。

テーブル拡張サポートが組み込まれているため、**DocuRef** や **DocuValue** テーブルの拡張やカスタム フィールド値は保持されリカバリが可能です。 

### <a name="recovering-attachments"></a>添付ファイルの回復

添付ファイルの回復が有効な場合、添付ファイルは次の 3 つの方法のいずれかで回復できます:
1. 削除した後すぐに、ユーザーは **添付ファイルを削除しました** 通知の [元に戻す] リンクを使用できます。
2. **添付ファイル** ページで **削除済み添付ファイル** ボタンを使用して、特定のレコードで回復できる削除された添付ファイルのリストにアクセスできます。 削除された添付ファイルは、確認のために開いたり、完全に削除したり、復元できます。
3. **システム管理** > **照会** で **削除済み添付ファイル** ページから削除された添付ファイルのリストへのアクセスが提供され、任意のレコードに回復できます。 削除された添付ファイルは、確認のために開いたり、完全に削除したり、復元できます。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-is-the-difference-between-document-handling-and-document-management"></a>ドキュメント処理とドキュメント管理の違いは何ですか。

ドキュメント処理とドキュメント管理の違いはありません。 両方とも同じ機能を示します。 異なるバージョンの製品では、異なる用語が使用されています。

### <a name="what-is-the-difference-between-document-management-and-print-management"></a>ドキュメント処理と印刷管理の違いは何ですか。

ドキュメント管理では、メモ、ドキュメント、および他のファイルを追加し記録できます。

印刷管理では選択したレポートの印刷設定を制御することができます。 印刷設定には、コピー数、印刷先、およびレポートに含めることができる多言語テキストが含まれます。 詳細については、 [ドキュメント レポーティング サービス](../../dev-itpro/analytics/document-reporting-services.md) を参照してください。

### <a name="what-is-the-difference-between-document-types-and-file-types"></a>ドキュメント タイプとファイル タイプの違いは何ですか。

ドキュメント タイプは、レコードに添付したドキュメント、または作成するテンプレートを分類するために使用します。 各ドキュメント タイプは、固有の場所に格納されることができます。 ドキュメント タイプのテーブルの名前は DocuType です。

ファイル タイプには、Microsoft Word ドキュメントおよび画像が含まれます。 ファイル タイプは、.txt、.png、.doc、.xlsx、または .pdf などのファイルの拡張子で表されます。

### <a name="does-document-management-integrate-with-office-365"></a>ドキュメント管理は Office 365 と統合されますか。

はい。 SharePoint 記憶域はネイティブでサポートされ、ドキュメント タイプの保管場所として選択できます。 さらに、任意の URL アドレス指定可能なファイルを **URL** ドキュメント タイプ経由で添付できます。

### <a name="how-does-the-default-storage-location-for-document-management-change-in-finance--operations-environments"></a>ドキュメント管理の規定の保存スペース場所は、財務 + 運営環境ではどのように変わりますか？

Finance + Operations 環境の場合、添付ファイルの Azure Blob ストレージ プロバイダーはファイル フォルダー ストレージ プロバイダーに置き換えられ、添付ファイルはクラウドに格納される代わりにオンプレミスに保存されます。 したがって、添付ファイルの既定の保管場所はファイル フォルダとなります。

### <a name="if-i-accidentally-delete-an-attachment-stored-in-azure-blob-storage-can-it-be-restored"></a>誤って Azure Blob Storage に格納されている添付ファイルを削除した場合、復元できますか。

Azure Blob Storage に格納されている添付ファイルが誤って削除された場合は、完全に削除されたことになり、ファイルへの参照情報も削除されてしまうため、復元や修復することができません。

### <a name="is-the-database-information-about-attachments-stored-separately-from-the-attachments-themselves"></a>添付ファイルに関するデータベースの情報は、添付ファイルそのものとは別の場所に保存されていますか？

添付ファイルの情報はDocuRefテーブルおよびDocuViewテーブルに格納されています。 DocuRefテーブルは、主に添付ファイルに関する情報を保持しています。 DocuRefの情報は、DocuViewレコードに関連付けられている情報と連携しています。 DocuRefテーブルは、添付ファイルを保持しています。 ファイルはデータベースの外に保存されるため、バックアップから復元するなどのデータベース上の操作は添付ファイルに関するデータベース情報のみに作用し、添付ファイルそのものには作用しません。

### <a name="can-attachments-be-stored-in-the-database"></a>添付ファイルをデータベースに保存できますか。

一連番号 既定では、添付ファイルは Azure Blob Storage に格納されます。

### <a name="what-are-the-main-differences-between-azure-blob-storage-and-database-storage"></a>Azure Blob Storage とデータベース ストレージの主な相違点は何ですか。

データベース ストレージは Azure SQL データベースです。 ファイル ストレージは Azure Blob Storage です。 Azure Blob Storage はよりシンプルで安価です。

### <a name="how-much-storage-do-we-get-for-azure-blob-storage"></a>Azure Blob Storage にどのくらいストレージを確保できますか。

詳細については [ライセンス ガイド](https://mbs.microsoft.com/Files/public/365/Dynamics365LicensingGuide.pdf) を参照してください。 現在、40 ギガバイト (GB) のストレージを使用できます。

### <a name="what-is-the-cost-for-additional-storage"></a>追加ストレージの費用はいくらですか。

追加ストレージのコストは変動しますが [標準の Azure ストレージ費用](https://azure.microsoft.com/pricing/details/storage/page-blobs/) と同様です。 すなわち、費用はおよそ GB あたり $0.05 です。

### <a name="how-can-we-learn-how-much-storage-weve-already-used"></a>既に使用しているストレージの量を確認する方法を教えてください。

データベースやファイル ストレージの制限に近づいた場合は、積極的なコミュニケーションが必要になります。 ただし、Microsoft Dynamics Lifecycle Services (LCS) は一部の情報を提供し、追加情報のサポート要求をログに記録できます。 

### <a name="is-there-an-option-to-export-all-document-attachments-from-the-system"></a>すべてのドキュメントの添付ファイルをシステムからエクスポートするか選択できますか。

添付ファイルをエクスポートできますが、標準の添付ファイル エンティティが存在しないため、その機能は標準の機能ではありません。 特定のビジネス ドキュメントやレコードに対する添付ファイルを提供するエンティティを作成する必要があります。

### <a name="how-can-attachments-be-extracted-from-the-system"></a>どのようにシステムから添付ファイルを抽出できますか。

添付ファイルを抽出するには、特定のビジネス ドキュメントやレコードに対する添付ファイル エンティティが作成される必要があります。 各レコード タイプの ID が異なるため、標準の添付ファイル エンティティがありません。 添付ファイル エンティティを作成する方法については、**AOT > データモデル > データ エンティティ** ノードの下にある "添付ファイル" を検索して、アプリケーション エクスプローラーの例を参照してください。

