---
title: 顧客の基本設定データをチャネル データベースに追加
description: このチュートリアルでは、RetailCustPreferences テーブルを小売チャネルのコマース ランタイム (CRT) に追加する方法と、新しいテーブルのデータをチャネル データベースに移動するサブジョブを作成する方法を示します。
author: kfend
manager: AnnBe
ms.date: 07/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations, Retail
ms.custom: 18081
ms.assetid: 3c13fe1d-2078-4539-b865-e266b6f56e60
ms.search.region: Global
ms.search.industry: Retail
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 71556dde632b06f51534b528000be037022fc693
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004606"
---
# <a name="add-customer-preference-data-to-channel-databases"></a><span data-ttu-id="734cd-103">顧客の基本設定データをチャネル データベースに追加</span><span class="sxs-lookup"><span data-stu-id="734cd-103">Add customer preference data to channel databases</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="734cd-104">このトピックは、Dynamics 365 for Finance and Operations バージョン 7.1 およびそれ以前のバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="734cd-104">This topic is applicable for Dynamics 365 for Finance and Operations version 7.1 and earlier.</span></span> <span data-ttu-id="734cd-105">バージョン 7.2 およびそれ以上の場合は、この実装はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="734cd-105">This implementation is not supported for versions 7.2 and higher.</span></span> <span data-ttu-id="734cd-106">これらのバージョンでは、オーバーレイせずに拡張モデルに従います。</span><span class="sxs-lookup"><span data-stu-id="734cd-106">For those versions, follow the extension model without overlayering.</span></span>

<span data-ttu-id="734cd-107">このチュートリアルでは、RetailCustPreferences テーブルを小売チャネルのコマース ランタイム (CRT) に追加する方法と、新しいテーブルのデータをチャネル データベースに移動するサブジョブを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="734cd-107">This tutorial shows how to add the RetailCustPreferences table to the commerce runtime (CRT) for the retail channel, and how to create a subjob to move the data in the new table to the channel database.</span></span>

<a name="add-the-retailcustpreferences-table-in-the-data-distribution-to-the-crt-for-the-retail-channel"></a><span data-ttu-id="734cd-108">小売チャネルの CRT へのデータ配布での RetailCustPreferences テーブルの追加</span><span class="sxs-lookup"><span data-stu-id="734cd-108">Add the RetailCustPreferences table in the data distribution to the CRT for the retail channel</span></span>
----------------------------------------------------------------------------------------------

<span data-ttu-id="734cd-109">チャネル スキーマは、チャネル データベースに送信されるデータの XML 記述です。</span><span class="sxs-lookup"><span data-stu-id="734cd-109">The channel schema is the XML description of the data that is sent to the channel database.</span></span>

1.  <span data-ttu-id="734cd-110">**小売** &gt; **本社の設定** &gt; **小売用スケジューラ** &gt; **小売チャネル スキーマ**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-110">Click **Retail** &gt; **Headquarters setup** &gt; **Retail scheduler** &gt; **Retail channel schema**.</span></span>
2.  <span data-ttu-id="734cd-111">チャネルに対応するスキーマ名を選択します。</span><span class="sxs-lookup"><span data-stu-id="734cd-111">Select the schema name that corresponds to the channel.</span></span> <span data-ttu-id="734cd-112">その後、**チャネル テーブル** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-112">Then click **Channel tables**.</span></span>
3.  <span data-ttu-id="734cd-113">**新規**をクリックし、**テーブル名**フィールドに、新しいテーブルの名前として **ax.RetailCustPreference** を入力します。</span><span class="sxs-lookup"><span data-stu-id="734cd-113">Click **New**, and then, in the **Table name** field, enter **ax.RetailCustPreference** as the name of the new table.</span></span>
4.  <span data-ttu-id="734cd-114">**チャネル テーブル フィールド**タブで、**新規**をクリックし、フィールド名 **ACCOUNTNUM**、**EMAILOPTIN**、および **RECID** を入力します。</span><span class="sxs-lookup"><span data-stu-id="734cd-114">On the **Channel table fields** tab, click **New**, and then enter the field names **ACCOUNTNUM**, **EMAILOPTIN**, and **RECID**.</span></span>
5.  <span data-ttu-id="734cd-115">**チャネル テーブル** ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="734cd-115">Close the **Channel tables** page.</span></span>

## <a name="create-a-subjob"></a><span data-ttu-id="734cd-116">サブジョブの作成</span><span class="sxs-lookup"><span data-stu-id="734cd-116">Create a subjob</span></span>
<span data-ttu-id="734cd-117">次に、チャネル データベースに新しいテーブルのデータを移動するために、CustTable ジョブのサブジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="734cd-117">Next, you create a subjob of the CustTable job to move data in the new table to the channel database.</span></span>

