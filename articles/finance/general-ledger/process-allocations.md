---
title: 配賦の処理
description: この記事では、配賦、Microsoft Dynamics 365 Finance で配賦を処理するためのオプション、および予算計画でそれらを使用する方法についての情報を提供します。 配賦は、複数の勘定科目の組み合わせ全体で金額を配分するのに使用されます。 経費、または収益が正しい会計のオブジェクトに付けられることを保証します。
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32271e967da2e7f3702b0c6c2dcdba460aa1b382
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770623"
---
# <a name="process-allocations"></a>配賦の処理

[!include [banner](../includes/banner.md)]

この記事では、配賦、配賦を処理するためのオプション、および予算計画でそれらを使用する方法についての情報を提供します。 配賦は、複数の勘定科目の組み合わせ全体で金額を配分するのに使用されます。 経費、または収益が正しい会計のオブジェクトに付けられることを保証します。

このプロセスをサポートする機能は次のとおりです。

-   勘定配布で分割アクションを使用する、またはドキュメントに財務分析コードの既定のテンプレートを適用することにより、トランザクション金額を手動で割り当てます。 詳細については、[勘定配布](../accounts-payable/accounting-distributions.md) を参照してください。
-   個別の主勘定で定義された配賦条件に基づいてトランザクション金額を自動的に割り当てます。 配賦勘定項目は、勘定項目がソースの勘定科目に定義した条件を満たす場合に、割合と相手方の勘定科目に基づいて仕訳帳ごとに生成されます。
-   元帳配賦ルールに基づいて元帳残高または固定金額を自動的に割り当てます。 元帳配賦ルールは、配賦仕訳帳を使用して定期的に処理されます。 

###  <a name="allocations-in-budget-planning"></a>予算計画での配賦

元帳配賦ルールは、予算計画に使用できます。 予算計画で元帳配賦ルールを使用するとき、配賦ルールは元帳と同じ動作をしますが、データ ソースと相手方のデータは予算計画から取得されます。 手動で予算計画に使用する元帳配賦ルールを選択できます。 また、ワークフロー プロセスの一部として実行される配賦スケジュールを使用できます。

> [!NOTE]
> 会社間元帳配賦ルールは予算計画には使用できません。





