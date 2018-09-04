---
title: "デモ データ"
description: "このトピックでは、Microsoft Dynamics 365 for Finance and Operations に使用できるデモ データの概要を示します。"
author: sericks007
manager: AnnBe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 56551
ms.assetid: d876e8de-d547-43e5-9259-f095821dc758
ms.search.region: Global
ms.author: pmantha
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: beecdd97d5e1d8afd4269b1f0f25d526b383eba1
ms.contentlocale: ja-jp
ms.lasthandoff: 08/09/2018

---

# <a name="demo-data"></a>デモ データ

[!include [banner](../includes/banner.md)]

このトピックでは、Microsoft Dynamics 365 for Finance and Operations に使用できるデモ データの概要を示します。


デモ データは、導入サポートとデモの目的で、Finance and Operations と一緒にリリースされる基本データ セットです。 現在のデモ データセットは、次の業種をサポートしています。


- Retail
- 配布
- サービス業
- 公的機関
- 個別およびプロセス製造

このデモ データ セットは、16 か国または地域にわたって 40 の言語をサポートしています。 また、さまざまな実装シナリオもサポートします。 次のテーブルに、デモ データ セットに含まれる法人を示します。

| 個法 | 説明                          |
|--------------|--------------------------------------|
| BRMF         | Contoso エンターテインメント システム ブラジル  |
| CNMF         | Contoso エンターテインメント中国          |
| DAT          | 既定の会社                      |
| DEMF         | Contoso エンターテインメント システム ドイツ |
| FRRT         | Contoso 小売 FR                    |
| FRSI         | Contoso コンサルティング FR                |
| GBSI         | Contoso コンサルティング GB                |
| GLCO         | Contoso グループ                        |
| GLMF         | Contoso エンターテインメント システム         |
| GLRT         | Contoso 小売                       |
| GLSI         | Contoso コンサルティング                   |
| INMF         | Contoso インド                        |
| ITCO         | Contoso イタリア                        |
| JPMF         | Contoso エンターテインメント日本          |
| MXMF         | Contoso エンターテインメント システム メキシコ  |
| MYMF         | Contoso エンターテインメント システム MYMF    |
| RUMF         | Contoso エンターテインメント システム ロシア  |
| RURT         | Contoso 小売 RUS                   |
| US01         | Contoso US01                         |
| USMF         | Contoso エンターテインメント システム USA     |
| USP2         | Contoso オレンジ ジュース                 |
| USPI         | Contoso プロセス産業             |
| USRT         | Contoso 小売 USA                   |
| USSI         | Contoso コンサルティング USA               |


## <a name="embedded-analytics"></a>埋め込み分析
5 社のデモ データが更新され、ワークスペース内の新しい埋め込み分析に関するレポートが改善されました。  改善されたレポート データに対して、以下の法人への埋め込み分析をフィルター処理します。

| 個法 | 説明                           |
|--------------|---------------------------------------|
| DEMF         | Contoso エンターテインメント システム ドイツ  |
| GLMF         | Contoso エンターテインメント                 |
| USMF         | Contoso エンターテインメント システム USA      |
| USRT         | Contoso 小売 USA                    |
| USSI         | Contoso コンサルティング USA                |

現金の概要 Power BI コンテンツからのレポートが、**現金の概要** および **銀行管理** ワークスペースで表示されます。 

データでキャッシュ フロー予測レポートを表示するには、まず、**現金および銀行管理領域** から **キャッシュ フロー予測の計算** 機能を使用して、予測計算プロセスを実行する必要があります。 これは、予測に含める会社ごとに完了する必要があります。 次に、**エンティティ格納** ページで、[LedgerCovLiquidityMeasurement] 集計メジャーを更新する必要があります。

説明するには、**データの生成**ページを**デモ データ**モジュールから使用し、キャッシュ フロー予測デモ データを追加できます。 このスクリプトは、キャッシュ フロー予測テーブルにデータを挿入して、レポートに必要な情報をすばやく入力します。 

与信および回収の分析は、**顧客の与信および回収の管理**ワークスペースで表示できます。 データを使用して分析を表示するには、まず、**エンティティ店舗** ページで CustCollectionsBIMeasurements 集計測定を更新する必要があります。

