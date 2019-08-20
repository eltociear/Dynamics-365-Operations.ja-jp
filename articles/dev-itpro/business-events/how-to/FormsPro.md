---
title: Microsoft Forms Pro でのビジネスイベントの使用
description: このトピックでは、製品の出荷時に調査がユーザーに送信されるシナリオについて説明します。 調査情報は Microsoft Forms Pro を使用して収集されます。
author: murrayfife
manager: AnnBe
ms.date: 07/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global for most topics. Set Country/Region name for localizations
ms.author: mufife
ms.search.validFrom: Platform update 27
ms.dyn365.ops.version: 2019-6-30
ms.openlocfilehash: f97b193ea885c98f73d77cc80c80a4e62f47ce93
ms.sourcegitcommit: 7887f24a2a91b69ca68960c45a0c12c70802d639
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "1738287"
---
# <a name="use-microsoft-forms-pro-with-business-events"></a><span data-ttu-id="51cb8-104">Microsoft Forms Pro でのビジネスイベントの使用</span><span class="sxs-lookup"><span data-stu-id="51cb8-104">Use Microsoft Forms Pro with business events</span></span>

[!include[banner](../../includes/banner.md)]

<span data-ttu-id="51cb8-105">このトピックでは、Microsoft Forms Pro を使用してビジネス イベントで使用できる調査を作成するシナリオを説明します。</span><span class="sxs-lookup"><span data-stu-id="51cb8-105">This topic goes through a scenario where Microsoft Forms Pro is used to create a survey that can be used with business events.</span></span> <span data-ttu-id="51cb8-106">特にここで説明するシナリオでは製品が出荷されたときに調査が顧客に送信されます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-106">Specifically, in the scenario that is described here, a survey is sent to customers when a product has been shipped.</span></span> <span data-ttu-id="51cb8-107">調査情報は Forms Pro を使用して収集されます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-107">The survey information is gathered by using Forms Pro.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="51cb8-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="51cb8-108">Prerequisites</span></span>

<span data-ttu-id="51cb8-109">Forms Pro を使用したことがない場合は、まず [Forms Pro のドキュメント](https://docs.microsoft.com/forms-pro/) を読んで使用方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="51cb8-109">If you haven't used Forms Pro before, you should first read the [Forms Pro documentation](https://docs.microsoft.com/forms-pro/) to learn how to use it.</span></span>

## <a name="scenario"></a><span data-ttu-id="51cb8-110">シナリオ</span><span class="sxs-lookup"><span data-stu-id="51cb8-110">Scenario</span></span>

1. <span data-ttu-id="51cb8-111">調査の作成</span><span class="sxs-lookup"><span data-stu-id="51cb8-111">Create a survey.</span></span> <span data-ttu-id="51cb8-112">調査に入力したタイトルに基づいて Forms Pro はアンケートの質問を提案します。</span><span class="sxs-lookup"><span data-stu-id="51cb8-112">Based on the title that you enter for the survey, Forms Pro suggests survey questions.</span></span>

    ![Forms Pro が提案する調査の質問](../../media/Forms_Pro1.png)

2. <span data-ttu-id="51cb8-114">販売注文は出荷を追跡します。</span><span class="sxs-lookup"><span data-stu-id="51cb8-114">The sales order tracks the shipment.</span></span> <span data-ttu-id="51cb8-115">製品が出荷されると、販売注文のステータスが **配送済** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-115">When the product has been shipped, the status of the sales order is changed to **Delivered**.</span></span>

    ![ステータスが「配送済」の販売注文](../../media/SalesOrder1.png)

    <span data-ttu-id="51cb8-117">そのため、**ステータス** フィールドの値が変更されるたびにアラートを作成するように、販売注文でアラートを構成します。</span><span class="sxs-lookup"><span data-stu-id="51cb8-117">Therefore, configure an alert on the sales order, so that an alert is created whenever the value of the **Status** field is changed.</span></span> <span data-ttu-id="51cb8-118">アラートがビジネス イベントとして送信されるように、必ず **外部に送信** オプションを **はい** に設定してください。</span><span class="sxs-lookup"><span data-stu-id="51cb8-118">Be sure to set the **Send externally** option to **Yes**, so that the alert will be sent out as a business event.</span></span>

    ![警告](../../media/Alerts1.png)

3. <span data-ttu-id="51cb8-120">販売注文のステータスが更新されるたびにビジネス イベントにトリガーされるフローを設定します (次のステップの図を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="51cb8-120">Set up the flow that will be triggered by the business event whenever the status of the sales order is updated (see the illustration in the next step).</span></span> <span data-ttu-id="51cb8-121">トリガーされた後、フローはフォーム コネクタを使用して、販売注文に登録されている顧客の電子メール アドレスに調査を送信します。</span><span class="sxs-lookup"><span data-stu-id="51cb8-121">After it's triggered, the flow will use the Forms connector to send the survey to the customer email address that is registered on the sales order.</span></span>

    <span data-ttu-id="51cb8-122">シナリオに必要な顧客の電子メール アドレスとその他の情報は、ビジネス イベント ペイロードに含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="51cb8-122">The customer email address and other information that is required for the scenario must be in the payload of the business event.</span></span> <span data-ttu-id="51cb8-123">ペイロードにこのデータがない場合は、適切なフィールドが含まれるように拡張できます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-123">If the payload doesn't have this data, it can be extended so that it includes the appropriate fields.</span></span> <span data-ttu-id="51cb8-124">詳細については [ビジネス イベント開発者ドキュメント](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/business-events/business-events-dev-doc) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51cb8-124">For more information, see the [Business events developer documentation](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/business-events/business-events-dev-doc).</span></span>

4. <span data-ttu-id="51cb8-125">このシナリオの調整には Microsoft Flow が使用されるため、Microsoft Dynamics 365 for Finance and Operations で **変更ベースのアラートが発生した場合** ビジネス イベントを有効化しないでください。</span><span class="sxs-lookup"><span data-stu-id="51cb8-125">Because Microsoft Flow is used to orchestrate this scenario, don't activate the **When a change based alert occurs** business event in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="51cb8-126">代わりに、ビジネス イベントを直接サブスクライブするように Microsoft Flow を設定します。</span><span class="sxs-lookup"><span data-stu-id="51cb8-126">Instead, set up Microsoft Flow so that it subscribes directly to the business event.</span></span>

    ![Flow](../../media/Flow1.png)

5. <span data-ttu-id="51cb8-128">フローは設定が完了するとトリガーされ、販売注文のステータスが更新されるたびに調査が送信されます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-128">After you've finished setting up the flow, it will be triggered and send out the survey whenever the sales order's status is updated.</span></span>

    ![調査](../../media/Survey1.png)

    <span data-ttu-id="51cb8-130">ユーザーが調査に入力して送信すると Forms Pro に分析が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51cb8-130">As users fill in the survey and submit it, Forms Pro shows some analytics.</span></span>

    ![Forms Pro の調査分析](../../media/Forms_Pro2.png)