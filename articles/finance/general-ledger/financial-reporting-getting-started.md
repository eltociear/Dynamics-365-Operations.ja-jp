---
title: 財務諸表の概要
description: このトピックでは、Microsoft Dynamics 365 Finance で財務報告にアクセスする場所、および財務報告機能の使用方法について説明します。 これには、用意された既定の財務諸表の説明が含まれています。
author: aprilolson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 10444
ms.assetid: 3eae6dc3-ee06-4b6d-9e7d-1ee2c3b10339
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f67296797d9a671ae071a13b1bbda73cf3fc6e7f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915180"
---
# <a name="financial-reporting-overview"></a>財務諸表の概要

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


このトピックでは、財務報告にアクセスする場所、および財務報告機能の使用方法について説明します。 これには、用意された既定の財務諸表の説明も含まれています。

<a name="accessing-financial-reporting"></a>財務報告へのアクセス
-----------------------------

**財務報告**メニューは次の場所にあります。

-   **総勘定元帳** &gt; **照会およびレポート**
-   **予算作成** &gt; **照会およびレポート** &gt; **基本予算作成**
-   **予算作成** &gt; **照会およびレポート** &gt; **予算計画**
-   **予算作成** &gt; **照会およびレポート** &gt; **予算管理**
-   連結

法人の財務諸表を作成、生成するには、その法人に次の情報を設定する必要があります。

-   会計カレンダー
-   元帳
-   勘定科目表
-   通貨

財務報告の機能は、セキュリティ ロールによって適切な権限、職務が割り当てられたユーザーが使用できます。 次のセクションでは、関連するロールとともにこれらの権限と職務を表示します。

### <a name="duties"></a>職務権限

| 職務のラベル                            | 説明                                                             | AOT 名                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| 財務諸表のセキュリティの管理 | 財務諸表のセキュリティを管理し、管理タスクを実行します | FinancialReportsSecurityMaintain |
| 財務諸表の管理            | 財務諸表をデザインおよび管理します。                                  | FinancialReportsMaintain         |
| 財務諸表の生成            | 財務諸表を生成および更新します。                                 | FinancialReportsGenerate         |
| 財務パフォーマンスの確認          | 財務パフォーマンスを確認および分析します。                               | FinancialReportsPerfReview       |

### <a name="privileges"></a>権限

| 権限のラベル                       | 説明                                                             | AOT 名                         |
|---------------------------------------|-------------------------------------------------------------------------|----------------------------------|
| 財務諸表のセキュリティの管理 | 財務諸表のセキュリティを管理し、管理タスクを実行します | FinancialReportsSecuritySystemMaintain |
| 財務諸表の管理            | 財務諸表をデザインおよび管理します。                                  | FinancialReportsMaintainReports  |
| 財務諸表の生成            | 財務諸表を生成および更新します。                                 | FinancialReportsGenerateReports  |
| 財務諸表の表示                | 財務諸表の表示。                                                 | FinancialReportsView             |

### <a name="roles"></a>ロール

| 権限のラベル                       | 関税                                  | ロール                                                                           |
|---------------------------------------|---------------------------------------|---------------------------------------------------------------------------------|
| 財務諸表のセキュリティの管理 | 財務諸表のセキュリティの管理 | セキュリティー管理者                                                          |
| 財務諸表の管理            | 財務諸表の管理            | アカウント マネージャー、会計監修者、財務コントローラー、予算マネージャー |
| 財務諸表の生成            | 財務諸表の生成            | CEO、CFO、経理担当                                                            |
| 財務諸表の表示                | 財務パフォーマンスの確認          | 未割当                                                                   |

ユーザーが追加されるかロールを変更すると、ユーザーは数分以内に財務報告にアクセスできるようになります。 **注記:** sysadmin ロールは、財務報告のすべてのロールに追加されます。

## <a name="report-deletions-and-expirations"></a>削除と有効期限の報告
レポートを生成したユーザーは、独自のレポートを削除できます。 **Financial Reporting セキュリティの管理**の職務権限を持つユーザーは、他のレポートを削除できます。 

