---
title: 保証契約
description: このトピックでは、資産管理の保証契約について説明します。
author: josaw1
manager: AnnBe
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: da60d098aff96780ca1e40832db34e3c9cc835e7
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "2569688"
---
# <a name="warranty-agreements"></a>保証契約

[!include [banner](../../includes/banner.md)]

 


資産管理では、資産または資産タイプに関連付けることができる保証条件を設定できます。 保証条件は特定の期間に対して作成されます。 保証は、完全補償または部分補償を行うように設定したり、時間、経費、および品目に関連する条件を設定したりすることができます。

最初のステップでは、設備に関する仕入先保証契約を作成します。 次に、資産または資産のタイプに保証契約を関連付けます。 仕入先保証契約は、情報提供の目的でのみ使用されます。 資産に対して仕入先保証が設定されている場合は、資産の保証期間を表示できます。

## <a name="create-a-warranty-agreement"></a>保証契約の作成

保証契約には、作業時間、経費、および品目の保証について、複数の契約明細行を含めることができます。

1. **資産管理** \> **設定** \> **資産** \> **保証**を選択します。
2. **新規**を選択して製品を作成します。
3. **保証**フィールドに、保証 ID を入力します。
4. **名前**フィールドに、説明を入力します。

    **詳細**クイック タブの**資産**フィールドには、保証契約を使用する有効な資産の数が表示されます。

5. 次の手順に従って、**時間保証**と**品目保証**のクイック タブで、時間または品目に関連する保証契約に含める必要がある明細行を追加します。

    1. **明細行の追加**を選択して、新しい条件を保証に追加します。 **明細行**フィールドに、連続する明細行番号が自動的に入力されます。
    2. **期間**フィールドで、保証期間のタイプを選択します。
    3. **間隔**フィールドに数値を入力します。 このフィールドでは、保証が有効な期間数を定義します。
    4. **割合**フィールドに、保証明細行の補償割合を入力します。 この割合は、会社の補償範囲を示します。

![保証ページ](media/01-warranty.png)
