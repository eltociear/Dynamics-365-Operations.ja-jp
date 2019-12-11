---
title: ページ モデルの用語集
description: このトピックでは、Microsoft Dynamics 365 Commerce サイトのページで使用されるさまざまな要素について説明します。
author: phinneyridge
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3c7b79e8b3bd68ba6246fe24916c60f476a26605
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697960"
---
# <a name="page-model-glossary"></a><span data-ttu-id="a0fa1-103">ページ モデルの用語集</span><span class="sxs-lookup"><span data-stu-id="a0fa1-103">Page model glossary</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a0fa1-104">このトピックでは、Microsoft Dynamics 365 Commerce サイトのページで使用されるさまざまな要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-104">This topic describes the various elements that are used on the pages of a Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="page-element-definitions"></a><span data-ttu-id="a0fa1-105">ページ要素の定義</span><span class="sxs-lookup"><span data-stu-id="a0fa1-105">Page element definitions</span></span>

<span data-ttu-id="a0fa1-106">次の表で、サイトの概観、およびコンテンツを変更する際に理解しておく必要がある条件の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-106">The following table provides a summary of terms that you should be familiar with when you change the look, feel, and content of your site.</span></span> <span data-ttu-id="a0fa1-107">さらに詳細な説明および手順については、リンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-107">For more thorough explanations and procedures, follow the links.</span></span>

