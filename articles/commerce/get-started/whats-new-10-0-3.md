---
title: Dynamics 365 for Retail バージョン 10.0.3 の新機能および変更された機能
description: このトピックでは Dynamics 365 Retail のプレビュー中の機能について説明します。
author: josaw1
manager: AnnBe
ms.date: 06/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-04-23
ms.dyn365.ops.version: Release 10
ms.openlocfilehash: 2c288b24339e765674ea7703365de7e4da4f382e
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004669"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-retail-version-1003"></a><span data-ttu-id="2f649-103">Dynamics 365 for Retail バージョン 10.0.3 の新機能および変更された機能</span><span class="sxs-lookup"><span data-stu-id="2f649-103">What's new or changed in Dynamics 365 for Retail version 10.0.3</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2f649-104">このトピックでは、Dynamics 365 Retail の新機能または変更された機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f649-104">This topic describes features that are new or changed in Dynamics 365 Retail.</span></span> 

<span data-ttu-id="2f649-105">Microsoft Dynamics 365 for Finance and Operations の機能については、[Finance and Operations バージョン 10.0.3 (2019 年 6 月) の新機能と変更点](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-changed-10-0-3) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f649-105">To learn about the features in Microsoft Dynamics 365 for Finance and Operations, see [What's new or changed in Finance and Operations version 10.0.3 (June 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-changed-10-0-3).</span></span>

## <a name="new-calculation-logic-for-autocharges-in-call-center-for-mixed-delivery-mode-sales-lines"></a><span data-ttu-id="2f649-106">混載配送モードの販売明細行の、コール センターにおける自動請求のための新しい計算ロジック</span><span class="sxs-lookup"><span data-stu-id="2f649-106">New calculation logic for autocharges in call center for mixed delivery mode sales lines</span></span>

<span data-ttu-id="2f649-107">この機能は既存の自動請求機能を改善し、異なる配送モードが異なるラインに適用されている混合カートに基づいて、小売企業が販売ラインに異なる料金を適用できるシナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2f649-107">This feature improves the existing autocharges functionality and support scenarios where retailers can apply different charges to sales lines based on mixed carts where different modes of delivery are being applied on different lines.</span></span>

<span data-ttu-id="2f649-108">この機能は、個々の販売ラインの特性に基づいてより現実的な料金の計算を可能にすることで、自動請求の新しい POS 機能に追加機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="2f649-108">This feature adds additional capabilities to the new POS features for autocharges by allowing a more realistic calculation of charges based on the individual sales line characteristics.</span></span>

## <a name="hq-extensions"></a><span data-ttu-id="2f649-109">HQ 拡張機能</span><span class="sxs-lookup"><span data-stu-id="2f649-109">HQ extensions</span></span> 

<span data-ttu-id="2f649-110">このリリースは Retail のカスタマイズがより簡単となる多数の拡張ポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="2f649-110">This release adds numerous extension points so that it's easier to customize Retail.</span></span> <span data-ttu-id="2f649-111">カスタム拡張シナリオをサポートするために、次の拡張ポイントが追加されました。</span><span class="sxs-lookup"><span data-stu-id="2f649-111">The following extension points have been added to support custom extension scenarios.</span></span>

- <span data-ttu-id="2f649-112">Retail Headquarters: 拡張性をサポートするためにリファクターされたメソッド。</span><span class="sxs-lookup"><span data-stu-id="2f649-112">Retail headquarters: Refactored methods to support extensibility.</span></span> <span data-ttu-id="2f649-113">これらのメソッドはリファクターされ、コマンド チェーン、デリゲート、またはメンバーへのアクセスの提供によって、拡張性をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2f649-113">These methods have been refactored to support extensibility through chain of command, delegates, or by providing access to members.</span></span>
- <span data-ttu-id="2f649-114">メソッド:</span><span class="sxs-lookup"><span data-stu-id="2f649-114">Methods:</span></span>

    - <span data-ttu-id="2f649-115">注文の取得</span><span class="sxs-lookup"><span data-stu-id="2f649-115">Order capture</span></span>
 
        1. <span data-ttu-id="2f649-116">RetailTransactionTransformer.readTransactionSalesTrans</span><span class="sxs-lookup"><span data-stu-id="2f649-116">RetailTransactionTransformer.readTransactionSalesTrans</span></span>
        1. <span data-ttu-id="2f649-117">RetailTransactionServiceOrders.createCustomerOrder</span><span class="sxs-lookup"><span data-stu-id="2f649-117">RetailTransactionServiceOrders.createCustomerOrder</span></span>
        1. <span data-ttu-id="2f649-118">Salesline.Insert</span><span class="sxs-lookup"><span data-stu-id="2f649-118">Salesline.Insert</span></span>
        1. <span data-ttu-id="2f649-119">Salesline.update</span><span class="sxs-lookup"><span data-stu-id="2f649-119">Salesline.update</span></span>

    - <span data-ttu-id="2f649-120">販売促進</span><span class="sxs-lookup"><span data-stu-id="2f649-120">Merchandising</span></span>

        1. <span data-ttu-id="2f649-121">RetailBarCodeManagement.CreateBarCodeNoDim</span><span class="sxs-lookup"><span data-stu-id="2f649-121">RetailBarCodeManagement.CreateBarCodeNoDim</span></span>
        1. <span data-ttu-id="2f649-122">EcoResProductRelationtable.validateWrite</span><span class="sxs-lookup"><span data-stu-id="2f649-122">EcoResProductRelationtable.validateWrite</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2f649-123">追加リソース</span><span class="sxs-lookup"><span data-stu-id="2f649-123">Additional resources</span></span>

### <a name="dynamics-365-april-19-release-notes"></a><span data-ttu-id="2f649-124">Dynamics 365 2019 年 4 月 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="2f649-124">Dynamics 365 April '19 release notes</span></span>

<span data-ttu-id="2f649-125">当社のビジネス アプリやプラットフォームの次回および最近リリースされた機能について検討中ですか?</span><span class="sxs-lookup"><span data-stu-id="2f649-125">Wondering about upcoming and recently released capabilities in any of our business apps or platform?</span></span>

<span data-ttu-id="2f649-126">[2019 年 4 月リリース ノートをご覧ください](https://docs.microsoft.com/business-applications-release-notes/April19/index)。</span><span class="sxs-lookup"><span data-stu-id="2f649-126">[Check out the April '19 release notes](https://docs.microsoft.com/business-applications-release-notes/April19/index).</span></span> <span data-ttu-id="2f649-127">あらゆる詳細情報を端から端まで徹底的に捕捉して一元化しました。計画を策定する際に 1 つのドキュメントでそれらの情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="2f649-127">We've captured all the details, end to end, top to bottom, in a single document that you can use for planning.</span></span>