仕入先支払分析は、**仕入先支払** ワークスペースで閲覧できます。 データを使用して分析を表示するには、まず、**エンティティ店舗** ページで VendPaymentBIMeasure 集計測定を更新する必要があります。

購買パフォーマンス分析は、調達およびソーシング モジュールから **購買支出の分析** ページで表示できます。 データを使用して分析を表示するには、まず、**エンティティ店舗** ページで購買キューブ集計測定を更新する必要があります。

販売と収益性の分析は、販売とマーケティング モジュールの **販売および収益性のパフォーマンス** ページで表示できます。 データを使用して分析を表示するには、まず、**エンティティ店舗** ページで販売キューブ集計測定を更新する必要があります。

生産パフォーマンス分析は、生産管理モジュールの **生産パフォーマンス** ページで見ることができます。 データを使用して分析を表示するには、まず、**エンティティ店舗** ページで製品キューブ集計測定を更新する必要があります。

説明するには、**データの生成**ページをデモ データ モジュールから使用し、生産実績デモ データを追加できます。 このスクリプトは、製造オーダーを生成し、関連するフィードバック ジャーナルを使用して、生産実績レポートにデータを入力します。 

倉庫パフォーマンス分析は、倉庫管理モジュールの **倉庫のパフォーマンス** ページで確認できます。 データを使用して分析を表示するには、まず、**エンティティ店舗** ページ] で倉庫集計測定を更新する必要があります。

説明するには、**データの生成**ページをデモ データ モジュールから使用し、倉庫実績デモ データを追加できます。 このスクリプトは、販売注文と倉庫作業を生成し、倉庫のパフォーマンス レポートにデータを入力します。 このデモ データは、デモ データ スイート モデルが環境に展開されている場合にのみ使用できます。

## <a name="vendor-collaboration"></a>仕入先コラボレーション
USMF というデモ会社には、デモで使用する仕入先 US-104 の 3 つの発注書があります。 US-104 の仕入先コラボレーションに対するアクセス権を持つ連絡担当者である、ユーザー ErinH としてログインすることができます。

## <a name="purchase-order-approval"></a>発注書の承認 
USMF というデモ会社には、承認すべき INGA についての 2 つの発注書があります。 ユーザー INGA としてログインして、承認待ちの発注書を参照することができます。 

## <a name="batch-transfer-rules-for-subledger-journals"></a>補助元帳仕訳のバッチ転送ルール
補助元帳仕訳帳勘定項目のバッチ転送ルールが **スケジュール済バッチ** に変更され、ベスト プラクティスが反映されます。 バッチは、10 分ごとに実行されるように構成されています。 バッチ処理が実行されるまで、すべてのソース ドキュメントの勘定項目が反映されないことを理解することが重要です。 総勘定元帳の即時効果を確認する必要がある場合は、**総勘定元帳**パラメータの**バッチ転送ルール** ページで**転送モード**を**同期**に設定します。 製品デモおよびトランザクション量が低い環境では同期が動作しても、大容量トランザクション環境ではパフォーマンスの問題が生じる可能性があります。  
[![一般会計パラメータ](./media/GL-parameters.PNG)](./media/GL-parameters.PNG)

## <a name="cost-accounting"></a>原価計算 
3 つの原価計算元帳がデモ データで作成されます。 原価計算元帳 USP2 は、法人 USP2 からのデータに基づく E2E デモ経験を提供します。 原価管理単位は、2 つの原価オブジェクト分析コード (原価部門と製品グループ) で構成されています。 実際原価、予算原価、統計測定は、2017 年の 12 会計年度期間すべてに転送されます。 2017 年のすべての会計年度期間に間接費計算も実行されました。

アクセス レベルのセキュリティは、コンフィギュレーションされていますが、有効になっていません。 これは、**原価会計パラメーター**ページで有効になります。
[![原価会計パラメーター](./media/Cost-accounting-parameters.PNG)](./media/Cost-accounting-parameters.PNG)


アクセス レベルのセキュリティが有効にした後、Alica を原価オブジェクト コントローラーのロールに割り当てます。 Alica としてログインして **原価管理** ワークスペースにアクセスすることができます。 アリシアはコスト センターのパフォーマンスを参照し、これらの計算がどのようにされたのか細部まで掘り下げて調べることができます。



