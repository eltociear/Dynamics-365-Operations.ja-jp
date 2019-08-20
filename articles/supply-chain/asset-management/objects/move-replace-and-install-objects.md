---
title: 資産の移動、置換、およびインストール
description: このトピックでは、資産管理で資産を移動、置換、およびインストールする方法について説明します。
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
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
ms.openlocfilehash: c0e6306698d351d33cae627e3741ad9a2eb6d893
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783417"
---
# <a name="move-replace-and-install-assets"></a><span data-ttu-id="7898e-103">資産の移動、置換、およびインストール</span><span class="sxs-lookup"><span data-stu-id="7898e-103">Move, replace, and install assets</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="7898e-104">このトピックでは、資産管理で資産を移動、置換、およびインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7898e-104">This topic explains how to move, replace, and install assets in Asset Management.</span></span> <span data-ttu-id="7898e-105">他の資産との関係を持たない個別資産を作成することも、親資産 (最上位レベルの資産) と関連する子資産 (下位資産) を含む資産構造を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7898e-105">You can create individual assets that have no relations to other assets, or you can create an asset structure that includes a parent asset (top-level asset) and related child assets (sub-assets).</span></span> <span data-ttu-id="7898e-106">資産管理では、資産の場所を移動および変更する 3 つのアプローチがあります。</span><span class="sxs-lookup"><span data-stu-id="7898e-106">In Asset Management, there are three approaches to moving and changing the location of an asset:</span></span>

- <span data-ttu-id="7898e-107">**移動** – 資産を別の資産構造または同じ資産構造内の別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="7898e-107">**Move** – Move an asset either to another asset structure or to another location in the same asset structure.</span></span>
- <span data-ttu-id="7898e-108">**置換** – 修復または改修できるように資産構造から資産を一時的に削除し、改修された資産を後で資産構造に戻します。</span><span class="sxs-lookup"><span data-stu-id="7898e-108">**Replace** – Temporarily remove an asset from an asset structure so that it can be repaired or refurbished, and then add the refurbished asset back to the asset structure later.</span></span> <span data-ttu-id="7898e-109">または、使用済み資産を新しい資産に完全に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7898e-109">Alternatively, permanently replace a used asset with a new asset.</span></span>
- <span data-ttu-id="7898e-110">**インストール** – 親資産および関連する子資産を機能場所にインストールします。</span><span class="sxs-lookup"><span data-stu-id="7898e-110">**Install** – Install a parent asset and any related child assets on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="7898e-111">移動、置換、またはインストールする資産は、別の機能場所に関連付けられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7898e-111">The asset that you move, replace, or install might be related to another functional location.</span></span> <span data-ttu-id="7898e-112">その場合、資産は機能場所の財務分析コードを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7898e-112">In that case, the asset might use financial dimensions of the functional location.</span></span> <span data-ttu-id="7898e-113">**機能場所のタイプ** ページで、機能場所での財務分析コードの処理を設定します。</span><span class="sxs-lookup"><span data-stu-id="7898e-113">On the **Functional location types** page, you set up the handling of financial dimensions on functional locations.</span></span>

## <a name="move-asset"></a><span data-ttu-id="7898e-114">資産移動</span><span class="sxs-lookup"><span data-stu-id="7898e-114">Move asset</span></span>

<span data-ttu-id="7898e-115">**資産移動** – 機能を使用して、資産を別の資産構造または同じ資産構造内の別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="7898e-115">Use the **Move asset** function to move an asset either to another asset structure or to another location in the same asset structure.</span></span> <span data-ttu-id="7898e-116">資産を資産構造から移動して、構造関係のないスタンドアロン資産にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7898e-116">You can also move an asset out of an asset structure so that it becomes a standalone asset that has no structure relations.</span></span>

