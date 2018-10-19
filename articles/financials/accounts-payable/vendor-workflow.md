---
title: "仕入先ワークフロー"
description: "仕入先情報を変更し、それを承認するワークフローを使用します。"
author: mikefalkner
manager: annbe
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: Vendor
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 950a1852acf9f3e4747ce2d55738c0eb3a646897
ms.contentlocale: ja-jp
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-workflow"></a><span data-ttu-id="0fd03-103">仕入先ワークフロー</span><span class="sxs-lookup"><span data-stu-id="0fd03-103">Vendor workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0fd03-104">仕入先ワークフローを使用すると、特定のフィールドに加えた変更が、仕入先に追加される前に承認用ワークフローに送信されます。</span><span class="sxs-lookup"><span data-stu-id="0fd03-104">When the vendor workflow is used, changes that are made to specific fields are sent to the workflow for approval before they are added to the vendor.</span></span>

## <a name="set-up-the-vendor-workflow"></a><span data-ttu-id="0fd03-105">仕入先ワークフローの設定</span><span class="sxs-lookup"><span data-stu-id="0fd03-105">Set up the vendor workflow</span></span>

<span data-ttu-id="0fd03-106">ワークフロー機能を使用する前に、最初にこの機能を有効化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fd03-106">Before you can use the workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="0fd03-107">**買掛金勘定 \> 設定 \> 買掛金勘定パラメーター**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-107">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
2. <span data-ttu-id="0fd03-108">**一般**タブの**仕入先承認**クイック タブで、**仕入先承認の有効化**オプションを**はい**に設定します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-108">On the **General** tab, on the **Vendor approval** FastTab, set the **Enable vendor approvals** option to **Yes**.</span></span>
3. <span data-ttu-id="0fd03-109">**データ エンティティの動作**フィールドで、データのインポート時に使用する必要がある動作を選択します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-109">In the **Data entity behavior** field, select the behavior that should be used when data is imported:</span></span>

    - <span data-ttu-id="0fd03-110">**承認なしの変更を許可する** – データ エンティティは、ワークフローでの処理なしで仕入先レコードを更新できます。</span><span class="sxs-lookup"><span data-stu-id="0fd03-110">**Allow changes without approval** – The data entity can update the vendor record without processing it through the workflow.</span></span>
    - <span data-ttu-id="0fd03-111">**変更内容を拒否する** – 仕入先レコードに変更を加えることはできません。</span><span class="sxs-lookup"><span data-stu-id="0fd03-111">**Reject changes** – Changes can't be made to the vendor record.</span></span> <span data-ttu-id="0fd03-112">ワークフローに対して有効なフィールドのインポートは失敗します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-112">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="0fd03-113">**変更提案を作成する** – ワークフローに対して有効なフィールドを除くすべてのフィールドが変更されます。</span><span class="sxs-lookup"><span data-stu-id="0fd03-113">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="0fd03-114">提案された変更として、これらのフィールドに対する新しい値が仕入先に追加され、ワークフローが自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-114">The new values for those fields will be added to the vendor as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="0fd03-115">仕入先フィールドの一覧で、変更が加えられる前に承認される必要がある各フィールドの**有効化**チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0fd03-115">In the list of vendor fields, select the **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="0fd03-116">**買掛金勘定 \> 設定 \> 買掛金勘定ワークフロー**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-116">Go to **Accounts payable \> Setup \> Accounts payable workflows**.</span></span>
6. <span data-ttu-id="0fd03-117">**新規**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-117">Select **New**.</span></span>
7. <span data-ttu-id="0fd03-118">**仕入先に対する提案済み変更内容に関するワークフロー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-118">Select **Proposed vendor changes workflow**.</span></span> 
8. <span data-ttu-id="0fd03-119">承認プロセスに一致するように、ワークフローを設定します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-119">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="0fd03-120">**仕入先に対する提案済み変更内容に対するワークフロー承認**のワークフロー承認要素は、仕入先への変更を適用します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-120">The **Workflow approval for proposed vendor change** workflow approval element will apply the changes to the vendor.</span></span>

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="0fd03-121">仕入先情報の変更およびワークフローへの変更の送信</span><span class="sxs-lookup"><span data-stu-id="0fd03-121">Change vendor information and submit the changes to the workflow</span></span>

<span data-ttu-id="0fd03-122">ワークフローに対する有効なフィールドを変更する場合、**提案済み変更内容**ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fd03-122">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="0fd03-123">このページでは、フィールドの元の値および入力した新しい値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0fd03-123">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="0fd03-124">変更したフィールドは、元の値に戻されました。</span><span class="sxs-lookup"><span data-stu-id="0fd03-124">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="0fd03-125">ステータス メッセージは、変更が送信されていないことも通知します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-125">A status message also informs you that your changes haven't been submitted.</span></span> 

<span data-ttu-id="0fd03-126">ワークフローに対する有効なフィールドを変更するたびに、そのフィールドが**提案済み変更内容**ページの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="0fd03-126">Every time that you change a field that is enabled for the workflow, that field is added to the list on the **Proposed changes** page.</span></span> <span data-ttu-id="0fd03-127">フィールドの提案値を破棄するには、リスト内のフィールドの横にある**破棄**ボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-127">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="0fd03-128">すべての変更を破棄するには、ページの下部にある**すべての変更を破棄**ボタンを使用します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-128">To discard all changes, use the **Discard all changes** button at the bottom of the page.</span></span> <span data-ttu-id="0fd03-129">**OK** を選択してページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0fd03-129">Select **OK** to close the page.</span></span>

<span data-ttu-id="0fd03-130">少なくとも 1 つの提案済み変更内容があると、アクション ウィンドウ上に 2 つのタブが表示されます: **提案済み変更内容**および**ワークフロー**。</span><span class="sxs-lookup"><span data-stu-id="0fd03-130">After you have at least one proposed change, two additional tabs appear on the action pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="0fd03-131">**提案済み変更内容**を選択して**提案済み変更内容**ページを開き、変更内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-131">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="0fd03-132">**変更をワークフローに送信するためワークフロー \> 送信**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-132">Select **Workflow \> Submit to submit the changes to workflow**.</span></span>

    <span data-ttu-id="0fd03-133">ページのステータスが**変更内容が承認保留中です**に変更されます。</span><span class="sxs-lookup"><span data-stu-id="0fd03-133">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="0fd03-134">ワークフローは、Microsoft Dynamics 365 for Finance and Operations で標準のワークフロー プロセスに従います。</span><span class="sxs-lookup"><span data-stu-id="0fd03-134">The workflow follows the standard workflow process in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="0fd03-135">承認者が**仕入先**ページに転送されると、**提案済み変更内容**ページで変更を確認でき、**ワークフロー \> 承認**を選択してワークフローを承認します。</span><span class="sxs-lookup"><span data-stu-id="0fd03-135">The approver is directed to the **Vendor** page, where he or she can review the changes on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="0fd03-136">すべての承認が完了すると、フィールドが提案された値で更新されます。</span><span class="sxs-lookup"><span data-stu-id="0fd03-136">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>
