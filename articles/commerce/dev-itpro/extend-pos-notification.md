---
title: POS のカスタム通知の表示
description: このトピックでは、販売時点管理 (POS) でカスタム通知を追加する方法について説明します。
author: mugunthanm
manager: AnnBe
ms.date: 09/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations, Retail
ms.custom: 28021
ms.assetid: ''
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2019-09-2019
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: c775c8e39e180ee50fb60faf2ac590eaaa4fb3a4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004582"
---
# <a name="show-custom-notifications-in-pos"></a><span data-ttu-id="ccb5d-103">POS のカスタム通知の表示</span><span class="sxs-lookup"><span data-stu-id="ccb5d-103">Show custom notifications in POS</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ccb5d-104">このトピックでは、POS でカスタム通知を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-104">This topic explains how to add custom notifications in POS.</span></span> <span data-ttu-id="ccb5d-105">このトピックは、最新のバイナリ修正プログラムが適用された Dynamics 365 for Finance and Operations および Dynamics 365 for Retail 7.3 以降のバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-105">This topic applies to Dynamics 365 for Finance and Operations and Dynamics 365 for Retail 7.3 and higher versions with latest binary fix.</span></span>

<span data-ttu-id="ccb5d-106">次のようなシナリオで、POS 通知フレームワークを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-106">You can extend POS notification framework for these scenarios:</span></span> 

- <span data-ttu-id="ccb5d-107">カスタム通知を表示して、店舗の関連付けが通知に基づいて必要なアクションを実行したり、カスタム ロジックを実行したりできるようにします。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-107">Show a custom notifications so that a store associate can perform a required actions based on that notifications or perform any custom logic.</span></span> 
- <span data-ttu-id="ccb5d-108">バックグラウンドで定期的に操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-108">Perform some operation periodically in the background.</span></span> <span data-ttu-id="ccb5d-109">ただし、パフォーマンスの問題が発生する可能性があるため、この方法はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-109">However, this is not recommend because it might cause performance issues.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="ccb5d-110">この機能の動作</span><span class="sxs-lookup"><span data-stu-id="ccb5d-110">How it works</span></span>

<span data-ttu-id="ccb5d-111">POS の通知フレームワークは、バックオフィスでコンフィギュレーションされた操作 (頻度はコンフィギュレーション可能) に対して定期的に実行され、Commerce Runtime (CRT) の通知サービス、およびバックオフィスのリアルタイム サービスを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-111">The notification framework in POS runs periodically for the configured operation in Headquarters (the frequency is configurable) and calls the notification service in commerce runtime (CRT) and Real time service in Headquarters.</span></span> <span data-ttu-id="ccb5d-112">POS が CRT で通知サービスに対する呼び出しを行うと、CRT はビジネス ロジックを実行し、特定の操作に対して POS に送信される通知があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-112">When POS makes the call to the notification service in CRT, CRT runs the business logic and checks if there is any notification to be sent to POS for that particular operation.</span></span> <span data-ttu-id="ccb5d-113">操作 ID はパラメーターとして要求に渡され、CRT 通知サービスが操作 ID を確認して通知の詳細を返します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-113">The operation ID is passed as a parameter to the request and the CRT notification service checks the operation ID and returns the notification details.</span></span> 

<span data-ttu-id="ccb5d-114">通知が存在する場合、CRT は POS に利用可能な通知があることを報告する応答を返します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-114">If the notification exists, then the CRT returns the response to POS reporting that there is a notification available.</span></span> <span data-ttu-id="ccb5d-115">この通知は、POS によって解析され、UI に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-115">POS parses this notification and shows it in the UI.</span></span> <span data-ttu-id="ccb5d-116">POS ユーザーが通知をクリックすると、POS の関連する操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-116">When the POS user clicks the notification, the relevant operation in POS is executed.</span></span> <span data-ttu-id="ccb5d-117">通知は操作に関連付けられ、操作ハンドラー内で実行するビジネス ロジックを記述します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-117">Notifications are tied to an operation and inside the operation handler write the business logic to be performed.</span></span>

<span data-ttu-id="ccb5d-118">CRT が通知に対する応答を返すと、通知、メッセージ、およびアクション パラメーターの数が返されます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-118">When the CRT returns the response for the notification, it returns the number of notifications, messages, and action parameters.</span></span> <span data-ttu-id="ccb5d-119">POS フレームワークには、応答を解析して POS 操作 ID を取得し、ユーザーが通知をクリックしたときにそれを呼び出す組み込みロジックがあります。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-119">The POS framework has built-in logic to parse the response to get the POS operation ID and call it when the user clicks the notification.</span></span> 