10.0.7 リリースから、有効期限の概念が導入されました。 機能管理ワークスペースでは、新しい必須機能が有効になります。 この機能には、次の変更が含まれています。
* 生成されると、新しく生成されたレポートには、有効期限が 90 日として自動的に設定されます。
* 機能がインストールされる前の既存のレポートには、90 日の有効期限が与えられます。 この日付は Financial Reporting サービスが実行されるまでの短い期間、空白で表示される場合があり、レポートが生成され、サービスは既存のレポートに対する更新を空白の有効期限で実行する場合があります。 
* **Financial Reporting セキュリティの管理**のユーザーには、この機能へのアクセス許可が与えられます。 **財務諸表の有効期限の管理**権限を付与された**財務諸表の管理**の職務権限であるすべてのユーザーは、有効期限を変更することもできます。 現在、次の 2 つの保存オプションを使用できます。 
  * 90 日間の有効期限
  * レポートが期限切れにならないように設定するためのオプション

90日間 などの有効期限を選択すると、今日から 90 日が付与されます。これは、レポートの生成時に設定された元の生成日とこの 90 日間は異なります。 

## <a name="default-reports"></a>既定のレポート
財務報告は 22 の既定の財務諸表を提供します。 すべてのレポートは既定の主勘定カテゴリを使用します。 このレポートは現状のまま使用するか、財務諸表のニーズに対する開始点として使用できます。 損益計算書や貸借対照表などの従来の財務諸表に加えて、これらの既定のレポートには、作成できる会計報告書のさまざまなタイプを示すレポートが含まれます。 

<!--Each report in the following table links to an Office Mix presentation about the report.-->

| 既定のレポート                                                                                         | 説明                                                                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 12 か月ローリング単一列損益計算書 – 既定 | 過去 12 か月の組織の収益性を、1 つの列で表示します。                                                                                                                                                                                                                                      |
| 12 か月トレンド損益計算書 – 既定                 | 過去 12 か月それぞれの組織の収益性を表示します。 この 12 か月は会計年度以上にまたがることができます。                                                                                                                                                                                             |
| 実績対予算 - 既定                                | 元の予算のすべての勘定の残高の詳細な情報を表示し、修正された予算を差異がある実績と比較します。                                                                                                                                                                          |
| 監査の詳細 – 既定                                  | すべての勘定の残高の詳細な情報を表示します。 このレポートには、レポート通貨と国内通貨で借方と貸方残高が、ユーザー ID、データを最後に変更したユーザー、最終変更日、仕訳帳 ID などの追加トランザクション情報とともに表示されます。 |
| 残高リスト - 既定                                   | すべての勘定の残高の詳細な情報を表示します。 このレポートは、開始残高と決算残高、伝票などの追加トランザクション情報とともに現在の期間と現時点の借方と貸方残高を表示します。                                                                    |
| 貸借対照表 – 既定                                   | 年度の組織の財務状態を表示します。                                                                                                                                                                                                                                                             |
| 貸借対照表と損益計算書の並行表示 - 既定 | 年の組織の財務状態と収益性を並べて表示します。                                                                                                                                                                                                                              |
| キャッシュ フロー – 既定                                       | 組織に出入りする現金についての洞察を得ます。                                                                                                                                                                                                                                   |
| JE と TB の詳細な確認 – 既定                      | すべての勘定の開始残高および活動の情報を表示します。                                                                                                                                                                                                                                                      |
| 詳細な試算表 - 既定                         | すべての勘定の、借方と貸方残高、残高の正味金額、トランザクションの日付、伝票、仕訳帳の説明が含まれる残高情報を表示します。                                                                                                                                  |
| 経費の3年間の四半期トレンド – 既定             | 過去 3 年間の 12 の四半期の経費についての洞察を得ます。                                                                                                                                                                                                                                   |
| 財務キャプション JE と TB の確認 – 既定            | 残高および資産の活動、負債、自己資本、収益、経費、利益、または損益財務キャプションを表示します。                                                                                                                                                                           |
| 損益計算書 - 既定                                | 現在の期間また年間累計の組織の収益性を表示します。                                                                                                                                                                                                                                   |
| 元帳トランザクション リスト – 既定                        | すべての勘定の残高の詳細な情報を表示します。 このレポートは、トランザクションの日付、仕訳帳番号、伝票、転記タイプ、追跡番号などの追加トランザクション情報とともに、借方と貸方残高を表示します。                                                                            |
| 比率 – 既定                                          | 年の組織の支払能力、収益性、能率比率を表示します。                                                                                                                                                                                                                           |
| ローリング 12 か月経費 – 既定                       | 過去 12 か月ごとの経費についての洞察を得ます。 この 12 か月は会計年度以上にまたがることができます。                                                                                                                                                                                                       |
| ローリング四半期損益計算書 – 既定               | 昨年と現時点での組織の収益性を、四半期ごとに表示します。                                                                                                                                                                                                                   |
| 並行表示の貸借対照表 – 既定                      | 年度の組織の財務状態を表示します。 このレポートには資産および負債、また株主の株主資本が並べて表示されています。                                                                                                                                                                                |
| 試算表の集計 – 既定                          | 開始残高および決算残高、借方と貸方残高、およびそれらの正味差額が含まれるすべての勘定の残高情報を表示します。                                                                                                                                                                  |
| 年次試算表の集計 – 既定           | 開始残高および決算残高、借方と貸方残高、およびそれらの今年度および昨年度の正味差額が含むすべての勘定の残高情報を提供します。                                                                                                                           |
| 毎週の販売と割引 - 既定                     | 1 か月の週単位の販売および割引についての洞察を得ます。 このレポートには、4 週間の合計が含まれます。                                                                                                                                                                                                              |
| 利用できる予算財源 - 既定                         | 修正予算、実際の経費、予算引当、すべての勘定に使用できる予算財源の詳細な比較を表示します。                                                                                                                                                                                  |

