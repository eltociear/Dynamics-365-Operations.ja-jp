---
title: サイトの計画の作成
description: 生産計画担当者は、特定品目を生産するための材料と能力要件を計算します。
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: daa185864052849b2c78d975a7eb02e9697cb618
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845176"
---
# <a name="create-a-plan-for-a-site"></a>サイトの計画の作成

[!include [task guide banner](../../includes/task-guide-banner.md)]

生産計画担当者は、特定品目を生産するための材料と能力要件を計算します。 調達提案が作成された後、計画している注文を検索し、注文を確定し、緊急を要する注文から始めます。 最も緊急な注文とは、現在の日付で確定される必要があるものです。 デモ データの会社 USMF を使用して、これらのタスクを実行します。


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a>品目の材料および能力計画を作成します
1. [マスター プラン] をクリックします。
    * 既定のダッシュボードに移動する必要があります。  
2. [実行] をクリックします。
3. [対象に含めるレコード] セクションを展開します。
4. [フィルター] をクリックします。
5. 一覧で、選択された行をマークします。
6. [基準] フィールドに値を入力します。
    * 例: D0001  
7. [OK] をクリックします。
8. [OK] をクリックします。
    * これには数分かかる場合があります。  
9. ページを更新します。

## <a name="identify-the-urgent-planned-orders-for-the-item"></a>品目の緊急計画注文を識別します
1. [品目番号列] フィルターを開きます。
2. [品目番号] フィールドで "次の値で始まる" フィルター演算子を使用して、値 "D0001" でフィルターを適用します。
3. [注文の日付列フィルター] を開きます。
4. [次の値と完全に一致する] フィルタ演算子を使用して、[注文日付] フィールドに値「現在の日付」でフィルターを適用します。

## <a name="firm-all-the-urgent-orders-for-the-item"></a>品目のすべての緊急注文を確定します
1. 一覧で、すべての行のマークを設定または解除します。
2. [確定] をクリックします。
3. [OK] をクリックします。

