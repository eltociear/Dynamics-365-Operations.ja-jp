---
title: 販売注文の収益認識
description: このトピックでは、販売注文と請求書の収益を認識するための基本的な機能について説明します。 収益認識は、販売注文と、販売注文から作成された対応する請求書で使用できます。
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: f0a5e4c01b34b2adb8e7e0af967af2c2562b4d87
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176000"
---
# <a name="revenue-recognition-on-sales-orders"></a><span data-ttu-id="5f325-104">販売注文の収益認識</span><span class="sxs-lookup"><span data-stu-id="5f325-104">Revenue recognition on sales orders</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!NOTE]
> <span data-ttu-id="5f325-105">収益認識機能は、機能管理を使用して有効にすることはまだできません。</span><span class="sxs-lookup"><span data-stu-id="5f325-105">The Revenue recognition feature can't yet be turned on through Feature management.</span></span> <span data-ttu-id="5f325-106">現時点では、コンフィギュレーション キーを使用して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f325-106">Currently, you must use configuration keys to turn it on.</span></span>

<span data-ttu-id="5f325-107">このトピックでは、販売注文と請求書の収益を認識するための基本的な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="5f325-107">This topic describes the basic functionality for recognizing revenue on sales orders and invoices.</span></span> <span data-ttu-id="5f325-108">収益認識は、販売注文と、販売注文から作成された対応する請求書で使用できます。</span><span class="sxs-lookup"><span data-stu-id="5f325-108">Revenue recognition is available on a sales order and on the corresponding invoice that is created from the sales order.</span></span> <span data-ttu-id="5f325-109">時間/実費払プロジェクトを使用して販売注文を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f325-109">The sales order can also be created through a Time and materials project.</span></span>

> [!NOTE]
> <span data-ttu-id="5f325-110">このトピックの図では、列が非表示になっているか、グリッドに追加されており、概念をより詳しく示しています。</span><span class="sxs-lookup"><span data-stu-id="5f325-110">In the illustrations in this topic, columns have been hidden or added to grids to better show the concepts.</span></span> <span data-ttu-id="5f325-111">したがって、図中のページとデータが、製品に表示されるものと異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f325-111">Therefore, the pages and data in the illustrations might differ from what you see in the product.</span></span>

## <a name="enter-a-sales-order"></a><span data-ttu-id="5f325-112">販売注文の入力</span><span class="sxs-lookup"><span data-stu-id="5f325-112">Enter a sales order</span></span>

<span data-ttu-id="5f325-113">次の販売注文が入力され、収益認識のために設定された 3 つの品目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5f325-113">The following sales order is entered and includes three items that are set up for revenue recognition.</span></span>

<span data-ttu-id="5f325-114">[![販売注文の入力](./media/revenue-recognition-so-basic-sales-order-header.png)](./media/revenue-recognition-so-basic-sales-order-header.png)</span><span class="sxs-lookup"><span data-stu-id="5f325-114">[![Enter a sales order](./media/revenue-recognition-so-basic-sales-order-header.png)](./media/revenue-recognition-so-basic-sales-order-header.png)</span></span>

<span data-ttu-id="5f325-115">収益認識の 2 つの概念を次に示します。</span><span class="sxs-lookup"><span data-stu-id="5f325-115">There are two concepts for revenue recognition:</span></span>

