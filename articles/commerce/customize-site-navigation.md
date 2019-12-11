---
title: サイト ナビゲーションのカスタマイズ
description: このトピックでは、カスタマイズされたオンライン ナビゲーション階層を作成して、Microsoft Dynamics 365 Commerce サイトで参照するため製品を整理する方法について説明します。
author: bicyclingfool
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8e1efb4a7484bd4626886c0f9aa40c3e4dfe304a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697477"
---
# <a name="customize-site-navigation"></a><span data-ttu-id="4dfc4-103">サイト ナビゲーションのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4dfc4-103">Customize site navigation</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="4dfc4-104">このトピックでは、カスタマイズされたオンライン ナビゲーション階層を作成して、Microsoft Dynamics 365 Commerce サイトで参照するため製品を整理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-104">This topic describes how to create a customized online navigation hierarchy to organize your products for browsing on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="4dfc4-105">概要</span><span class="sxs-lookup"><span data-stu-id="4dfc4-105">Overview</span></span>

<span data-ttu-id="4dfc4-106">オンライン店舗では、製品カテゴリを移動することで、顧客は製品を検索して参照することができます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-106">Online storefronts typically let customers discover and browse products by navigating through product categories.</span></span> <span data-ttu-id="4dfc4-107">この機能は通常、ページ上部にあるタブまたは左側にあるナビゲーション バーによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-107">This capability is usually provided by tabs at the top of the page or by a navigation bar on the left.</span></span> <span data-ttu-id="4dfc4-108">Dynamics 365 Commerce では、カテゴリ ナビゲーションの階層構造と、さまざまなカテゴリに含まれる製品を作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-108">In Dynamics 365 Commerce, you can create and manage the hierarchal structure of your category navigation and the products that are included in the various categories.</span></span>

## <a name="create-a-retail-channel-navigation-hierarchy"></a><span data-ttu-id="4dfc4-109">小売チャネル ナビゲーション階層を作成する</span><span class="sxs-lookup"><span data-stu-id="4dfc4-109">Create a retail channel navigation hierarchy</span></span>

<span data-ttu-id="4dfc4-110">小売チャネルのナビゲーション階層を作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-110">To create a retail channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="4dfc4-111">**小売 \> 製品とカテゴリ \> カテゴリと製品の管理**に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-111">Go to **Retail \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="4dfc4-112">**カテゴリ階層**を選択し、**新規**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-112">Select **Category hierarchies**, and then select **New**.</span></span>
1. <span data-ttu-id="4dfc4-113">階層に名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-113">Name the hierarchy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4dfc4-114">作成する最上位カテゴリは、ルート カテゴリ ノードです。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-114">The topmost category that you create is the root category node.</span></span> <span data-ttu-id="4dfc4-115">サイトには表示されません。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-115">It won't be shown on your site.</span></span> <span data-ttu-id="4dfc4-116">サイトに単一のトップ レベル ノードが表示されているカテゴリ階層を作成するには、カテゴリを作成し、ルート カテゴリの子として名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-116">To create a category hierarchy where a single top-level node is shown on your site, create and name the category as a child of the root category.</span></span>

1. <span data-ttu-id="4dfc4-117">**新しいカテゴリ ノード**を選択し、カテゴリに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-117">Select **New category node**, and name the category.</span></span>
1. <span data-ttu-id="4dfc4-118">必要に応じて、兄弟カテゴリと子カテゴリの作成を続行します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-118">Continue to create sibling and child categories as you require.</span></span>

<span data-ttu-id="4dfc4-119">トップレベルのカテゴリの下に作成した各カテゴリに製品を割り当てることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-119">You can now assign products to each category that you created under the top-level category.</span></span>

## <a name="customize-the-order-of-categories"></a><span data-ttu-id="4dfc4-120">カテゴリの順序のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="4dfc4-120">Customize the order of categories</span></span>

