---
title: Commerce Runtime (CRT) のアーキテクチャおよびコンフィギュレーション
description: この記事では、Commerce Runtime (CRT) のアーキテクチャと構成に関する情報を提供します。 CRT は、ビジネス ロジックをカプセル化するポータブル .NET ライブラリの集合です。 コマース チャネルのエンジンとして機能します。
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Operations, Retail
ms.custom: 218654
ms.assetid: ac422f7e-bc71-4b42-b8c1-4702c6c18421
ms.search.region: Global
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: ebb1381536d32a2e94caf619f1133ce40c429f83
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004592"
---
# <a name="commerce-runtime-crt-architecture-and-configuration"></a><span data-ttu-id="1bd88-105">Commerce Runtime (CRT) のアーキテクチャおよびコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="1bd88-105">Commerce runtime (CRT) architecture and configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1bd88-106">この記事では、Commerce Runtime (CRT) のアーキテクチャと構成に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1bd88-106">This article provides information about the architecture and configuration of Commerce Runtime (CRT).</span></span> <span data-ttu-id="1bd88-107">CRT は、ビジネス ロジックをカプセル化するポータブル .NET ライブラリの集合です。</span><span class="sxs-lookup"><span data-stu-id="1bd88-107">The CRT is a collection of portable .NET libraries that encapsulate business logic.</span></span> <span data-ttu-id="1bd88-108">コマース チャネルのエンジンとして機能します。</span><span class="sxs-lookup"><span data-stu-id="1bd88-108">It serves as the engine for the commerce channel.</span></span> 

<a name="commerce-runtime-architecture"></a><span data-ttu-id="1bd88-109">Commerce Runtime のアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="1bd88-109">Commerce Runtime architecture</span></span>
-----------------------------

<span data-ttu-id="1bd88-110">次の図は、Microsoft Dynamics 365 Commerce Runtime (CRT) のコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="1bd88-110">The following diagram shows the components of the Microsoft Dynamics 365 Commerce Runtime (CRT).</span></span> 

<span data-ttu-id="1bd88-111">[![Commerce Runtime コンポーネント](./media/crt-architecture-1024x793.jpg)](./media/crt-architecture.jpg)</span><span class="sxs-lookup"><span data-stu-id="1bd88-111">[![Commerce Runtime components](./media/crt-architecture-1024x793.jpg)](./media/crt-architecture.jpg)</span></span>

### <a name="data-access"></a><span data-ttu-id="1bd88-112">データ アクセス</span><span class="sxs-lookup"><span data-stu-id="1bd88-112">Data access</span></span>

<span data-ttu-id="1bd88-113">データベースの上は、データ アクセス レイヤーです。</span><span class="sxs-lookup"><span data-stu-id="1bd88-113">On top of the database is a data access layer.</span></span> <span data-ttu-id="1bd88-114">データ アクセス レイヤーでは、生データがメモリ内のオブジェクトに変換されます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-114">In the data access layer, raw data is translated into objects in memory.</span></span> <span data-ttu-id="1bd88-115">たとえば、オブジェクトは、製品である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1bd88-115">For example, an object might be a product.</span></span> <span data-ttu-id="1bd88-116">製品は、価格や色などの属性を持ちます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-116">Products have attributes, such as price and color.</span></span> <span data-ttu-id="1bd88-117">データ アクセス レイヤーには、オブジェクトを操作するための機能があります。</span><span class="sxs-lookup"><span data-stu-id="1bd88-117">The data access layer has functions that you can use to manipulate the objects.</span></span> <span data-ttu-id="1bd88-118">ストアド プロシージャは、サービスとワークフローで使用できるデータ エンティティにデータベースからデータのパケットを渡します。</span><span class="sxs-lookup"><span data-stu-id="1bd88-118">Stored procedures pass packets of data from the database to data entities that can be used in services and workflows.</span></span> <span data-ttu-id="1bd88-119">データのパケットを更新して、コマースに追加する新しいフィールドを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-119">You can update the packets of data to include new fields that you add in Commerce.</span></span>

### <a name="services"></a><span data-ttu-id="1bd88-120">サービス</span><span class="sxs-lookup"><span data-stu-id="1bd88-120">Services</span></span>

