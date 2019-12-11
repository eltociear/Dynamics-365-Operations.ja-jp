---
title: サイト ページにスクリプト コードを追加してテレメトリをサポートする
description: このトピックでは、クライアント側のテレメトリの収集をサポートするクライアント側のスクリプト コードをサイト ページに追加する方法について説明します。
author: bicyclingfool
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a5f82426d87cd2e0faa0195a841899bb03f9df08
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697339"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="f070a-103">サイト ページにスクリプト コードを追加してテレメトリをサポートする</span><span class="sxs-lookup"><span data-stu-id="f070a-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="f070a-104">このトピックでは、クライアント側のテレメトリの収集をサポートするクライアント側のスクリプト コードをサイト ページに追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f070a-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="f070a-105">概要</span><span class="sxs-lookup"><span data-stu-id="f070a-105">Overview</span></span>

<span data-ttu-id="f070a-106">Web Analytics は、顧客がサイトとどのように対話するかを理解し、最大のコンバージョンのためにエクスペリエンスを最適化するのに役立つ決定を下したい場合に、重要なツールとなります。</span><span class="sxs-lookup"><span data-stu-id="f070a-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="f070a-107">Google Analytics、Clicky、Moz Analytics、KISSMetrics など、これらの目標を達成するために、多くの Web Analytics パッケージが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f070a-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="f070a-108">ほとんどの Web Analytics パッケージでは、サイトのすべてのページの HTML の **\<head\>** 要素にクライアント側のスクリプト コードを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f070a-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="f070a-109">このトピックの手順は、Microsoft Dynamics 365 Commerce がネイティブに提供していない他のカスタム クライアント側機能にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="f070a-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="f070a-110">スクリプ トコードに再利用可能なフラグメントを作成する</span><span class="sxs-lookup"><span data-stu-id="f070a-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="f070a-111">スクリプト コードのフラグメントを作成すると、サイトのすべてのページで再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f070a-111">After you create a fragment for your script code, it can be reused across all pages on your site.</span></span>

1. <span data-ttu-id="f070a-112">**フラグメント \> 新しいページ フラグメント**に移動します。</span><span class="sxs-lookup"><span data-stu-id="f070a-112">Go to **Fragments \> New page fragment**.</span></span>
2. <span data-ttu-id="f070a-113">**外部スクリプト**を選択し、フラグメントの名前を入力して、**OK** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f070a-113">Select **External Script**, enter a name for the fragment, and then select **OK**.</span></span>
3. <span data-ttu-id="f070a-114">フラグメント階層で、作成したフラグメントの**スクリプトの挿入**モジュールの子を選択します。</span><span class="sxs-lookup"><span data-stu-id="f070a-114">In the fragment hierarchy, select the **script injector** module child of the fragment that you just created.</span></span>
4. <span data-ttu-id="f070a-115">右側のプロパティ ウィンドウで、クライアント側のスクリプトを追加し、必要に応じてその他のコンフィギュレーション オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="f070a-115">In the property pane on the right, add your client-side script, and set other configuration options as you require.</span></span>

## <a name="add-the-fragment-to-templates"></a><span data-ttu-id="f070a-116">フラグメントのテンプレートへの追加</span><span class="sxs-lookup"><span data-stu-id="f070a-116">Add the fragment to templates</span></span>

1. <span data-ttu-id="f070a-117">**テンプレート**に移動して、スクリプト コードを追加するページのテンプレートを開きます。</span><span class="sxs-lookup"><span data-stu-id="f070a-117">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
2. <span data-ttu-id="f070a-118">左ウィンドウでテンプレート階層を展開し、**HTML ヘッド** スロットを表示します。</span><span class="sxs-lookup"><span data-stu-id="f070a-118">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
3. <span data-ttu-id="f070a-119">**HTML Head** スロットの省略ボタン (**...**) を選択し、**フラグメントの追加**を選択します。</span><span class="sxs-lookup"><span data-stu-id="f070a-119">Select the ellipsis button (**...**) for the **HTML Head** slot, and then select **Add fragment**.</span></span>
4. <span data-ttu-id="f070a-120">スクリプト コードに対して作成したフラグメントを選択します。</span><span class="sxs-lookup"><span data-stu-id="f070a-120">Select the fragment that you created for your script code.</span></span>
5. <span data-ttu-id="f070a-121">テンプレートを保存し、チェックインします。</span><span class="sxs-lookup"><span data-stu-id="f070a-121">Save the template, and check it in.</span></span>

> [!NOTE]
> <span data-ttu-id="f070a-122">作業が完了したら、フラグメントとマスタ テンプレートを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f070a-122">After you've finished, you must publish the fragment and the master template.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="f070a-123">追加リソース</span><span class="sxs-lookup"><span data-stu-id="f070a-123">Additional resources</span></span>

[<span data-ttu-id="f070a-124">ロゴの追加</span><span class="sxs-lookup"><span data-stu-id="f070a-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="f070a-125">サイト テーマの選択</span><span class="sxs-lookup"><span data-stu-id="f070a-125">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="f070a-126">お気に入りの追加</span><span class="sxs-lookup"><span data-stu-id="f070a-126">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="f070a-127">ようこそメッセージの追加</span><span class="sxs-lookup"><span data-stu-id="f070a-127">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="f070a-128">著作権に関する注意事項の追加</span><span class="sxs-lookup"><span data-stu-id="f070a-128">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="f070a-129">サイトに言語を追加する</span><span class="sxs-lookup"><span data-stu-id="f070a-129">Add languages to your site</span></span>](add-languages-to-site.md)