<span data-ttu-id="4dfc4-121">既定では、定義したカテゴリはサイトでアルファベット順に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-121">By default, the categories that you define will appear in alphabetical order on your site.</span></span> <span data-ttu-id="4dfc4-122">ただし、カテゴリの表示順序をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-122">However, you can also customize the display order of categories.</span></span>

## <a name="assign-a-category-hierarchy-type"></a><span data-ttu-id="4dfc4-123">カテゴリ階層タイプの割り当て</span><span class="sxs-lookup"><span data-stu-id="4dfc4-123">Assign a category hierarchy type</span></span>

1. <span data-ttu-id="4dfc4-124">**小売 \> 製品とカテゴリ \> カテゴリと製品の管理**に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-124">Go to **Retail \> Products and categories \> Category and product management**.</span></span>
1. <span data-ttu-id="4dfc4-125">**カテゴリ階層**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-125">Select **Category hierarchies**.</span></span>
1. <span data-ttu-id="4dfc4-126">アクション ペイン、**カテゴリ階層**タブの、**設定**グループで、**階層タイプの関連付け**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-126">On the Action Pane, on the **Category hierarchy** tab, in the **Set up** group, select **Associate hierarchy type**.</span></span>
1. <span data-ttu-id="4dfc4-127">**新規** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-127">Select **New**.</span></span>
1. <span data-ttu-id="4dfc4-128">**カテゴリ階層タイプ** フィールドで、**小売チャネル ナビゲーション階層**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-128">In the **Category hierarchy type** field, select **Retail channel navigation hierarchy**.</span></span>
1. <span data-ttu-id="4dfc4-129">**カテゴリ階層**フィールドで、以前に作成したチャンネル ナビゲーション階層を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-129">In the **Category hierarchy** field, select the channel navigation hierarchy that you created earlier.</span></span>

## <a name="publish-new-or-updated-navigation-hierarchies"></a><span data-ttu-id="4dfc4-130">新規または更新されたナビゲーション階層の公開</span><span class="sxs-lookup"><span data-stu-id="4dfc4-130">Publish new or updated navigation hierarchies</span></span>

<span data-ttu-id="4dfc4-131">オンライン店舗でナビゲーション階層を使用できるようにするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-131">To make your navigation hierarchy available to your online storefront, follow these steps.</span></span>

1. <span data-ttu-id="4dfc4-132">**小売 \> チェネル設定 \> チャネル カテゴリと製品属性**に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-132">Go to **Retail \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="4dfc4-133">左側のツリーで、オンライン ストアを選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-133">In the tree on the left, select your online store.</span></span>
1. <span data-ttu-id="4dfc4-134">**チャネル更新の公開**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-134">Select **Publish channel updates**.</span></span>
1. <span data-ttu-id="4dfc4-135">**小売 \> 小売 IT \> 配送スケジュール**の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-135">Go to **Retail \> Retail IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="4dfc4-136">一覧から**ジョブ 1040** を見つけ、選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-136">In the list, find and select **Job 1040**.</span></span>
1. <span data-ttu-id="4dfc4-137">**今すぐ実行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-137">Select **Run now**.</span></span>
1. <span data-ttu-id="4dfc4-138">ジョブ 1070 および 1150 についても、手順 5 と 6 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-138">Repeat steps 5 and 6 for jobs 1070 and 1150.</span></span>

## <a name="show-categories-on-your-site"></a><span data-ttu-id="4dfc4-139">サイトにカテゴリを表示する</span><span class="sxs-lookup"><span data-stu-id="4dfc4-139">Show categories on your site</span></span>

<span data-ttu-id="4dfc4-140">オンライン店舗でカテゴリ階層を表示するには、テンプレートまたはフラグメント内の適切な場所にナビゲーション メニュー モジュールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-140">To show your category hierarchy on your online storefront, you must add the navigation menu module in the appropriate location in a template or fragment.</span></span> <span data-ttu-id="4dfc4-141">サイトがバインドされているチャンネルに小売ナビゲーション階層を公開している場合は、ナビゲーション メニュー モジュールにナビゲーション階層が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-141">The navigation menu module will then show your navigation hierarchy, provided that you've published your retail navigation hierarchy to the channel that your site is bound to.</span></span>

