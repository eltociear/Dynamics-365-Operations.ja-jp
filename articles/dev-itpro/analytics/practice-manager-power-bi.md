---
title: "プラクティス マネージャー Power BI コンテンツ"
description: "このトピックでは、プラクティス マネージャー Power BI コンテンツの内容について説明します。 コンテンツに含まれているレポートにアクセスする方法を説明し、コンテンツを作成するために使用するデータ モデルおよびエンティティについての情報を提供します。"
author: KimANelson
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 99e5b5087cc72c01ff3e92d0b2b3a6279385eb19
ms.contentlocale: ja-jp
ms.lasthandoff: 09/29/2017

---

# <a name="practice-manager-power-bi-content"></a>プラクティス マネージャー Power BI コンテンツ

[!include[banner](../includes/banner.md)]

このトピックでは、**プラクティス マネージャー** Microsoft Power BI コンテンツの内容について説明します。 Power BI レポートにアクセスする方法を説明し、コンテンツを作成するために使用するデータ モデルおよびエンティティについての情報を提供します。

## <a name="overview"></a>概要

**プラクティス マネージャー** Power BI コンテンツは、プラクティス マネージャーおよびプロジェクト マネージャー用に作成されました。 組織が取り組んでいるプロジェクトに関連した主要メトリックスが提供されます。 ダッシュ ボードでは、プロジェクトおよび関連する顧客の概要を示します。 レポート レベルのフィルターは、特定の法人のレポートに使用できます。 この Power BI コンテンツは、プロジェクト会計集計の測定からデータを取得します。

[**プラクティス マネージャー**] Power BI コンテンツには、5 つのレポート ページが含まれます。1 つの概要ページと、プロジェクト原価、収益、達成額管理、および時間測定値の詳細を示す 4 つのページで、さまざまな分析コードに分割されています。

コンテンツ内のすべての金額はシステム通貨で表示されます。 システム通貨は、[**システム パラメーター**] ページで設定できます。

## <a name="accessing-the-power-bi-content"></a>Power BI コンテンツへのアクセス
Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (2017 年 7 月) を使用している場合、[**プラクティス マネージャー**] Power BI コンテンツは [**プロジェクト管理**] ワークスペースで表示されます。

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Power BI コンテンツに含まれるレポート

次の表は、**プラクティス マネージャー** Power BI コンテンツの各レポート ページに表示されるメトリックスの詳細について説明しています。

| レポート ページ       | メトリックス |
|-------------------|---------|
| プロジェクトの概要 | <ul><li>作成済プロジェクト</li><li>見積済のプロジェクト</li><li>処理中のプロジェクト</li><li>ステージ別のプロジェクト数</li><li>都市別のプロジェクト数</li><li>顧客別の実績収益</li><li>プロジェクト別の予算粗利</li><li>達成額管理の概要</li></ul> |
| コスト              | <ul><li>月別の [実際] 対 [予算原価]</li><li>年別の [実際] 対 [予算原価]</li><li>カテゴリ別の [実際] 対 [予算原価]</li><li>トランザクション タイプ別の実際原価</li></ul> |
| 収益           | <ul><li>月別の実績収益</li><li>郵便番号別の実績収益</li><li>カテゴリ別の [実際] 対 [予算収益]</li><li>顧客の業種別の実績収益</li></ul> |
| EVM               | プロジェクト別の原価とスケジュール業績インデックス |
| 時間             | <ul><li>[支払い請求可能な実績稼働時間数] 対 [支払請求可能な実績非稼動時間数] 対 [予算時間]</li><li>プロジェクト別の [支払い請求可能な実績稼働時間数] 対 [支払請求可能な実績非稼動時間数]</li><li>リソース別の [支払い請求可能な実績稼働時間数] 対 [支払請求可能な実績非稼動時間数]</li><li>プロジェクト別の請求可能な実績時間の比率</li><li>リソース別の請求可能な実績時間数の比率</li></ul> |

これらすべてのレポートのグラフとタイルはフィルター処理し、ダッシュボードに固定することができます。 Power BI のフィルター処理と固定方法の詳細については、「[ダッシュボードの作成およびコンフィギュレーション](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/)」を参照してください。 また、基になるデータをエクスポートする機能を使用するなら、視覚化で要約されている基になるデータをエクスポートすることができます。

## <a name="extending-the-power-bi-content"></a>Power BI コンテンツの拡張
Microsoft Dynamics Lifecycle Services (LCS) で利用できるコンテンツ パックを使用すると、Microsoft Dynamics 365 にログインしない人々に関する優れた分析ができます。 ほかのレポートまたはビジュアルを含める場合、および、Power BI.com テナント分析のためにそれらを発行するために、これらのコンテンツ パックを変更できます。 

