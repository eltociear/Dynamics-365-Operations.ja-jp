---
title: 小売顧客のギフト カードの残高を清算します。
description: このトピックでは、Microsoft Dynamics 365 Commerce で現在利用できる外部ギフト カード清算機能について説明します。
author: rapraj
manager: josaw1
ms.date: 02/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: IT Pro
ms.devlang: ''
ms.reviewer: rhaertle
ms.search.scope: Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: rapraj
ms.search.validFrom: 2019-10-02
ms.dyn365.ops.version: Dynamics 365 10.0
ms.openlocfilehash: d399b6e24a52ad0ebd2c28d583bb7c2413e698bd
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004581"
---
# <a name="cash-out-gift-card-balance-for-a-retail-customer"></a><span data-ttu-id="bbe5e-103">小売顧客のギフト カードの残高を清算します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-103">Cash out gift card balance for a retail customer</span></span>

<span data-ttu-id="bbe5e-104">このトピックは、Dynamics 365 Retail Modern POS (MPOS) のギフト カード清算機能の概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-104">This topic provides an overview of the cash out gift card feature for the Dynamics 365 Retail Modern POS (MPOS).</span></span> 

<span data-ttu-id="bbe5e-105">清算機能の目的は、レジ担当者がギフト カードにある残額の清算を許可することです。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-105">The purpose of the cash out feature is to allow cashiers to cash out the remaining amount on a gift card.</span></span> <span data-ttu-id="bbe5e-106">小売業者は顧客の要望により、ギフト カードにあるさほど多くない残高を交換する必要がよくあります。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-106">Retailers often need to exchange a low balance gift card for cash at the customer's request.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="bbe5e-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="bbe5e-107">Prerequisites</span></span>
- <span data-ttu-id="bbe5e-108">支払コネクタおよび対応する支払ゲートウェイまたはプロセッサは、機能をサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-108">The payment connector and corresponding payment gateway or processor must support the feature.</span></span> <span data-ttu-id="bbe5e-109">*支払コネクタ*は、Dynamics 365 Commerce (および関連コンポーネント) と支払サービスの間の通信を促進する拡張機能です。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-109">The *payment connector* is an extension which facilitates communication between Dynamics 365 Commerce (and associated components) and a payment service.</span></span> <span data-ttu-id="bbe5e-110">このトピックで説明されているコネクタは、標準支払 SDK を使用して実装されています。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-110">The connector described in this topic was implemented using the standard payments SDK.</span></span>
- <span data-ttu-id="bbe5e-111">ギフト カードが外部のギフト カードの場合は、バック オフィスと、POS の両方を外部のギフト カードにコンフィギュレーションする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-111">If the gift cards are external gift cards, the external gift card must be configured for both the Headquarters and the POS.</span></span> <span data-ttu-id="bbe5e-112">ギフト カードをコンフィギュレーションする前に、小売業者は外部のギフト カード サービス プロバイダーのアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-112">Before the gift card can be configured, the retailer must have an account with an external gift card service provider.</span></span>

## <a name="scenarios"></a><span data-ttu-id="bbe5e-113">シナリオ</span><span class="sxs-lookup"><span data-stu-id="bbe5e-113">Scenarios</span></span>
<span data-ttu-id="bbe5e-114">ギフト カード清算機能は、たとえば、ワシントン州では清算しきい値を $5 にする、といったシナリオに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-114">The cash out gift card feature is applicable to a scenario where, for example, in Washington state, the cash out threshold is $5.</span></span> <span data-ttu-id="bbe5e-115">この場合、小売業者には、ギフト カードを清算し、清算業務が有効となるギフト カード残高の限度額の操作を設定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-115">Retailers in this case will have the option to set up an operation to cash out a gift card and set the gift card balance limits under which the cash out operation can be enabled.</span></span>

## <a name="configure-headquarters"></a><span data-ttu-id="bbe5e-116">バックオフィスのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="bbe5e-116">Configure Headquarters</span></span>

