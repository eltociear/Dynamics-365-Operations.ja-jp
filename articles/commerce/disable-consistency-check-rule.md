---
title: 小売トランザクションの整合性チェックのルールを無効にする
description: このトピックでは、Microsoft Dynamics 365 Commerce に導入された小売トランザクションの整合性チェックのルールを無効にする機能について説明します。
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: b11b901fafc3907e9d3cae5cd554cc9a868a414c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004346"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a><span data-ttu-id="35609-103">小売トランザクションの整合性チェックのルールを無効にする</span><span class="sxs-lookup"><span data-stu-id="35609-103">Disable rules in the retail transaction consistency checker</span></span> 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="35609-104">小売業者に固有の業務シナリオとプロセスが実現します。</span><span class="sxs-lookup"><span data-stu-id="35609-104">Retailers can have business scenarios and processes that are unique to them.</span></span> <span data-ttu-id="35609-105">したがって、コマース トランザクション整合性チェックに既定で含まれるあらゆるルールが、すべての小売業者に適用されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="35609-105">Therefore, not all the rules that are included by default in the commerce transaction consistency checker are applicable to all retailers.</span></span> <span data-ttu-id="35609-106">差異を調節するため、Microsoft Dynamics 365 Commerce には、適用されないルールを無効にするための機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="35609-106">To accommodate differences, Microsoft Dynamics 365 Commerce provides functionality that can be used to disable the rules that aren't applicable.</span></span>

<span data-ttu-id="35609-107">ご利用中の環境内にある小売トランザクション整合性チェックで使用できるルールの一覧を表示したり、各ルールの状態を表示したりするには、**Retail と Commerce \>本社の設定 \> パラメーター \> コマース パラメーター** に移動し、**トランザクションの検証** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="35609-107">To view the list of rules that are available in the transaction consistency checker in your environment, and to see the status of each rule, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and select the **Transaction validation** tab.</span></span>

<span data-ttu-id="35609-108">既定では、すべてのルールの状態が **有効** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="35609-108">By default, the status of every rule is set to **Enabled**.</span></span> <span data-ttu-id="35609-109">したがって、すべてのルールを使用して小売トランザクションを検証してからコマース明細書に取り込まれます。</span><span class="sxs-lookup"><span data-stu-id="35609-109">Therefore, all the rules are used to validate transactions before they are pulled into the commerce statements.</span></span> <span data-ttu-id="35609-110">ルールを無効にするには、状態を **無効**に変更します。</span><span class="sxs-lookup"><span data-stu-id="35609-110">To disable a rule, change its status to **Disabled**.</span></span> <span data-ttu-id="35609-111">明細書の計算プロセス中にトランザクションが検証されている場合、無効になっているルールは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="35609-111">Disabled rules aren't considered when transactions are validated during the statement calculation process.</span></span>

<span data-ttu-id="35609-112">有効になっているルールに関係なく、検証プロセス全体を回避するには **Retail と Commerce \> 本社の設定 \> パラメーター \> コマース パレメーター**に移動し、**トランザクションの検証** タブで、**コマース トランザクションの整合性チェックの無効化** オプション **はい** に設定します。</span><span class="sxs-lookup"><span data-stu-id="35609-112">To bypass the whole validation process, regardless of the rules that are enabled, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and then, on the **Transaction validation** tab, set the **Disable consistency checker for Commerce transactions** option to **Yes**.</span></span> <span data-ttu-id="35609-113">このオプションを **いいえ** に設定すると、ユーザー インターフェイス (UI) から **はい** に設定し直すことはできません。</span><span class="sxs-lookup"><span data-stu-id="35609-113">After this option is set to **No**, it can't be set back to **Yes** from the user interface (UI).</span></span>