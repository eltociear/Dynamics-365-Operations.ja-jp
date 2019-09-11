---
title: 消費レポートの作成
description: このトピックでは、資産管理で消費レポートを作成する方法について説明します。
author: josaw1
manager: AnnBe
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3d978f8b991211e477dd8f766fe67432d9d493d0
ms.sourcegitcommit: c0b581e4c647b6c47bc14d1d7bfe267832afecba
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "1913096"
---
# <a name="create-consumption-reports"></a><span data-ttu-id="9f06e-103">消費レポートの作成</span><span class="sxs-lookup"><span data-stu-id="9f06e-103">Create consumption reports</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="9f06e-104">資産管理の作業指示書で消費登録を作成および転記すると、消費の詳細を表示する 2 つのレポートが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9f06e-104">When you've created and posted consumption registrations on work orders in Asset Management, two reports are available to display consumption details.</span></span>


## <a name="asset-consumption-report"></a><span data-ttu-id="9f06e-105">資産消費レポート</span><span class="sxs-lookup"><span data-stu-id="9f06e-105">Asset consumption report</span></span>

<span data-ttu-id="9f06e-106">作業指示書で消費を転記した場合、資産消費レポートを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="9f06e-106">When you have posted consumption on work orders, you can print an asset consumption report.</span></span> <span data-ttu-id="9f06e-107">このレポートには、時間、時間原価、品目原価、および資産に転記された経費が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f06e-107">The report displays hours, hour costs, item costs, and expenses posted on assets.</span></span>

1. <span data-ttu-id="9f06e-108">**資産管理** > **レポート** > **資産** > **資産消費**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f06e-108">Click **Asset management** > **Reports** > **Assets** > **Asset consumption**.</span></span>

2. <span data-ttu-id="9f06e-109">**資産消費**ダイアログでは、該当するトグル ボタンで "はい" を選択して表示するパラメータおよび詳細レベルを選択し、**表示**セクションで機能的な場所レベルを挿入します。</span><span class="sxs-lookup"><span data-stu-id="9f06e-109">In the **Asset consumption** dialog, select the parameters and detail level you want to see by selecting "Yes" on the relevant toggle buttons, and inserting a functional location level in the **Show** section.</span></span>
    - <span data-ttu-id="9f06e-110">**レベル** フィールドを使用すると、機能の場所に関する資産明細行の詳細度を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9f06e-110">You can use the **Levels** field to indicate how detailed you want the asset lines to be regarding functional locations.</span></span> <span data-ttu-id="9f06e-111">たとえば、フィールドに数値 "1" を挿入し、複数レベルの機能的な場所の構造がある場合、機能的な場所に対するすべての資産が最上位レベルに表示されます。そのため、明細行が下位レベルにある機能的な場所から追加されます。</span><span class="sxs-lookup"><span data-stu-id="9f06e-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all assets for a functional location will be shown on the top level, and therefore a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="9f06e-112">**レベル** フィールドに数値 "0" を挿入すると、関連するすべての機能の場所レベルのすべての資産を示す詳細結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f06e-112">If you insert the number "0" in the **Levels** field, you will see a detailed result showing all assets on all the functional location levels to which they are related.</span></span> 
    - <span data-ttu-id="9f06e-113">**すべての下位資産の合計**トグル ボタンで "はい" を選択すると、レポート内の各下位資産の合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f06e-113">Select "Yes" on the **Sum on all sub assets** toggle button to see sums for each sub asset in the report.</span></span>

3. <span data-ttu-id="9f06e-114">**日付**セクションで日付範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f06e-114">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="9f06e-115">**宛先**クイック タブで、レポートを画面に表示するか、印刷するか、またはファイルまたは電子メールとして保存するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9f06e-115">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="9f06e-116">必要に応じて、特定の資産を選択してレポートに表示できます。</span><span class="sxs-lookup"><span data-stu-id="9f06e-116">If required, you can select specific assets to be displayed in the report.</span></span> <span data-ttu-id="9f06e-117">**対象に含めるレコード** クイック タブで、**フィルター**をクリックし、レポートに含める資産を追加します。</span><span class="sxs-lookup"><span data-stu-id="9f06e-117">On the **Records to include** FastTab, click **Filter**, and add the assets you want to include in the report.</span></span>

6. <span data-ttu-id="9f06e-118">**OK** をクリックしてレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="9f06e-118">Click **OK** to generate the report.</span></span>


## <a name="work-order-consumption-report"></a><span data-ttu-id="9f06e-119">作業指示書の消費レポート</span><span class="sxs-lookup"><span data-stu-id="9f06e-119">Work order consumption report</span></span>

<span data-ttu-id="9f06e-120">作業指示書で消費を転記した場合、作業指示書の消費レポートを印刷できます。</span><span class="sxs-lookup"><span data-stu-id="9f06e-120">When you have posted consumption on work orders, you can print a work order consumption report.</span></span> <span data-ttu-id="9f06e-121">このレポートには、時間、時間原価、品目原価、および作業指示書に転記された経費が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f06e-121">The report displays hours, hour costs, item costs, and expenses posted on work orders.</span></span>

1. <span data-ttu-id="9f06e-122">**資産管理** > **レポート** > **作業指示書** > **作業指示書消費**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9f06e-122">Click **Asset management** > **Reports** > **Work orders** > **Work order consumption**.</span></span>

2. <span data-ttu-id="9f06e-123">**作業指示書消費**ダイアログで、**表示**セクションの該当するトグル ボタンで "はい" を選択することにより、レポートに含めるパラメーターを選択します。</span><span class="sxs-lookup"><span data-stu-id="9f06e-123">In the **Work order consumption** dialog, select the parameters you want to include in the report by selecting "Yes" on the relevant toggle buttons in the **Show** section.</span></span>

3. <span data-ttu-id="9f06e-124">**日付**セクションで日付範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="9f06e-124">Select a date interval in the **Dates** section.</span></span>

4. <span data-ttu-id="9f06e-125">**宛先**クイック タブで、レポートを画面に表示するか、印刷するか、またはファイルまたは電子メールとして保存するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="9f06e-125">On the **Destination** FastTab, select if you want to display the report on screen, print it, or save it as a file or email.</span></span>

5. <span data-ttu-id="9f06e-126">必要に応じて、特定の作業指示書を選択してレポートに表示できます。</span><span class="sxs-lookup"><span data-stu-id="9f06e-126">If required, you can select specific work orders to be displayed in the report.</span></span> <span data-ttu-id="9f06e-127">**対象に含めるレコード** クイック タブで、**フィルター**をクリックし、レポートに含める作業指示を追加します。</span><span class="sxs-lookup"><span data-stu-id="9f06e-127">On the **Records to include** FastTab, click **Filter**, and add the work orders you want to include in the report.</span></span>

6. <span data-ttu-id="9f06e-128">**OK** をクリックしてレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="9f06e-128">Click **OK** to generate the report.</span></span>


>[!NOTE]
><span data-ttu-id="9f06e-129">また、[作業指示書レポート](../work-orders/work-order-report.md) を生成することもできます。これにはより多くの作業指示の詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9f06e-129">You can also generate a [work order report](../work-orders/work-order-report.md), which contains more work order details.</span></span>
