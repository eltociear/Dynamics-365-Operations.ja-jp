---
title: プロセス ジョブのかんばんルールの変更
description: この手順は、使用されているかんばんルールの指定されたかんばんへの変更を対象としています。
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c036f6aad79e33df6009913d1e21ff6176f22593
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843796"
---
# <a name="change-kanban-rules-for-a-process-job"></a>プロセス ジョブのかんばんルールの変更

[!include [task guide banner](../../includes/task-guide-banner.md)]

この手順は、使用されているかんばんルールの指定されたかんばんへの変更を対象としています。 これは負荷リソースのレベルに、または故障の場合に便利です。 この手順の作成に使用するデモ データの会社は USMF です。 この手順は、リーン生産会社で働いていて、バリュー ストリームを担当するプランナーを対象としています。


## <a name="copy-kanban-rule"></a>かんばんルールのコピー
1. [かんばんルール] に移動します。
2. 一覧で、目的のレコードを見つけ、選択します。
    * L0001 のイベントかんばんルール 000022 を選択します。  
3. [かんばんルールの複製] をクリックします。
4. [OK] をクリックします。

## <a name="change-kanban-rule"></a>かんばんルールの変更
1. ページを閉じます。
2. [かんばん作業のスケジューリング] に移動する。
3. 一覧で、選択された行をマークします。
    * かんばん 000177 の明細行を選択します。  
4. [代替かんばんルールの使用] をクリックします。
5. [次へ] をクリックします。
6. [かんばんルール] フィールドで、値を入力または選択します。
    * 先に作成されたかんばんルールを選択します。 これは、最大数のかんばんルールです。  
7. [完了] をクリックします。
    * ここでは、かんばん作業は別のかんばんルールを使用します。 これは負荷の作業セルのレベルに有用です。  