1. <span data-ttu-id="bbe5e-117">**すべての店舗**ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-117">Open the **All stores** page.</span></span>
2. <span data-ttu-id="bbe5e-118">一覧で、**ヒューストン**の店舗を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-118">In the list, select the **Houston** store.</span></span>
3. <span data-ttu-id="bbe5e-119">**アクション ウィンドウ**で、**設定** &gt; **支払方法**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-119">On the **Action Pane**, select **Set up** &gt; **Payment methods**.</span></span>
4. <span data-ttu-id="bbe5e-120">**支払方法** を検索して **支払方法** ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-120">Search for **payment methods** to open the **Payment methods** page.</span></span>
5. <span data-ttu-id="bbe5e-121">**ギフト カード**支払方法を選択し、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-121">Select the **Gift Card** payment method, and then follow these steps:</span></span>

    1. <span data-ttu-id="bbe5e-122">**金額**クイック タブ セクションで、**ギフト カードを清算**フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-122">In the **Amount** FastTab section, select the **Cash Out Gift Card** field.</span></span>
    2. <span data-ttu-id="bbe5e-123">**ギフト カードを清算**フィールドに、**ギフト カード清算しきい値**の額を入力します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-123">In the **Cash Out Gift Card** field, enter the **Gift card Cash out threshold** amount.</span></span>
    3. <span data-ttu-id="bbe5e-124">**保存** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-124">Select **Save**.</span></span>

    ![ギフト カードのしきい値を設定](./media/GiftCardCashout01.png)

6. <span data-ttu-id="bbe5e-126">**ボタン グリッド**ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-126">Open the **Button grid** page.</span></span>
7. <span data-ttu-id="bbe5e-127">ページの左側にあるナビゲーション バーで、**F2S1M** を検索してフィルター処理オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-127">In the navigation bar on the left side of the page, search for **F2S1M**, and select the filtered option.</span></span>
8. <span data-ttu-id="bbe5e-128">**アクション ウィンドウ**で、**デザイナー**を選択し、ボタン デザイナー アプリケーションをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-128">On the **Action Pane**, select **Designer** to download the button designer application.</span></span>
9. <span data-ttu-id="bbe5e-129">グリッド デザイナーが表示されたら、空の (灰色) 領域を右クリックして、**新規作成ボタン** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-129">When the grid designer appears, right-click on an empty (gray) area, and then select **New button**.</span></span>

    ![新しいボタン](./media/07.png)

10. <span data-ttu-id="bbe5e-131">新しいボタンを右クリックし、**ボタン プロパティ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-131">Right-click the new button, and then select **Button properties**.</span></span>
11. <span data-ttu-id="bbe5e-132">次のマトリックスに従って**アクション**、**支払タイプ**、および**ボタンのテキスト**プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-132">Set the **Action**, **Cash out gift card**, and **Text on button** properties according to the following matrix.</span></span>

    | <span data-ttu-id="bbe5e-133">アクション</span><span class="sxs-lookup"><span data-stu-id="bbe5e-133">Action</span></span>            | <span data-ttu-id="bbe5e-134">支払タイプ</span><span class="sxs-lookup"><span data-stu-id="bbe5e-134">Payment type</span></span>       | <span data-ttu-id="bbe5e-135">ボタンのテキスト</span><span class="sxs-lookup"><span data-stu-id="bbe5e-135">Text on button</span></span>        |
    |-------------------|--------------------|-----------------------|
    |<span data-ttu-id="bbe5e-136">ギフト カードをキャッシュ アウトする</span><span class="sxs-lookup"><span data-stu-id="bbe5e-136">Cash out gift card</span></span> |     <span data-ttu-id="bbe5e-137">ギフト カード</span><span class="sxs-lookup"><span data-stu-id="bbe5e-137">Gift Card</span></span>      | <span data-ttu-id="bbe5e-138">ギフト カードをキャッシュ アウトする</span><span class="sxs-lookup"><span data-stu-id="bbe5e-138">Cash out gift card</span></span>    |

    <span data-ttu-id="bbe5e-139">完了したら、ボタンのレイアウトは次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-139">When you've finished, your button layout should resemble the following illustration.</span></span>

    ![完了したボタン レイアウト](./media/GiftCardCashout02.png)

12. <span data-ttu-id="bbe5e-141">**OK** をクリックし、デザイナーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-141">Click **Ok** and close the designer.</span></span>
13. <span data-ttu-id="bbe5e-142">**配送スケジュール**を検索します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-142">Search for **Distribution Schedule**.</span></span>
14. <span data-ttu-id="bbe5e-143">ページの左側にあるナビゲーション バーで、**1090**、**1115**、および **1070** を検索します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-143">In the navigation bar on the left side of the page, search for **1090**, **1115**, and **1070**.</span></span>
15. <span data-ttu-id="bbe5e-144">**アクション ウィンドウ**で、**今すぐ実行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-144">On the **Action Pane**, select **Run now**.</span></span>
16. <span data-ttu-id="bbe5e-145">**ダウンロード セッション**を検索してジョブのステータスを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-145">Check the status of the job by searching for **Download sessions**.</span></span>
17. <span data-ttu-id="bbe5e-146">すべてのジョブの横に **適用済** が表示されるまで待ってから、ブラウザーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-146">Wait until **Applied** appears next to all the jobs, and then close the browser.</span></span>


