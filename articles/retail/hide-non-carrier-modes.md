---
title: POS の出荷オプションから配送業者以外の配送モードを非表示にする
description: このトピックでは、販売時点管理 (POS) アプリケーションで出荷注文が作成された際、配送業者以外の配送モードが選択に表示されないようにする構成オプションについて説明します。
author: hhainesms
manager: annbe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhainesms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 09ea83b3336b208f8af0a91025c2e6c50d64c385
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "2659024"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a><span data-ttu-id="16142-103">POS の出荷オプションから配送業者以外の配送モードを非表示にする</span><span class="sxs-lookup"><span data-stu-id="16142-103">Hide non-carrier delivery modes from the shipping options in POS</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="16142-104">このトピックでは、販売時点管理 (POS) アプリケーションで使用可能な構成オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="16142-104">This topic describes a configuration option that is available for the point of sale (POS) application.</span></span> <span data-ttu-id="16142-105">この構成オプションにより、POS で出荷注文が作成された際の配送モードの選択動作が変更されます。</span><span class="sxs-lookup"><span data-stu-id="16142-105">This configuration option changes the behavior for the selection of a mode of delivery when shipment orders are created in POS.</span></span>

<span data-ttu-id="16142-106">POS で顧客の出荷注文を作成する際、出荷の配送モードを選択できます。</span><span class="sxs-lookup"><span data-stu-id="16142-106">When users create customer shipment orders in POS, they can select a mode of delivery for the shipment.</span></span> <span data-ttu-id="16142-107">この機能は、注文全体が出荷されているか、選択された明細行のみであるかにかかわらず使用可能です。</span><span class="sxs-lookup"><span data-stu-id="16142-107">This functionality is available regardless of whether the whole order is being shipped or only selected lines.</span></span>

<span data-ttu-id="16142-108">既定では、配送モードが選択されたダイアログ ボックスには、チャネル、品目、および配送先住所の組み合わせに対する有効な配送モードがすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="16142-108">By default, the dialog box where a mode of delivery is selected shows all the valid modes of delivery for the combination of a channel, an item, and a delivery address.</span></span> <span data-ttu-id="16142-109">これらの配送モードは、**配送モード**ページの Retail Headquarters (**販売とマーケティング \> 設定 \> 配送 \> 配送モード**) で定義されます。</span><span class="sxs-lookup"><span data-stu-id="16142-109">These modes of delivery are defined on the **Modes of delivery** page in Retail Headquarters (**Sales and marketing \> Setup \> Distribution \> Modes of delivery**).</span></span> <span data-ttu-id="16142-110">「配送業者以外」の配送モード、たとえば **Carryout** や **Pickup** などは、ダイアログ ボックスでの選択のために表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="16142-110">"Non-carrier" modes of delivery, such as **Carryout** or **Pickup**, might also appear for selection in the dialog box.</span></span>

<span data-ttu-id="16142-111">ただし、このダイアログ ボックスには、配送業者以外の配送モードを隠すことができる機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="16142-111">However, a feature has been added that lets you hide non-carrier modes of delivery in the dialog box.</span></span> <span data-ttu-id="16142-112">この機能を有効にするには**小売パラメーター**ページの、**顧客注文**タブで、**出荷注文に対する配送モードのみを表示**オプションを**はい**に設定します。</span><span class="sxs-lookup"><span data-stu-id="16142-112">To turn on this feature, on the **Retail parameters** page, on the **Customer orders** tab, set the **Show only carrier mode options for ship orders** option to **Yes**.</span></span> <span data-ttu-id="16142-113">この機能を有効にして、情報をチャネル データベースに同期するための適切な配送ジョブを実行した後は、POS での出荷順序の作成プロセス中に、配送業者以外の配送モードは表示されないようになります。</span><span class="sxs-lookup"><span data-stu-id="16142-113">After you turn on this feature and run the appropriate distribution jobs to sync the information to the channel database, non-carrier modes of delivery won't appear for selection during the process of creating shipment orders in POS.</span></span>