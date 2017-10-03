---
title: "移動平均"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 65531
ms.assetid: dfd10099-8f7f-44b1-917e-df37c2fe8773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0018f5df3d0d2882c300b6458bfb8adfba84e2ad
ms.contentlocale: ja-jp
ms.lasthandoff: 05/25/2017

---

# <a name="moving-average"></a>移動平均

[!include[banner](../includes/banner.md)]


次に、移動平均原価を原価計算方法として使用するときの前提条件を示します。
1.  **品目モデル グループ** ページの**在庫モデル** フィールドで、[移動平均] がオンになっている品目モデル グループを設定します。 **注記 :** 既定では、移動平均 を選択した場合、**現物在庫の転記** フィールドおよび **資産在庫の転記** フィールドも選択されます。 

2.  **転記**ページの**在庫**タブで、勘定を**移動平均の価格差異**および**移動平均の原価再評価**の勘定に割り当てます。 原価を比例して経費処理する場合は、**移動平均の価格差異**の勘定が使用できます。 これが起きるのは、購買入庫と仕入請求書の原価に差異があるためであり、また元の在庫数量と現在の手持在庫数量に差異があるためです。 製品の移動平均原価を新しい単価に合わせて調整するときは、**移動平均の原価の再評価**の勘定を使用します。
3.  **リリースされた製品**ページで、移動平均品目モデル グループを製品に割り当てます。 **注記 :** 在庫決算プロセスは、会計期間のみをクローズします。 これは、品目モデル グループとして割り当てられた移動平均がある製品には影響しません。

## <a name="convert-to-the-moving-average-costing-method"></a>移動平均原価計算方法への換算
製品は、移動平均在庫評価方法を使用するように変換できます。 このタイプの変換は、通常、現年度の最後の月を締めた後の年度の最後に行われます。 これには、製品の現在の価格モデルが使用されます。 在庫原価計算方法を、平均原価または標準原価に基づく原価計算方法から移動平均に基づくメソッドへ変更できます。 

原価計算方法を標準原価計算方法から移動平均方法に変更する場合、次の作業を行う必要があります。

1.  在庫数量と値が 0 (ゼロ) になるように調整します。
2.  在庫金額と数量が 0 (ゼロ) の後に、品目モデル グループを移動平均に変更します。
3.  数量と価格が在庫に戻るように調整します。

在庫原価計算方法を、移動平均方法から、先入れ先出し (FIFO) 方法、後入れ先出し (LIFO)、または加重平均方法には変更できません。

**注記 :** 標準コストから移動加重平均への換算は、手動プロセスです。

次の例では、移動平均原価計算方法を使用した効果について説明します。 コンフィギュレーションには次の 4 つがあります。
-   発注書と比例して経理処理する原価との差異
-   移動平均の製品および在庫調整
-   生産での移動平均
-   前の日付のトランザクションでの移動平均

## <a name="purchase-order-and-proportionally-expensed-cost-difference"></a>発注書と比例して経理処理する原価との差異
移動平均では、製品の原価は購買入庫によって決まります。 仕入請求書を転記するとき、購買入庫と仕入請求書の原価に違いがある場合、差額は在庫の現在の製品に合わせて調整され、残りの金額が経費として処理されます。 

この例では、発注書が作成され、ある原価で入庫され、仕入請求書は異なる原価で転記されます。

1.  数量 2、単価 10.00 の発注書を作成します。
2.  その製品の購買入庫を作成します。
3.  数量 1、単価 10.00 の販売注文を作成します。
4.  数量 2、単価 12.00 の発注書を作成します。

単価 2.00 の差額は、仕入請求書の転記時に、[移動平均の価格差異] 勘定に転記されます。 その理由は、2 つの製品を 20.00 の原価で購入したことによります。 製品の 1 つは、単価 10.00 で販売されました。 仕入請求書は、数量 2 が単価 12.00 で転記されました。 製品の単価は 14.00 で転記することはできません。

## <a name="moving-average-product-and-inventory-adjustment"></a>移動平均の製品および在庫調整
製品の移動平均原価を調整する必要がある場合、在庫調整は今日の日付に許可されます。 在庫調整の日付をさかのぼって、製品の移動平均原価を訂正することができません。 後続のトランザクションによる原価フローを設定することはできません。 