- <span data-ttu-id="5f325-116">**収益価格を決定します。**</span><span class="sxs-lookup"><span data-stu-id="5f325-116">**Determine the revenue price.**</span></span> <span data-ttu-id="5f325-117">収益価格は、リリースされた製品の設定に基づいて計算されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-117">The revenue price is calculated based on the setup of the released products.</span></span> <span data-ttu-id="5f325-118">収益価格は顧客に表示されませんが、販売注文請求書の会計にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-118">The revenue price is never shown to the customer but is used only for the accounting of the sales order invoice.</span></span> <span data-ttu-id="5f325-119">販売の一部として印刷される販売注文明細行および伝票は、引き続き単位/定価を表示します。</span><span class="sxs-lookup"><span data-stu-id="5f325-119">The sales order lines and the documents that are printed as part of the sale continue to show the unit/list price.</span></span>
- <span data-ttu-id="5f325-120">**収益認識がいつ発生するかを決定します。**</span><span class="sxs-lookup"><span data-stu-id="5f325-120">**Determine when revenue recognition should occur.**</span></span> <span data-ttu-id="5f325-121">収益スケジュールは、収益をどのように認識するかを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-121">A revenue schedule is used to determine when revenue should be recognized.</span></span>

    <span data-ttu-id="5f325-122">この例では、最初の品目 S0001 が **1O** (1回限り) の収益スケジュールに割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="5f325-122">In this example, the first item, S0001, is assigned to a **1O** (one-occurrence) revenue schedule.</span></span> <span data-ttu-id="5f325-123">この明細行は、将来インストールが行われた後に収益が認識されるマイルストーン タイプのシナリオを表します。</span><span class="sxs-lookup"><span data-stu-id="5f325-123">This line represents a milestone-type scenario, where the revenue will be recognized after the installation occurs in the future.</span></span> <span data-ttu-id="5f325-124">したがって、収益はインストールが完了するまで延期されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-124">Therefore, revenue will be deferred until the installation is completed.</span></span>

    <span data-ttu-id="5f325-125">2 番目の項目である S0008 は、契約の事後サポート (PCS) 品目として設定されたサービス品目です。</span><span class="sxs-lookup"><span data-stu-id="5f325-125">The second item, S0008, is a service item that is set up as a post contract support (PCS) item.</span></span> <span data-ttu-id="5f325-126">継続的なエンジニアリング サービスは、12 か月間にわたって顧客に提供されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-126">The sustained engineering services are provided to the customer over a 12-month period.</span></span> <span data-ttu-id="5f325-127">したがって、既定では、**12M** の収益スケジュールが製品に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5f325-127">Therefore, a **12M** revenue schedule is assigned to the product by default.</span></span> <span data-ttu-id="5f325-128">この品目は PCS 品目なので、契約の開始日と終了日を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f325-128">Because this item is a PCS item, contract start and end dates must be defined.</span></span> <span data-ttu-id="5f325-129">既定では、契約の開始日と終了日は品目の詳細の設定タブにあります。収益スケジュールでは、**12M** の設定が定義されており、次の図に示すように契約条件が自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-129">By default, the contract start and end dates are found on Item details – Setup tab. On the revenue schedule, the setup for **12M** is defined so that the contract terms are automatically filled in as shown in the following illustration.</span></span>

    <span data-ttu-id="5f325-130">[![収益スケジュール](./media/revenue-recognition-so-basic-revenue-schedules.png)](./media/revenue-recognition-so-basic-revenue-schedules.png)</span><span class="sxs-lookup"><span data-stu-id="5f325-130">[![Revenue schedules](./media/revenue-recognition-so-basic-revenue-schedules.png)](./media/revenue-recognition-so-basic-revenue-schedules.png)</span></span>

    <span data-ttu-id="5f325-131">3 番目の項目である S0012 はハードウェアであり、既定では収益スケジュールが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="5f325-131">The third item, S0012, is hardware, and no revenue schedule is assigned by default.</span></span> <span data-ttu-id="5f325-132">ハードウェアの収益は、品目が請求されるとすぐに認識されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-132">The revenue for the hardware is recognized as soon as the item is invoiced.</span></span>

## <a name="confirm-the-sales-order"></a><span data-ttu-id="5f325-133">販売注文の確認</span><span class="sxs-lookup"><span data-stu-id="5f325-133">Confirm the sales order</span></span>

<span data-ttu-id="5f325-134">収益価格と収益スケジュールに関する追加情報を表示するには、販売注文のアクション ペインの**管理**タブにある**収益認識**グループのボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="5f325-134">To view additional details about the revenue price and revenue schedule, use the buttons in the **Revenue recognition** group on the **Manage** tab on the Action Pane of the sales order.</span></span> <span data-ttu-id="5f325-135">この時点では販売注文が確定されていないため、収益認識に使用されるボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5f325-135">Because the sales order isn't confirmed at this point, the buttons that are used for revenue recognition are unavailable.</span></span> <span data-ttu-id="5f325-136">これらのボタンは、販売注文がフルフィルメントを実行するステージを通じて進行するため、使用可能または使用不可になります。</span><span class="sxs-lookup"><span data-stu-id="5f325-136">These buttons become available or unavailable as the sales order progresses through the stages that lead to fulfillment.</span></span>

<span data-ttu-id="5f325-137">[![販売注文ヘッダー](./media/revenue-recognition-so-basic-sales-order-header-02.png)](./media/revenue-recognition-so-basic-sales-order-header-02.png)</span><span class="sxs-lookup"><span data-stu-id="5f325-137">[![Sales order header](./media/revenue-recognition-so-basic-sales-order-header-02.png)](./media/revenue-recognition-so-basic-sales-order-header-02.png)</span></span>

