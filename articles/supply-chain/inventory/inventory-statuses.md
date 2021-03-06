---
title: 在庫状態
description: この記事は、在庫を分類し、追跡する在庫状態を使用する方法について説明します。
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 79ddc91aa3bbe0613543595006b10e6e0bef4427
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653492"
---
# <a name="inventory-statuses"></a>在庫状態

[!include [banner](../includes/banner.md)]

この記事は、在庫を分類し、追跡する在庫状態を使用する方法について説明します。

在庫を分類するために在庫状態を使用できます。 これにより、補充またはプット アウェイ作業などの適切なアクションを開始できます。

在庫状態の使用方法の例を次に示します。

-   手持在庫、入庫トランザクション、および出荷トランザクションの在庫状態を作成します。
-   倉庫トランザクションの既定の在庫状態を指定します。
-   着荷前、着荷時、または品目が棚卸資産移動中にプット アウェイされる場合に品目の棚卸資産の状態を変更します。
-   返品された品目の価格決定およびマスタ プラン中の品目補充の計画のために在庫状態を使用します。

棚卸資産の状態は保管分析コード グループの分析コードの 1 つです。 在庫状態が使用できるか使用できないかを分類できます。また、**在庫ブロック** パラメーターを使用して、使用できない在庫状態の品目をブロックできます。 ブロックされた状態の品目は現物在庫と見なされ、製造オーダー、販売注文、移動オーダー、または出荷トランザクションで使用できません。

入荷作業のために使用できるか、使用できないかいずれかの在庫状態の倉庫品目を使用できます。 たとえば、**準備完了**という名前の使用可能な状態、**破損**という名前の使用できない状態、**ブロック**という名前のブロックされた状態を作成します。 入庫品目または返品品目の発注書を作成するときに、品目が破損したり、または壊れていれば、購買注文明細行の **破損** で、これらの品目の在庫状態を変更できます。 これらの品目を受領したら、状態が自動的に **ブロック** に設定されます。 モバイル デバイスを使用して破損した品目をスキャンすると、Supply Chain Management は、場所ディレクティブおよび作業テンプレートを使用し、これらの品目をプット アウェイするための適切な場所または場所の範囲に関する情報を表示します。 返品品目の場合、**在庫トランザクション** ページで **引当** 払出タイプが作成されます。

出荷作業の場合、使用可能な在庫状態の品目を使用します。 状態が **破損** の品目で、これらの品目にマスタ プランが実行されている場合、品目は存在しないと見なされ、在庫が自動的に補充されます。

在庫状態を設定したら、サイト、品目、および倉庫の既定の在庫状態を設定できます。 また、販売、移動、発注書の既定のステータスを設定できます。 販売注文および出荷の移動オーダーの既定のステータスでは、**在庫ブロック** オプションは **はい** に設定できません。 サイト、倉庫、品目、発注書、移動オーダー、または販売注文の既定の設定に基づく在庫状態は、モバイル デバイスを使用して、発注書、販売注文、または在庫移動指示明細行で変更できます。

利用可能な在庫状態を持つ品目の補充を計画するには、**保管分析コード グループ** ページで、保管分析コードの **分析コード別補充計画** オプションを選択します。 **品目の補充** ウィザードを開くと、使用可能な状態の品目が **ステータス** ページに表示されます。 これらの品目の補充設定を作成するには、利用可能な棚卸資産の状態の棚卸資産の状態 ID を選択します。 補充設定に基づいて、品目要件を計算し、マスタ プラン中に利用できる品目の供給と需要を予測できます。 ブロックされた在庫状態の品目補充設定を作成することはできません。 代わりに、**品目補充** ページを使用して、品目補充パラメータを作成または変更します。