| <span data-ttu-id="a0fa1-108">相談</span><span class="sxs-lookup"><span data-stu-id="a0fa1-108">Term</span></span> | <span data-ttu-id="a0fa1-109">説明およびメモ</span><span class="sxs-lookup"><span data-stu-id="a0fa1-109">Description and notes</span></span> |
|------|-----------------------|
| [<span data-ttu-id="a0fa1-110">モジュール</span><span class="sxs-lookup"><span data-stu-id="a0fa1-110">Module</span></span>](work-with-modules.md) | <p><span data-ttu-id="a0fa1-111">**定義:** モジュールは、Web ページのスケルトンの作成および構成をするための構成要素です。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-111">**Definition:** Modules are building block that can be authored and make up the skeleton of a webpage.</span></span> <span data-ttu-id="a0fa1-112">ヘッダー、ヒーロー、およびカルーセル モジュールがその例です。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-112">Examples include header, hero, and carousel modules.</span></span></p><p><span data-ttu-id="a0fa1-113">**選択される場所:** テンプレート、レイアウト、ページ、およびフラグメントの作成ステージなど、サイト作成のワークフローのさまざまなステージで、配置したモジュールを選択し、コンフィギュレーションすることができます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-113">**Where it's selected:** Deployed modules can be selected and configured in various stages of the site authoring workflow, such as the template, layout, page, and fragment authoring stages.</span></span></p><p><span data-ttu-id="a0fa1-114">**編集されている場所:** カスタム モジュールは、ソフトウェア開発キット (SDK) を使用し、コード内で作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-114">**Where it's edited:** Custom modules are created in code by using the software development kit (SDK).</span></span> <span data-ttu-id="a0fa1-115">次に、選択内容が利用可能になるサイトにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-115">They are then uploaded to your site, where they become available for selection.</span></span></p> |
| <span data-ttu-id="a0fa1-116">モジュールのプロパティ</span><span class="sxs-lookup"><span data-stu-id="a0fa1-116">Module property</span></span> | <p><span data-ttu-id="a0fa1-117">**定義:** モジュールのプロパティは、モジュールごとに定義される特定の設定です。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-117">**Definition:** Module properties are specific settings that are defined by the module.</span></span> <span data-ttu-id="a0fa1-118">E コマース作成ツールで編集できます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-118">They can be edited in the e-Commerce authoring tools.</span></span> <span data-ttu-id="a0fa1-119">たとえば、モジュールのプロパティは、バナー モジュールのヘッダーと背景イメージを設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-119">For example, module properties are used to set the heading and background image of a banner module.</span></span></p><p><span data-ttu-id="a0fa1-120">**コンフィギュレーションされる場所:** モジュールのプロパティは、テンプレート、レイアウト、ページ、フラグメント、およびアプリ設定の作成環境 (エディター) に表示されるプロパティ ウィンドウで選択し、コンフィギュレーションされます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-120">**Where it's configured:** Module properties are selected and configured in the property pane that appears in the authoring environments (editors) for templates, layouts, pages, fragments, and app settings.</span></span></p> |
| [<span data-ttu-id="a0fa1-121">テンプレート</span><span class="sxs-lookup"><span data-stu-id="a0fa1-121">Template</span></span>](templates-layouts-overview.md) | <p><span data-ttu-id="a0fa1-122">**定義:** テンプレートは、ページのカテゴリ (たとえば、マーケティング ページ、カテゴリ ページ、および製品ページ) に使用するモジュールの組み合わせおよびオプションを定義します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-122">**Definition:** Templates define the module combinations and options that should be used for a category of pages (for example, marketing pages, category pages, and product pages).</span></span></p><p><span data-ttu-id="a0fa1-123">**選択される場所:** ページまたはレイアウトの作成ワークフローの中でテンプレートを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-123">**Where it's selected:** Templates can be selected during page or layout creation workflows.</span></span></p><p><span data-ttu-id="a0fa1-124">**編集される場所:** テンプレートはテンプレート エディターで作成します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-124">**Where it's edited:** Templates are authored in the template editor.</span></span> <span data-ttu-id="a0fa1-125">作成または変更にコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-125">No code is required to create or modify them.</span></span></p> |
| [<span data-ttu-id="a0fa1-126">レイアウト</span><span class="sxs-lookup"><span data-stu-id="a0fa1-126">Layout</span></span>](templates-layouts-overview.md) | <p><span data-ttu-id="a0fa1-127">**定義:** レイアウトは、親テンプレートのオプション セットからの、最終的なモジュールの選択および配置を定義します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-127">**Definition:** Layouts define the final selection and arrangement of modules from the parent template's set of options.</span></span> <span data-ttu-id="a0fa1-128">レイアウトは、1 ページに対してコンフィギュレーションすることができ (*カスタム レイアウト*)、また複数のページごとに共有することもできます (*プリセット レイアウト*)。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-128">A layout can be configured for a single page (*custom layout*), or it can be shared by multiple pages (*preset layout*).</span></span></p><p><span data-ttu-id="a0fa1-129">**選択される場所:** レイアウトは、新しいページの作成時か、または既存のページに異なるレイアウトが必要な場合に、選択できます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-129">**Where it's selected:** Layouts can be selected during new page creation or when a different layout is required for an existing page.</span></span></p><p><span data-ttu-id="a0fa1-130">**編集される場所:** レイアウトはレイアウト エディターで作成します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-130">**Where it's edited:** Layouts are authored in the layout editor.</span></span> <span data-ttu-id="a0fa1-131">作成または変更にコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-131">No code is required to create or modify them.</span></span></p> |
| <span data-ttu-id="a0fa1-132">ページ インスタンス</span><span class="sxs-lookup"><span data-stu-id="a0fa1-132">Page instance</span></span> | <p><span data-ttu-id="a0fa1-133">**定義:** ページ インスタンスは、1 ページに対する最終的な、ページ固有のローカライズされたコンテンツを定義します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-133">**Definition:** Page instances define the final, page-specific localized content for a single page.</span></span> <span data-ttu-id="a0fa1-134">このコンテンツは、モジュール プロパティの値から派生します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-134">This content is derived from the values of module properties.</span></span></p><p><span data-ttu-id="a0fa1-135">**選択される場所:** ページは、URL が割り当てられる時に選択されます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-135">**Where it's selected:** Pages are selected when URLs are assigned.</span></span></p><p><span data-ttu-id="a0fa1-136">**編集される場所:** ページはページ エディターで編集します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-136">**Where it's edited:** Pages are edited in the page editor.</span></span> <span data-ttu-id="a0fa1-137">作成または変更にコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-137">No code is required to create or modify them.</span></span></p> |
| [<span data-ttu-id="a0fa1-138">テーマ</span><span class="sxs-lookup"><span data-stu-id="a0fa1-138">Theme</span></span>](select-site-theme.md) | <p><span data-ttu-id="a0fa1-139">**定義:** テーマは、カスケード スタイル シート (CSS) を定義し、ページでレンダリングされるモジュールの概観を決定します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-139">**Definition:** Themes define the Cascading Style Sheet (CSS), and determine the look and feel of the modules that are rendered on a page.</span></span></p><p><span data-ttu-id="a0fa1-140">**選択される場所:** テーマが Microsoft Dynamics Lifecycle Services (LCS) を使用してアップロードされた後、ページ コンテナー モジュールのプロパティとして選択できます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-140">**Where it's selected:** After a theme is uploaded to your site by using Microsoft Dynamics Lifecycle Services (LCS), it can be selected as a property of the page container module.</span></span></p><p><span data-ttu-id="a0fa1-141">**編集される場所:** 現在、テーマは SDK を使用して作成および編集できます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-141">**Where it's edited:** Themes are currently created and edited by using the SDK.</span></span> <span data-ttu-id="a0fa1-142">次に、LCS を使用してサイトにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-142">They are then uploaded to your site by using LCS.</span></span></p> |
| [<span data-ttu-id="a0fa1-143">フラグメント</span><span class="sxs-lookup"><span data-stu-id="a0fa1-143">Fragment</span></span>](work-with-fragments.md) | <p><span data-ttu-id="a0fa1-144">**定義:** フラグメントは、コンテンツをローカライズし、完全にコンフィギュレーションしたモジュールで、再利用および複数のページ間での 1 か所の更新ができます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-144">**Definition:** Fragments are fully configured modules that have localized content that can be reused and centrally updated across multiple pages.</span></span> <span data-ttu-id="a0fa1-145">たとえば、ヘッダー モジュールから作成されたフラグメントは、すべてのテンプレート内およびサイト間のすべてのページ上で使用でき、1 か所で更新できます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-145">For example, a fragment that is created from a header module can be used in all templates and on all pages across your site, and centrally updated in one place.</span></span></p><p><span data-ttu-id="a0fa1-146">**選択される場所:** フラグメントは、モジュールを選択できる任意の場所で選択できます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-146">**Where it's selected:** Fragments can be selected wherever modules can be selected.</span></span> <span data-ttu-id="a0fa1-147">モジュールが、再利用可能な一括作成を通して効率を向上させるために、代用することができます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-147">They can be substituted for a module to help increase efficiency through reusable and centralized authoring.</span></span></p><p><span data-ttu-id="a0fa1-148">**編集される場所:** フラグメントはフラグメント エディターで編集します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-148">**Where it's edited:** Fragments are edited in the fragment editor.</span></span> <span data-ttu-id="a0fa1-149">作成または変更にコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-149">No code is required to create or modify them.</span></span></p> |
| <span data-ttu-id="a0fa1-150">URL</span><span class="sxs-lookup"><span data-stu-id="a0fa1-150">URL</span></span> | <p><span data-ttu-id="a0fa1-151">**定義:** ユニフォーム リソース ロケータ (URL) は、Web ページまたは他の URL をポイントするアドレスです。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-151">**Definition:** Uniform resource locators (URLs) are addresses that point to webpages or other URLs.</span></span></p><p><span data-ttu-id="a0fa1-152">**選択される場所:** URL は、ページ間のリンクが必要な時に選択されます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-152">**Where it's selected:** URLs are selected wherever links between pages are required.</span></span></p><p><span data-ttu-id="a0fa1-153">**編集される場所:** URL は URL エディターで編集します。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-153">**Where it's edited:** URLs are edited in the URL editor.</span></span> <span data-ttu-id="a0fa1-154">作成または変更にコードは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-154">No code is required to create or modify them.</span></span></p> |
| <span data-ttu-id="a0fa1-155">資産</span><span class="sxs-lookup"><span data-stu-id="a0fa1-155">Asset</span></span> | <p><span data-ttu-id="a0fa1-156">**定義:** 資産とは、.jpg、.docx、.pdf、または .mpg などの拡張子を持つファイル バイナリです。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-156">**Definition:** Assets are file binaries that have an extension such as .jpg, .docx, .pdf, or .mpg.</span></span></p><p><span data-ttu-id="a0fa1-157">**選択される場所:** 資産は、必要とされるモジュールに対して、モジュール プロパティとして選択されます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-157">**Where it's selected:** Assets are selected as module properties for modules that require them.</span></span></p><p><span data-ttu-id="a0fa1-158">**編集される場所:** 資産はアップロードされ、関連するメタ データは資産マネージャーで編集されます。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-158">**Where it's edited:** Assets are uploaded, and associated metadata is edited in the asset manager.</span></span></p> |

## <a name="additional-resources"></a><span data-ttu-id="a0fa1-159">追加リソース</span><span class="sxs-lookup"><span data-stu-id="a0fa1-159">Additional resources</span></span>

[<span data-ttu-id="a0fa1-160">コンテンツを追加する方法</span><span class="sxs-lookup"><span data-stu-id="a0fa1-160">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="a0fa1-161">ドキュメントの状態とライフサイクル</span><span class="sxs-lookup"><span data-stu-id="a0fa1-161">Document states and lifecycle</span></span>](document-states-overview.md)

[<span data-ttu-id="a0fa1-162">モジュールで動作</span><span class="sxs-lookup"><span data-stu-id="a0fa1-162">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="a0fa1-163">フラグメントで動作</span><span class="sxs-lookup"><span data-stu-id="a0fa1-163">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="a0fa1-164">テンプレートとレイアウトの概要</span><span class="sxs-lookup"><span data-stu-id="a0fa1-164">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="a0fa1-165">サイト ナビゲーションのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="a0fa1-165">Customize site navigation</span></span>](customize-site-navigation.md)