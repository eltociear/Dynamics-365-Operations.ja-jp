---
title: 特定の日時のワーク オーダーのスケジュール設定
description: このトピックでは、資産管理で特定の日時にワーク オーダーのスケジュール設定をする方法について説明します。
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
ms.openlocfilehash: 0f818c4c3b669cc94e37cba1e3571c57b5c0dd1b
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887368"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a><span data-ttu-id="ee04d-103">特定の日時のワーク オーダーのスケジュール設定</span><span class="sxs-lookup"><span data-stu-id="ee04d-103">Schedule work order on specific date and time</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="ee04d-104">ワーク オーダーを特定の日*および*時間にスケジュール設定する必要がある場合は、資産管理の標準スケジューリング プロセスを上書きして、特定のスケジュールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ee04d-104">If a work order must be scheduled on a specific date *and* time, you can override the standard scheduling process in Asset Management and create a specific schedule for a work order.</span></span>

1. <span data-ttu-id="ee04d-105">**資産管理** > **共通** > **作業指示書** > **すべての作業指示書**または**有効な作業指示書**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee04d-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="ee04d-106">ワーク オーダーの一覧で、**ワーク オーダー**列のワーク オーダー ID をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee04d-106">In the work order list, click on the Work order ID in the **Work order** column.</span></span>

3. <span data-ttu-id="ee04d-107">**編集** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee04d-107">Click **Edit**.</span></span>

4. <span data-ttu-id="ee04d-108">**ワーク オーダー ヘッダー** クイック タブで、**予定開始**および**予定終了**フィールドに、開始日時と終了日時を挿入します。</span><span class="sxs-lookup"><span data-stu-id="ee04d-108">On the **Work order header** FastTab, insert start and end dates and times in the **Expected start** and **Expected end** fields.</span></span>

![図 1](media/05-work-order-scheduling.png)

5. <span data-ttu-id="ee04d-110">**全般**タブで、**スケジュール**をクリックして標準スケジュール プロセスを使用するか、特定の作業者にワーク オーダーをスケジュールする場合は、**派遣**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee04d-110">On the **General** tab, click **Schedule** to use the standard scheduling process, or click **Dispatch** if you want to schedule the work order to a specific worker.</span></span>

6. <span data-ttu-id="ee04d-111">既定の確保済能力を上書きして、ワーク オーダーが予定期間内にスケジュールされるようにするには、**ワーク オーダーのスケジュール設定**ダイアログ > **無限能力**セクションで下の図が示すように選択を行います。</span><span class="sxs-lookup"><span data-stu-id="ee04d-111">In order to override any existing capacity reservations to ensure that the work order is scheduled in the expected period, make the selections as shown in the figure below in the **Schedule work order** dialog > **Finite capacity** section.</span></span> <span data-ttu-id="ee04d-112">これは、予定された開始時刻にワーク オーダーを開始する必要があるため、スケジューリング プロセスは既存の確保済能力を無視することを意味します。</span><span class="sxs-lookup"><span data-stu-id="ee04d-112">This means that the scheduling process will ignore existing capacity reservations because the work order must start on the expected start time.</span></span>

![図 2](media/06-work-order-scheduling.png)

7. <span data-ttu-id="ee04d-114">**OK** をクリックしてスケジューリングを開始します。</span><span class="sxs-lookup"><span data-stu-id="ee04d-114">Click **OK** to start scheduling.</span></span>

8. <span data-ttu-id="ee04d-115">スケジューリング プロセスの結果、ダブル ブッキングが発生した場合は、画面にメッセージが表示され、関連するワーク オーダーを調整することができます。</span><span class="sxs-lookup"><span data-stu-id="ee04d-115">If the scheduling process results in double bookings, you will see a message on the screen, and you can adjust the related work orders.</span></span>

>[!NOTE]
><span data-ttu-id="ee04d-116">ワーク オーダーのメンテナンス作業者スケジューリングするには、そのメンテナンス作業者が予定されている開始日時に対応可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee04d-116">In order to schedule a maintenance worker for the work order, that maintenance worker must be available at the expected start date and time.</span></span> <span data-ttu-id="ee04d-117">作業者の使用可能性は、[作業者カレンダー](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md)で設定されます。</span><span class="sxs-lookup"><span data-stu-id="ee04d-117">Worker availability is set up in the [worker calendar](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span></span> 
