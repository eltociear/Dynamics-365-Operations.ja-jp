---
title: ワークフロー カテゴリの作成
description: このトピックでは、ワークフロー カテゴリの作成方法を説明します。
author: RobinARH
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: 202694
ms.assetid: 33349e0d-d8ac-4d20-8f9b-5f85d4e01004
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: Platform update 1
ms.openlocfilehash: 5e96e4a1d0e069224ee78cebf8b7fdf6c891dc99
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850740"
---
# <a name="create-a-workflow-category"></a><span data-ttu-id="3a5e9-103">ワークフロー カテゴリの作成</span><span class="sxs-lookup"><span data-stu-id="3a5e9-103">Create a workflow category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3a5e9-104">ワークフロー タイプを作成する際には、ワークフロー タイプをその質問に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-104">When you create a workflow type, you must assign it to a workflow category.</span></span> <span data-ttu-id="3a5e9-105">ワークフロー カテゴリによって、特定のモジュールでワークフロー タイプを使用できるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-105">The workflow category determines whether the workflow type is available in a specific module.</span></span> <span data-ttu-id="3a5e9-106">適切なワークフロー カテゴリがまだ存在していない場合は、作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-106">If an appropriate workflow category doesn't already exist, you must create it.</span></span>

<span data-ttu-id="3a5e9-107">たとえば、顧客請求書のワークフロー タイプは、 **マスター プラン** モジュールでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-107">For example, a workflow type for a customer invoice should not be available in the **Master planning** module.</span></span> <span data-ttu-id="3a5e9-108">ワークフロー タイプを **顧客** モジュールでのみ使用できるようにするには、ワークフロー カテゴリの作成時に **顧客** モジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-108">To make the workflow type available only in the **Customer** module, select the **Customer** module when you create a workflow category.</span></span>

<span data-ttu-id="3a5e9-109">このトピックでは、ワークフロー カテゴリの作成方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-109">This topic describes how to create a workflow category.</span></span>

## <a name="create-a-workflow-category"></a><span data-ttu-id="3a5e9-110">ワークフロー カテゴリの作成</span><span class="sxs-lookup"><span data-stu-id="3a5e9-110">Create a workflow category</span></span>

1. <span data-ttu-id="3a5e9-111">アプリケーション エクスプローラーで、 **ビジネス プロセスとワークフロー** ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-111">In Application Explorer, expand the **Business Process and Workflow** node.</span></span>
2. <span data-ttu-id="3a5e9-112">次のいずれかの手順に従って、ワークフロー カテゴリを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-112">Follow one of these steps to create the workflow category:</span></span>

    + <span data-ttu-id="3a5e9-113">**ワークフロー カテゴリ** ノードを右クリックし、 **新しいワークフロー カテゴリ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-113">Right-click the **Workflow Categories** node, and then select **New Workflow Category**.</span></span> <span data-ttu-id="3a5e9-114">新しいワークフロー カテゴリ グループが **ワークフロー カテゴリ** ノードの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-114">A new workflow category group appears under the **Workflow Categories** node.</span></span> <span data-ttu-id="3a5e9-115">新しいワークフロー カテゴリを右クリックし、 **プロパティ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-115">Right-click the new workflow category, and then select **Properties**.</span></span>
    + <span data-ttu-id="3a5e9-116">**プロジェクト** メニューの **新しい項目の追加** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-116">On the **Project** menu, select **Add new item**.</span></span> <span data-ttu-id="3a5e9-117">**新しい項目の追加** ダイアログ ボックスで、 **ワークフロー カテゴリ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-117">In the **Add new item** dialog box, select **Workflow category**.</span></span> <span data-ttu-id="3a5e9-118">新しいカテゴリ名を入力し、 **作成** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-118">Enter a name for the category, and then select **Create**.</span></span>

