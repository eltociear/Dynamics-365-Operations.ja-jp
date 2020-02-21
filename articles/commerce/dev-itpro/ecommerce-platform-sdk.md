---
title: E コマース プラットフォーム ソフトウェア開発キット (SDK)
description: このトピックでは、電子商取引プラットフォーム SDK について説明します。
author: kfend
manager: AnnBe
ms.date: 07/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations, Retail
ms.custom: 18101
ms.assetid: c0b1740b-1cbb-47c4-94e8-779cde8411af
ms.search.region: Global
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9deff4f5efb5d7c17b72d67f28a0be02dd2492ec
ms.sourcegitcommit: c0edf2f59d40bda784ea2472c21293c4a450770e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029204"
---
#  <a name="e-commerce-platform-software-development-kit-sdk"></a><span data-ttu-id="29686-103">E コマース プラットフォーム ソフトウェア開発キット (SDK)</span><span class="sxs-lookup"><span data-stu-id="29686-103">e-Commerce platform software development kit (SDK)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29686-104">このトピックでは、電子商取引プラットフォーム SDK について説明します。</span><span class="sxs-lookup"><span data-stu-id="29686-104">This topic describes the e-Commerce Platform SDK.</span></span> <span data-ttu-id="29686-105">E コマース プラットフォーム SDK は、次のコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="29686-105">The e-Commerce Platform SDK consist of the following components:</span></span>

