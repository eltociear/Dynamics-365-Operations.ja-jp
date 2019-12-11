---
title: 統合された税
description: このトピックでは、Finance and Operations と Common Data Service 間の税データの統合について説明します。
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b6be53e9a2065373ca37c2791568a8161823803f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772413"
---
## <a name="integrated-tax"></a><span data-ttu-id="6e204-103">統合された税</span><span class="sxs-lookup"><span data-stu-id="6e204-103">Integrated tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e204-104">税設定データでは、間接税 (VAT、GST、売上税) および源泉徴収税の両方の設定が定義されます。</span><span class="sxs-lookup"><span data-stu-id="6e204-104">Tax setup data defines the setup for both indirect taxes (VAT, GST, Sales tax) and withholding tax.</span></span> <span data-ttu-id="6e204-105">税金計算ルール、税率、税務会計、決済、およびその他の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e204-105">It describes the tax calculation rule, tax rate, tax accounting, settlement, and other concepts.</span></span>

## <a name="templates"></a><span data-ttu-id="6e204-106">テンプレート</span><span class="sxs-lookup"><span data-stu-id="6e204-106">Templates</span></span>

<span data-ttu-id="6e204-107">次の表に示すように、税データには、データ操作中に連携して動作するエンティティ マップのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e204-107">Tax data includes a collection of entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="6e204-108">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="6e204-108">Finance and Operations</span></span>   | <span data-ttu-id="6e204-109">Customer Engagement アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6e204-109">Customer Engagement application</span></span>
-------------------------|---------------------------------
<span data-ttu-id="6e204-110">税コード</span><span class="sxs-lookup"><span data-stu-id="6e204-110">Tax codes</span></span>                  | <span data-ttu-id="6e204-111">msdyn\_taxcodes.md</span><span class="sxs-lookup"><span data-stu-id="6e204-111">msdyn\_taxcodes.md</span></span>
<span data-ttu-id="6e204-112">税グループ</span><span class="sxs-lookup"><span data-stu-id="6e204-112">Tax groups</span></span>               | <span data-ttu-id="6e204-113">msdyn\_taxgroups.md</span><span class="sxs-lookup"><span data-stu-id="6e204-113">msdyn\_taxgroups.md</span></span>
<span data-ttu-id="6e204-114">税品目グループ</span><span class="sxs-lookup"><span data-stu-id="6e204-114">Tax item groups</span></span>          | <span data-ttu-id="6e204-115">msdyn\_taxitemgroups.md</span><span class="sxs-lookup"><span data-stu-id="6e204-115">msdyn\_taxitemgroups.md</span></span>
<span data-ttu-id="6e204-116">免税</span><span class="sxs-lookup"><span data-stu-id="6e204-116">Tax Exemptions</span></span>           | <span data-ttu-id="6e204-117">msdyn\_taxexemptcodes.md</span><span class="sxs-lookup"><span data-stu-id="6e204-117">msdyn\_taxexemptcodes.md</span></span>
<span data-ttu-id="6e204-118">税務当局</span><span class="sxs-lookup"><span data-stu-id="6e204-118">Tax Authorities</span></span>          | <span data-ttu-id="6e204-119">msdyn\_taxauthorities.md</span><span class="sxs-lookup"><span data-stu-id="6e204-119">msdyn\_taxauthorities.md</span></span>
<span data-ttu-id="6e204-120">源泉徴収税コード</span><span class="sxs-lookup"><span data-stu-id="6e204-120">Withholding tax codes</span></span>      | <span data-ttu-id="6e204-121">msdyn\_withholdingtaxcodes.md</span><span class="sxs-lookup"><span data-stu-id="6e204-121">msdyn\_withholdingtaxcodes.md</span></span>
<span data-ttu-id="6e204-122">源泉徴収税グループ</span><span class="sxs-lookup"><span data-stu-id="6e204-122">Withholding tax groups</span></span>   | <span data-ttu-id="6e204-123">msdyn\_withholdingtaxgroups.md</span><span class="sxs-lookup"><span data-stu-id="6e204-123">msdyn\_withholdingtaxgroups.md</span></span>
<span data-ttu-id="6e204-124">税勘定科目グループ</span><span class="sxs-lookup"><span data-stu-id="6e204-124">Tax Ledger Account Group</span></span> | <span data-ttu-id="6e204-125">msdyn\_taxpostinggroups</span><span class="sxs-lookup"><span data-stu-id="6e204-125">msdyn\_taxpostinggroups</span></span>  

[!include [banner](../includes/dual-write-symbols.md)]

[!include [Tax groups](dual-write/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax item groups](dual-write/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Exemptions](dual-write/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax Authorities](dual-write/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Withholding tax codes](dual-write/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](dual-write/WithholdingGroups-msdyn-withholdingtaxgroups.md)]

[!include [Tax Ledger Account Group](dual-write/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]
