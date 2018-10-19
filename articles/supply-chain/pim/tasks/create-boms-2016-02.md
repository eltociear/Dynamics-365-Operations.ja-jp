--- 
title: "BOM の作成 (2016 年 2 月)"
description: "このタスクでは、完成品と半完成品の部品表の構造の作成について説明します。"
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 6c5cfb8aae1a61d14f7a7969f688cb282530840d
ms.contentlocale: ja-jp
ms.lasthandoff: 10/16/2018

---
# <a name="create-boms-february-2016"></a><span data-ttu-id="5f108-103">BOM の作成 (2016 年 2 月)</span><span class="sxs-lookup"><span data-stu-id="5f108-103">Create BOMs (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5f108-104">このタスクでは、完成品と半完成品の部品表の構造の作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f108-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="5f108-105">これは、BOM 計算シリーズの 4 番目のタスクです。</span><span class="sxs-lookup"><span data-stu-id="5f108-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="5f108-106">このタスクの作成に使用するデモ データの会社は USMF です。</span><span class="sxs-lookup"><span data-stu-id="5f108-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="5f108-107">半完成品の BOM の作成</span><span class="sxs-lookup"><span data-stu-id="5f108-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="5f108-108">[製品情報管理] > [製品] > [リリースされた製品] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5f108-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="5f108-109">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5f108-110">品目番号 BOM_2 を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="5f108-111">アクション ペインで、[エンジニア] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="5f108-112">[BOM バージョン] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-112">Click BOM versions.</span></span>
5. <span data-ttu-id="5f108-113">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-113">Click New.</span></span>
6. <span data-ttu-id="5f108-114">[BOM と BOM バージョン] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="5f108-115">[名前] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="5f108-116">たとえば、[BOM_2] を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="5f108-117">[サイト] フィールドで値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5f108-118">たとえば、サイト 1 を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="5f108-119">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-119">Click OK.</span></span>
10. <span data-ttu-id="5f108-120">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-120">Click New.</span></span>
11. <span data-ttu-id="5f108-121">[品目番号] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="5f108-122">この例では、「ITEM_C」を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="5f108-123">[倉庫] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="5f108-124">たとえば、11 を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="5f108-125">[ヘッダー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-125">Click Header.</span></span>
14. <span data-ttu-id="5f108-126">[承認] をクリックして、部品表を承認します。</span><span class="sxs-lookup"><span data-stu-id="5f108-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="5f108-127">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-127">Click OK.</span></span>
16. <span data-ttu-id="5f108-128">[承認] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-128">Click Approve.</span></span>
    * <span data-ttu-id="5f108-129">[承認] ボタンは、[BOM バージョン] セクションのツールバーにあります。</span><span class="sxs-lookup"><span data-stu-id="5f108-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="5f108-130">表示されていない場合は、部品表のページの右上にあるヘッダーをクリックして、[承認] を表示します。</span><span class="sxs-lookup"><span data-stu-id="5f108-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="5f108-131">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-131">Click OK.</span></span>
18. <span data-ttu-id="5f108-132">[有効化] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-132">Click Activate.</span></span>
19. <span data-ttu-id="5f108-133">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5f108-133">Close the page.</span></span>
20. <span data-ttu-id="5f108-134">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5f108-134">Close the page.</span></span>
21. <span data-ttu-id="5f108-135">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5f108-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="5f108-136">完成品の BOM の作成</span><span class="sxs-lookup"><span data-stu-id="5f108-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="5f108-137">一覧で、選択された行のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="5f108-138">品目番号 BOM_1 を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="5f108-139">アクション ペインで、[エンジニア] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="5f108-140">[BOM バージョン] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-140">Click BOM versions.</span></span>
4. <span data-ttu-id="5f108-141">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-141">Click New.</span></span>
5. <span data-ttu-id="5f108-142">[BOM と BOM バージョン] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="5f108-143">[名前] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="5f108-144">たとえば、[BOM_1] を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="5f108-145">[サイト] フィールドで値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="5f108-146">たとえば、サイト 1 を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="5f108-147">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-147">Click OK.</span></span>
9. <span data-ttu-id="5f108-148">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-148">Click New.</span></span>
10. <span data-ttu-id="5f108-149">[品目番号] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="5f108-150">この例では、「ITEM_A」を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="5f108-151">[倉庫] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="5f108-152">この例では、「11」を選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="5f108-153">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-153">Click New.</span></span>
13. <span data-ttu-id="5f108-154">[品目番号] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="5f108-155">この例では、「ITEM_B」を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="5f108-156">[倉庫] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="5f108-157">たとえば、11 を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="5f108-158">[新規] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-158">Click New.</span></span>
16. <span data-ttu-id="5f108-159">[品目番号] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="5f108-160">この例では、「BOM_2」を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f108-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="5f108-161">一覧で、選択された行をマークします。</span><span class="sxs-lookup"><span data-stu-id="5f108-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="5f108-162">[倉庫] フィールドで、値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="5f108-163">この例では、倉庫 11 を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="5f108-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="5f108-164">[ヘッダー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-164">Click Header.</span></span>
20. <span data-ttu-id="5f108-165">[承認] をクリックして、部品表を承認します。</span><span class="sxs-lookup"><span data-stu-id="5f108-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="5f108-166">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-166">Click OK.</span></span>
22. <span data-ttu-id="5f108-167">[承認] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-167">Click Approve.</span></span>
    * <span data-ttu-id="5f108-168">[承認] ボタンは、[BOM バージョン] セクションのツールバーにあります。</span><span class="sxs-lookup"><span data-stu-id="5f108-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="5f108-169">表示されていない場合は、部品表のページの右上にあるヘッダーをクリックして、[承認] を表示します。</span><span class="sxs-lookup"><span data-stu-id="5f108-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="5f108-170">[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-170">Click OK.</span></span>
24. <span data-ttu-id="5f108-171">[有効化] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5f108-171">Click Activate.</span></span>
25. <span data-ttu-id="5f108-172">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5f108-172">Close the page.</span></span>
26. <span data-ttu-id="5f108-173">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5f108-173">Close the page.</span></span>
27. <span data-ttu-id="5f108-174">ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="5f108-174">Close the page.</span></span>

