---
title: "減価償却計算の丸め金額"
description: "この記事は、帳簿設定ページの [減価償却の丸め] フィールドについて説明します。"
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 0cb514dfb8c37b8c027ab895cb970af1b0135bf0
ms.lasthandoff: 03/31/2017


---

# <a name="round-off-amount-for-depreciation-calculations"></a>減価償却計算の丸め金額

この記事は、帳簿設定ページの [減価償却の丸め] フィールドについて説明します。

丸め減価償却金額は各帳簿に設定されます。 丸め減価償却金額は、固定資産の将来の減価償却と金額を示すおよび償却提案で使用されます。固定資産減価償却プロファイル。 この帳簿で許可される減価償却の最小金額を入力します。 

丸め設定に関係なく、最後の減価償却期間の減価償却金額の丸めはおこなわれません。 最後の償却期間の最後に、固定資産の金額は 0 (ゼロ) になるか、または仕損価格を使用する場合は仕損価格となる必要があります。

### <a name="example"></a>例

丸めを使用しない減価償却は、2,444.44 として計算されます。 次の表に示すように、丸めの設定に応じてさまざまな金額が提示されます。

| 丸め方法 | 算出償却額 |
|-----------------|---------------------|
| 0.1 の丸め    | 2,444.40            |
| 1.00 の丸め   | 2,444.00            |
| 10.00 の丸め  | 2,440.00            |
| 100.00 の丸め | 2,400.00            |