-   <span data-ttu-id="29686-106">フレームワーク</span><span class="sxs-lookup"><span data-stu-id="29686-106">Framework</span></span>
-   <span data-ttu-id="29686-107">コントロール</span><span class="sxs-lookup"><span data-stu-id="29686-107">Controls</span></span>
-   <span data-ttu-id="29686-108">発行 (バージョン 1661 以上でサポートされます: [Retail サーバーでのサービス間認証のサポート](https://community.dynamics.com/ax/b/axforretail/archive/2016/09/24/support-for-service-to-service-authentication-in-retail-server))</span><span class="sxs-lookup"><span data-stu-id="29686-108">Publishing (only supported in version 1661 and higher: [Support for Service to Service authentication in Retail Server](https://community.dynamics.com/ax/b/axforretail/archive/2016/09/24/support-for-service-to-service-authentication-in-retail-server))</span></span>
-   <span data-ttu-id="29686-109">サンプル ASP.net Web サイト</span><span class="sxs-lookup"><span data-stu-id="29686-109">Sample ASP.net website</span></span>

## <a name="use-the-sample-aspnet-website"></a><span data-ttu-id="29686-110">サンプル asp.net web サイトの使用</span><span class="sxs-lookup"><span data-stu-id="29686-110">Use the sample asp.net website</span></span>


### <a name="download-the-retail-sdk"></a><span data-ttu-id="29686-111">Retail SDK をダウンロード</span><span class="sxs-lookup"><span data-stu-id="29686-111">Download the Retail SDK</span></span>

<span data-ttu-id="29686-112">Retail SDK は、開発環境と、Retail SDK フォルダーにある修正プログラム パッケージで使用できます。</span><span class="sxs-lookup"><span data-stu-id="29686-112">The Retail SDK is available in development environments, and in hotfix packages in a Retail SDK folder.</span></span> <span data-ttu-id="29686-113">詳細については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29686-113">For more information see:</span></span>

- <span data-ttu-id="29686-114">開発インスタンスから SDK を取得すると、構成および使用の準備がすぐに整います。</span><span class="sxs-lookup"><span data-stu-id="29686-114">If you get the SDK from a development instance, it is immediately ready for configuration and use.</span></span> <span data-ttu-id="29686-115">詳細については、「[アクセス インスタンス](../../dev-itpro/dev-tools/access-instances.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29686-115">For more information, see [Access instances](../../dev-itpro/dev-tools/access-instances.md).</span></span> 
- <span data-ttu-id="29686-116">修正プログラムから SDK を取得する場合は、修正プログラムのパッケージでは圧縮フォルダとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="29686-116">If you get the SDK from a hotfix, it is included in the hotfix package as a zipped folder.</span></span> <span data-ttu-id="29686-117">修正プログラムは累積的であり、その他のすべての修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="29686-117">Hotfixes are cumulative and include all other fixes.</span></span> 

<span data-ttu-id="29686-118">Visual Studio Online などのソース管理システムに SDK を配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="29686-118">We recommend that you put the SDK in a source control system such as Visual Studio Online.</span></span>

### <a name="use-the-retail-sdk-to-create-the-sample-aspnet-website"></a><span data-ttu-id="29686-119">Retail SDK を使用して、サンプルの asp.net Web サイトを作成します</span><span class="sxs-lookup"><span data-stu-id="29686-119">Use the Retail SDK to create the sample asp.net website</span></span>
1.  <span data-ttu-id="29686-120">管理者モードで Visual Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="29686-120">Open Visual Studio in Admin mode.</span></span> <span data-ttu-id="29686-121">これは、inetpub フォルダーにパブリッシュするために必要です。</span><span class="sxs-lookup"><span data-stu-id="29686-121">This is necessary for publishing to the inetpub folder.</span></span>
2.  <span data-ttu-id="29686-122">C:\\Microsoft Dynamics AX70\\RetailSdkOnlineStoreOnlineStore.sln を開き、すべてのフレームワーク コンポーネントを含めます。</span><span class="sxs-lookup"><span data-stu-id="29686-122">Open C:\\Microsoft Dynamics AX70\\RetailSdkOnlineStoreOnlineStore.sln contains all the framework components.</span></span>
3.  <span data-ttu-id="29686-123">サンプルのオンライン ストアは C:\\Microsoft Dynamics AX70\\RetailSdkSampleExtensionsOnlineStore にあります。</span><span class="sxs-lookup"><span data-stu-id="29686-123">The sample online store is available at C:\\Microsoft Dynamics AX70\\RetailSdkSampleExtensionsOnlineStore.</span></span>
4.  <span data-ttu-id="29686-124">Visual Studio 内から Web ストア フロントをコンパイルし、公開します。</span><span class="sxs-lookup"><span data-stu-id="29686-124">Compile and publish the web store front, from within Visual Studio.</span></span>
5.  <span data-ttu-id="29686-125">IIS マネージャーから RetailStorefrontWebSite のパスを更新します。</span><span class="sxs-lookup"><span data-stu-id="29686-125">Update the path of the RetailStorefrontWebSite from IIS Manager.</span></span>
    -  <span data-ttu-id="29686-126">既定の設定によって作成された RetailStorefrontWebSite は C:\\Microsoft Dynamics AX70\\Retail Store Front\\Package を指定することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="29686-126">Note that RetailStorefrontWebSite created by the default setup points to C:\\Microsoft Dynamics AX70\\Retail Store Front\\Package.</span></span>
    -  <span data-ttu-id="29686-127">ただし、RetailSDK から Web ストアフロントを公開すると、C:\\inetpub\\RetailWeb\\Storefront でファイルがドロップされます。</span><span class="sxs-lookup"><span data-stu-id="29686-127">However, the publishing of the web storefront from RetailSDK will drop the files at C:\\inetpub\\RetailWeb\\Storefront.</span></span>
    -  <span data-ttu-id="29686-128">したがって、RetailStorefrontWebSite の物理パスは、以前と同じポートで Web ストア フロントにアクセスする「C:\\inetpub\\RetailWeb\\Storefront」にポイントするように更新される必要があります。</span><span class="sxs-lookup"><span data-stu-id="29686-128">Hence, the physical path of the RetailStorefrontWebSite must be updated to point to “C:\\inetpub\\RetailWeb\\Storefront” to access web storefront on the same ports as before.</span></span> <span data-ttu-id="29686-129">もう 1 つのオプションは、新しい Web サイトを作成し inetpub 場所を指すことです。</span><span class="sxs-lookup"><span data-stu-id="29686-129">Another option would be to create a new website and have that point to the inetpub location.</span></span>

6.  <span data-ttu-id="29686-130">`http://localhost:55080` を参照、または `https://usnconeboxax1ecom.cloud.onebox.dynamics.com/` にアクセスして、テスト asp.net Web サイトを表示します。</span><span class="sxs-lookup"><span data-stu-id="29686-130">Browse to `http://localhost:55080` or access `https://usnconeboxax1ecom.cloud.onebox.dynamics.com/` to see a test asp.net website.</span></span>

### <a name="enabling-anonymous-access"></a><span data-ttu-id="29686-131">匿名アクセスの有効化</span><span class="sxs-lookup"><span data-stu-id="29686-131">Enabling anonymous access</span></span>

<span data-ttu-id="29686-132">E コマース Web サイトでは、匿名アクセスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="29686-132">e-Commerce websites need to enable anonymous access.</span></span> <span data-ttu-id="29686-133">これは、アプリ設定の Commerce Scale Unit web.config で web.config ファイルとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="29686-133">This is available as a web.config file in the Commerce Scale Unit web.config under app settings.</span></span> <span data-ttu-id="29686-134">Web サイトが動作するため、これが有効であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="29686-134">Please ensure that this is enabled to have the website work.</span></span> 

`
add key="IsAnonymousEnabled" value="true"
`

### <a name="externally-accessing-the-aspnet-website"></a><span data-ttu-id="29686-135">ASP.net Web サイトに外部からアクセス</span><span class="sxs-lookup"><span data-stu-id="29686-135">Externally accessing the ASP.net website</span></span>

<span data-ttu-id="29686-136">これらのいずれかが当てはまる場合は、次の設定変更が必要になります。</span><span class="sxs-lookup"><span data-stu-id="29686-136">The following configuration changes will be required if either of these applies:</span></span>

-   <span data-ttu-id="29686-137">電子商取引サーバーと同梱上にはないブラウザー内から Web ストア フロントにアクセスしています。</span><span class="sxs-lookup"><span data-stu-id="29686-137">If you are accessing web storefront from within a browser that is not on the same box as the e-Commerce server.</span></span>
-   <span data-ttu-id="29686-138">電子商取引サーバーと Commerce Scale Unit が 2 つの異なるボックス上にある場合。</span><span class="sxs-lookup"><span data-stu-id="29686-138">If the e-Commerce server and Commerce Scale Unit are on two different boxes.</span></span>

<span data-ttu-id="29686-139">RetailStorefrontWebSite の web.config ファイル内の "retailServerUrl" を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29686-139">You will need to update the “retailServerUrl” inside the web.config file of the RetailStorefrontWebSite.</span></span> <span data-ttu-id="29686-140">ローカル ホストの代わりにマシン名を使用するには、次の 2 つのフィールドを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29686-140">The following two fields will need to be updated to use the machine name instead of local host:</span></span>

- <span data-ttu-id="29686-141">retailServerUrl=<http://localhost:35080/RetailServer/V1></span><span class="sxs-lookup"><span data-stu-id="29686-141">retailServerUrl=<http://localhost:35080/RetailServer/V1></span></span>
- <span data-ttu-id="29686-142">&lt;キーの追加 ="RetailServerRoot" 値 ="<http://localhost:35080/RetailServer/V1>" /&gt;</span><span class="sxs-lookup"><span data-stu-id="29686-142">&lt;add key="RetailServerRoot" value="<http://localhost:35080/RetailServer/V1>" /&gt;</span></span>

<span data-ttu-id="29686-143">Web ストア フロントを HTTPS 経由でアクセスする場合は、前述の Url を同等の HTTPS に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29686-143">If you are accessing the web storefront over HTTPS, then you will need to update the above URLs to the HTTPS equivalent.</span></span>

### <a name="operating-unit-or-channel-configuration"></a><span data-ttu-id="29686-144">作業単位またはチャンネルのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="29686-144">Operating unit or channel configuration</span></span>

<span data-ttu-id="29686-145">E コマースの Web サイトは、web.configで指定された作業単位数 (チャネル) で動作します。これを変更するには、以下の OU \# を変更します。</span><span class="sxs-lookup"><span data-stu-id="29686-145">The e-Commerce website will operate on an operating unit number(channel) specified in the web.config. To change it, change the OU \# below.</span></span> <span data-ttu-id="29686-146">Fabrikam はデモ データ内で「077」であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="29686-146">Note that Fabrikam is “077” in the demo data.</span></span> <span data-ttu-id="29686-147">RetailStorefrontWebSite の web.config 内の "retailServerUrl" を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29686-147">You will need to update the “retailServerUrl” inside web.config of the RetailStorefrontWebSite.</span></span> <span data-ttu-id="29686-148">ローカル ホストの代わりにマシン名を使用するには、次の 2 つのフィールドを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29686-148">The following two fields will need to be updated to use the machine name instead of local host:</span></span>

    <ecommerceControls productUrlFormat="/Pages/ProductDetails/ProductDetails.aspx?itemId={0}" retailServerUrl="http://localhost:35080/RetailServer/V1" operatingUnitNumber="068">

    <add key="OperatingUnitNumber" value="068" />

## <a name="configure-authentication-providers"></a><span data-ttu-id="29686-149">認証プロバイダーのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="29686-149">Configure authentication providers</span></span>
### <a name="authentication-providers-that-you-are-using"></a><span data-ttu-id="29686-150">使用している認証プロバイダー</span><span class="sxs-lookup"><span data-stu-id="29686-150">Authentication providers that you are using</span></span>

<span data-ttu-id="29686-151">E コマース プラットフォームは、認証のためのメカニズムとして OpenID を使用します。</span><span class="sxs-lookup"><span data-stu-id="29686-151">The e-Commerce platform uses OpenID as the mechanism for authentication.</span></span> <span data-ttu-id="29686-152">以下のテーブルに選択した任意の OpenID プロバイダーを登録することにより、この作業を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="29686-152">You can register any OpenID provider of your choice to the tables below to make this work.</span></span> <span data-ttu-id="29686-153">必要に応じて、テストにログインすることができます。</span><span class="sxs-lookup"><span data-stu-id="29686-153">You can then log in to test as needed.</span></span>

1.  <span data-ttu-id="29686-154">web.config ファイルを編集し、次のように変更してください。</span><span class="sxs-lookup"><span data-stu-id="29686-154">Edit the web.config file and change it to the following.</span></span>

        redirectUrl=https://usnconeboxax1ecom.cloud.onebox.dynamics.com/en/Pages/OauthV2Redirect/OauthV2Redirect.aspx

    <span data-ttu-id="29686-155">後続のステップは、追加プロバイダーを登録する場合にのみ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="29686-155">The subsequent steps should only be done to register additional providers.</span></span>

2.  <span data-ttu-id="29686-156">**Retail 共有パラメーター -&gt; ID プロバイダーを開く**フォームは、追加プロバイダーを登録するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="29686-156">The **Retail Shared Parameters -&gt; Open ID Providers** form can be used to register additional providers.</span></span>
3.  <span data-ttu-id="29686-157">配送スケジュール 1110 を実行します。</span><span class="sxs-lookup"><span data-stu-id="29686-157">Run distribution schedule 1110.</span></span>
