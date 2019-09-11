---
title: 作業指示の派遣
description: このトピックでは、資産管理で作業指示を派遣する方法について説明します。
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.openlocfilehash: 3b1621cf0f1e47d7bd5fe2fa0b41fbcd61f14def
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887208"
---
# <a name="dispatch-work-order"></a><span data-ttu-id="afc5a-103">作業指示の派遣</span><span class="sxs-lookup"><span data-stu-id="afc5a-103">Dispatch work order</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="afc5a-104">**派遣**機能を使用して、1 つの作業指示または作業指示ジョブを 1 人の作業者にスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="afc5a-104">You can schedule one work order or work order jobs to one worker using the **Dispatch** functionality.</span></span>

1. <span data-ttu-id="afc5a-105">**資産管理** > **共通** > **作業指示書** > **すべての作業指示書**または**有効な作業指示書**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="afc5a-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="afc5a-106">一覧で作業指示を選択します。</span><span class="sxs-lookup"><span data-stu-id="afc5a-106">Select the work order in the list.</span></span>

3. <span data-ttu-id="afc5a-107">**一般**タブで、**派遣**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="afc5a-107">On the **General** tab, click **Dispatch**.</span></span>

4. <span data-ttu-id="afc5a-108">**作業指示のスケジュール** ダイアログで、**作業者**フィールドの作業者を選択します。</span><span class="sxs-lookup"><span data-stu-id="afc5a-108">n the **Schedule work order** dialog, select the worker in the **Worker** field.</span></span>

5. <span data-ttu-id="afc5a-109">**スケジュール時間**フィールドでは、予定勤務時間と予測時間とが異なる場合に、予定勤務時間を挿入できます。</span><span class="sxs-lookup"><span data-stu-id="afc5a-109">In the **Schedule hours** field, you can insert expected work hours in case expected work hours differ from forecast hours.</span></span>

6. <span data-ttu-id="afc5a-110">**開始予定**フィールドでは、必要に応じて開始日時を編集できます。</span><span class="sxs-lookup"><span data-stu-id="afc5a-110">In the **Scheduled start** field, you can edit start date and time, if required.</span></span>

7. <span data-ttu-id="afc5a-111">スケジュール プロセスで、他のジョブで既にスケジュールされているリソースに関する能力制限を遵守する必要がある場合は、**資産**、**ツール**および**作業者**の各トグルボタンが "はい" に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="afc5a-111">If the scheduling process should observe capacity limitations regarding resources already scheduled on other jobs, make sure that the **Asset**, **Tool**, and **Worker** toggle buttons are set to "Yes".</span></span> <span data-ttu-id="afc5a-112">スケジューリング プロセスに関する詳細情報を表示するには、**詳細**トグル ボタンで "はい" を選択します。</span><span class="sxs-lookup"><span data-stu-id="afc5a-112">If you want to see detailed information about the scheduling process, select "Yes" on the **Verbose** toggle button.</span></span> <span data-ttu-id="afc5a-113">これは、作業指示について計算されたスコアに関する詳細情報が、情報ログに表示されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="afc5a-113">This means detailed information about the calculated scores on the work order is shown in the Infolog.</span></span>

8. <span data-ttu-id="afc5a-114">**スケジュールの無視**トグル ボタンで "はい" を選択して、カレンダーの休業日を無視します (資産、作業者、およびツールに適用)。</span><span class="sxs-lookup"><span data-stu-id="afc5a-114">Select "Yes" on the **Ignore schedule** toggle button to ignore closed days in the calendar (applies to asset, worker, and tools).</span></span> <span data-ttu-id="afc5a-115">**実行予定の無視**トグル ボタンで "はい" を選択すると、スケジューリングに関連する作業指示で選択された可能性のある制限を無視できます。</span><span class="sxs-lookup"><span data-stu-id="afc5a-115">Select "Yes" on the **Ignore scheduled execution** toggle button to ignore limitations that may have been selected on the work order regarding scheduling.</span></span> <span data-ttu-id="afc5a-116">実行予定の設定に関する情報については、[実行予定](../setup-for-work-orders/scheduled-execution.md) セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="afc5a-116">Refer to the [Scheduled execution](../setup-for-work-orders/scheduled-execution.md) section for information on the setup of scheduled execution.</span></span>

9. <span data-ttu-id="afc5a-117">**OK**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="afc5a-117">Click **OK**.</span></span> <span data-ttu-id="afc5a-118">作業指示書のライフサイクル状態は、**資産管理** > **設定** > **作業指示** > **ライフサイクル モデル**の順で指定された "スケジュール済" ライフサイクル状態に自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="afc5a-118">The work order lifecycle state is automatically updated to the "Scheduled" lifecycle state specified **Asset management** > **Setup** > **Work orders** > **Lifecycle models**.</span></span>

<span data-ttu-id="afc5a-119">次の図は、**作業指示のスケジュール** ダイアログでの派遣選択の例を示します。</span><span class="sxs-lookup"><span data-stu-id="afc5a-119">The figure below shows an example of dispatch selections in the **Schedule work order** dialog.</span></span>

![図 1](media/04-work-order-scheduling.png)

>[!NOTE]
><span data-ttu-id="afc5a-121">作業指示のスケジュールを削除する場合は、**すべての作業指示**で作業指示を選択し、**一般**タブの **スケジュールの削除**をクリックして実行します。スケジュールを削除した場合、作業指示ライフサイクル状態を手動で更新することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="afc5a-121">If you want to delete the schedule on a work order, this is done by selecting the work order in **All work orders** and clicking **Delete schedule** on the **General** tab. Remember to manually update the work order lifecycle state if you delete the schedule.</span></span>