## <a name="opening-financial-reports"></a>財務諸表を開く
**財務報告** メニューをクリックすると、会社の既定の財務レポートの一覧が表示されます。 これにより、レポートを開くおよび変更できます。 既定のレポートの 1 つを開くには、レポートの名前を選択します。 レポートを初めて開くと、前の月のレポートが自動的に生成されます。 たとえば、2016 年 8 月にレポートを初めて開くと、2016 年 7 月 31 日のレポートが生成されます。 レポートを開いた後、データの特定の部分をドリルダウンしたり、レポート オプションを変更することによりレポートの検討を開始できます。

## <a name="creating-and-modifying-financial-reports"></a>財務レポートの作成および変更
財務報告リストから、新しいレポートを作成するか、既存のレポートを変更できます。 適切なアクセス許可が付与されると、[アクション] ウィンドウの **新規** をクリックして新しい財務諸表を作成できます。 レポート デザイナー プログラムがデバイスにダウンロードされます。 レポート デザイナー プログラムを起動すると、新しいレポートを作成できます。 新しいレポートは保存した後、財務報告リストに表示されます。 このリストには、財務で使用している会社に対して作成されているレポートだけが表示されます。 

> [!NOTE] 
> レポート デザイナーのクライアントをダウンロードしているコンピューターには、Microsoft .NET Framework のバージョン 4.6.2 がインストールされている必要があります。 このバージョンの Microsoft .NET Framework は、[Microsoft ダウンロード センター](https://www.microsoft.com/download/details.aspx?id=53345) からダウンロードしてインストールできます。 Chrome を使用している場合、レポート デザイナーのクライアントをダウンロードするために ClickOnce 拡張機能をインストールする必要があります。 匿名モードで起動している場合、ClickOnce の拡張機能が匿名モードに対して有効化されていることを確認します。 財務報告リストに表示されるレポートは変更できます。 レポート名の周りの領域が選択されている場合、[アクション] ウィンドウの **編集** をクリックします。 レポート デザイナー プログラムが開始されます。

## <a name="additional-resources"></a>その他のリソース
- [財務諸表の表示](view-financial-reports.md)