> [!NOTE]
> <span data-ttu-id="4dfc4-142">ストア スターター キットに含まれているナビゲーション メニュー モジュールにより、ユーザーはサブカテゴリを持たないカテゴリにのみ移動できます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-142">The navigation menu module that is included in the store starter kit lets users navigate only to categories that don't have subcategories.</span></span> <span data-ttu-id="4dfc4-143">顧客がサブカテゴリを持つカテゴリに移動できるようにする場合は、ナビゲーション メニュー モジュールをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-143">If your customers should be able to navigate to categories that have subcategories, you must customize the navigation menu module.</span></span>

## <a name="add-custom-navigation-options"></a><span data-ttu-id="4dfc4-144">カスタム ナビゲーション オプションを追加する</span><span class="sxs-lookup"><span data-stu-id="4dfc4-144">Add custom navigation options</span></span>

<span data-ttu-id="4dfc4-145">ナビゲーション メニューでは、製品カテゴリ階層に含まれていないナビゲーション オプションを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-145">On your navigation menu, you can add navigation options that aren't part of your product category hierarchy.</span></span> <span data-ttu-id="4dfc4-146">たとえば、製品カテゴリの一覧の最後に、サイトに対して作成した連絡先ページを指す**お問い合わせ**項目を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-146">For example, at the end of the list of product categories, you can add a **Contact Us** item that points to a contact page that you've built for your site.</span></span>

<span data-ttu-id="4dfc4-147">ナビゲーション メニューにカスタム ナビゲーション オプションを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-147">To add custom navigation options to your navigation menu, follow these steps.</span></span>

1. <span data-ttu-id="4dfc4-148">カスタマイズするテンプレートまたはフラグメントで、ナビゲーション メニュー モジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-148">In the template or fragment that you want to customize, select the navigation menu module.</span></span>
1. <span data-ttu-id="4dfc4-149">プロパティ ウィンドウの**データ** タブで、**品目の追加**を選択し、新しいコンテンツ管理システム (CMS) を選択します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-149">In the property pane, on the **Data** tab, select **Add item** to create a new content management system (CMS) navigation item.</span></span>
1. <span data-ttu-id="4dfc4-150">リンク テキストと URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-150">Enter link text and a URL.</span></span>
1. <span data-ttu-id="4dfc4-151">手順 2 と 3 を繰り返して、さらにカスタム ナビゲーション オプションを追加します。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-151">Repeat steps 2 and 3 to add more custom navigation options.</span></span>
1. <span data-ttu-id="4dfc4-152">完了したら、テンプレートまたはフラグメントを保存し、チェックインします。</span><span class="sxs-lookup"><span data-stu-id="4dfc4-152">When you've finished, save the template or fragment, and check it in.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4dfc4-153">追加リソース</span><span class="sxs-lookup"><span data-stu-id="4dfc4-153">Additional resources</span></span>

[<span data-ttu-id="4dfc4-154">テンプレートとレイアウトの概要</span><span class="sxs-lookup"><span data-stu-id="4dfc4-154">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="4dfc4-155">テンプレートの使用</span><span class="sxs-lookup"><span data-stu-id="4dfc4-155">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="4dfc4-156">プリセット レイアウトの使用</span><span class="sxs-lookup"><span data-stu-id="4dfc4-156">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="4dfc4-157">フラグメントで動作</span><span class="sxs-lookup"><span data-stu-id="4dfc4-157">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="4dfc4-158">モジュールで動作</span><span class="sxs-lookup"><span data-stu-id="4dfc4-158">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="4dfc4-159">ページ URL の作成</span><span class="sxs-lookup"><span data-stu-id="4dfc4-159">Create a page URL</span></span>](create-page-url.md)