---
title: 資産と作業指示書
description: このトピックでは、資産管理の資産と作業指示書について説明します。
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd55988578be2b0287b399549f17642bfb1693b
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783400"
---
# <a name="assets-and-work-orders"></a><span data-ttu-id="e1968-103">資産と作業指示書</span><span class="sxs-lookup"><span data-stu-id="e1968-103">Assets and work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="e1968-104">このトピックでは、資産管理の資産と作業指示書について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1968-104">This topic describes assets and work orders in Asset Management.</span></span> <span data-ttu-id="e1968-105">資産と作業指示書は、資産管理の中心的な部分です。</span><span class="sxs-lookup"><span data-stu-id="e1968-105">Assets and work orders are the central parts of Asset Management.</span></span> <span data-ttu-id="e1968-106">*資産*は、継続的なメンテナンスとサービスを必要とする機械または機械部品です。</span><span class="sxs-lookup"><span data-stu-id="e1968-106">An *asset* is a machine or machine part that requires continuous maintenance and service.</span></span> <span data-ttu-id="e1968-107">資産は、階層構造で作成でき、機能の場所に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e1968-107">Assets can be created in a hierarchical structure, and they can be related to functional locations.</span></span> <span data-ttu-id="e1968-108">メンテナンス ジョブは、資産構造のすべてのレベルで計画できます。</span><span class="sxs-lookup"><span data-stu-id="e1968-108">Maintenance jobs can be planned at all levels in the asset structure.</span></span>

<span data-ttu-id="e1968-109">製品情報や資産仕様、必要なメンテナンス計画など、さまざまなデータが資産ごとに設定されます。</span><span class="sxs-lookup"><span data-stu-id="e1968-109">Various data, such as product information and asset specification, and required maintenance plans are set up on each asset.</span></span> <span data-ttu-id="e1968-110">次の図は、資産データの概要と、資産のジョブ タイプへの関連付けを示しています。</span><span class="sxs-lookup"><span data-stu-id="e1968-110">The following illustration shows an overview of asset data and the affiliation of assets to job types.</span></span> <span data-ttu-id="e1968-111">赤色のテキストは、継承と依存関係を示す場合などに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1968-111">Red text is used for examples that show inheritance and dependencies.</span></span>

![図 1](media/05-overview-image.png)

<span data-ttu-id="e1968-113">すべての作業指示書には、予防的メンテナンス、修繕メンテナンス、検査などの作業指示書タイプがあります。</span><span class="sxs-lookup"><span data-stu-id="e1968-113">Every work order has a work order type, such preventive maintenance, corrective maintenance, or inspection.</span></span> <span data-ttu-id="e1968-114">作業指示書には、1 つ以上のワーク オーダー ジョブが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1968-114">The work order contains one or more work order jobs.</span></span> <span data-ttu-id="e1968-115">すべての作業指示書ジョブは、資産および関連するジョブ タイプに対して実行する必要があるジョブを定義します。</span><span class="sxs-lookup"><span data-stu-id="e1968-115">Every work order job defines a job that must be performed on an asset and a related job type.</span></span> <span data-ttu-id="e1968-116">関連するジョブ タイプの例には、10,000 km、50,000 km、1 年間のオーバーホール、および安全検査が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e1968-116">Examples of related job types include 10,000 km, 50,000 km, 1-year overhaul, and safety inspection.</span></span> <span data-ttu-id="e1968-117">1 つの作業指示書を複数の資産に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e1968-117">One work order can be related to multiple assets.</span></span>

<span data-ttu-id="e1968-118">次の図は、作業指示書のキー データの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="e1968-118">The following illustration shows an overview of the key data in a work order.</span></span>

![図 2](media/06-overview-image.png)

<span data-ttu-id="e1968-120">作業指示書は別の作業指示書に関連付けることができ、ジョブ タイプには作業指示書を作成する後続のジョブを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e1968-120">A work order can be related to another work order, and job types can contain succeeding jobs that create a work order.</span></span> <span data-ttu-id="e1968-121">一般に、作業指示書間に依存関係はありません。</span><span class="sxs-lookup"><span data-stu-id="e1968-121">In general, there are no dependencies between work orders.</span></span> <span data-ttu-id="e1968-122">したがって、作業指示書のライフサイクル状態を変更でき、各々無関係にスケジューリングできます。</span><span class="sxs-lookup"><span data-stu-id="e1968-122">Therefore, they can change their work order lifecycle state and can be scheduled independently of each other.</span></span>

<span data-ttu-id="e1968-123">作業指示書は、修繕メンテナンス、予防的メンテナンス、または再有効化メンテナンスに関連するさまざまな方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="e1968-123">Work orders can be created in various ways that are related to corrective, preventive, or reactive maintenance.</span></span> <span data-ttu-id="e1968-124">また、作業指示書を手動で作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1968-124">You can also create work orders manually.</span></span> <span data-ttu-id="e1968-125">次の図は、作業指示書の自動または手動で作成するプロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="e1968-125">The following illustration shows an overview of the process for automatic or manual creation of work orders.</span></span>

![図 3](media/07-overview-image.png)

<span data-ttu-id="e1968-127">作業指示書でメンテナンス ジョブをスケジュールして実行する場合、複数のステップを完了しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1968-127">Several steps must be completed when you want to schedule and run a maintenance job on a work order.</span></span> <span data-ttu-id="e1968-128">次の図は、作業指示書処理の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="e1968-128">The following illustration shows an overview of the processing for a work order.</span></span>

![図 4](media/08-overview-image.png)

> [!NOTE]
> <span data-ttu-id="e1968-130">一般に、Microsoft Dynamics 365 for Finance and Operations および**アセット管理**モジュールで作業する場合は、**新規**を選択して新しいレコードを作成するか、**編集**を選択して既存のレコードを更新してから、**保存**を選択して新規または編集したデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="e1968-130">In general, when you work in Microsoft Dynamics 365 for Finance and Operations and the **Asset Management** module, you select **New** to create a new record, you select **Edit** to update an existing record, and you select **Save** to save new or edited data.</span></span>