## <a name="configure-and-test-retail-modern-pos"></a><span data-ttu-id="bbe5e-147">Retail Modern POS のコンフィギュレーションとテスト</span><span class="sxs-lookup"><span data-stu-id="bbe5e-147">Configure and test Retail Modern POS</span></span>

1. <span data-ttu-id="bbe5e-148">Retail Modern POS の申請を開始</span><span class="sxs-lookup"><span data-stu-id="bbe5e-148">Start the Retail Modern POS (MPOS) application.</span></span>
2. <span data-ttu-id="bbe5e-149">標準の資格情報を使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-149">Sign in by using the standard credentials.</span></span>
3. <span data-ttu-id="bbe5e-150">メッセージが表示されたら、**ドロワー以外の操作の実行** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-150">When you're prompted, select **Perform a non-drawer operation**.</span></span>
4. <span data-ttu-id="bbe5e-151">メイン画面で、**ハードウェア ステーションの選択**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-151">On the main screen, select **Select hardware station**.</span></span>
5. <span data-ttu-id="bbe5e-152">ページの右側にあるバーで、**管理**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-152">On the bar on the right side of the page, select **Manage**.</span></span>
6. <span data-ttu-id="bbe5e-153">**仮想周辺機器** をオンにし、**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-153">Turn on **Virtual Peripherals**, and then select **OK**.</span></span>
7. <span data-ttu-id="bbe5e-154">**使用可能なペアリング済ステーション** フィールドで、**仮想周辺機器**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-154">In the **Available paired stations** field, select **Virtual Peripherals**.</span></span>
8. <span data-ttu-id="bbe5e-155">新しいシフトを開くか、非ドロワー操作を実行するように求められます。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-155">You're prompted to either open a new shift or perform non-drawer operations.</span></span> <span data-ttu-id="bbe5e-156">新しいシフトを開くことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-156">You can now open a new shift.</span></span>
9. <span data-ttu-id="bbe5e-157">メイン画面で、**現在のトランザクション**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-157">On the main screen, select **Current transaction**.</span></span>
10. <span data-ttu-id="bbe5e-158">**ギフト カード** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-158">Select **Gift cards**.</span></span>
11. <span data-ttu-id="bbe5e-159">**ギフト カードの清算**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-159">Select **Cash out gift card**.</span></span>
12. <span data-ttu-id="bbe5e-160">ギフト番号を入力もしくはスキャンします。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-160">Enter or scan the gift number.</span></span>
13. <span data-ttu-id="bbe5e-161">**現在のトランザクション**に、清算用の**ギフト カードの清算**行が追加されます。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-161">The line for **gift card cash out** will be added to the **Current transaction** for cash out.</span></span>
14. <span data-ttu-id="bbe5e-162">**現金**支払メソッドを選択すると、トランザクションの完了時にドロワーが開きます。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-162">Select the **Cash** payment method and the drawer will open when the transaction is completed.</span></span> 

       ![完了したボタン レイアウト](./media/GiftCardCashout03.png)

## <a name="troubleshooting"></a><span data-ttu-id="bbe5e-164">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bbe5e-164">Troubleshooting</span></span> 

<span data-ttu-id="bbe5e-165">すべての一般的な問題については、Modern POS または IIS ハードウェア ステーション イベント ログを常に参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-165">For all general issues, you should always consult the Modern POS or IIS Hardware Station event logs.</span></span> <span data-ttu-id="bbe5e-166">ログは、Windows イベント ログの以下のノードにあります。</span><span class="sxs-lookup"><span data-stu-id="bbe5e-166">The logs can be found under these nodes in the Windows event log:</span></span>
  - <span data-ttu-id="bbe5e-167">**Application and Services Logs > Microsoft > Dynamics > Commerce-ModernPOS**</span><span class="sxs-lookup"><span data-stu-id="bbe5e-167">**Application and Services Logs > Microsoft > Dynamics > Commerce-ModernPOS**</span></span>
  - <span data-ttu-id="bbe5e-168">**Application and Services Logs > Microsoft > Dynamics > Commerce-Hardware Station**</span><span class="sxs-lookup"><span data-stu-id="bbe5e-168">**Application and Services Logs > Microsoft > Dynamics > Commerce-Hardware Station**</span></span>