<span data-ttu-id="5f325-138">最初の 3 つのボタンを使用して、収益認識の設定での品目の収益価格の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="5f325-138">The first three buttons provide details about the revenue price for the items on the sales order setup for revenue recognition.</span></span>

- <span data-ttu-id="5f325-139">**収益価格の配賦** - このボタンは、販売注文が確認された後または請求書が転記された後に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5f325-139">**Revenue price allocation** – This button becomes available after the sales order is confirmed or the invoice is posted.</span></span> <span data-ttu-id="5f325-140">販売注文の確認および請求書の転記の両方で、収益を計算して、勘定項目で認識または繰延される価格を認識する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f325-140">Both sales order confirmation and invoice posting calculate the revenue to recognize the price that will be recognized or deferred on the accounting entry.</span></span> <span data-ttu-id="5f325-141">設定によっては、計算される収益価格が顧客に表示される単価と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f325-141">Depending on the setup, the revenue price that is calculated can differ from the unit price that is shown to the customer.</span></span>
- <span data-ttu-id="5f325-142">**新しい注文明細行で価格を再配賦** - このボタンは、販売注文が確認された後または請求書が転記された後に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5f325-142">**Reallocate price with new order lines** – This button becomes available after the sales order is confirmed or the invoice is posted.</span></span> <span data-ttu-id="5f325-143">再配賦プロセスは、現在の販売注文、請求後、または新しい販売注文に新しい明細行を追加した後に認識される必要がある収益を再計算するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-143">The reallocation process is used to recalculate the revenue that must be recognized after a new line is added either to the current sales order, after it's invoiced, or to a new sales order.</span></span> <span data-ttu-id="5f325-144">どちらの場合も、新しい品目を追加すると契約が変更されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-144">In both scenarios, the addition of a new item causes a change to the contract.</span></span> <span data-ttu-id="5f325-145">したがって、収益価格を再配賦する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f325-145">Therefore, the revenue price must be reallocated.</span></span>
- <span data-ttu-id="5f325-146">**収益価格配賦の更新** - このボタンは、販売注文が確定した後で使用できますが、販売注文が請求された後は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5f325-146">**Update revenue price allocation** – This button becomes available after the sales order is confirmed, but it becomes unavailable after the sales order is invoiced.</span></span> <span data-ttu-id="5f325-147">この更新は、販売注文を確認することなく収益価格配賦を再実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-147">The update is used to rerun the revenue price allocation without having to confirm the sales order.</span></span> <span data-ttu-id="5f325-148">販売注文が請求された後、収益価格を再計算することはできません。</span><span class="sxs-lookup"><span data-stu-id="5f325-148">After the sales order is invoiced, the revenue price can't be recalculated.</span></span>

<span data-ttu-id="5f325-149">最後の 2 つのボタンを使用すると、収益スケジュールを持つ販売注文の品目の収益スケジュールに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-149">The last two buttons provide details about the revenue schedule for those items on the sales order that have a revenue schedule.</span></span>

- <span data-ttu-id="5f325-150">**予定収益認識スケジュール** - このボタンは、販売注文が確定した後で使用できますが、販売注文が請求された後は使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5f325-150">**Expected revenue recognition schedule** – This button becomes available after the sales order is confirmed, but it becomes unavailable after the sales order is invoiced.</span></span> <span data-ttu-id="5f325-151">予定収益スケジュールを示すページが開きます。</span><span class="sxs-lookup"><span data-stu-id="5f325-151">It opens a page that shows the expected revenue schedule.</span></span> <span data-ttu-id="5f325-152">最終スケジュールは、指定された出荷日を使用するのに対し、最終スケジュールでは実際の出荷日を使用するため、最終スケジュールは変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5f325-152">The final schedule might change, because the expected schedule uses the requested ship date, whereas the final schedule uses the actual ship date.</span></span>
- <span data-ttu-id="5f325-153">**収益認識のスケジュール** - このボタンは、販売注文が請求された後に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5f325-153">**Revenue recognition schedule** – This button becomes available after the sales order is invoiced.</span></span> <span data-ttu-id="5f325-154">確認が行われるとき、または梱包明細が作成されるときは、最終の収益認識のスケジュールは作成されません。</span><span class="sxs-lookup"><span data-stu-id="5f325-154">The final revenue recognition schedule isn't created when confirmation occurs or a packing slip is created.</span></span> <span data-ttu-id="5f325-155">販売注文が請求された場合にのみ作成されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-155">It's created only when the sales order is invoiced.</span></span>

