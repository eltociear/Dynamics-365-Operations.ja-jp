---
title: クロス レートの指定
description: このトピックでは、Microsoft Dynamics 365 Finance のクロス レートに関する情報を提供します。
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 146794557a3a6ba1801598fe6b814e209d9f5fc6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178722"
---
# <a name="specify-the-cross-rate"></a>クロス レートの指定

[!include [banner](../includes/banner.md)]

このトピックでは、クロス レートの目的、および請求書で支払決済するときのクロス レート指定方法について説明します。 次の基準がすべて適用される場合、クロス レートを使用します。 
-   請求書で支払を決済する。 
-   支払の明細行と請求書の明細行が異なる通貨を使用する。 
-   いずれの通貨も会計通貨ではない。 

クロス レートは、支払トランザクションの通貨を支払会計通貨に換算するためには使用されません。 代わりに、為替レート テーブルからの為替レートは、支払トランザクションの通貨金額と支払の会計通貨金額の値の計算のために取得されます。 

たとえば、会計通貨が USD で、請求書の通貨が CAD で、支払の通貨が EUR の場合です。 クロス レートを使用して為替レートを入力すると、CAD と EUR の間で直接換算でき、USD を介する必要はありません。 請求書と基本支払を選択すると、請求明細行にクロス レートを入力することができます。 クロス レートは、決済日時点での、これらのトランザクションの通貨間の為替レートです。

1.  次のページのいずれかに移動します:
- **売掛金勘定 > 共通 > 顧客 > すべての顧客** 
- **買掛金勘定 > 共通 > 仕入先 > すべての仕入先** 
- **調達 > 共通 > 仕入先 > すべての仕入先**
2.  未処理トランザクションを決済する顧客または仕入先を選択します。 
3.  顧客用に、**すべての顧客**リスト ページで、**収集 > 未処理トランザクションの決済**に移動します。 仕入先用に、**すべての仕入先**リスト ページで、**請求書 > 未処理トランザクションの決済**に移動します。 
4.  基本支払であるトランザクションを選択し、**支払をマーク**をクリックします。 **マーク**列のチェック ボックスがオンになり、**基本支払**列に情報アイコンが表示されます。 
5.  **クロス レート** フィールドに、決済日現在の請求通貨と支払通貨の間の為替レートを入力します。 