3. <span data-ttu-id="3a5e9-119">**プロパティ** シートで、必要に応じて次のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-119">On the **Properties** sheet, set the following properties, as required.</span></span>

    | <span data-ttu-id="3a5e9-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3a5e9-120">Property</span></span> | <span data-ttu-id="3a5e9-121">金額</span><span class="sxs-lookup"><span data-stu-id="3a5e9-121">Value</span></span> |
    |---|---|
    | <span data-ttu-id="3a5e9-122">氏名</span><span class="sxs-lookup"><span data-stu-id="3a5e9-122">Name</span></span> | <span data-ttu-id="3a5e9-123">ワークフロー カテゴリを参照するために使用される名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-123">Specify the name that is used to reference the workflow category.</span></span> |
    | <span data-ttu-id="3a5e9-124">ラベル</span><span class="sxs-lookup"><span data-stu-id="3a5e9-124">Label</span></span> | <span data-ttu-id="3a5e9-125">ユーザー インターフェイス (UI) でワークフロー カテゴリに使用されるラベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-125">Specify the label that is used for the workflow category in the user interface (UI).</span></span> |
    | <span data-ttu-id="3a5e9-126">ヘルプ テキスト</span><span class="sxs-lookup"><span data-stu-id="3a5e9-126">Help Text</span></span> | <span data-ttu-id="3a5e9-127">ワークフロー コンフィギュレーション UI でワークフロー カテゴリに表示される説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-127">Specify the description that is shown for the workflow category in the workflow configuration UI.</span></span> |
    | <span data-ttu-id="3a5e9-128">モジュール</span><span class="sxs-lookup"><span data-stu-id="3a5e9-128">Module</span></span> | <span data-ttu-id="3a5e9-129">ワークフローが使用できるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-129">Specify the module that the workflow will be available in.</span></span> <span data-ttu-id="3a5e9-130">既定のモジュールは **元帳** です。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-130">The default module is **Ledger**.</span></span> |

<span data-ttu-id="3a5e9-131">ワークフローカテゴリを作成した後、ワークフロー タイプをバインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-131">After you create a workflow category, a workflow type can be bound to it.</span></span> <span data-ttu-id="3a5e9-132">通常は、 **ワークフロー** ウィザードでこの手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-132">Typically, the **Workflow** wizard completes this step.</span></span> <span data-ttu-id="3a5e9-133">ただし、次の手順では、ワークフロー タイプをワークフロー カテゴリに手動でバインドする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-133">However, the following procedure explains how to manually bind a workflow type to a workflow category.</span></span>

## <a name="bind-a-workflow-type-to-a-workflow-category"></a><span data-ttu-id="3a5e9-134">ワークフロー タイプをワークフロー カテゴリにバインドする</span><span class="sxs-lookup"><span data-stu-id="3a5e9-134">Bind a workflow type to a workflow category</span></span>

1. <span data-ttu-id="3a5e9-135">アプリケーションエクスプローラーで、 **ビジネスプロセスとワークフロー** ノードを展開し、次に **ワークフロー タイプ** ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-135">In Application Explorer, expand the **Business Process and Workflow** node, and then expand the **Workflow Types** node.</span></span>
2. <span data-ttu-id="3a5e9-136">ワークフロー カテゴリにバインドするワークフロー タイプを右クリックし、 **プロパティ** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-136">Right-click the workflow type that you want to bind to a workflow category, and then select **Properties**.</span></span>
3. <span data-ttu-id="3a5e9-137">**プロパティ** シートで、 **カテゴリ** プロパティを前の手順で作成したワークフロー カテゴリに設定します。</span><span class="sxs-lookup"><span data-stu-id="3a5e9-137">On the **Properties** sheet, set the **Category** property to the workflow category that you created in the previous procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a5e9-138">参照</span><span class="sxs-lookup"><span data-stu-id="3a5e9-138">See also</span></span>

[<span data-ttu-id="3a5e9-139">ワークフロー タイプの作成</span><span class="sxs-lookup"><span data-stu-id="3a5e9-139">Creating a workflow type</span></span>](workflow-type-create.md)

[<span data-ttu-id="3a5e9-140">新しいワークフロー タイプの作成</span><span class="sxs-lookup"><span data-stu-id="3a5e9-140">Create a new workflow type</span></span>](workflow-type-create-new.md)