<span data-ttu-id="5f325-156">次の例では、販売注文が確認されたときに収益価格配賦が発生しています。</span><span class="sxs-lookup"><span data-stu-id="5f325-156">In the following example, revenue price allocation occurred when the sales order was confirmed.</span></span> <span data-ttu-id="5f325-157">収益価格の配賦が異なる場合でも、**認識する収益**フィールドの合計金額は、顧客に請求される販売注文明細行の合計と同じである必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5f325-157">Note that, even though the revenue prices are allocated differently, the total amount in the **Revenue to recognize** field must still equal the sum of the sales order lines that are invoiced to the customer.</span></span> <span data-ttu-id="5f325-158">たとえば、税を除く販売注文明細行の合計は、1,499 ドルになります。</span><span class="sxs-lookup"><span data-stu-id="5f325-158">For example, the sum of the sales order lines, excluding tax, is $,1499.</span></span> <span data-ttu-id="5f325-159">したがって、**認識する収益**の合計も 1,499 ドルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f325-159">Therefore, the sum of the **Revenue to recognize** values must also be $,1499.</span></span>

<span data-ttu-id="5f325-160">[![収益価格の配賦](./media/revenue-recognition-so-basic-revenue-price-allocation.png)](./media/revenue-recognition-so-basic-revenue-price-allocation.png)</span><span class="sxs-lookup"><span data-stu-id="5f325-160">[![Revenue price allocation](./media/revenue-recognition-so-basic-revenue-price-allocation.png)](./media/revenue-recognition-so-basic-revenue-price-allocation.png)</span></span>

<span data-ttu-id="5f325-161">予定の収益認識スケジュールも作成されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-161">The expected revenue recognition schedule is also created.</span></span> <span data-ttu-id="5f325-162">収益のスケジュールでは、**認識する収益**の値を繰り延べる金額として認識します。</span><span class="sxs-lookup"><span data-stu-id="5f325-162">The revenue schedule uses the **Revenue to recognize** value as the amount to defer.</span></span> <span data-ttu-id="5f325-163">品目 S0001 は 300 ドルではなく 321.21 ドルに繰り延べられ、品目 S0008 は 100 ドルではなく 160.61 ドルに繰り延べられます。</span><span class="sxs-lookup"><span data-stu-id="5f325-163">Item S0001 defers $321.21 instead of $300, and item S0008 defers $160.61 instead of $100.</span></span> <span data-ttu-id="5f325-164">収益が繰り延べられていないため、品目 S0012 は予定スケジュールには表示されません。</span><span class="sxs-lookup"><span data-stu-id="5f325-164">Item S0012 isn't shown in the expected schedule because the revenue isn't deferred.</span></span> <span data-ttu-id="5f325-165">転記が発生すると、品目 S0012 は収益勘定科目に直接 1,017.18 ドルで転記されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-165">When posting occurs, item S0012 posts $1,017.18 directly to the revenue ledger account.</span></span>