この例では、移動平均原価は製品に合わせて調整されます。

1.  移動平均原価の調整の対象となる製品を選択します。 **注記 :** **移動平均の再評価** ページでは、製品に使用可能な在庫を確認できます。 選択した製品は、転記数量が 1、転記価格が 12.00、転記された単位原価が 12.00、そして単位原価が 12.00 です。
2.  ここで、**単位原価**フィールドを 16.00 に更新します。 システムは残りのフィールドを計算します。
3.  調整が転記されます。

**注記 :** 移動平均コストは、今日の日付でのみ調整できます。

**伝票の決済**ページで、[移動平均の原価の再評価] の勘定に転記された 4.00 の調整を確認できます。

## <a name="moving-average-with-production"></a>生産での移動平均
移動平均で、生産された品目がサポートされます。 実稼働環境で移動平均を使用する予定の場合は、**生産管理パラメーター** ページの**見積原価価格の使用**のスライダーを選択する必要があります。 すなわち、見積時に計算された原価価格が、実際の BOM 計算原価価格の代わりに使用されるということです。

## <a name="moving-average-with-a-backdated-transaction"></a>前の日付のトランザクションでの移動平均
さかのぼった日付のトランザクションが現在の移動平均原価に割り当てられ、製品の現物の数量が更新されますが、製品の移動平均原価には影響しません。 この移動平均の例では、移動平均の製品に対してさかのぼったトランザクションが転記されます。

1.  数量 1、原価 20.00 の移動平均製品の在庫調整を作成します。
2.  製品の在庫トランザクション履歴は、次のようになります。
    -   在庫トランザクションは 1、原価は 16.00、転記日付は 1 月 15 日、トランザクションの日付は 1 月 15 日。
    -   在庫調整は 1、原価は 20.00、転記日付は 1 月 1 日、トランザクションの日付は 1 月 15 日。
3.  調整を転記します。

**在庫トランザクション** ページで、製品の現在の移動平均が 16.00 のままで、4.00 が経費として処理されたことを確認できます。 過去の日付で転記することが可能ですが、原価の差額は経費として処理され、移動平均原価には影響しません。

## <a name="inventory-value-report"></a>在庫金額レポート
この移動平均の例では、製品の現在の移動平均の計算をサポートするために、在庫金額のレポートが印刷されます。 [在庫金額] レポートは、トランザクションを古い順に印刷して、原価とともに、製品の移動平均原価計算をサポートできます。 レポートは、製品の移動平均原価を表示します。 **在庫金額のレポート**ダイアログ ボックスで [日付範囲] を使用すると、**トランザクションの時刻**や**転記日付**でレポートを並び替えることができます。 **転記日付** オプションは、従来から使用されているレポートの印刷方法です。 **トランザクションが時刻**オプションは、トランザクションが報告され、製品の移動平均原価が更新される実際の日付です。 移動平均原価計算を経時的に表示する場合は、**トランザクション時刻で並べ替え** オプションを使用して、[在庫金額レポート] を印刷します。 次の表は、**トランザクション時刻で並べ替え**オプションを使用してレポートを印刷した製品のトランザクションを表示しています。

| トランザクションの時刻 | 日         | トランザクション タイプ           | 梱包明細から | 金額 | 平均単位原価 |
|------------------|--------------|----------------------------|----------|--------|-------------------|
|                  | 10 月 1 日    | 期首残高          | 0        | 0.00   | 0.00              |
| 10 月 8 日        | 9 月 28 日 | さかのぼった日付の入庫          | 1        | 16.00  | 16.00             |
| 10 月 3 日        | 10 月 3 日    | 購買入庫           | 2        | 20.00  | 12.00             |
| 10 月 5 日        | 10 月 5 日    | 販売注文                | -1       | -10.00 | 13.00             |
| 10 月 7 日        | 10 月 7 日    | 仕入請求書           |          | 2.00   | 14.00             |
| 10 月 8 日        | 10 月 8 日    | 移動平均の再評価 |          | 4.00   | 16.00             |
|                  | 10 月 31 日   | 小計                      | 2        | 32.00  | 16.00             |

 **注記 :** **トランザクション時刻で並べ替え** オプションを使用して一般会計を在庫と一致させることはできません。 レポートは、**転記日付**オプションを使用して印刷する必要があります。