<span data-ttu-id="ccb5d-120">POS ユーザーが通知をクリックしたときに行われる動作について、操作内のカスタム ロジックに記述できます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-120">You can write custom logic inside the operation on what should happen when the POS user clicks the notification.</span></span> <span data-ttu-id="ccb5d-121">CRT からの POS への追加パラメーターをアクション プロパティを使用して送信し、POS の操作要求内で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-121">Additional parameters from CRT to POS can be sent using the action property, and will be available inside the operation request in POS.</span></span>

### <a name="example"></a><span data-ttu-id="ccb5d-122">例</span><span class="sxs-lookup"><span data-stu-id="ccb5d-122">Example</span></span>
<span data-ttu-id="ccb5d-123">集配の注文を準備するように POS ユーザーに通知するために、CRT に集配の注文があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-123">To notify the POS user to prepare orders for pickup, inside CRT check if there an order for pickup.</span></span> <span data-ttu-id="ccb5d-124">その場合、関連するパラメーターを使用して通知応答を更新します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-124">If so, update the notification response with relevant parameter.</span></span> <span data-ttu-id="ccb5d-125">POS が応答を解析し、通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-125">POS will parse the response and show the notification.</span></span> <span data-ttu-id="ccb5d-126">POS ユーザーが通知をクリックすると、POS は通知からのパラメーターを持つ操作を呼び出し (パラメーターを送信するかどうかは拡張機能ロジックによって異なります)、操作内で保留中のすべての集配の注文が読み取られ、POS ユーザーが追加のアクションを実行できるように、UI に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-126">When the POS user clicks the notification, POS calls the operation with the parameter from the notification (it’s up to the extension logic whether to send parameters or not) and inside the operation read all the pending orders for pickup and show it in the UI for the POS user to take further action.</span></span>

## <a name="steps-required-to-enable-notification-for-custom-operation"></a><span data-ttu-id="ccb5d-127">カスタム操作の通知を有効にするために必要な手順</span><span class="sxs-lookup"><span data-stu-id="ccb5d-127">Steps required to enable notification for custom operation</span></span>

1. <span data-ttu-id="ccb5d-128">**Retail とコマース > チャネル設定 > POS 設定 > POS > POS 操作**のバックオフィスで新しい操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-128">Create a new operation in Headquarters under **Retail and Commerce > Channel Setup > POS Setup > POS > POS operations**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ccb5d-129">カスタム操作に 5000 より大きい操作 ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-129">Use an operation ID greater than 5000 for custom operation.</span></span>
    
2. <span data-ttu-id="ccb5d-130">通知サービスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-130">Extend the notification service.</span></span>  <span data-ttu-id="ccb5d-131">通知サービスのスケジューラが実行されると、通知メッセージを取得するために、CRT とリアルタイム トランザクション サービス拡張コードの両方が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-131">When the scheduler for the notification service runs, it calls both the CRT and Real time transaction service extension code to get the notification message.</span></span>