<span data-ttu-id="5f325-166">[![予定収益認識スケジュール](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)</span><span class="sxs-lookup"><span data-stu-id="5f325-166">[![Expected revenue recognition schedule](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)</span></span>

## <a name="create-the-packing-slip"></a><span data-ttu-id="5f325-167">梱包明細の作成</span><span class="sxs-lookup"><span data-stu-id="5f325-167">Create the packing slip</span></span>

<span data-ttu-id="5f325-168">次に、販売注文に対して梱包明細を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5f325-168">Next, the packing slip can be created for the sales order.</span></span> <span data-ttu-id="5f325-169">梱包明細の転記時に収益は認識されません。</span><span class="sxs-lookup"><span data-stu-id="5f325-169">No revenue is recognized when the packing slip is posted.</span></span> <span data-ttu-id="5f325-170">販売注文が確認されなかった場合、梱包明細を転記しても収益価格計算は行われません。</span><span class="sxs-lookup"><span data-stu-id="5f325-170">If the sales order wasn't confirmed, posting of the packing slip doesn't trigger revenue price calculation.</span></span> <span data-ttu-id="5f325-171">また、予定収益認識スケジュールまたは最終収益認識スケジュールの作成もトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="5f325-171">It also doesn't trigger creation of the expected or final revenue recognition schedule.</span></span> <span data-ttu-id="5f325-172">梱包明細に対する収益を繰り延べるように品目のモデル グループが設定されている場合は、請求書の転記で使用される新しい繰延収益勘定ではなく、現在の転記プロファイルの勘定科目を使用して転記が続行されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-172">If the item model group is set up to defer revenue on the packing slip, it will continue to post by using the current posting profile ledger accounts, not the new deferred revenue accounts that are used on the invoice posting.</span></span>

## <a name="create-the-invoice"></a><span data-ttu-id="5f325-173">請求書の作成</span><span class="sxs-lookup"><span data-stu-id="5f325-173">Create the invoice</span></span>

<span data-ttu-id="5f325-174">最後の手順は、販売注文の請求です。</span><span class="sxs-lookup"><span data-stu-id="5f325-174">The final step is to invoice the sales order.</span></span> <span data-ttu-id="5f325-175">請求書の伝票を確認すると、品目 S0001 と S0008 の収益が繰延 (321.21 + 160.61 = 481.82 ドル) になり、品目 S0012 の残余金額が収益 (1017.18) に転記されたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="5f325-175">If you look at the invoice's voucher, you will notice that the revenue for items S0001 and S0008 was deferred ($321.21 + 160.61 = 481.82), and the remaining amount for item S0012 was posted to revenue (1,017.18).</span></span> <span data-ttu-id="5f325-176">これらの値は、販売注文明細行の合計に一致する 1,499 ドルに加算されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-176">These values add up to $1,499, which matches the sum of the sales order lines.</span></span>

<span data-ttu-id="5f325-177">[![伝票トランザクション](./media/revenue-recognition-so-voucher-transactions.png)](./media/revenue-recognition-so-voucher-transactions.png)</span><span class="sxs-lookup"><span data-stu-id="5f325-177">[![Voucher transactions](./media/revenue-recognition-so-voucher-transactions.png)](./media/revenue-recognition-so-voucher-transactions.png)</span></span>

<span data-ttu-id="5f325-178">請求書が作成された後、収益認識のための**収益価格配賦**、**新しい注文明細行への価格再配賦**、および**収益認識スケジュール**ボタンが使用できるようになりますが、**収益価格配賦の更新**および**予定収益認識スケジュール**ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5f325-178">After the invoice is created, the **Revenue price allocation**, **Reallocate price with new order lines**, and **Revenue recognition schedule** buttons for revenue recognition become available, but the **Update revenue price allocation** and **Expected revenue recognition schedule** buttons are unavailable.</span></span>

<span data-ttu-id="5f325-179">[![利用可能な収益認識ボタンの可用性](./media/revenue-recognition-so-basic-after-invoice-buttons.png)](./media/revenue-recognition-so-basic-after-invoice-buttons.png)</span><span class="sxs-lookup"><span data-stu-id="5f325-179">[![Available revenue recognition button availability](./media/revenue-recognition-so-basic-after-invoice-buttons.png)](./media/revenue-recognition-so-basic-after-invoice-buttons.png)</span></span>

<span data-ttu-id="5f325-180">**収益価格配賦**ボタンはまだ使用可能で、収益価格計算を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5f325-180">The **Revenue price allocation** button is still available so that you can view the revenue price calculation.</span></span> <span data-ttu-id="5f325-181">販売注文を確認後に何も変更しなかった場合は、請求書を転記しても、**認識する収益**フィールドで計算された金額は変更されません。</span><span class="sxs-lookup"><span data-stu-id="5f325-181">If nothing changed on the sales order after it was confirmed, posting of the invoice won't change the calculated amount in the **Revenue to recognize** field.</span></span>

<span data-ttu-id="5f325-182">予定収益認識スケジュールが削除され、最終収益認識スケジュールに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="5f325-182">The expected revenue recognition schedule is removed and replaced with the final revenue recognition schedule.</span></span> <span data-ttu-id="5f325-183">収益スケジュールの詳細は販売注文明細行ごとに管理され、契約上の責務が満たされたときに、繰延収益を実際の収益にリリースするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5f325-183">The revenue schedule details are maintained for each sales order line and are used to release the deferred revenue to actual revenue as the contractual obligations are met.</span></span>

<span data-ttu-id="5f325-184">[![最終収益認識スケジュール](./media/revenue-recognition-so-revenue-recognition-schedule.png)](./media/revenue-recognition-so-revenue-recognition-schedule.png)</span><span class="sxs-lookup"><span data-stu-id="5f325-184">[![Final revenue recognition schedule](./media/revenue-recognition-so-revenue-recognition-schedule.png)](./media/revenue-recognition-so-revenue-recognition-schedule.png)</span></span>