---
title: メンテナンスの状態
description: このトピックでは、資産管理でメンテナンス ステータスを計算する方法について説明します。
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.openlocfilehash: 516607c056125a16e075c33f3c2ad069efb396d9
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918352"
---
# <a name="maintenance-status"></a><span data-ttu-id="5daab-103">メンテナンスの状態</span><span class="sxs-lookup"><span data-stu-id="5daab-103">Maintenance status</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="5daab-104">資産管理で計算を実行し、特定の期間の新しい、有効な、および完了済みのメンテナンス要求、保守要求、作業指示書、およびメンテナンス ダウンタイム活動に関する概要を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5daab-104">In Asset Management, you can make a calculation to see an overview of new, active, and completed maintenance requests, work orders, and maintenance downtime activities for a specific period.</span></span> <span data-ttu-id="5daab-105">また、同じ期間に完了した条件評価の数を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="5daab-105">You can also see the number of completed condition assessments for the same period.</span></span> <span data-ttu-id="5daab-106">この計算を使用して、受信および完了したメンテナンス要求および作業指示書に関するワークロードの概要を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="5daab-106">Use this calculation to get an overview of workload regarding incoming and completed maintenance requests and work orders.</span></span>

## <a name="make-a-maintenance-status-calculation"></a><span data-ttu-id="5daab-107">メンテナンス ステータスの計算の実行</span><span class="sxs-lookup"><span data-stu-id="5daab-107">Make a maintenance status calculation</span></span>

1. <span data-ttu-id="5daab-108">**資産管理** > **照会** > **メンテナンス ステータス**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5daab-108">Click **Asset management** > **Inquiries** > **Maintenance status**.</span></span>

2. <span data-ttu-id="5daab-109">**ステータスの計算** ダイアログ内の**開始日**および**終了日**フィールドで、計算を実行する期間を選択します。</span><span class="sxs-lookup"><span data-stu-id="5daab-109">In the **Calculate status** dialog, select the period for which you want to make the calculation in the **From date** and **To date** fields.</span></span>

3. <span data-ttu-id="5daab-110">**レベル** フィールドを使用すると、機能の場所に関するメンテナンス明細行の詳細度を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5daab-110">You can use the **Level** field to indicate how detailed you want the maintenance lines to be regarding functional locations.</span></span> <span data-ttu-id="5daab-111">たとえば、フィールドに「1」の番号を挿入し、複数レベルの機能的な場所構造がある場合、機能的な場所に対するすべてのメンテナンス明細行が最上位レベルに表示されます。したがって明細行のステータスは、下位レベルにある機能的な場所から追加される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5daab-111">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance lines for a functional location will be shown on the top level, and therefore the status on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="5daab-112">**レベル** フィールドに数値 "0" を挿入すると、関連するすべての機能的な場所レベルですべてメンテナンス明細行を示す、詳細な結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5daab-112">If you insert the number "0" in the **Level** field, you see a detailed result showing all maintenance lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="5daab-113">**OK** をクリックして、計算を開始します。</span><span class="sxs-lookup"><span data-stu-id="5daab-113">Click **OK** to start the calculation.</span></span>

5. <span data-ttu-id="5daab-114">**グループ化**アクション ウィンドウ グループで、関連するボタンをクリックすると、計算の必要な詳細レベルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5daab-114">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="5daab-115">選択したアクション ウィンドウ ボタンが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="5daab-115">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="5daab-116">ボタンをクリックして、有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="5daab-116">Click on a button to activate or deactivate it.</span></span>

6. <span data-ttu-id="5daab-117">**グループ化**ボタンを有効化または無効化するか、または新しい期間に対して計算を実行することにより変更を行うたびに**更新**ボタンをクリックし、計算を更新してください。</span><span class="sxs-lookup"><span data-stu-id="5daab-117">Remember to click the **Update** button to update the calculation each time you make changes by activating or deactivating **Group by...** buttons, or by making a calculation for a new period.</span></span>

7. <span data-ttu-id="5daab-118">新しいメンテナンス ステータスの計算を作成する場合、**ステータス**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5daab-118">Click **Status** if you want to create a new maintenance status calculation.</span></span>

>[!NOTE]
><span data-ttu-id="5daab-119">**メンテナンス ステータス**に表示される結果には、実際の開始日時があるメンテナンス要求および作業指示書のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5daab-119">The results shown in **Maintenance status** only include maintenance requests and work orders that have an actual start date and time.</span></span> <span data-ttu-id="5daab-120">終了日時は空白にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5daab-120">End date and time may be blank.</span></span>

<span data-ttu-id="5daab-121">*例 1:*</span><span class="sxs-lookup"><span data-stu-id="5daab-121">*Example 1:*</span></span>

<span data-ttu-id="5daab-122">次の図では、**年**および**月**ボタンが有効化されています。</span><span class="sxs-lookup"><span data-stu-id="5daab-122">In the figure below, the **Year** and **Month** buttons have been activated.</span></span> <span data-ttu-id="5daab-123">ここでは、メンテナンス要求と作業指示書に関連する月ごとのワークロードおよびスループットに関する一般的な概要を示します。</span><span class="sxs-lookup"><span data-stu-id="5daab-123">Here, you get a general overview on a monthly basis of workload and throughput related to maintenance requests and work orders.</span></span> 

![図 1](media/13-controlling-and-reporting.png)

<span data-ttu-id="5daab-125">*例 2:*</span><span class="sxs-lookup"><span data-stu-id="5daab-125">*Example 2:*</span></span>

<span data-ttu-id="5daab-126">次の図では、機能の場所に関する情報が追加されています。</span><span class="sxs-lookup"><span data-stu-id="5daab-126">In the figure below, information about functional locations has been added.</span></span> <span data-ttu-id="5daab-127">地理的な場所、工場、または作業領域を表す機能の場所間でワークロードおよびスループットを比較することができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5daab-127">Now, it is possible to compare workload and throughput across functional locations, which may represent geographical locations, factories, or work areas.</span></span> 

![図 2](media/14-controlling-and-reporting.png)