LCS の共有資産ライブラリに [**プラクティス マネージャー**] Power BI コンテンツがあります。 コンテンツのダウンロード方法および組織で実装する方法の詳細については、「[Microsoft およびパートナーからの LCS での Power BI コンテンツ](power-bi-content-microsoft-partners.md)」を参照してください。 Power BI コンテンツの実装方法を示すデモを視聴するには、「[Microsoft の Power BI コンテンツおよび Dynamics Lifecycle Services のパートナー](https://mix.office.com/watch/9puyb1b2xs1w)」の Office Mix を参照してください。

使用している Dynamics 365 バージョンに適用される [**プラクティス マネージャー**] コンテンツをダウンロードしてください。

## <a name="understanding-the-data-model-and-entities"></a>データ モデルおよびエンティティの理解

次のデータは、[**プラクティス マネージャー**] Power BI コンテンツのレポート ページに入力するために使用されます。 このデータは、エンティティ ストアで実施される集計の測定として表されます。 エンティティ ストアは、分析に最適化された Microsoft SQL Server データベースです。 詳細については、「[エンティティ ストアとの Power BI の統合](power-bi-integration-entity-store.md)」を参照してください。

次のセクションでは、各エンティティで使用される集計の測定について説明します。

### <a name="entity-projectaccountingcubeactualhourutilization"></a>エンティティ: ProjectAccountingCube_ActualHourUtilization
[**データ ソース:**] ProjEmplTrans

| キー集計の測定      | フィールド                              | 説明 | 
|--------------------------------|------------------------------------|-------------|
| 支払い請求可能な実績稼働時間数 | Sum(ActualUtilizationBillableRate) | 支払い請求可能な実績稼働時間数の合計。 |
| 支払請求可能な実績非稼動時間数   | Sum(ActualBurdenBillableRate)      | 実績非稼動の比率の合計。 |

### <a name="entity-projectaccountingcubeactuals"></a>エンティティ: ProjectAccountingCube_Actuals
[**データ ソース:**] ProjTransPosting

| キー集計の測定 | フィールド              | 説明 | 
|---------------------------|--------------------|-------------|
| 実績収益            | Sum(ActualRevenue) | 全トランザクションの転記済収益の合計。 |   
| 実際原価               | Sum(ActualCost)    | 全トランザクション タイプの転記済原価の合計。 |

### <a name="entity-projectaccountingcubecustomer"></a>エンティティ: ProjectAccountingCube_Customer
[**データ ソース:**] CustTable

| キー集計の測定 | フィールド                                            | 説明 | 
|---------------------------|--------------------------------------------------|-------------|
| プロジェクト数        | COUNTA(ProjectAccountingCube_Projects[PROJECTS]) | 使用可能なプロジェクトの数。 |


### <a name="entity-projectaccountingcubeforecasts"></a>エンティティ: ProjectAccountingCube_Forecasts
[**データ ソース:**] ProjTransBudget

| キー集計の測定 | フィールド                  | 説明 | 
|---------------------------|------------------------|-------------|
| 予算原価               | Sum(BudgetCost)        | 全トランザクション タイプの予測原価の合計。 |
| 予算収益            | Sum(BudgetRevenue)     | 未収 / 請求済み予測収益の合計。  |
| 予算粗利       | Sum(BudgetGrossMargin) | 全予測収益の合計と全予測原価の合計の差額。 |

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>エンティティ: ProjectAccountingCube_ProjectPlanCostsView
[**データ ソース:**] プロジェクト

| キー集計の測定 | フィールド                    | 説明 | 
|---------------------------|--------------------------|-------------|
| 予定原価              | Sum(SumOfTotalCostPrice) | 計画タスクのすべてのプロジェクト トランザクション タイプにおける合計原価価格の見積。 |

### <a name="entity-projectaccountingcubeprojects"></a>エンティティ: ProjectAccountingCube_Projects
[**データ ソース:**] プロジェクト

| キー集計の測定    | フィールド | 説明 | 
|------------------------------|-------|-------------|
| コスト パフォーマンス インデックス       | ProjectAccountingCube_Projects[達成額] / ProjectAccountingCube_Projects[完了済みのタスクの合計実際原価] | 合計達成額を合計実際原価で除算した計算。 |
| スケジュール業績インデックス   | ProjectAccountingCube_Projects[達成額] / ProjectAccountingCube_Projects[完了済みのタスクの合計予定原価] | 合計達成額を合計予定原価で除算した計算。 |
| 作業の完了率 | 作業の完了率 = ProjectAccountingCube_Projects[完了済みのタスクの合計実際原価] / (ProjectAccountingCube_Projects[完了済みのタスクの合計実際原価] + ProjectAccountingCube_Projects[プロジェクトの合計予定原価] - ProjectAccountingCube_Projects[完了済みのタスクの合計予定原価]) | 完了タスクの合計実際原価およびプロジェクトの予定原価に基づいた作業の合計完了率。 |
| 支払請求可能な実績時間数の比率  | ProjectAccountingCube_Projects[プロジェクトの支払い請求可能な実績稼働時間数の合計] / (ProjectAccountingCube_Projects[プロジェクトの支払い請求可能な実績稼働時間数の合計] + ProjectAccountingCube_Projects[プロジェクトの支払い請求可能な実績非稼動時間数]) | 実績稼働時間数と実績非稼動時間数に基づいた支払請求可能な実績時間数の合計。 |
| 達成額                 | ProjectAccountingCube_Projects[プロジェクトの合計予定原価] * ProjectAccountingCube_Projects[作業の完了率] | 合計予定原価と作業の完了率の乗算。 |

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>エンティティ: ProjectAccountingCube_TotalEstimatedCosts 
[**データ ソース:**] ProjTable

| キー集計の測定       | フィールド               | 説明 | 
|---------------------------------|---------------------|-------------|
| 完了した活動の予定原価 | Sum(TotalCostPrice) | 完了タスクのすべてのプロジェクト トランザクション タイプにおける合計原価価格の見積。 |
