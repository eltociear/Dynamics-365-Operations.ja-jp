---
title: ビジネス ドキュメント管理の概要
description: このトピックでは、ER フレームワークのビジネス ドキュメント管理機能を使用する方法について説明します。
author: NickSelin
manager: AnnBe
ms.date: 08/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d756436373b10f9538788a3292135a73c9c45d04
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873156"
---
# <a name="business-document-management-overview"></a><span data-ttu-id="d0abd-103">ビジネス ドキュメント管理の概要</span><span class="sxs-lookup"><span data-stu-id="d0abd-103">Business document management overview</span></span>

<span data-ttu-id="d0abd-104">ビジネス ユーザーは、[電子申告 (ER) フレームワーク](general-electronic-reporting.md) を使用し、さまざまな国 / 地域の法的要件に従って発信ドキュメントの形式を構成できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-104">Business users use the [Electronic reporting (ER) framework](general-electronic-reporting.md) to configure formats for outbound documents in accordance with the legal requirements of various countries/regions.</span></span> <span data-ttu-id="d0abd-105">また、生成されるドキュメントに配置されるアプリケーション データを指定するため、データフローを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-105">Users can also define the dataflow to specify what application data is placed in generated documents.</span></span> <span data-ttu-id="d0abd-106">ER フレームワークは、定義済みテンプレートを使用して、Microsoft Office 形式 (Excel Workbooks または Word ドキュメント) で発信ドキュメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-106">The ER framework generates outbound documents in Microsoft Office formats (Excel workbooks or Word documents) by using predefined templates.</span></span> <span data-ttu-id="d0abd-107">必要なドキュメントが生成されるときに、構成されたデータフローに従って、テンプレートに必要なデータが設定されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-107">The templates are populated with required data in accordance to configured dataflow while required documents are generated.</span></span> <span data-ttu-id="d0abd-108">特定の発信ドキュメントを生成するために、ER ソリューションの一部として、構成された各形式を公開できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-108">Each configured format can be published as part of an ER solution to generate specific outbound documents.</span></span> <span data-ttu-id="d0abd-109">これは、異なる発信ドキュメントを生成するために使用できるテンプレートを含める ER 形式コンフィギュレーションによって、表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-109">This is represented by an ER format configuration that can contain templates you can use to generate different outbound documents.</span></span> <span data-ttu-id="d0abd-110">ビジネス ユーザーは、このフレームワークを使用して、必要なビジネス ドキュメントを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-110">Business users can use this framework to manage required business documents.</span></span>

<span data-ttu-id="d0abd-111">**ビジネス ドキュメント管理**は、ER フレームワークを基盤に構築されており、ビジネス ユーザーが Microsoft Office 365 サービスまたは適切な Microsoft Office デスクトップ アプリケーションを使用して、ビジネス ドキュメント テンプレートを編集することができます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-111">**Business document management** is built on top of the ER framework and enables business users to edit business document templates by using Microsoft Office 365 service or appropriate Microsoft Office desktop application.</span></span> <span data-ttu-id="d0abd-112">ドキュメントを編集する際には、ビジネス ドキュメントのデザインを変更したり、ソース コードの変更および新しい配置無しで、Dynamics 365 for Finance and Operations 内からの追加データ用のプレス ホルダーを追加したりします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-112">Edits to the documents might include changing business document designs and adding placeholders for additional data from within Dynamics 365 for Finance and Operations without source code changes and new deployments.</span></span> <span data-ttu-id="d0abd-113">ER フレームワークには、ビジネス ドキュメントのテンプレートを更新するために必要な知識がありません。</span><span class="sxs-lookup"><span data-stu-id="d0abd-113">No knowledge of the ER framework is required to update templates of business documents.</span></span>

> [!NOTE]
> <span data-ttu-id="d0abd-114">ビジネス ドキュメント管理を使用すると、注文書や請求書などのビジネス ドキュメントの作成に使用されるテンプレートを変更できます。テンプレートが変更され新しいバージョンが発行されている間に、このバージョンは必要なビジネス ドキュメントの生成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-114">Be aware that Business document management allows you to modify templates that are used to produce business documents such as orders, invoices, etc. While a template has been modified and a new version of it has been published, this version is used to generate required business documents.</span></span> <span data-ttu-id="d0abd-115">ビジネス ドキュメント管理を使用して、既に生成されたビジネス ドキュメントを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0abd-115">Business document management cannot be used to modify already generated business documents.</span></span>

## <a name="supported-deployments"></a><span data-ttu-id="d0abd-116">サポートされている配置</span><span class="sxs-lookup"><span data-stu-id="d0abd-116">Supported deployments</span></span>