1. <span data-ttu-id="734cd-118">Retail Headquarters で **小売** &gt; **本社の設定** &gt; **小売用スケジューラ** &gt; **スケジューラ サブジョブ** とクリックして、そして **新規** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-118">In Retail Headquarters, click **Retail** &gt; **Headquarters setup** &gt; **Retail scheduler** &gt; **Scheduler subjobs**, and then click **New**.</span></span>
2. <span data-ttu-id="734cd-119">**サブジョブ番号**および**説明**フィールドに **RetailCustPreference** を入力します。</span><span class="sxs-lookup"><span data-stu-id="734cd-119">In the **Subjob number** and **Description** fields, enter **RetailCustPreference**.</span></span>
3. <span data-ttu-id="734cd-120">**小売チャネル スキーマ** フィールドで、**Dynamics 365 Retail** を選択します。</span><span class="sxs-lookup"><span data-stu-id="734cd-120">In the **Retail channel schema** field, select **Dynamics 365 Retail.**</span></span>
4. <span data-ttu-id="734cd-121">**チャネル テーブル名**フィールドで、**ax.RetailCustPreference** を選択します。</span><span class="sxs-lookup"><span data-stu-id="734cd-121">In the **Channel table name** field, select **ax.RetailCustPreference**.</span></span>
5. <span data-ttu-id="734cd-122">**テーブル名**フィールドで、**RetailCustPreference** を選択します。</span><span class="sxs-lookup"><span data-stu-id="734cd-122">In the **table name** field, select **RetailCustPreference**.</span></span>
6. <span data-ttu-id="734cd-123">**チャネル フィールド マッピング**タブで、**フィールドの照合**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-123">On the **Channel field mapping** tab, click **Match fields**.</span></span> <span data-ttu-id="734cd-124">**開始** フィールドと **終了** フィールドの列に入力されます。</span><span class="sxs-lookup"><span data-stu-id="734cd-124">The **From** field and **To** field columns are filled in.</span></span> <span data-ttu-id="734cd-125">**上記の手順で UI を使用する代わりに、代替方法として、コードで実行することもできます。**</span><span class="sxs-lookup"><span data-stu-id="734cd-125">**Alternative approach, instead of using the UI in the steps above this can also accomplished in code:**</span></span>
   1.  <span data-ttu-id="734cd-126">Microsoft Visual Studio を起動してから、アプリケーション オブジェクト ツリー (AOT) で **RetailCDXSeedData\_AX7** クラスを見つけます。</span><span class="sxs-lookup"><span data-stu-id="734cd-126">Start Microsoft Visual Studio, and then, in the Application Object Tree (AOT) find the **RetailCDXSeedData\_AX7** class.</span></span>
   2.  <span data-ttu-id="734cd-127">次のメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="734cd-127">Add the following method.</span></span>

           private void C_RetailCustPreference()
           {
               jobIDContainer = ['1010'];
               subjobID = 'RetailCustPreference';
               axTableName = tableStr(RetailCustPreference);
               axFieldNames = [
               fieldStr(RetailCustPreference, AccountNum),
               fieldStr(RetailCustPreference, EmailOptIn),
               fieldStr(RetailCustPreference, RecId)
               ];
           }

   3.  <span data-ttu-id="734cd-128">クラスをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="734cd-128">Compile the class.</span></span>
   4.  <span data-ttu-id="734cd-129">インターネット インフォメーション サービス (IIS) をリセットします。</span><span class="sxs-lookup"><span data-stu-id="734cd-129">Reset Internet Information Services (IIS).</span></span>
   5.  <span data-ttu-id="734cd-130">クライアントに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="734cd-130">Switch to the client.</span></span>
   6.  <span data-ttu-id="734cd-131">**小売** &gt; **本社の設定** &gt; **小売用スケジューラ** &gt; **小売用スケジューラの初期化**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-131">Click **Retail** &gt; **Headquarters setup** &gt; **Retail scheduler** &gt; **Initialize retail scheduler**.</span></span> <span data-ttu-id="734cd-132">必要なスケジューラ サブジョブ定義が生成され、サブジョブがスケジューラ ジョブに追加されます。</span><span class="sxs-lookup"><span data-stu-id="734cd-132">The required scheduler subjob definition is generated, and the subjob is added to the scheduler job.</span></span>

7. <span data-ttu-id="734cd-133">**小売** &gt; **本社の設定** &gt; **小売用スケジューラ** &gt; **小売チャネル スキーマ**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-133">Click **Retail** &gt; **Headquarters setup** &gt; **Retail scheduler** &gt; **Retail channel schema**.</span></span>
8. <span data-ttu-id="734cd-134">**小売チャンネル スキーマ** ページの、左側のナビゲーション ウィンドウで、**Dynamics 365 Retail** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-134">On the **Retail channel schema** page, in the left navigation pane, click **Dynamics 365 Retail.**</span></span>
9. <span data-ttu-id="734cd-135">**小売データの配布**タブで、**エクスポート**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-135">On the **Retail data distribution** tab, click **Export**.</span></span>
10. <span data-ttu-id="734cd-136">使用しているブラウザーに応じて、次のいずれかのステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="734cd-136">Follow one of these steps, depending on the browser that you're using:</span></span>
    -   <span data-ttu-id="734cd-137">Google Chrome を使用している場合は、XML ファイルをダウンロードするように求められる必要があります。</span><span class="sxs-lookup"><span data-stu-id="734cd-137">If you're using Google Chrome, you should be prompted to download an XML file.</span></span> <span data-ttu-id="734cd-138">ファイルをパスに保存します。</span><span class="sxs-lookup"><span data-stu-id="734cd-138">Save the file to a path.</span></span>
    -   <span data-ttu-id="734cd-139">Internet Explorer を使用している場合は、web ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="734cd-139">If you're using Internet Explorer, a webpage will open.</span></span> <span data-ttu-id="734cd-140">ページ内を右クリックし、**ソースの表示** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-140">Right-click in the page, and then click **View source**.</span></span> <span data-ttu-id="734cd-141">次に、ページ ソースのコンテンツをファイル パスに保存します。</span><span class="sxs-lookup"><span data-stu-id="734cd-141">Then save the contents of the page source to a file path.</span></span>

