---
title: ドメイン名のコンフィギュレーション
description: このトピックでは、Microsoft Dynamics 365 E コマース サイトのドメイン名をコンフィギュレーションする方法について説明します。
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7a988f533757cc3f8555fcf4fb724a22a5b014f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770461"
---
# <a name="configure-your-domain-name"></a><span data-ttu-id="4e6df-103">ドメイン名のコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="4e6df-103">Configure your domain name</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="4e6df-104">このトピックでは、Microsoft Dynamics 365 E コマース サイトのドメイン名をコンフィギュレーションする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e6df-104">This topic explains how to configure a domain name for a Microsoft Dynamics 365 e-commerce site.</span></span> 

## <a name="add-domains-during-e-commerce-initialization"></a><span data-ttu-id="4e6df-105">E-コマースの初期化中にドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="4e6df-105">Add domains during e-Commerce initialization</span></span>

<span data-ttu-id="4e6df-106">ドメインを E コマース環境に関連付けるには、[新しい E コマース サイトの配置](deploy-ecommerce-site.md) に記載され E コマースを初期化します。</span><span class="sxs-lookup"><span data-stu-id="4e6df-106">To associate domains with your e-commerce environment, initialize e-Commerce as described in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span> <span data-ttu-id="4e6df-107">初期化中、E コマース環境のプロビジョニングに使用する情報を提供するように求められます。</span><span class="sxs-lookup"><span data-stu-id="4e6df-107">During initialization, you're asked to provide information that will be used to provision your e-Commerce environment.</span></span> <span data-ttu-id="4e6df-108">**サポートされるホスト名**フィールドに、この環境で使用する予定のすべてのドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="4e6df-108">In the **Supported host names** field, add all the domains that you plan to use with this environment.</span></span> <span data-ttu-id="4e6df-109">複数のドメインはセミコロンで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e6df-109">Multiple domains should be separated with semi-colon.</span></span> <span data-ttu-id="4e6df-110">この方法で、全ての必要な E コーマース コンポーネントでドメインがコンフィギュレーションされ、それらは、コンテンツ配信ネットワーク (CDN) または Web サーバーからのトラフィックを切り替えて、それを E コマース フロント エンドにポイントする際に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="4e6df-110">In this way, the domains are configured in all the required e-Commerce components, and they are ready to be used when you switch traffic from your content delivery network (CDN) or web server and point it to the e-Commerce front ends.</span></span>

## <a name="add-domains-after-e-commerce-initialization"></a><span data-ttu-id="4e6df-111">E-コマースの初期化後にドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="4e6df-111">Add domains after e-Commerce initialization</span></span>

<span data-ttu-id="4e6df-112">E コマースの初期化後に新しいドメインを E コマース環境に関連付けるには、サービス要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e6df-112">To associate new domains with your e-Commerce environment after e-Commerce initialization, you must submit a service request.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4e6df-113">追加リソース</span><span class="sxs-lookup"><span data-stu-id="4e6df-113">Additional resources</span></span>

[<span data-ttu-id="4e6df-114">オンライン ストアの概要</span><span class="sxs-lookup"><span data-stu-id="4e6df-114">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="4e6df-115">E コマース サイトの作成</span><span class="sxs-lookup"><span data-stu-id="4e6df-115">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="4e6df-116">新しい E コマース サイトの配置</span><span class="sxs-lookup"><span data-stu-id="4e6df-116">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="4e6df-117">チャンネルとオンライン サイトの関連付け</span><span class="sxs-lookup"><span data-stu-id="4e6df-117">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="4e6df-118">コンテンツ配信ネットワーク (CDN) のサポートの追加</span><span class="sxs-lookup"><span data-stu-id="4e6df-118">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="4e6df-119">場所に基づく店舗検出の有効化</span><span class="sxs-lookup"><span data-stu-id="4e6df-119">Enable location-based store detection</span></span>](enable-store-detection.md)

[<span data-ttu-id="4e6df-120">ユーザー ログイン用のカスタム ページの設定</span><span class="sxs-lookup"><span data-stu-id="4e6df-120">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)