<span data-ttu-id="1bd88-121">データ アクセス レイヤーの上は、サービス レイヤーです。</span><span class="sxs-lookup"><span data-stu-id="1bd88-121">On top of the data access layer is a services layer.</span></span> <span data-ttu-id="1bd88-122">リアルタイム データのクエリを処理します。</span><span class="sxs-lookup"><span data-stu-id="1bd88-122">Services query for real-time data.</span></span> <span data-ttu-id="1bd88-123">これらのサービスを使用して、既存の機能をカスタマイズしたり、新しい機能を含む独自のサービスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-123">You can use these services to customize existing functionality, or you can add your own services that include new functionality.</span></span>

### <a name="workflows"></a><span data-ttu-id="1bd88-124">ワークフロー</span><span class="sxs-lookup"><span data-stu-id="1bd88-124">Workflows</span></span>

<span data-ttu-id="1bd88-125">サービス レイヤーの上は、ワークフロー レイヤーです。</span><span class="sxs-lookup"><span data-stu-id="1bd88-125">On top of the services layer is the workflow layer.</span></span> <span data-ttu-id="1bd88-126">ワークフローは、業務プロセスを定義するサービスとビジネス ロジックの集合です。</span><span class="sxs-lookup"><span data-stu-id="1bd88-126">A workflow is a collection of services and business logic that, together, define business processes.</span></span> <span data-ttu-id="1bd88-127">たとえば、顧客がカートに品目を追加すると、価格の取得、検証の実行、在庫数量の確認、出荷費用の計算、税計算、および割引計算をするためワークフローを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-127">For example, when a customer adds an item to the cart, you can use a workflow to get the price, perform validation, check the inventory quantity, calculate shipping charges, calculate tax, and calculate discounts.</span></span> <span data-ttu-id="1bd88-128">コマースに含まれているワークフローを使用することも、新しいワークフローを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-128">You can use the workflows that are included in Commerce, or you can create new workflows.</span></span> <span data-ttu-id="1bd88-129">ワークフローを使用して、業務プロセスの一部としてサードパーティ製システムに接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-129">You can even use a workflow to connect to a third-party system as part of your business processes.</span></span>

### <a name="api"></a><span data-ttu-id="1bd88-130">API</span><span class="sxs-lookup"><span data-stu-id="1bd88-130">API</span></span>

<span data-ttu-id="1bd88-131">ワークフロー レイヤーーの上は、アプリケーション プログラミング インターフェイス (API) レイヤーです。</span><span class="sxs-lookup"><span data-stu-id="1bd88-131">On top of the workflow layer is the application programming interface (API) layer.</span></span> <span data-ttu-id="1bd88-132">項目に関する情報の取得、価格の計算、配送料の計算、および発注などのタスクのために API を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-132">You can use the API for tasks such as getting information about items, calculating prices, calculating shipping charges, and placing orders.</span></span> <span data-ttu-id="1bd88-133">業務プロセスに合わせて API を拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-133">You can extend the API to fit your business processes.</span></span>

## <a name="commerce-runtime-configuration"></a><span data-ttu-id="1bd88-134">Commerce Runtime のコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="1bd88-134">Commerce Runtime configuration</span></span>
<span data-ttu-id="1bd88-135">サービスは、CRT コンフィギュレーション ファイルのタイプとして列挙されます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-135">Services are enumerated as types in the CRT configuration file.</span></span> <span data-ttu-id="1bd88-136">タイプを CRT 構成ファイルに追加して、どのサービスが CRT に読み込まれるかコントロールすることができます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-136">You can add types in the CRT configuration file to control which services are loaded in the CRT.</span></span> <span data-ttu-id="1bd88-137">コンフィギュレーション ファイルに一覧表示された順序でサービスが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-137">Services are loaded in the order in which they are listed in the configuration file.</span></span> <span data-ttu-id="1bd88-138">すべての既定サービスは自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-138">All the default services are loaded automatically.</span></span> <span data-ttu-id="1bd88-139">ただし、既定のサービスのいずれかの上に新しいサービスを追加する場合、新しいサービスは既定のサービスに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="1bd88-139">However, if you add a new service above one of the default services, the new service replaces the default service.</span></span>