<span data-ttu-id="d0abd-117">現在、ビジネス ドキュメント管理の機能はクラウド配置に対してのみ実装されています。</span><span class="sxs-lookup"><span data-stu-id="d0abd-117">Currently, the Business document management feature is implemented only for cloud deployments.</span></span> <span data-ttu-id="d0abd-118">この機能が、オンプレミス配置にとって重要な場合は、[アイデア](https://experience.dynamics.com/ideas/) サイトからフィードバックを提供し通知します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-118">If this feature is critical to your on-premises deployment, let us know by providing feedback on the [Ideas](https://experience.dynamics.com/ideas/) site.</span></span>

## <a name="supported-microsoft-office-applications"></a><span data-ttu-id="d0abd-119">サポートされる Microsoft Office アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d0abd-119">Supported Microsoft Office applications</span></span>

<span data-ttu-id="d0abd-120">Microsoft Office のデスクトップ アプリケーションを使用して、Excel または Word 形式でテンプレートを編集するビジネス ドキュメント管理を使うには、Microsoft Office の 2010 またはそれ以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0abd-120">To use Business document management for editing templates in Excel or Word formats by using Microsoft Office desktop applications, you must have Microsoft Office 2010 or later installed.</span></span> <span data-ttu-id="d0abd-121">これは Finance and Operations のクラウドおよびオンプレミス配置でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d0abd-121">This is supported in cloud and on-premises deployment of Finance and Operations.</span></span>

## <a name="business-document-availability"></a><span data-ttu-id="d0abd-122">ビジネス ドキュメントの使用可能性</span><span class="sxs-lookup"><span data-stu-id="d0abd-122">Business document availability</span></span>

<span data-ttu-id="d0abd-123">次のレポートは、Excel ベースのテンプレートと共に、パブリック プレビューのリリースで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-123">The following reports, with Excel-based templates, will available with the release of the public preview:</span></span>

<span data-ttu-id="d0abd-124">**売掛金勘定** (2019 年 8 月)</span><span class="sxs-lookup"><span data-stu-id="d0abd-124">**Accounts receivable** (August 2019)</span></span>

- <span data-ttu-id="d0abd-125">販売前請求書</span><span class="sxs-lookup"><span data-stu-id="d0abd-125">Sales advance invoice</span></span>
- <span data-ttu-id="d0abd-126">販売注文梱包明細票</span><span class="sxs-lookup"><span data-stu-id="d0abd-126">Sales order packing slip</span></span>

<span data-ttu-id="d0abd-127">**買掛金勘定** (2019 年 8 月)</span><span class="sxs-lookup"><span data-stu-id="d0abd-127">**Accounts payable** (August 2019)</span></span>

- <span data-ttu-id="d0abd-128">仕入事前請求書</span><span class="sxs-lookup"><span data-stu-id="d0abd-128">Purchase advance invoice</span></span>
- <span data-ttu-id="d0abd-129">発注書</span><span class="sxs-lookup"><span data-stu-id="d0abd-129">Purchase order</span></span>
- <span data-ttu-id="d0abd-130">発注書の梱包明細</span><span class="sxs-lookup"><span data-stu-id="d0abd-130">Purchase order packing slip</span></span>

<span data-ttu-id="d0abd-131">さらに多くのレポートが使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-131">More reports will become available.</span></span> <span data-ttu-id="d0abd-132">追加のレポートに関する特別な通知は、個別に送信されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-132">Special notifications about additional reports will be sent separately.</span></span> 

<span data-ttu-id="d0abd-133">2019 年 10 月のリリースに予定されているすべてのレポートの全一覧は、[Word および Excel のコンフィギュレーション可能なビジネス ドキュメント レポート](https://docs.microsoft.com/en-us/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details) に表示されています。</span><span class="sxs-lookup"><span data-stu-id="d0abd-133">A complete list of all the reports planned for the October 2019 release can be found in [Configurable business documents reporting in Word and Excel](https://docs.microsoft.com/en-us/dynamics365-release-plan/2019wave2/dynamics365-finance-operations/configurable-business-documents-reporting-word-excel-pdf#feature-details).</span></span>

# <a name="example-enable-configure-and-use-business-document-management"></a><span data-ttu-id="d0abd-134">例: ビジネス ドキュメント管理の有効化、コンフィギュレーション、および使用</span><span class="sxs-lookup"><span data-stu-id="d0abd-134">Example: Enable, configure, and use Business document management</span></span>

<span data-ttu-id="d0abd-135">この機能の詳細を知るには、このトピックの例を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-135">To learn more about this feature, complete the example in this topic.</span></span>

## <a name="configure-er-parameters"></a><span data-ttu-id="d0abd-136">ER パラメーターのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d0abd-136">Configure ER parameters</span></span>

<span data-ttu-id="d0abd-137">ビジネス ドキュメント管理は ER フレームワーク上に構築されているので、ER パラメータをコンフィギュレーションして、ビジネス ドキュメント管理の操作を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-137">Because Business document management is built on top of the ER framework, you must configure the ER parameters to start working with Business document management.</span></span> <span data-ttu-id="d0abd-138">これを行うには、[ER フレームワークをコンフィギュレーション](electronic-reporting-er-configure-parameters.md) で説明されているように、ER パラメータを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-138">To do this, you need to set up the ER parameters as described in [Configure the ER framework](electronic-reporting-er-configure-parameters.md).</span></span> <span data-ttu-id="d0abd-139">[コンフィギュレーション プロバイダーの作成および有効としてマーク](tasks/er-configuration-provider-mark-it-active-2016-11.md) で説明されているように、新しいコンフィギュレーション プロバイダーを追加する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-139">You also need to add a new configuration provider as described in [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

![ER ワークスペース](./media/BDM-Overview-ERSetting.png)

## <a name="import-er-solutions"></a><span data-ttu-id="d0abd-141">ER ソリューションのインポート</span><span class="sxs-lookup"><span data-stu-id="d0abd-141">Import ER solutions</span></span>

<span data-ttu-id="d0abd-142">ビジネス ドキュメント テンプレートを含む ER コンフィギュレーションは、Finance and Operations の現在のインスタンスにインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-142">You must import ER configurations that contain business documents templates to the current instance of Finance and Operations.</span></span> <span data-ttu-id="d0abd-143">この手順を実行するには、次のファイルをダウンロードしてローカルに保存します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-143">Download and locally store the following files to complete this procedure.</span></span>

<span data-ttu-id="d0abd-144">**サンプル ER 顧客請求ソリューション**</span><span class="sxs-lookup"><span data-stu-id="d0abd-144">**Sample ER customer invoicing solution**</span></span>

| <span data-ttu-id="d0abd-145">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="d0abd-145">**File**</span></span>                                  | <span data-ttu-id="d0abd-146">**コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="d0abd-146">**Content**</span></span>                                |
|-------------------------------------------|--------------------------------------------|
| <span data-ttu-id="d0abd-147">Customer invoicing model.version.2.xml</span><span class="sxs-lookup"><span data-stu-id="d0abd-147">Customer invoicing model.version.2.xml</span></span>    | [<span data-ttu-id="d0abd-148">ER データ モデル構成</span><span class="sxs-lookup"><span data-stu-id="d0abd-148">ER data model configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="d0abd-149">Customer FTI report (GER).version.2.3.xml</span><span class="sxs-lookup"><span data-stu-id="d0abd-149">Customer FTI report (GER).version.2.3.xml</span></span> | [<span data-ttu-id="d0abd-150">自由書式の請求書 ER 形式コンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d0abd-150">Free text invoice ER format configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

<span data-ttu-id="d0abd-151">**サンプル ER 支払 チェック ソリューション**</span><span class="sxs-lookup"><span data-stu-id="d0abd-151">**Sample ER payment checks solution**</span></span>

| <span data-ttu-id="d0abd-152">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="d0abd-152">**File**</span></span>                                  | <span data-ttu-id="d0abd-153">**コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="d0abd-153">**Content**</span></span>                                |
|-------------------------------------------|--------------------------------------------|
| <span data-ttu-id="d0abd-154">Model for cheques.version.10.xml</span><span class="sxs-lookup"><span data-stu-id="d0abd-154">Model for cheques.version.10.xml</span></span>          | [<span data-ttu-id="d0abd-155">ER データ モデル構成</span><span class="sxs-lookup"><span data-stu-id="d0abd-155">ER data model configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="d0abd-156">Cheques printing format.version.10.9.xml</span><span class="sxs-lookup"><span data-stu-id="d0abd-156">Cheques printing format.version.10.9.xml</span></span>  | [<span data-ttu-id="d0abd-157">支払小切手 ER 形式コンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d0abd-157">Payment cheque ER format configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

<span data-ttu-id="d0abd-158">**サンプル ER 対外取引ソリューション**</span><span class="sxs-lookup"><span data-stu-id="d0abd-158">**Sample ER foreign trade solution**</span></span>

| <span data-ttu-id="d0abd-159">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="d0abd-159">**File**</span></span>                                  | <span data-ttu-id="d0abd-160">**コンテンツ**</span><span class="sxs-lookup"><span data-stu-id="d0abd-160">**Content**</span></span>                                |
|-------------------------------------------|--------------------------------------------|
| <span data-ttu-id="d0abd-161">Intrastat model.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="d0abd-161">Intrastat model.version.1.xml</span></span>             | [<span data-ttu-id="d0abd-162">ER データ モデル構成</span><span class="sxs-lookup"><span data-stu-id="d0abd-162">ER data model configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="d0abd-163">Intrastat report.version.1.9.xml</span><span class="sxs-lookup"><span data-stu-id="d0abd-163">Intrastat report.version.1.9.xml</span></span>          | [<span data-ttu-id="d0abd-164">イントラスタット管理レポート ER 形式コンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d0abd-164">Intrastat control report ER format configuration</span></span>](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

<span data-ttu-id="d0abd-165">各ファイルをインポートするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-165">Use the following procedure to import each file.</span></span> <span data-ttu-id="d0abd-166">対応する ER *形式*コンフィギュレーションをインポートする前に、上のテーブルにある各 ER ソリューションの ER *データ モデル*コンフィギュレーションをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-166">Import the ER *data model* configuration of each ER solution in the tables above before you import the corresponding ER *format* configuration.</span></span>

1. <span data-ttu-id="d0abd-167">**組織管理** \> **電子申告** \> **コンフィギュレーション**ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-167">Open the **Organization administration** \> **Electronic reporting** \> **Configurations** page.</span></span>
2. <span data-ttu-id="d0abd-168">ページ上部で、**交換**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-168">On the top of the page, select **Exchange**.</span></span>
3. <span data-ttu-id="d0abd-169">**XML ファイルから読み込む**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-169">Select **Load from XML file**.</span></span>
4. <span data-ttu-id="d0abd-170">**参照**を選択して、必要な XML ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-170">Select **Browse** to load the required XML file.</span></span>
5. <span data-ttu-id="d0abd-171">**OK** を選択して、コンフィギュレーションのインポートを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-171">Select **OK** to confirm configuration’s import.</span></span>

![ER コンフィギュレーション ページ](./media/BDM-Overview-ERSolutions.png)

<span data-ttu-id="d0abd-173">ER コンフィギュレーションのインポートの詳細については、[ER コンフィギュレーション ライフサイクルの管理](general-electronic-reporting-manage-configuration-lifecycle.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0abd-173">For more information about importing ER configurations, see [Manage the ER configuration lifecycle](general-electronic-reporting-manage-configuration-lifecycle.md).</span></span>

## <a name="enable-business-document-management"></a><span data-ttu-id="d0abd-174">ビジネス ドキュメント管理の有効</span><span class="sxs-lookup"><span data-stu-id="d0abd-174">Enable Business document management</span></span>

<span data-ttu-id="d0abd-175">ビジネス ドキュメント管理を開始するには、**機能管理**ワークスペースを開いて、**ビジネス ドキュメント管理**機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-175">To start Business document management, you need to open the **Feature management** workspace and enable the **Business document management** feature.</span></span>

<span data-ttu-id="d0abd-176">すべての法人に対してビジネス ドキュメント管理の機能を有効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-176">Use the following procedure to enable Business document management functionality for all legal entities.</span></span>

1. <span data-ttu-id="d0abd-177">**機能管理**ワークスペースを開きます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-177">Open the **Feature management** workspace.</span></span>
2. <span data-ttu-id="d0abd-178">**新規**タブで、一覧から**ビジネス ドキュメント管理**の機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-178">On the **New** tab, select the **Business document management** feature in the list.</span></span>
3. <span data-ttu-id="d0abd-179">**直ちに有効化**を選択し、選択した機能をオンにします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-179">Select **Enable now** to turn on the selected feature.</span></span>
4. <span data-ttu-id="d0abd-180">ページを更新して、新しい機能にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-180">Refresh the page to access the new feature.</span></span>

![機能管理ワークスペース](./media/BDM-Overview-FMEnabling.png)

<span data-ttu-id="d0abd-182">新規機能の有効化についての詳細は、[機能管理の概要](../../fin-and-ops/get-started/feature-management/feature-management-overview.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0abd-182">For more information about activating new features, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="configure-parameters"></a><span data-ttu-id="d0abd-183">パラメータのコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d0abd-183">Configure parameters</span></span>

<span data-ttu-id="d0abd-184">次のセクションの情報を使用して、ビジネス ドキュメント管理の基本パラメータを設定します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-184">Use the information in the following sections to set up the basic parameters for Business document management.</span></span>

### <a name="prerequisites-for-parameter-setup"></a><span data-ttu-id="d0abd-185">パラメーター セットアップの前提条件</span><span class="sxs-lookup"><span data-stu-id="d0abd-185">Prerequisites for parameter setup</span></span>
<span data-ttu-id="d0abd-186">ビジネス ドキュメント管理を設定する前に、ドキュメント管理のフレームワークで必要なドキュメント タイプを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-186">Before you can set up Business document management, you must set up the required document type in the Document management framework.</span></span> <span data-ttu-id="d0abd-187">このドキュメント タイプは、ER レポート用のテンプレートとして使用される、Office 形式 (Excel および Word) のドキュメントの一時的な保管場所を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-187">This document type is used to specify a temporary storage of documents in Office formats (Excel and Word) that are used as templates for ER reports.</span></span> <span data-ttu-id="d0abd-188">一時保管テンプレートは、Office デスクトップ アプリケーションを使用して編集できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-188">The temporary storage template can be edited by using the Office desktop applications.</span></span>

<span data-ttu-id="d0abd-189">このドキュメント タイプについては、次の属性値を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-189">For this document type, the following attribute values must be selected.</span></span>

| <span data-ttu-id="d0abd-190">**属性名**</span><span class="sxs-lookup"><span data-stu-id="d0abd-190">**Attribute name**</span></span>  | <span data-ttu-id="d0abd-191">**属性値**</span><span class="sxs-lookup"><span data-stu-id="d0abd-191">**Attribute value**</span></span>   |
|---------------------|-----------------------|
| <span data-ttu-id="d0abd-192">クラス</span><span class="sxs-lookup"><span data-stu-id="d0abd-192">Class</span></span>               | <span data-ttu-id="d0abd-193">ファイルの添付</span><span class="sxs-lookup"><span data-stu-id="d0abd-193">Attach file</span></span>           |
| <span data-ttu-id="d0abd-194">グループ化</span><span class="sxs-lookup"><span data-stu-id="d0abd-194">Group</span></span>               | <span data-ttu-id="d0abd-195">ファイル</span><span class="sxs-lookup"><span data-stu-id="d0abd-195">File</span></span>                  |
| <span data-ttu-id="d0abd-196">保管場所</span><span class="sxs-lookup"><span data-stu-id="d0abd-196">Location</span></span>            | <span data-ttu-id="d0abd-197">SharePoint</span><span class="sxs-lookup"><span data-stu-id="d0abd-197">SharePoint</span></span>            |

<span data-ttu-id="d0abd-198">必要なドキュメント管理パラメータおよびドキュメント タイプの設定方法については、[ドキュメント管理のコンフィギュレーション](../../fin-and-ops/organization-administration/configure-document-management.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0abd-198">For information about how to set up the required document management parameters and document types, see [Configure document management](../../fin-and-ops/organization-administration/configure-document-management.md).</span></span>

![ドキュメント管理のドキュメント タイプを設定](./media/BDM-Overview-DMSetting.png)

### <a name="set-up-parameters"></a><span data-ttu-id="d0abd-200">パラメータの設定</span><span class="sxs-lookup"><span data-stu-id="d0abd-200">Set up parameters</span></span>

<span data-ttu-id="d0abd-201">基本ビジネス ドキュメント管理パラメータは、**ビジネス ドキュメント パラメーター**ページで設定できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-201">Basic Business document management parameters can be set up on the **Business document parameters** page.</span></span> <span data-ttu-id="d0abd-202">特定のユーザーのみがページにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-202">Only specific users can access the page.</span></span> <span data-ttu-id="d0abd-203">これには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-203">This includes:</span></span>

- <span data-ttu-id="d0abd-204">**システム管理者**ロールに割り当てられるユーザー。</span><span class="sxs-lookup"><span data-stu-id="d0abd-204">Users who are assigned to the **System administrator** role.</span></span>
- <span data-ttu-id="d0abd-205">職務権限を実行するようコンフィギュレーションされているロールに割り当てられているユーザー、**ビジネス ドキュメント パラメーターを維持** (AOT 名 **ERBDMaintainParameters**)。</span><span class="sxs-lookup"><span data-stu-id="d0abd-205">Users who are assigned to any role that is configured to perform the duty, **Maintain Business document management parameters** (AOT name **ERBDMaintainParameters**).</span></span>

<span data-ttu-id="d0abd-206">すべての法人に対して基本パラメーターを設定するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-206">Use the following procedure to set up the basic parameters for all legal entities.</span></span>

1. <span data-ttu-id="d0abd-207">**ビジネス ドキュメント パラメーター**ページへのアクセス権を持つユーザーとして、Finance and Operations にログインします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-207">Sign in to Finance and Operations as a user with access to the **Business document parameters** page.</span></span>
2. <span data-ttu-id="d0abd-208">**組織管理** \> **電子レポート** \> **ビジネス ドキュメント管理** \> **ビジネス ドキュメント パラメーター**の順で移動します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-208">Go to **Organization administration** \> **Electronic reporting** \> **Business document management** \> **Business document parameters**.</span></span>
3.  <span data-ttu-id="d0abd-209">**ビジネス ドキュメント パラメーター**ページの**添付ファイル**タブから、**SharePoint ドキュメント タイプ**フィールドで、Office デスクトップ アプリケーションを使用して編集する間に、Office 形式のテンプレートを一時的に保存する際に使用するドキュメント タイプを定義します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-209">On the **Business document parameters** page, on the **Attachments** tab, in the **SharePoint document type** field, define the document type that should be used to temporarily store templates in Office formats while they are edited using the Office desktop applications.</span></span> 

> [!NOTE]
> <span data-ttu-id="d0abd-210">このパラメーターでは、SharePoint 場所を使用してコンフィギュレーションされているタイプのドキュメントのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-210">Only document types that are configured using a SharePoint location are available for this parameter.</span></span>

![ビジネス ドキュメント管理パラメーターの設定](./media/BDM-Overview-BDMSetting.png)

<span data-ttu-id="d0abd-212">選択したドキュメント タイプは会社固有であり、選択したドキュメント タイプがコンフィギュレーションされている会社のビジネス ドキュメント管理をユーザーが使用する場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-212">The selected document type is company-specific and will be used when the user is working with Business document management in the company for which the selected document type is configured.</span></span> <span data-ttu-id="d0abd-213">ユーザーがもう一つの会社のビジネス ドキュメント管理を使用している際、この会社にコンフィギュレーションされていない場合は、選択された同じドキュメント タイプが使われます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-213">When the user is working with Business document management in another company, the same selected document type will be used if one has not been configured for this company.</span></span> <span data-ttu-id="d0abd-214">ドキュメント タイプが構成されている際、**SharePoint ドキュメント**タイプ フィールドで選択されたものの代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-214">When a document type has been configured, it will be used instead of the one selected in the **SharePoint document type** field.</span></span>

## <a name="configure-access-permissions"></a><span data-ttu-id="d0abd-215">アクセス許可のコンフィギュレーション</span><span class="sxs-lookup"><span data-stu-id="d0abd-215">Configure access permissions</span></span>

<span data-ttu-id="d0abd-216">既定では、ビジネス ドキュメント管理のアクセス許可が有効になっていない場合、ビジネス ドキュメント管理のワークスペースへのアクセス権を持つすべてのユーザーには、 Finance and Operations で使用可能な ER ソリューション テンプレートがすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-216">By default, when access to Business document management permissions is not enabled, every user with access to the Business document management workspace will see all of the ER solution templates that are available in Finance and Operations.</span></span> <span data-ttu-id="d0abd-217">ビジネス ドキュメント管理のワークスペースには、**ビジネス ドキュメント タイプ**タグによってマークされた ER 形式コンフィギュレーションに存在するテンプレートのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-217">The Business document management workspace will show only those templates that reside in ER format configurations and that are marked by a **Business document type** tag.</span></span>

![ER コンフィギュレーション ページ](./media/BDM-Overview-ERFormatTags.png)

<span data-ttu-id="d0abd-219">ビジネス ドキュメント管理のワークスペースで使用できるテンプレートの一覧は、アクセス許可をコンフィギュレーションすることによって制限できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-219">The list of templates available in the Business document management workspace can be restricted by configuring access permissions.</span></span> <span data-ttu-id="d0abd-220">異なるテンプレートがさまざまなビジネス ドメイン (機能領域) のビジネス ドキュメントを作成するため使用されることは重要で、特定のユーザーがビジネス ドキュメント管理のワークスペースで編集するために別のテンプレートにアクセスできるように許可します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-220">This may be important when different templates are used to produce business documents for different business domains (functional areas), and you want to allow specific users access to different templates for editing in the Business document management workspace.</span></span>

<span data-ttu-id="d0abd-221">ビジネス ドキュメント管理のアクセス許可は、**アクセス許可のコンフィギュレーター**に対して設定できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-221">Business document management access permissions can be set on the **Configurator of access permissions**.</span></span> <span data-ttu-id="d0abd-222">次のユーザーのみがページにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-222">Only the following users can access the page:</span></span>

- <span data-ttu-id="d0abd-223">**システム管理者**ロールに割り当てられるユーザー。</span><span class="sxs-lookup"><span data-stu-id="d0abd-223">Users assigned to the **System administrator** role.</span></span>
- <span data-ttu-id="d0abd-224">職務権限を実行するようにコンフィギュレーションされている他のロールに割り当てられたユーザー、**編集用にビジネス ドキュメント テンプレートにアクセスするよう許可をコンフィギュレーション** (AOT 名 **ERBDTemplatesSecurity**)。</span><span class="sxs-lookup"><span data-stu-id="d0abd-224">Users assigned to any other role that is configured to perform the duty, **Configure permissions to access Business document templates for editing** (AOT name **ERBDTemplatesSecurity**).</span></span>

<span data-ttu-id="d0abd-225">すべての法人に対してビジネス ドキュメント管理の許可のアクセス設定をするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-225">Use the following procedure to set up the access Business document management permissions for all legal entities.</span></span>

1. <span data-ttu-id="d0abd-226">**アクセス許可のコンフィギュレーター**ページへのアクセス権を持つユーザーとして、Finance and Operations にログインします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-226">Sign in to Finance and Operations as a user with access to the **Configurator of access permissions** page.</span></span>
2. <span data-ttu-id="d0abd-227">**組織管理** \> **電子レポート** \> **ビジネス ドキュメント管理** \> **アクセス許可の管理**の順で移動します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-227">Go to **Organization administration** \> **Electronic reporting** \> **Business document management** \> **Manage access permissions**.</span></span>

<span data-ttu-id="d0abd-228">ビジネス ドキュメント管理のアクセス許可の使用が現在有効になっていないことを知らせる通知に、注意してください。</span><span class="sxs-lookup"><span data-stu-id="d0abd-228">Pay attention to the notification informing you that the usage of access permissions for Business document management is currently not enabled.</span></span>

![ビジネス ドキュメント管理のアクセス許可ページのコンフィギュレーター](./media/BDM-Overview-TemplatesAccess1.png)

<span data-ttu-id="d0abd-230">この設定では、**ビジネス ドキュメント テンプレートの管理** (AOT 名 **ERBDManageTemplates**) の職務権限を実行するようにコンフィギュレーションされているセキュリティ ロールに割り当てられているすべてのユーザーが、ビジネス ドキュメント管理のワークスペースを開くことができます。そして、Finance and Operations で有効なすべてのテンプレートを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-230">With this setting, every user assigned to any security role that is configured to perform the **Manage Business document templates** (AOT name **ERBDManageTemplates**) duty is able to open the Business document management workspace and can edit any template that is available in Finance and Operations.</span></span>

<span data-ttu-id="d0abd-231">次の図は、**売掛金管理係**ロールに割り当てられたユーザーのビジネス ドキュメント管理のワークスペースで使用できるものを示しています。</span><span class="sxs-lookup"><span data-stu-id="d0abd-231">The following graphic shows what is available in the Business document management workspace for users assigned to the **Accounts receivable clerk** role.</span></span> <span data-ttu-id="d0abd-232">現在のアクセス許可の設定を使用すると、ユーザーは、請求、規制上のレポート、および支払など、さまざまな機能領域からビジネス ドキュメント テンプレートを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-232">With the current access permissions setting, the user can edit business document templates from different functional areas including invoicing, regulatory reporting, and payments.</span></span>

![ビジネス ドキュメント管理のワークスペース ページ](./media/BDM-Overview-TemplatesForAlice1.png)

3. <span data-ttu-id="d0abd-234">**アクセス許可のコンフィギュレーター**ページで、**アクセス許可の設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-234">On the **Configurator of access permissions** page, select **Access permissions setting**.</span></span>
4. <span data-ttu-id="d0abd-235">**テンプレートを編集するためのアクセス許可を設定**ダイアログ ボックスで、**コンフィギュレーションされたアクセス許可の適用**オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-235">In the **Settings of access permissions to edit templates** dialog box, enable the **Apply configured access permissions** option.</span></span>
5. <span data-ttu-id="d0abd-236">**OK** を選択して、ビジネス ドキュメント管理のアクセス権が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-236">Select **OK** to confirm that Business document management access permissions have been enabled.</span></span>

![ビジネス ドキュメント管理のアクセス許可ページのコンフィギュレーション](./media/BDM-Overview-TemplatesAccess2.png)

6. <span data-ttu-id="d0abd-238">**追加**を選択して、ビジネス ドキュメント管理のテンプレートにアクセスするための許可をコンフィギュレーションする必要がある新しいビジネス ロールを入力します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-238">Select **Add** to enter a new business role for which permissions to access Business document management templates must be configured.</span></span>
7. <span data-ttu-id="d0abd-239">**セキュリティ ロール** ダイアログ ボックスで、**売掛金管理係**ロールを選択し、**OK** を選択してロールの選択を確認します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-239">In the **Security roles** dialog box, select the **Accounts receivable clerk** role and then select **OK** to confirm the role selection.</span></span>
8. <span data-ttu-id="d0abd-240">**コンフィギュレーションのタグごとのアクセス許可**タブで、**新規**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-240">On the **Access permissions per tags of configurations** tab, select **New**.</span></span>
9. <span data-ttu-id="d0abd-241">**タグ タイプ**フィールドで、**機能領域**を選択し、**ID** フィールドで、**請求**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-241">In the **Tag type** field, select **Functional area**, and in the **ID** field, select **Invoicing**.</span></span>
10. <span data-ttu-id="d0abd-242">**保存**を選択すると、選択したロールに対してコンフィギュレーションされたアクセス許可が格納されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-242">Select **Save** to store configured access permissions for the selected role.</span></span>

  <span data-ttu-id="d0abd-243">現在の設定とは、**売掛金管理係**ロールに割り当てられ、職務権限である**ビジネス ドキュメント テンプレートの管理** (AOT 名 **ERBDManageTemplates**) を実行しているすべてのユーザーのことであり、**機能領域**タグの**請求**値を持つ ER 形式コンフィギュレーション テンプレートが、ビジネス ドキュメント管理のワークスペースで編集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-243">The current setting means that for any user who is assigned to the **Accounts receivable clerk** role and performing the duty, **Manage Business document templates** (AOT name **ERBDManageTemplates**), ER format configuration templates that have the **Invoicing** value for the **Functional area** tag will be available to edit in the Business document management workspace.</span></span>

11. <span data-ttu-id="d0abd-244">**関連情報**ウィンドウを現在のページの右側から切り替えます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-244">Switch the **Related information** pane from the right side of the current page.</span></span> <span data-ttu-id="d0abd-245">**関連情報**ウィンドウには、コンフィギュレーション済のアクセス許可がどのように適用されるか示されます。これには、**売掛金管理係**ロールに割り当てられているユーザーが使用できる ER コンフィギュレーション テンプレートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-245">The **Related information** pane shows how the configured access permissions will be applied, including what ER configuration templates will be available for users that are assigned to the **Accounts receivable clerk** role.</span></span>

![ビジネス ドキュメント管理のアクセス許可ページのコンフィギュレーション](./media/BDM-Overview-TemplatesAccess3.png)

12. <span data-ttu-id="d0abd-247">**コンフィギュレーションごとのアクセス許可**タブで、**追加**オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-247">On the **Access permissions per configurations** tab, select the **Add** option.</span></span>
13. <span data-ttu-id="d0abd-248">**コンフィギュレーションの選択**ダイアログボックスで、**イントラスタット レポート**の ER 形式コンフィギュレーションをマークします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-248">In the **Select configuration** dialog box, mark the **Intrastat report** ER format configuration.</span></span>
14. <span data-ttu-id="d0abd-249">**OK** を選択して、選択したコンフィギュレーションのエントリを確認し、**保存**を選択して、選択したロールのコンフィギュレーション済のアクセス許可を保存します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-249">Select **OK** to confirm the entry of the selected configurations and then select **Save** to store the configured access permissions for the selected role.</span></span>

<span data-ttu-id="d0abd-250">現在の設定とは、**売掛金管理係**ロールに割り当てられ、職務権限である**ビジネス ドキュメント テンプレートの管理** (AOT 名 **ERBDManageTemplates**) を実行しているすべてのユーザーのことであり、次のテンプレートが、ビジネス ドキュメント管理のワークスペースで編集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-250">The current setting means that for any user assigned to the **Accounts receivable clerk** role and performing the duty, **Manage Business document templates** (AOT name **ERBDManageTemplates**), the following templates will be available to edit in the Business document management workspace:</span></span>

- <span data-ttu-id="d0abd-251">**機能領域**タグの値**請求**をもつテンプレート。</span><span class="sxs-lookup"><span data-stu-id="d0abd-251">Templates that have the value, **Invoicing** for the **Functional area** tag.</span></span>
- <span data-ttu-id="d0abd-252">**コンフィギュレーションごとのアクセス許可**タブで表示される ER 形式コンフィギュレーションからテンプレートを行います (この例の**法令報告**ドメインの**イントラスタット レポート**形式コンフィギュレーションからテンプレート)。</span><span class="sxs-lookup"><span data-stu-id="d0abd-252">Templates from ER format configurations that are listed on the **Access permissions per configurations** tab (templates from the **Intrastat report** format configuration of the **Statutory reporting** domain in this example).</span></span>

![ビジネス ドキュメント管理のアクセス許可ページのコンフィギュレーション](./media/BDM-Overview-TemplatesAccess4.png)

<span data-ttu-id="d0abd-254">次の図では、ビジネス ドキュメント管理のワークスペースが**売掛金管理係**ロールに割り当てられたユーザーに提供するものを示します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-254">The following graphic shows what the Business document management workspace provides to a user assigned to the **Accounts receivable clerk** role.</span></span> <span data-ttu-id="d0abd-255">現在のビジネス ドキュメントの管理アクセス許可の設定では、ユーザーは**請求**ドメインおよび**イントラスタット レポート**の ER形式コンフィギュレーションからビジネス ドキュメント テンプレートを編集できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-255">With the current Business document management access permissions setting, the user can edit business document templates from the **Invoicing** domain and the **Intrastat report** ER format configuration.</span></span> <span data-ttu-id="d0abd-256">**支払**ドメインからのテンプレートでは、**売掛金勘定係**ロールにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="d0abd-256">Templates from the **Payments** domain are not accessible for the **Accounts receivable clerk** role.</span></span>

![ビジネス ドキュメント管理のワークスペース ページ](./media/BDM-Overview-TemplatesForAlice2.png)

> [!NOTE]
> <span data-ttu-id="d0abd-258">**コンフィギュレーションごとのアクセス許可**ルールでは、ER 形式コンフィギュレーションの固有の特定 ID を使用して保存されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-258">The **Access permissions per configurations** rules are stored by using the unique identification ID of an ER format configuration.</span></span> <span data-ttu-id="d0abd-259">つまり、これらのルールは、それらを参照する ER コンフィギュレーションが削除されると、削除されません。</span><span class="sxs-lookup"><span data-stu-id="d0abd-259">This means that these rules will not be deleted when an ER configuration that refers to them are deleted.</span></span> <span data-ttu-id="d0abd-260">削除したコンフィギュレーションを、Finance and Operations のインスタンスに戻すと、これらのルールによって再度参照されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-260">When you import deleted configurations back to this instance of Finance and Operations, these rules will refer to them again.</span></span> <span data-ttu-id="d0abd-261">削除したコンフィギュレーションを再度インポートした後で、再度ルールを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d0abd-261">There is no need to set up the rules again after the deleted configurations are imported again.</span></span>

## <a name="use-business-document-management-to-edit-templates"></a><span data-ttu-id="d0abd-262">ビジネス ドキュメント管理を使用して、テンプレートの編集</span><span class="sxs-lookup"><span data-stu-id="d0abd-262">Use Business document management to edit templates</span></span>

<span data-ttu-id="d0abd-263">ビジネス ユーザーは、ビジネス ドキュメント管理ワークスペースで、ビジネス ドキュメント テンプレートにアクセスして編集を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-263">Business users can access business document templates for editing in the Business document management workspace.</span></span> <span data-ttu-id="d0abd-264">ビジネス ドキュメント管理のワークスペースにアクセスできるのは、次のユーザーだけです。</span><span class="sxs-lookup"><span data-stu-id="d0abd-264">Only the following users can access the Business document management workspace:</span></span>

- <span data-ttu-id="d0abd-265">ロールに割り当てられるユーザー、**システム管理者**。</span><span class="sxs-lookup"><span data-stu-id="d0abd-265">Users assigned to the role, **System administrator**.</span></span>
- <span data-ttu-id="d0abd-266">職務権限を実行するようにコンフィギュレーションされているロールに割り当てられたユーザー、**ビジネス ドキュメント テンプレートの管理** (AOT 名 **ERBDManageTemplates**)。</span><span class="sxs-lookup"><span data-stu-id="d0abd-266">Users assigned to any role that is configured to perform the duty, **Manage Business document templates** (AOT name **ERBDManageTemplates**).</span></span>

<span data-ttu-id="d0abd-267">ビジネス ドキュメント管理のワークスペースにて、自由書式の請求書テンプレートを編集するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d0abd-267">Use the following procedure to edit free text invoice templates in the Business document management workspace.</span></span> <span data-ttu-id="d0abd-268">この手順を実行する前に、トピックの上記の手順をすべて完了しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-268">Before you complete this procedure, you must have completed all of the preceding procedures in this topic.</span></span>

1. <span data-ttu-id="d0abd-269">ビジネス ドキュメント管理のワークスペースへのアクセス権を持つユーザーとして、Finance and Operations にログインします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-269">Sign in to Finance and Operations as a user with access to the Business document management workspace.</span></span>
2. <span data-ttu-id="d0abd-270">ビジネス ドキュメント管理のワークスペースを開きます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-270">Open the Business document management workspace.</span></span>

![ビジネス ドキュメント管理のワークスペース ページ](./media/BDM-Overview-EditingTemplate1.png)

<span data-ttu-id="d0abd-272">**テンプレート**タブには、選択したテンプレートの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-272">The **Template** tab presents the content of the selected template.</span></span> <span data-ttu-id="d0abd-273">**詳細**タブを選択して、選択したテンプレートとこのテンプレートが格納されている ER 形式コンフィギュレーションの詳細をレビューします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-273">Select the **Details** tab to review details of the selected template as well as details of an ER format configuration this template resides in.</span></span> <span data-ttu-id="d0abd-274">すべてのテンプレートが**発行済**の状態になっており、**リビジョン**列に詳細が含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-274">Notice that all of the templates have a status of **Published**, and contain no details in the **Revision** column.</span></span> <span data-ttu-id="d0abd-275">これは、テンプレートが現在編集されていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-275">This means that these templates are not currently being edited.</span></span>

### <a name="initiate-editing-templates-owned-by-your-configuration-provider"></a><span data-ttu-id="d0abd-276">コンフィギュレーション プロバイダーが所有する編集テンプレートを開始します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-276">Initiate editing templates owned by your configuration provider</span></span>

1. <span data-ttu-id="d0abd-277">ビジネス ドキュメント管理のワークスペースで、一覧の**小切手の印刷形式**テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-277">In the Business document management workspace, select the **Cheques printing format** template in the list.</span></span>
2. <span data-ttu-id="d0abd-278">**詳細**タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-278">Select the **Details** tab.</span></span>

![ビジネス ドキュメント管理のワークスペース ページ](./media/BDM-Overview-EditingTemplate2.png)

<span data-ttu-id="d0abd-280">**編集テンプレート**オプションでは、選択したテンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-280">The **Edit template** option is available for the selected template.</span></span> <span data-ttu-id="d0abd-281">このオプションは、有効な ER コンフィギュレーション プロバイダー (この例では **Litware, inc.**) によって所有されている ER フォーマット コンフィギュレーションのテンプレートに対して、常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-281">This option is always available for a template in an ER format configuration that is owned by the active ER configuration provider (**Litware, Inc.** in this example).</span></span> <span data-ttu-id="d0abd-282">**テンプレートの編集**を選択すると、基になる ER 形式コンフィギュレーションの下書きバージョンの既存のテンプレートが編集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-282">When **Edit template** is selected, the existing template from the draft version of the underlying ER format configuration will be available to edit.</span></span>

### <a name="initiate-editing-templates-owned-by-other-providers"></a><span data-ttu-id="d0abd-283">他のプロバイダーが所有する編集テンプレートを開始</span><span class="sxs-lookup"><span data-stu-id="d0abd-283">Initiate editing templates owned by other providers</span></span>

1. <span data-ttu-id="d0abd-284">ビジネス ドキュメント管理のワークスペースで、一覧の**顧客 FTI レポート (GER)** テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-284">In the Business document management workspace, select the **Customer FTI report (GER)** template in the list.</span></span>
2. <span data-ttu-id="d0abd-285">**詳細**タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-285">Select the **Details** tab.</span></span>

![ビジネス ドキュメント管理のワークスペース ページ](./media/BDM-Overview-EditingTemplate3.png)

<span data-ttu-id="d0abd-287">**新規ドキュメント**オプションでは、選択したテンプレートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-287">The **New document** option is available for the selected template.</span></span> <span data-ttu-id="d0abd-288">このオプションは、別のプロバイダー (この例では **Microsoft**) によって提供されている ER フォーマット コンフィギュレーションのテンプレートに対して、常に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-288">This option is always available for a template in an ER format configuration provided by another provider (**Microsoft** in this example).</span></span> <span data-ttu-id="d0abd-289">**新規ドキュメント**を選択すると、新しいテンプレートを編集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-289">When **New document** is selected, a new template will be available to edit.</span></span> <span data-ttu-id="d0abd-290">編集したテンプレートは、自動的に生成される新規 ER 形式コンフィギュレーションで保存されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-290">The edited template will then be stored in a new ER format configuration that is automatically generated.</span></span>

### <a name="start-editing-a-template"></a><span data-ttu-id="d0abd-291">テンプレートの編集開始</span><span class="sxs-lookup"><span data-stu-id="d0abd-291">Start editing a template</span></span>

1. <span data-ttu-id="d0abd-292">選択したテンプレートで、**新規ドキュメント**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-292">From the selected template, select **New document**.</span></span>
2. <span data-ttu-id="d0abd-293"> **タイトル**フィールドで、必要に応じて編集可能なテンプレートのタイトルを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-293">In the **Title** field, change the title of the editable template if needed.</span></span> <span data-ttu-id="d0abd-294">このテキストは、自動的に作成される ER 形式コンフィギュレーションに名前を付けるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-294">The text will be used to name the ER format configuration that is automatically created.</span></span> <span data-ttu-id="d0abd-295">編集したテンプレートを含む、このコンフィギュレーション (**顧客 FTI レポート (GER) コピー**) のドラフト バージョンは、現在のユーザーに対して ER 形式を実行するよう自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-295">Note that the draft version of this configuration (**Customer FTI report (GER) Copy**) that will contain the edited template will automatically be marked to run this ER format for the current user.</span></span> <span data-ttu-id="d0abd-296">同時に、基本 ER 形式コンフィギュレーションからの変更されていない元のテンプレートを使用して、他のユーザーがこの ER 形式を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-296">At the same time, the non-modified original template from the base ER format configuration will be used to run this ER format for any other user.</span></span>
3. <span data-ttu-id="d0abd-297">**名前**フィールドで、自動的に作成される編集可能なテンプレートの最初のリビジョンの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-297">In the **Name** field, change the name of the first revision of the editable template that will be created automatically.</span></span>
4. <span data-ttu-id="d0abd-298">**コメント**フィールドで、自動的に作成された編集可能なテンプレートのリビジョンの注釈を変更します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-298">In the **Comment** field, change the remark for the automatically created revision of the editable template.</span></span>

![ビジネス ドキュメント管理のワークスペース ページ](./media/BDM-Overview-EditingTemplate4.png)

5. <span data-ttu-id="d0abd-300">**OK** を選択して、編集プロセスの開始を確認します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-300">Select **OK** to confirm the start of the editing process.</span></span>

<span data-ttu-id="d0abd-301">Finance and Operations の **BDM テンプレート エディター**ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-301">The **BDM template editor** page of Finance and Operations will open.</span></span> <span data-ttu-id="d0abd-302">選択したテンプレートは、Office 365 を使用してオンライン編集できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-302">The selected template will be available for online editing by using Office 365.</span></span>

![ビジネス ドキュメント管理のワークスペース ページ](./media/BDM-Overview-EditingLayout1.png)

### <a name="edit-a-template-in-office-365"></a><span data-ttu-id="d0abd-304">Office 365 でテンプレートを編集</span><span class="sxs-lookup"><span data-stu-id="d0abd-304">Edit a template in Office 365</span></span>

<span data-ttu-id="d0abd-305">Office 365 機能を使用して、テンプレートを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-305">Modify the template by using the functionality of the Office 365.</span></span> <span data-ttu-id="d0abd-306">たとえば、Office online で、テンプレート ヘッダーの**レギュラー**から**太字**にフィールド プロンプトのフォントを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-306">For example, in Office online, change the font of the field prompts in the template header from **Regular** to **Bold**.</span></span> <span data-ttu-id="d0abd-307">これらの変更は、ER フレームワーク用にコンフィギュレーションされているプライマリ テンプレートのストレージ (既定では、Azure blob storage) に保存されている編集可能なテンプレートに対して自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-307">These changes are automatically stored for the editable template that is stored in the primary template’s storage (by default, the Azure blob storage) that is configured for the ER framework.</span></span>

![ビジネス ドキュメント管理のテンプレートのエディター ページ](./media/BDM-Overview-EditingLayout2.png)

### <a name="edit-a-template-in-the-office-desktop-application"></a><span data-ttu-id="d0abd-309">Office のデスクトップ アプリケーションでのテンプレートの編集</span><span class="sxs-lookup"><span data-stu-id="d0abd-309">Edit a template in the Office desktop application</span></span>

1. <span data-ttu-id="d0abd-310">**デスクトップ アプリケーションで開く**オプションを選択して、Office のデスクトップ アプリケーション (この例では Excel) の機能を使用し、テンプレートを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-310">Select the **Open in Desktop App** option to modify the template by using the functionality of the Office desktop application (Excel in this example).</span></span> <span data-ttu-id="d0abd-311">編集可能なテンプレートは、固定保管場所から、SharePoint フォルダーとしてビジネス ドキュメント管理パラメータでコンフィギュレーションされている一時的な保管場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-311">The editable template is copied from the permanent storage to the temporary storage configured in the Business document management parameters as a SharePoint folder.</span></span>
2. <span data-ttu-id="d0abd-312">Office のデスクトップ Excel アプリケーションにて、一時的なファイルの保管場所からテンプレートを開くことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-312">Confirm that you want to open the template from the temporary file storage in the Office desktop Excel application.</span></span>

![ビジネス ドキュメント管理のワークスペース ページ](./media/BDM-Overview-EditingLayout3.png)

3. <span data-ttu-id="d0abd-314">テンプレートを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-314">Modify the template.</span></span> <span data-ttu-id="d0abd-315">たとえば、**黒**から**青**に色を更新してテンプレート ヘッダーのフィールド プロンプトのフォントを変更します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-315">For example, change the font of the fields prompts in the template header by updating color from **Black** to **Blue**.</span></span>

![ビジネス ドキュメント管理のテンプレートのエディター ページ](./media/BDM-Overview-EditingLayout4.png)

4. <span data-ttu-id="d0abd-317">Excel デスクトップ アプリケーションで**保存**を選択して、一時的な保管場所にテンプレートの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-317">Select **Save** in the Excel desktop application to store the template changes in the temporary storage.</span></span>

![ビジネス ドキュメント管理のテンプレートのエディター ページ](./media/BDM-Overview-EditingLayout5.png)

5. <span data-ttu-id="d0abd-319">Excel デスクトップ アプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-319">Close the Excel desktop application.</span></span>
6. <span data-ttu-id="d0abd-320">**保存されたコピーを同期**を選択して、一時的テンプレート保管を固定テンプレート保管に同期します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-320">Select **Sync stored copy** to synchronize the temporary template storage to the permanent template storage.</span></span>

> [!NOTE]
> <span data-ttu-id="d0abd-321">一時的ファイル保管内の編集可能なテンプレートのコピーは、テンプレート編集の現セッションでのみ保持されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-321">The copy of the editable template in the temporary file storage is kept for only the current session of template editing.</span></span> <span data-ttu-id="d0abd-322">**BDM テンプレート エディター**ページを閉じて、このセッションを終了すると、コピーは削除されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-322">When you finish this session by closing the **BDM template editor** page, this copy will be deleted.</span></span> <span data-ttu-id="d0abd-323">一時的ファイル保管場所でテンプレートを調整し、**保存されたコピーの同期**選択しなかった場合は、**BDM テンプレート エディター**ページを閉じようとすると、変更を保存するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-323">If you adjusted the template in the temporary file storage and did not select **Sync stored copy**, when you try to close the **BDM template editor** page, a message will ask whether you want to store introduced changes.</span></span> <span data-ttu-id="d0abd-324">固定ファイル場所のテンプレートへの変更を保存したい場合は、**はい**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-324">Select **Yes** if you want to save your changes to the template in the permanent file location.</span></span>

### <a name="validate-a-template"></a><span data-ttu-id="d0abd-325">テンプレートの検証</span><span class="sxs-lookup"><span data-stu-id="d0abd-325">Validate a template</span></span>

1. <span data-ttu-id="d0abd-326">**BDM テンプレート エディター**ページで、**問題点を確認**を選択して、基になる ER 形式コンフィギュレーションに対して変更したテンプレートを検証します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-326">On the **BDM template editor** page, select **Check for issues** to validate the modified template against the underlying ER format configuration.</span></span> <span data-ttu-id="d0abd-327">推奨事項 (該当する場合) に従って、テンプレートを基本の ER 形式コンフィギュレーションの形式の構造に配置します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-327">Follow the recommendations (if any) to align the template with the structure of the format from the base ER format configuration.</span></span>
2. <span data-ttu-id="d0abd-328">**形式の表示**を選択すると、編集可能なテンプレートに配置する必要がある基本の ER 形式コンフィギュレーションからの形式の現構造が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-328">Select **Show format** to view the current structure of the format from the base ER format configuration that must be aligned with the editable template.</span></span> 
3. <span data-ttu-id="d0abd-329">**フォーマットの非表示**を選択して、ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-329">Select **Hide format** to close the pane.</span></span>

![BDM テンプレートのエディター ページ](./media/BDM-Overview-EditingTemplate6.png)

4. <span data-ttu-id="d0abd-331">**BDM テンプレートのエディター**ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-331">Close the **BDM template editor** page.</span></span>

<span data-ttu-id="d0abd-332">更新されたテンプレートが**テンプレート**タブに表示されます。編集したテンプレートの状態が**ドラフト**になり、現在のリビジョンが空ではなくなったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-332">The updated template is shown on the **Template** tab. Notice that the status of the edited template is now **Draft** and the current revision is no longer empty.</span></span> <span data-ttu-id="d0abd-333">これは、このテンプレートの編集のプロセスが開始されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-333">This means that the process of this template’s editing has been started.</span></span>

![ビジネス ドキュメント管理のワークスペース ページ](./media/BDM-Overview-EditingTemplate5.png)

### <a name="test-the-modified-template"></a><span data-ttu-id="d0abd-335">変更したテンプレートのテスト</span><span class="sxs-lookup"><span data-stu-id="d0abd-335">Test the modified template</span></span> 

1. <span data-ttu-id="d0abd-336">Finance and Operations で、会社 **USMF** に変更します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-336">In Finance and Operations, change to the company, **USMF**.</span></span>
2. <span data-ttu-id="d0abd-337">**売掛金勘定** \> **請求書** \> **すべての自由書式の請求書**に移動します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-337">Go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span>
3. <span data-ttu-id="d0abd-338">**FTI-00000002** 請求書を選択し、**印刷管理**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-338">Select the **FTI-00000002** invoice, and then select **Print management**.</span></span>
4. <span data-ttu-id="d0abd-339">**モジュール - 売掛金** \> **ドキュメント** \> **自由書式の請求** \> **元のドキュメント**レベルを選択して、処理する請求書の範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-339">Select the **Module - accounts receivable** \> **Documents** \> **Free text invoice** \> **Original document** level to specify the scope of invoices for processing.</span></span>
5. <span data-ttu-id="d0abd-340">**レポート形式**フィールドで、指定したドキュメント レベルの**顧客 FTI レポート (GER) コピー**の ER 形式を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-340">In the **Report format** field, select the **Customer FTI report (GER) Copy** ER format for the specified document level.</span></span>

![管理設定ページを印刷](./media/BDM-Overview-TestRun1.png)

6. <span data-ttu-id="d0abd-342">**エスケープ**を押して、現在のページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-342">Press **Escape** to close the current page.</span></span>
7. <span data-ttu-id="d0abd-343">**印刷**を選択し、**選択済**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-343">Select **Print**, and then click **Selected**.</span></span>
8. <span data-ttu-id="d0abd-344">ドキュメントをダウンロードし、Excel デスクトップ アプリケーションを使用して開きます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-344">Download the document and open it using the Excel desktop application.</span></span>

![自由書式の請求書のページ](./media/BDM-Overview-TestRun2.png)

<span data-ttu-id="d0abd-346">変更したテンプレートは、選択した品目に対して自由書式の請求書レポートを生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-346">The modified template is used to generate the free text invoice report for the selected item.</span></span> <span data-ttu-id="d0abd-347">テンプレートに加えた変更によってこのレポートがどのように影響を受けるかを分析するには、別のアプリケーション セッションでテンプレートを変更した直後に、1 つのアプリケーション セッションでこのレポートを実行します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-347">To analyze how this report is affected by the changes that you introduced to the template, you can run this report in one application session right after you modified the template in another application session.</span></span>

### <a name="create-an-alternative-template-revision"></a><span data-ttu-id="d0abd-348">代替テンプレート リビジョンの作成</span><span class="sxs-lookup"><span data-stu-id="d0abd-348">Create an alternative template revision</span></span>

1. <span data-ttu-id="d0abd-349">**BDM テンプレート エディター**ページを開いて、**顧客 FTI レポート (GER) コピー**のテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-349">Open the **BDM template editor** page and select the **Customer FTI report (GER) Copy** template.</span></span>
2. <span data-ttu-id="d0abd-350">**リビジョン**タブで、**新規**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-350">On the **Revisions** tab, select **New**.</span></span>
3. <span data-ttu-id="d0abd-351">必要に応じて、**名前**フィールドで 2 番目のリビジョンの名前を変更し、現在有効な最初のリビジョンの基準とします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-351">If needed, in the **Name** field, change the name of the second revision and base it on the currently active first revision.</span></span>
4. <span data-ttu-id="d0abd-352">必要であれば、**コメント**フィールドで、自動的に作成された編集可能なテンプレートのリビジョンの注釈を変更します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-352">If needed, in the **Comment** field, change the remark for the automatically created revision of the editable template.</span></span>

![ビジネス ドキュメント管理のワークスペース ページ](./media/BDM-Overview-AddRevision.png)

<span data-ttu-id="d0abd-354">固定テンプレートの保管場所に保存されているテンプレートの新しいリビジョンを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d0abd-354">You created a new revision of your template that has been stored in the permanent template’s storage.</span></span> <span data-ttu-id="d0abd-355">現在アクティブとして選択されている 2 番目のリビジョンのテンプレートの編集を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-355">Now you can continue editing the template of the second revision that is currently selected as active.</span></span>

5. <span data-ttu-id="d0abd-356">最初のリビジョンを選択し、**アクティブに設定**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-356">Select the first revision and then select **Set active**.</span></span> <span data-ttu-id="d0abd-357">いつでもそのテンプレートのリビジョンに戻りたい場合、アクティブである別のリビジョンを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-357">You can select another revision as active if at any time you want to return to that revision of the template.</span></span>
6. <span data-ttu-id="d0abd-358">2 番目のリビジョンを選択し、**削除**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-358">Select the second revision, and then select **Delete**.</span></span>
7. <span data-ttu-id="d0abd-359">**OK** を選択し、選択したリビジョンを削除することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-359">Select **OK** to confirm that you want to delete the selected revision.</span></span> <span data-ttu-id="d0abd-360">非アクティブなリビジョンは、不要になった時点で削除できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-360">You can delete any of the non-active revisions when they are no longer needed.</span></span>

### <a name="delete-a-modified-template"></a><span data-ttu-id="d0abd-361">変更したテンプレートの削除</span><span class="sxs-lookup"><span data-stu-id="d0abd-361">Delete a modified template</span></span>

1. <span data-ttu-id="d0abd-362">**BDM テンプレート エディター**ページで、**テンプレート**タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-362">On the **BDM template editor** page, select the **Template** tab.</span></span>
2. <span data-ttu-id="d0abd-363">**削除**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-363">Select **Delete**.</span></span>
3. <span data-ttu-id="d0abd-364">**OK** を選択して削除を確認した場合、変更したテンプレートを持つ**顧客 FTI レポート (GER) コピー**の ER 形式は削除されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-364">If you select **OK** to confirm deletion, the **Customer FTI report (GER) Copy** ER format with the modified template will be deleted.</span></span> <span data-ttu-id="d0abd-365">**キャンセル**を選択して、他のオプションをエクスプローラーします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-365">Select **Cancel** to explore other options.</span></span>

### <a name="revoke-changes-of-template"></a><span data-ttu-id="d0abd-366">テンプレートの変更の無効化</span><span class="sxs-lookup"><span data-stu-id="d0abd-366">Revoke changes of template</span></span>

<span data-ttu-id="d0abd-367">現在アクティブなプロバイダーによって所有されている ER 形式からテンプレートを編集する場合は、テンプレートに導入された変更を取り消すためのオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-367">When you edit the template from an ER format that is owned by the current active provider, you will be offered the option to revoke changes introduced for the template.</span></span>

![ビジネス ドキュメント管理のワークスペース ページ](./media/BDM-Overview-RevokeChanges.png)

1. <span data-ttu-id="d0abd-369">**BDM テンプレート エディター**ページで、**テンプレート**タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-369">On the **BDM template editor** page, select the **Template** tab.</span></span>
2. <span data-ttu-id="d0abd-370">**取り消し**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-370">Select **Undo**.</span></span>
3. <span data-ttu-id="d0abd-371">**OK** を選択しテンプレートに導入された変更を取り消す場合、変更したテンプレートは元のテンプレートに置き換えられ、すべての変更が削除されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-371">If you select **OK** to revoke the changes introduced for the template, the modified template will be replaced by the original template and all changes will be removed.</span></span> <span data-ttu-id="d0abd-372">テンプレートに対する変更を取り消すと、テンプレートを削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-372">When you revoke changes to the template, you will be able to delete the template.</span></span> <span data-ttu-id="d0abd-373">**キャンセル**を選択して、他のオプションをエクスプローラーします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-373">Select **Cancel** to explore other options.</span></span>

### <a name="publish-a-modified-template"></a><span data-ttu-id="d0abd-374">変更したテンプレートの公開</span><span class="sxs-lookup"><span data-stu-id="d0abd-374">Publish a modified template</span></span>
1. <span data-ttu-id="d0abd-375">**BDM テンプレート エディター**ページの**テンプレート**タブで、**公開**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-375">On the **BDM template editor** page, on the **Template** tab, select **Publish**.</span></span>
2. <span data-ttu-id="d0abd-376">**OK** を選択して公開の確認をする場合、変更したテンプレートが含まれる派生**顧客 FTI レポート (GER) コピー**の ER 形式の下書きバージョンが完了としてマークされます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-376">If you select **OK** to confirm publishing, the draft version of the derived **Customer FTI report (GER) Copy** ER format that contains the modified template will be marked as completed.</span></span> <span data-ttu-id="d0abd-377">変更したテンプレートは、Finance and Operations の他のユーザーが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d0abd-377">The modified template becomes available for other users of Finance and Operations.</span></span> <span data-ttu-id="d0abd-378">この ER 形式の完全版では、テンプレートの最後のアクティブ リビジョンのみが保持されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-378">The completed versions of this ER format will keep only the last active revision of your template.</span></span> <span data-ttu-id="d0abd-379">他のリビジョンは削除されます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-379">Other revisions will be deleted.</span></span> <span data-ttu-id="d0abd-380">**キャンセル**を選択して、他のオプションをエクスプローラーします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-380">Select **Cancel** to explore other options.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d0abd-381">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="d0abd-381">Frequently asked questions</span></span>

#### <a name="i-selected-new-document-but-instead-of-opening-the-bdm-template-editor-page-in-finance-and-operations-i-have-been-sent-to-the-office-365-web-page"></a><span data-ttu-id="d0abd-382">**新規ドキュメント**を選択したが、Finance and Operations の **BDM テンプレート エディター**ページを開く代わりに、Office 365 の Web ページに送信しました。</span><span class="sxs-lookup"><span data-stu-id="d0abd-382">I selected **New document**, but instead of opening the **BDM template editor** page in Finance and Operations, I have been sent to the Office 365 web page.</span></span>
<span data-ttu-id="d0abd-383">これは、Office 365 のリダイレクトが Finance and Operations へ戻るという既知の問題です。</span><span class="sxs-lookup"><span data-stu-id="d0abd-383">This is a known issue with the Office 365 redirection back to Finance and Operations.</span></span> <span data-ttu-id="d0abd-384">これは、最初に Office 365 に署名したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-384">This happens when you sign to Office 365 the first time.</span></span> <span data-ttu-id="d0abd-385">この問題を回避するには、ブラウザーの**戻る**ボタンを選択して、Finance and Operations へ戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-385">To work around this issue, select the **Back** button of your browser to navigate back to Finance and Operations.</span></span>

#### <a name="i-understand-how-to-edit-a-template-by-using-office-365-in-the-first-application-session-and-how-to-use-the-template-in-the-second-application-session-adjusting-the-template-to-see-how-my-changes-affect-the-generated-business-document-can-i-do-this-using-the-office-desktop-application"></a><span data-ttu-id="d0abd-386">最初のアプリケーション セッションで Office 365 を使用してテンプレートを編集する方法と、テンプレートを調整して 2 番目のアプリケーション セッションでテンプレートを使う方法を理解し、変更が生成されたビジネス ドキュメントにどのように影響するかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-386">I understand how to edit a template by using Office 365 in the first application session and how to use the template in the second application session adjusting the template to see how my changes affect the generated business document.</span></span> <span data-ttu-id="d0abd-387">Office デスクトップ アプリケーションを使用してこれを行うことができますか。</span><span class="sxs-lookup"><span data-stu-id="d0abd-387">Can I do this using the Office desktop application?</span></span>
<span data-ttu-id="d0abd-388">はい、できます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-388">Yes, you can.</span></span> <span data-ttu-id="d0abd-389">最初のアプリケーション セッションで、**デスクトップ アプリケーションを開く**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-389">In the first application session, select **Open in Desktop App**.</span></span> <span data-ttu-id="d0abd-390">テンプレートは一時ファイル保管場所に保存され、Office デスクトップ アプリケーションで開かれます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-390">Your template will be stored in the temporary file storage and opened in the Office desktop application.</span></span> <span data-ttu-id="d0abd-391">次に、生成されたビジネス ドキュメントのテンプレートの変更をプレビューするために、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-391">Next, complete the following steps to preview your template changes in the generated business document:</span></span>

1. <span data-ttu-id="d0abd-392">Office デスクトップ アプリケーションを使用して、テンプレートに変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="d0abd-392">Make changes in the template by using the Office desktop application.</span></span>
2. <span data-ttu-id="d0abd-393">Office デスクトップ アプリケーションで、**保存**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-393">Select **Save** in the Office desktop application.</span></span>
3. <span data-ttu-id="d0abd-394">最初のアプリケーション セッションの **BDM テンプレート エディター**ページで、**保存されたコピーの同期**を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-394">On the **BDM template editor** page of the first application session, select **Sync stored copy**.</span></span>
4. <span data-ttu-id="d0abd-395">2 番目のアプリケーション セッションで、このテンプレートの ER 形式を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0abd-395">Execute this template ER format in the second application session.</span></span>

#### <a name="i-get-the-error-value-cannot-be-null-parameter-name-externalid-when-i-select-open-in-desktop-app-how-do-i-work-around-this"></a><span data-ttu-id="d0abd-396">「値を Null にすることは出来ません」というエラーが発生。</span><span class="sxs-lookup"><span data-stu-id="d0abd-396">I get the error ‘Value cannot be null.</span></span> <span data-ttu-id="d0abd-397">パラメーター名: externalId’、**デスクトップ アプリケーションを開く**を選択した場合。</span><span class="sxs-lookup"><span data-stu-id="d0abd-397">Parameter name: externalId’ when I select **Open in Desktop App**.</span></span> <span data-ttu-id="d0abd-398">回避するにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="d0abd-398">How do I work around this?</span></span> 
<span data-ttu-id="d0abd-399">殆どの場合、Finance and Operations のこのインスタンスを配置するために使用された Azure AD と異なる Azure AD ドメインの Finance and Operations の現インスタンスにログインします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-399">Most likely you signed in to the current instance of Finance and Operations of the Azure AD domain which differs from the Azure AD domain that was used to deploy this instance of Finance and Operations.</span></span> <span data-ttu-id="d0abd-400">Office デスクトップ アプリケーションを使用して編集可能にするためのテンプレートを保存するために使用される SharePoint サービスは、Finance and Operations と同じドメインに属しているので、SharePoint サービスにアクセスするためのアクセス許可はありません。</span><span class="sxs-lookup"><span data-stu-id="d0abd-400">Because the SharePoint service, which is used to store templates for making them available for editing by using the Office desktop applications, belongs to the same domain as Finance and Operations, we have no permissions to access the SharePoint service.</span></span> <span data-ttu-id="d0abd-401">この問題を解決するには、適切な Azure AD ドメインを持つユーザーの資格情報を使用して、Finance and Operations の現インスタンスにログインします。</span><span class="sxs-lookup"><span data-stu-id="d0abd-401">To resolve this issue, sign in to the current instance of Finance and Operations using the credentials of a user with the correct Azure AD domain.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d0abd-402">追加リソース</span><span class="sxs-lookup"><span data-stu-id="d0abd-402">Additional resources</span></span>

[<span data-ttu-id="d0abd-403">電子申告の概要</span><span class="sxs-lookup"><span data-stu-id="d0abd-403">Electronic reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="d0abd-404">OPENXML 形式のレポートを生成するコンフィギュレーションを設計する</span><span class="sxs-lookup"><span data-stu-id="d0abd-404">Design a configuration for generating reports in OPENXML format</span></span>](tasks/er-design-reports-openxml-2016-11.md)

[<span data-ttu-id="d0abd-405">Word 形式でレポートを生成するための ER コンフィギュレーションのデザイン</span><span class="sxs-lookup"><span data-stu-id="d0abd-405">Design ER configurations to generate reports in Word format</span></span>](tasks/er-design-configuration-word-2016-11.md)

[<span data-ttu-id="d0abd-406">ER を使用して生成されるドキュメントへの画像や図形の埋め込み</span><span class="sxs-lookup"><span data-stu-id="d0abd-406">Embed images and shapes in documents that you generate by using ER</span></span>](electronic-reporting-embed-images-shapes.md)

[<span data-ttu-id="d0abd-407">Power BI にデータをプルするよう電子申告を構成する</span><span class="sxs-lookup"><span data-stu-id="d0abd-407">Configure Electronic reporting to pull data into Power BI</span></span>](general-electronic-reporting-report-configuration-get-data-powerbi.md)