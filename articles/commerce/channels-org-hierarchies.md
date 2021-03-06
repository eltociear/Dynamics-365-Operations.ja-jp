---
title: 組織階層の設定
description: このトピックでは、Microsoft Dynamics 365 Commerce での組織階層の設定方法について説明します。
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6c19542089526c1e17fb1133d52cf042f244fb80
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002338"
---
# <a name="set-up-organization-hierarchies"></a>組織階層の設定


[!include [banner](includes/banner.md)]

このトピックでは、Microsoft Dynamics 365 Commerce での組織階層の設定方法について説明します。

## <a name="overview"></a>概要

チャネルを作成する前に、組織階層が設定されていることを確認する必要があります。

業務について、さまざまな観点から表示と報告を行う組織階層を使用できます。 たとえば、税金、法律、または法令についての報告に使用する 1 つの階層を設定できます。 法的に必須でなくても、内部報告に使用する財務情報を報告する別の階層を設定できます。

組織階層を作成する前に、組織を作成する必要があります。 詳細については、[法人の作成](channels-legal-entities.md) または [作業単位の作成](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json) を参照してください。


詳細については、次のトピックを参照してください。
- [組織と組織階層の概要](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies)
- [組織階層の計画](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy?toc=/dynamics365/commerce/toc.json)
- [組織階層の作成](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a>組織階層の作成

組織階層を作成するには、次の手順に従います。

1. ナビゲーション ウィンドウで、**モジュール \> Retail と Commerce \> チャネル設定 \> 組織階層**の順に移動します。
1. アクション ウィンドウで、**新規**を選択します。
1. **名前**フィールドに値を入力します。
1. **目的**セクションで、**目的の割り当て**を選択します。
1. 一覧で、目的のレコードを見つけ、選択します。 組織階層に割り当てる目的を選択します。
1. **割り当て済の階層**セクションで、**追加**を選択します。
1. 一覧で、選択された行をマークします。 作成した階層を検索します。
1. **OK** を選択します。

次の図は、架空の「Adventure Works」店舗のセットのために作成された組織階層の例を示しています。

![組織階層の例](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a>階層への組織の追加

階層に組織を追加するには、次の手順に従います。

1. 一覧で、目的のレコードを見つけ、選択します。 階層を選択します。
1. アクション ウィンドウで、**表示**を選択します。
1. 必要に応じて組織を追加します。
1. 組織を追加するには、**編集**を選択して、**挿入**を選択します。 変更が完了したら、ドラフトを保存して変更を公開できます。

次の図は、「モール」、「アウトレット」、「オンライン」、および「コール センター」チャネルの 4 つの原価部門が追加された階層ルートに追加された法人を示しています。 その後、さまざまな小売、コール センター、およびオンライン チャネルをそれぞれに追加できます。

![階層デザイナーの例](media/hierarchy-designer.png)

## <a name="additional-resources"></a>追加リソース

[組織と組織階層の概要](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[組織階層の計画](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[法人の作成](channels-legal-entities.md)

[作業単位の作成](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[チャネルの概要](channels-overview.md)

[チャネル設定の前提条件](channels-prerequisites.md)