> [!NOTE]
> <span data-ttu-id="7898e-117">資産が修復または一時的に置き換えられている場合は、この機能を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7898e-117">Don't use this function if assets are being repaired or temporarily replaced.</span></span> <span data-ttu-id="7898e-118">代わりに、このトピックの後半で説明される**資産置換**機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="7898e-118">Instead, use the **Replace asset** functionality that is described later in this topic.</span></span>

1. <span data-ttu-id="7898e-119">**資産管理** \> **共通** \> **資産** \> **全資産**または**有効な資産**を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-119">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="7898e-120">一覧で、資産を選択して移動します。</span><span class="sxs-lookup"><span data-stu-id="7898e-120">In the list, select the asset to move.</span></span> <span data-ttu-id="7898e-121">資産に子資産がある場合は、それらの資産も移動します。</span><span class="sxs-lookup"><span data-stu-id="7898e-121">If the asset has child assets, you also move those assets.</span></span>
3. <span data-ttu-id="7898e-122">**資産移動**を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-122">Select **Move asset**.</span></span>
4. <span data-ttu-id="7898e-123">資産を資産構造の一部になるように移動するには、**親資産**フィールド内の新しい親資産を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-123">To move the asset so that it becomes part of an asset structure, select the new parent asset in the **Parent asset** field.</span></span> <span data-ttu-id="7898e-124">子資産を移動し、構造関係のないスタンドアロン資産にする場合は、**親資産**フィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="7898e-124">If you're moving a child asset, and you want to make it a standalone asset that has no structure relations, leave the **Parent asset** field blank.</span></span>
5. <span data-ttu-id="7898e-125">既定では、**有効**フィールドは現在の日時に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7898e-125">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="7898e-126">ただし、資産移動が有効になる異なる日時を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7898e-126">However, you can select a different date and time that the asset move is valid from.</span></span>
6. <span data-ttu-id="7898e-127">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-127">Select **OK**.</span></span>

## <a name="replace-asset"></a><span data-ttu-id="7898e-128">資産置換</span><span class="sxs-lookup"><span data-stu-id="7898e-128">Replace asset</span></span>