3.  <span data-ttu-id="ccb5d-132">POS の拡張。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-132">Extend POS.</span></span> <span data-ttu-id="ccb5d-133">POS では、ユーザーが通知をクリックしたときに行われる動作について、POS 操作内のロジックに記述します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-133">In POS, write the logic inside the POS operation for what should happen when the user clicks the notification.</span></span> <span data-ttu-id="ccb5d-134">新しい POS 操作の作成方法については、[ボタン グリッド デザイナーを使用して POS 操作を POS レイアウトに追加](add-pos-operations.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-134">For instructions on how to create a new POS operation, see [Add POS operations to POS layouts by using Button grid designer](add-pos-operations.md).</span></span>

4. <span data-ttu-id="ccb5d-135">カスタム操作を使用して、バックオフィスの通知サービスをコンフィギュレーションします。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-135">Configure the notification service in Headquarters with the custom operation.</span></span> <span data-ttu-id="ccb5d-136">スケジューラを実行する場合、カスタム操作が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-136">When the scheduler runs it, includes the custom operation.</span></span> <span data-ttu-id="ccb5d-137">POS で通知をコンフィギュレーションする方法については、[ボタン グリッド デザイナーを使用して POS 操作を POS レイアウトに追加](../notifications-pos.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-137">For instructions on to configure notification in POS, see [Add POS operations to POS layouts by using Button grid designer](../notifications-pos.md).</span></span>

    <span data-ttu-id="ccb5d-138">POS ユーザーが通知をクリックすると、CRT から返された応答に基づいて、フレームワークは適切な操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-138">When the POS user clicks the notification, the framework calls the right operation based on the response returned form the CRT.</span></span> <span data-ttu-id="ccb5d-139">バックオフィスでコンフィギュレーションされているすべての通知に対して通知サービスが実行され、操作 ID と通知の詳細と共に応答が返されます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-139">The notification service runs for all the notifications configured in Headquarters and returns the response with the operation id and notification details.</span></span> <span data-ttu-id="ccb5d-140">そのため、POS は操作 ID のコンテキストを持つことになり、フレームワークはこれを使用してオペレーションの実装を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-140">So, POS will have the context of operation ID and the framework will use this to call your operation implementation.</span></span>

> [!NOTE] 
> <span data-ttu-id="ccb5d-141">通知スケジューラは、CRT とバックオフィスの両方で、新しい通知があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-141">The notification scheduler checks both CRT and Headquarters to check if there are any new notifications.</span></span> <span data-ttu-id="ccb5d-142">シナリオに応じて、バックオフィスまたは CRT のみのリアルタイム トランザクション サービスを拡張します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-142">Depending on the scenario, extend the real time transaction service in Headquarters or only CRT.</span></span> <span data-ttu-id="ccb5d-143">通知にリアルタイム処理が必要なシナリオでは、バックオフィスのリアルタイム トランザクション サービス メソッドを拡張し、リアルタイム処理が不要な場合には、CRT のみを拡張します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-143">Scenarios where real-time processing is required for the notification then extend the Real-time transaction service method in Headquarters if real-time processing is not required the extend only CRT.</span></span>

## <a name="extend-the-notification-service-in-crt"></a><span data-ttu-id="ccb5d-144">CRT の通知サービスの拡張</span><span class="sxs-lookup"><span data-stu-id="ccb5d-144">Extend the notification service in CRT</span></span>

<span data-ttu-id="ccb5d-145">CRT の通知サービスを拡張するには、**GetNotificationsExtensionServiceRequest** を上書きし、**GetNotificationsExtensionServiceResponse** を返します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-145">To extend the notification service in CRT override the **GetNotificationsExtensionServiceRequest** and return the **GetNotificationsExtensionServiceResponse**.</span></span>

<span data-ttu-id="ccb5d-146">通知サービスを拡張する方法については、Retail SDK にサンプルが用意されています (**RetailSDK\SampleExtensions\CommerceRuntime\Extensions.NotificationSample**)。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-146">There is a sample in the Retail SDK on how to extend the notification service (**RetailSDK\SampleExtensions\CommerceRuntime\Extensions.NotificationSample**).</span></span>
+ <span data-ttu-id="ccb5d-147">**GetNotificationsExtensionServiceRequest** には、操作 ID、スタッフ、およびチャネルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-147">**GetNotificationsExtensionServiceRequest**: Contains the operation ID, staff and channel.</span></span> <span data-ttu-id="ccb5d-148">この Retail Headquarters コンフィギュレーションに基づいて、POS はコンフィギュレーションされた各操作に対して通知スケジューラを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-148">Based on the Retail Headquarters configuration, POS runs the notification scheduler for each configured operation.</span></span>
+ <span data-ttu-id="ccb5d-149">**GetNotificationsExtensionServiceResponse** は、応答で通知の詳細エンティティ (**NotificationDetailCollection**) を返し、**GetNotificationsExtensionServiceResponse** を更新して、すべての通知を返します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-149">**GetNotificationsExtensionServiceResponse**: In the response return the notification detail entity (**NotificationDetailCollection**), update the **GetNotificationsExtensionServiceResponse** and return all the notifications.</span></span> <span data-ttu-id="ccb5d-150">これはコレクションなので、複数の通知を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-150">Because it is a collection, multiple notifications can be returned.</span></span>

## <a name="notification-details-entity-contains-the-below-property"></a><span data-ttu-id="ccb5d-151">通知の詳細エンティティには次のプロパティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-151">Notification details entity contains the below property</span></span>

| <span data-ttu-id="ccb5d-152">プロパティ名</span><span class="sxs-lookup"><span data-stu-id="ccb5d-152">Property name</span></span>          | <span data-ttu-id="ccb5d-153">データ型</span><span class="sxs-lookup"><span data-stu-id="ccb5d-153">Data type</span></span>      | <span data-ttu-id="ccb5d-154">説明</span><span class="sxs-lookup"><span data-stu-id="ccb5d-154">Description</span></span>                                                                 |
|------------------------|----------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="ccb5d-155">ActionProperty</span><span class="sxs-lookup"><span data-stu-id="ccb5d-155">ActionProperty</span></span>         | <span data-ttu-id="ccb5d-156">文字列</span><span class="sxs-lookup"><span data-stu-id="ccb5d-156">string</span></span>         | <span data-ttu-id="ccb5d-157">POS 操作に送信するカスタム プロパティ。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-157">Custom property to send to POS operation.</span></span>                                       |
| <span data-ttu-id="ccb5d-158">DisplayText</span><span class="sxs-lookup"><span data-stu-id="ccb5d-158">DisplayText</span></span>            | <span data-ttu-id="ccb5d-159">文字列</span><span class="sxs-lookup"><span data-stu-id="ccb5d-159">string</span></span>         | <span data-ttu-id="ccb5d-160">通知ディスプレイ テキスト。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-160">Notification display text.</span></span>                                                       |
| <span data-ttu-id="ccb5d-161">IsLiveContentOnly</span><span class="sxs-lookup"><span data-stu-id="ccb5d-161">IsLiveContentOnly</span></span>      | <span data-ttu-id="ccb5d-162">ブール</span><span class="sxs-lookup"><span data-stu-id="ccb5d-162">bool</span></span>           | <span data-ttu-id="ccb5d-163">通知がライブ コンテンツのみを対象としているかどうかを示すインジケーター。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-163">Indicator whether the notification is only for live content.</span></span>                    |
| <span data-ttu-id="ccb5d-164">IsNew</span><span class="sxs-lookup"><span data-stu-id="ccb5d-164">IsNew</span></span>                  | <span data-ttu-id="ccb5d-165">ブール</span><span class="sxs-lookup"><span data-stu-id="ccb5d-165">bool</span></span>           | <span data-ttu-id="ccb5d-166">通知が新しいかどうかを示すインジケーター。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-166">Indicator whether the notification is new or not.</span></span>                                |
| <span data-ttu-id="ccb5d-167">IsSuccess</span><span class="sxs-lookup"><span data-stu-id="ccb5d-167">IsSuccess</span></span>              | <span data-ttu-id="ccb5d-168">ブール</span><span class="sxs-lookup"><span data-stu-id="ccb5d-168">bool</span></span>           | <span data-ttu-id="ccb5d-169">通知が成功したかどうかを示すインジケーター。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-169">Indicator whether the notification was success or not.</span></span>                           |
| <span data-ttu-id="ccb5d-170">ItemCount</span><span class="sxs-lookup"><span data-stu-id="ccb5d-170">ItemCount</span></span>              | <span data-ttu-id="ccb5d-171">long</span><span class="sxs-lookup"><span data-stu-id="ccb5d-171">long</span></span>           | <span data-ttu-id="ccb5d-172">通知の数</span><span class="sxs-lookup"><span data-stu-id="ccb5d-172">Number of notification.</span></span>                                                          |
| <span data-ttu-id="ccb5d-173">LastUpdatedDateTime</span><span class="sxs-lookup"><span data-stu-id="ccb5d-173">LastUpdatedDateTime</span></span>    | <span data-ttu-id="ccb5d-174">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="ccb5d-174">DateTimeOffset</span></span> | <span data-ttu-id="ccb5d-175">アクション プロパティの項目が最後に更新された日時。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-175">The last updated date time of the item in the action property.</span></span>                   |
| <span data-ttu-id="ccb5d-176">LastUpdatedDateTimeStr</span><span class="sxs-lookup"><span data-stu-id="ccb5d-176">LastUpdatedDateTimeStr</span></span> | <span data-ttu-id="ccb5d-177">文字列</span><span class="sxs-lookup"><span data-stu-id="ccb5d-177">string</span></span>         | <span data-ttu-id="ccb5d-178">文字列形式のアクション プロパティの項目が最後に更新された日時。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-178">The last updated date time of the item in the action property in string format.</span></span> |

## <a name="detailed-steps"></a><span data-ttu-id="ccb5d-179">詳細な手順</span><span class="sxs-lookup"><span data-stu-id="ccb5d-179">Detailed steps</span></span>

1. <span data-ttu-id="ccb5d-180">Retail SDK から **Runtime.Extensions.NotificationSample.proj** を開きます (**RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.NotificationSample**)。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-180">Open **Runtime.Extensions.NotificationSample.proj** from the Retail SDK (**RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.NotificationSample**).</span></span>
2. <span data-ttu-id="ccb5d-181">標準の名前付け規則に従ってプロジェクトの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-181">Rename the project according to standard naming convention.</span></span>
3. <span data-ttu-id="ccb5d-182">プロジェクト内には、**NotificationExtensionService.cs** と呼ばれるクラス ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-182">Inside the project there is a class file called **NotificationExtensionService.cs**.</span></span> <span data-ttu-id="ccb5d-183">ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-183">Open the file.</span></span>
4. <span data-ttu-id="ccb5d-184">**GetNotificationsExtensionServiceRequest** クラスは、カスタム通知を追加するために上書きされます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-184">**GetNotificationsExtensionServiceRequest** class is overridden to add custom notification.</span></span> <span data-ttu-id="ccb5d-185">**GetNotificationsExtensionServiceRequest** を上書きし、**GetNotificationsExtensionServiceResponse** を返します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-185">Override the **GetNotificationsExtensionServiceRequest** and return the **GetNotificationsExtensionServiceResponse**.</span></span>
5. <span data-ttu-id="ccb5d-186">新しいクラスを作成して **GetNotificationsExtensionServiceRequest** を上書きするか、サンプル テンプレートを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-186">Either create a new class and override the **GetNotificationsExtensionServiceRequest** or use the sample template.</span></span> <span data-ttu-id="ccb5d-187">次の手順では、テンプレートが使用されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-187">The following steps assume that the template is used:</span></span>
6. <span data-ttu-id="ccb5d-188">**NotificationExtensionService** クラスには、メソッド名 **Process** があります。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-188">In the **NotificationExtensionService** class, there is a method names **Process**.</span></span> <span data-ttu-id="ccb5d-189">このコードは、メソッド内で操作 ID を確認し、操作 ID に基づいて通知の詳細オブジェクトを作成し、通知を追加します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-189">Inside the method the code checks the operation ID and based on the operation ID it creates notification details object and adds any notifications.</span></span> <span data-ttu-id="ccb5d-190">カスタム操作 ID かどうかを確認し、通知があるかどうかを確認するロジックを作成します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-190">Check if it's custom operation ID and then write logic to check is there are any notification.</span></span> <span data-ttu-id="ccb5d-191">通知がある場合は、詳細を含む通知オブジェクトを作成し、応答と共に返します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-191">If so, then create a notification object with the details and return it with the response.</span></span> <span data-ttu-id="ccb5d-192">その後、POS が応答を解析し、通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-192">Then POS will parse the response and show the notification.</span></span>
    > [!NOTE]
    > <span data-ttu-id="ccb5d-193">プロセス メソッド内のサンプルの実装を削除し、カスタム ロジックだけを保持します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-193">Remove the sample implementation inside the process method and just keep the custom logic.</span></span>

    ```csharp
    namespace Contoso
    {
        namespace Commerce.Runtime.NotificationSample
        {
            using System;
            using Microsoft.Dynamics.Commerce.Runtime;
            using Microsoft.Dynamics.Commerce.Runtime.DataModel;
            using Microsoft.Dynamics.Commerce.Runtime.Services.Messages;
            /// <summary>
            /// Service class responsible executing the service requests.
            /// </summary>
            public class NotificationExtensionService : SingleRequestHandler<GetNotificationsExtensionServiceRequest, GetNotificationsExtensionServiceResponse>
            {
                /// <summary>
                /// The handler for the <c>GetNotificationsExtensionServiceRequest</c> request.
                /// </summary>
                /// <param name="request">The request with the operation.</param>
                /// <returns>The notification details for the operation.</returns>
                protected override GetNotificationsExtensionServiceResponse Process(GetNotificationsExtensionServiceRequest request)
                {
                    ThrowIf.Null(request, "request");
                    NotificationDetailCollection details = new NotificationDetailCollection();
                    DateTimeOffset lastNotificationDateTime = DateTimeOffset.Now;
                    string myOperationId = "5000";
                    // do the actual work here
                    if ((request.SubscribedOperation).ToString() == myOperationId)
                    {
                        NotificationDetail detail = new NotificationDetail()
                        {
                        // Text which will display for the notification detail in the POS notification center
                        DisplayText = "Custom notification",
                        // Number of notifications found
                        ItemCount = 1,
                        // Timestamp of creation of latest notification item (Used to determine whether notification is new)
                        LastUpdatedDateTime = lastNotificationDateTime,
                        // Boolean value representing whether the attempt to get notifications for the given operation was successful
                        IsSuccess = true,
                        // If you would like POS to navigate to a specific action property for the given operation
                        // when the notification tile is clicked, define the action property as well.
                        ActionProperty = "1"
                        };
                    details.Add(detail);
                    }
                    var serviceResponse = new GetNotificationsExtensionServiceResponse(details);
                    return serviceResponse;
                }
            }
        }
    }
    ```
7. <span data-ttu-id="ccb5d-194">変更を完了すると、プロジェクトをビルドし、**\RetailServer\webroot\bin\Ext** に出力ライブラリをドロップします。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-194">Once done with the changes build the project and drop the output library in **\RetailServer\webroot\bin\Ext**.</span></span>
8. <span data-ttu-id="ccb5d-195">**CommerceRuntime.Ext.config** に出力ライブラリを登録します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-195">Register the output library in **CommerceRuntime.Ext.config**.</span></span>
9. <span data-ttu-id="ccb5d-196">CRT 拡張機能で使用されているのと同じ操作 ID を使用して、POS で新しい操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-196">Create a new operation in POS with the same operation ID used in the CRT extension.</span></span> <span data-ttu-id="ccb5d-197">この例の場合、**5000** です。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-197">In this example, it is **5000**.</span></span> <span data-ttu-id="ccb5d-198">5000 より大きい操作 ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-198">Use any operation ID greater than 5000.</span></span>
    <span data-ttu-id="ccb5d-199">ユーザーが通知タイルをクリックすると、POS フレームワークは使用される操作 ID の操作ハンドラーを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-199">When the user clicks the notification tile, the POS framework calls the operation handler for the operation id used.</span></span> <span data-ttu-id="ccb5d-200">ハンドラー内で、POS ユーザーが通知をクリックしたときに行われる動作について、必要なロジックを追加します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-200">Inside the handler, add required logic for what should happen when the POS user clicks the notification.</span></span> <span data-ttu-id="ccb5d-201">POS 操作要求、応答、およびハンドラーの作成方法については、 [販売時点管理 (POS) での注文通知の表示](add-POS-operations.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-201">For instructions on how to create a POS  operation request, response, and handler, see [Show order notifications in the point of sale (POS)](add-POS-operations.md).</span></span>
    > [!NOTE]
    > <span data-ttu-id="ccb5d-202">通知の詳細エンティティのアクション プロパティが POS 操作要求に送信され、そのアクション プロパティを使用して通知サービスから POS にカスタム情報が渡されます。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-202">The action property in the Notification detail entity will be sent to the POS operation request, use that action property to pass any custom information from the notification service to POS.</span></span>
10. <span data-ttu-id="ccb5d-203">[販売時点管理 (POS) での注文通知の表示](../notifications-pos.md) の指示に従って、通知スケジューラをコンフィギュレーションします。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-203">Configure the notification scheduler according to the instructions in [Show order notifications in the point of sale (POS)](../notifications-pos.md).</span></span>

## <a name="validate-the-customization"></a><span data-ttu-id="ccb5d-204">カスタマイズの検証</span><span class="sxs-lookup"><span data-stu-id="ccb5d-204">Validate the customization</span></span>

1. <span data-ttu-id="ccb5d-205">拡張 Cloud POS または Modern POS を起動します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-205">Launch the extended Cloud POS or Modern POS.</span></span>
2. <span data-ttu-id="ccb5d-206">POS は、通知スケジューラのコンフィギュレーションに基づいて通知サービスをトリガーします。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-206">POS triggers the notification service based on your notification scheduler configuration.</span></span>
3. <span data-ttu-id="ccb5d-207">CRT プロジェクトを w3wp.exe にアタッチして、CRT コードをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-207">Debug the CRT code by attaching the CRT project to w3wp.exe.</span></span> <span data-ttu-id="ccb5d-208">このブレークポイントは、通知サービスが POS から呼び出されたときに必ずヒットします。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-208">The breakpoint should hit whenever the notification service is called from POS.</span></span>
4. <span data-ttu-id="ccb5d-209">POS で通知を受信したら、通知をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-209">When the notification received in POS, click the notification.</span></span> <span data-ttu-id="ccb5d-210">POS 操作ハンドラーを呼び出し、ハンドラー内に記述されたカスタムロジックを実行します。</span><span class="sxs-lookup"><span data-stu-id="ccb5d-210">It should call the POS operation handler and execute the custom logic written inside the handler.</span></span>