11. <span data-ttu-id="734cd-142">Notepad++ などテキスト エディターで、保存した XML ファイルを開き、これらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="734cd-142">In a text editor such as Notepad++, open the XML file that you just saved, and follow these steps.</span></span>
    1.  <span data-ttu-id="734cd-143">次の行を検索します: **&lt;Table name=“RetailCustTable”&gt;**。</span><span class="sxs-lookup"><span data-stu-id="734cd-143">Search for the following line: **&lt;Table name=“RetailCustTable”&gt;**.</span></span> <span data-ttu-id="734cd-144">29 行目前後と 744 行目前後に 2 つのインスタンスがあります。</span><span class="sxs-lookup"><span data-stu-id="734cd-144">There are two instances, at approximately line 29 and line 744.</span></span>
    2.  <span data-ttu-id="734cd-145">両方の **&lt;Table name=“RetailCustTable”&gt;** コード ブロックの最後の行の後に次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="734cd-145">Add the following code after the last line in both **&lt;Table name=“RetailCustTable”&gt;** code blocks.</span></span> <span data-ttu-id="734cd-146">コードを **&lt;/Table&gt;** タグの後に追加します。</span><span class="sxs-lookup"><span data-stu-id="734cd-146">You add the code after the **&lt;/Table&gt;** tag.</span></span>

            <Table name="RetailCustPreference">
                <LinkGroup>
                    <Link type="FieldMatch" fieldName="accountNum" parentFieldName="AccountNum" />
                </LinkGroup>
            </Table>

12. <span data-ttu-id="734cd-147">ファイルの編集が終了した後、クライアントおよび **Retail チャンネル スキーマ** ページ‎に戻ります。</span><span class="sxs-lookup"><span data-stu-id="734cd-147">After you've finished editing the file, go back to client and the **Retail channel schema** page.</span></span> <span data-ttu-id="734cd-148">左のナビゲーション ウィンドウで、**Dynamics 365 Retail** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-148">In the left navigation pane, click **Dynamics 365 Retail.**</span></span>
13. <span data-ttu-id="734cd-149">**小売データの配布**タブで、**インポート**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-149">On the **Retail data distribution** tab, click **Import**.</span></span>
14. <span data-ttu-id="734cd-150">表示されるダイアログ ボックスで、**参照**をクリックし、編集した XML ファイルを選択してから、**OK** をクリックしてファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="734cd-150">In the dialog box that opens, click **Browse**, select the XML file that you just edited, and then click **OK** to import the file.</span></span>
15. <span data-ttu-id="734cd-151">**小売チャネル スキーマ** ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="734cd-151">Close the **Retail channel schema** page.</span></span>
16. <span data-ttu-id="734cd-152">**小売** &gt; **本社の設定** &gt; **小売用スケジューラ** &gt; **スケジューラ ジョブ**の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-152">Click **Retail** &gt; **Headquarters setup** &gt; **Retail scheduler** &gt; **Scheduler job**.</span></span>
17. <span data-ttu-id="734cd-153">**スケジューラ ジョブ**ページで、**1010** をクリックし、「顧客」ジョブを選択します。</span><span class="sxs-lookup"><span data-stu-id="734cd-153">On the **Scheduler job** page, click **1010** to select the “Customers” job.</span></span>
18. <span data-ttu-id="734cd-154">**サブジョブ**タブで、**新規**をクリックし、**RetailCustPreference** をサブジョブ番号として入力します。</span><span class="sxs-lookup"><span data-stu-id="734cd-154">On the **Subjobs** tab, click **New**, and then enter **RetailCustPreference** as the subjob number.</span></span> <span data-ttu-id="734cd-155">**保存** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-155">Click **Save**.</span></span>
19. <span data-ttu-id="734cd-156"><strong>小売チャネル スキーマ</strong> ページで、スキーマ名として **Dynamics 365 Retail** を選択してから、**クエリの生成** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="734cd-156">On the <strong>Retail channel schema</strong> page, select **Dynamics 365 Retail** as the schema name, and then click **Generate queries**.</span></span>