<span data-ttu-id="7898e-129">修復、改修、または古くなった資産を新しい資産による完全な置換に関連して**資産置換**機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="7898e-129">Use the **Replace asset** function in connection with repairs, refurbishment, or permanent replacement of a worn-out asset by a new asset.</span></span> <span data-ttu-id="7898e-130">この機能は、資産構造内の子資産を置き換えるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7898e-130">This function is used to replace child assets in an asset structure.</span></span> <span data-ttu-id="7898e-131">親資産 (現在親資産を持たない資産) の場合、この置換は機能場所で行われます。</span><span class="sxs-lookup"><span data-stu-id="7898e-131">For parent assets (that is, assets that don't currently have a parent asset), this replacement is done on a functional location.</span></span> <span data-ttu-id="7898e-132">機能場所での親資産の置換方法の詳細については、[機能場所に資産をインストールする](../functional-locations/install-objects-on-functional-locations.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7898e-132">For more information about how to replace parent assets on a functional location, see [Install assets on functional locations](../functional-locations/install-objects-on-functional-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7898e-133">修理店が生産部門に関連している場合は、**修復**、**仕損**、**保管**などの機能場所を作成して、資産の修理と交換を処理できます。</span><span class="sxs-lookup"><span data-stu-id="7898e-133">If a repair shop is related to your production department, you can create functional locations such as **Repair**, **Scrap**, and **Storage** to handle the repair and replacement of assets.</span></span>

1. <span data-ttu-id="7898e-134">**資産管理** \> **共通** \> **資産** \> **全資産**または**有効な資産**を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-134">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="7898e-135">一覧で、子資産を選択し置換します。</span><span class="sxs-lookup"><span data-stu-id="7898e-135">In the list, select the child asset to replace.</span></span> <span data-ttu-id="7898e-136">資産に子資産がある場合は、それらの資産も置換します。</span><span class="sxs-lookup"><span data-stu-id="7898e-136">If the asset has child assets, you also replace those assets.</span></span>
3. <span data-ttu-id="7898e-137">**資産置換**を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-137">Select **Replace asset**.</span></span>

    <span data-ttu-id="7898e-138">**構造変更**フィールドに、選択した資産と関連する子資産が資産構造内で移動した最後の日時が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7898e-138">The **Structure change** field shows the last date and time that the selected asset and related child assets were moved in the asset structure.</span></span>

4. <span data-ttu-id="7898e-139">**選択した資産**セクションの、**ターゲット機能場所**フィールドで、資産の移動先である機能場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-139">In the **Selected asset** section, in the **Target functional location** field, select the functional location to move the asset to.</span></span> <span data-ttu-id="7898e-140">たとえば、**修復**または**仕損**の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-140">For example, select the **Repair** or **Scrap** location.</span></span>

    <span data-ttu-id="7898e-141">**親資産**セクション内の、**有効**フィールドに、親資産および関連する子資産が現在の機能場所にインストールまたは移動した最後の日時が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7898e-141">In the **Parent asset** section, the **Effective** field shows the last date and time that the parent asset and related child assets were installed or moved on the current functional location.</span></span>

5. <span data-ttu-id="7898e-142">**新しい資産**セクション内の、**資産**フィールドで、選択した資産の一時的または完全な置換として挿入する資産を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-142">In the **New asset** section, in the **Asset** field, select the asset to insert as a temporary or permanent replacement for the selected asset.</span></span> <span data-ttu-id="7898e-143">この資産は、現在**保管**などの別の機能場所にある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7898e-143">This asset might currently be located on another functional location, such as **Storage**.</span></span>
7. <span data-ttu-id="7898e-144">**有効開始**セクション内の、**有効**フィールドは規定で現在の日時に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7898e-144">In the **Effective from** section, the **Effective** field is set to the current date and time by default.</span></span> <span data-ttu-id="7898e-145">ただし、資産置換が有効になる異なる日時を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7898e-145">However, you can select a different date and time that the asset replacement is valid from.</span></span>
8. <span data-ttu-id="7898e-146">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-146">Select **OK**.</span></span>

## <a name="install-asset"></a><span data-ttu-id="7898e-147">資産のインストール</span><span class="sxs-lookup"><span data-stu-id="7898e-147">Install asset</span></span>

<span data-ttu-id="7898e-148">**資産のインストール**機能を使用して、機能場所に資産構造をインストールします。</span><span class="sxs-lookup"><span data-stu-id="7898e-148">Use the **Install asset** function to install an asset structure on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="7898e-149">常に親資産を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-149">Always select a parent asset.</span></span> <span data-ttu-id="7898e-150">親資産と関連する子資産は、選択した機能場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="7898e-150">The parent asset and related child assets will be moved to the selected functional location.</span></span>

1. <span data-ttu-id="7898e-151">**資産管理** \> **共通** \> **資産** \> **全資産**または**有効な資産**を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-151">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="7898e-152">一覧で、別の機能場所にインストールする親資産を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-152">In the list, select the parent asset to install on another functional location.</span></span>
3. <span data-ttu-id="7898e-153">**資産のインストール**を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-153">Select **Install asset**.</span></span>

    <span data-ttu-id="7898e-154">**属性**セクションに、親資産に設定されている資産属性が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7898e-154">The **Attributes** section shows the asset attributes that are set up on the parent asset.</span></span>

4. <span data-ttu-id="7898e-155">**機能場所**フィールドで、新しい場所を選択してください。</span><span class="sxs-lookup"><span data-stu-id="7898e-155">In the **Functional location** field, select the new location.</span></span>
5. <span data-ttu-id="7898e-156">既定では、**有効**フィールドは現在の日時に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7898e-156">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="7898e-157">ただし、資産構造のインストールが有効になる異なる日時を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7898e-157">However, you can select a different date and time that the installation on the asset structure is valid from.</span></span>
6. <span data-ttu-id="7898e-158">**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7898e-158">Select **OK**.</span></span>