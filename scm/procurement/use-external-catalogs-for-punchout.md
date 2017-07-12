---
title: "パンチアウト eProcurement の外部カタログの使用"
description: "このトピックでは、外部カタログを使用して要求を作成し送信する方法について説明します。"
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 01955aefb27bd18809b35fd025c9dd1b8eb70520
ms.contentlocale: ja-jp
ms.lasthandoff: 06/20/2017


---

# <a name="use-external-catalogs-for-punchout-eprocurement"></a>パンチアウト eProcurement の外部カタログの使用
パンチアウト e-procurement の外部カタログを使用すると、自身のマスター データで仕入先の製品に関する情報を管理する必要はありません。 代わりに、仕入先の Web サイトのショッピング カートが正しい製品情報を持つ要求明細行に変換されます。 

自身のマスター データでは仕入先の製品の説明や価格を管理しないようにします。 代わりに、パンチアウト e-procurement の外部カタログを使用します。 その後、従業員は要求を作成するときに仕入先の外部カタログ サイトに「パンチアウト」できます (つまり、システムを離れて仕入先のサイトに移動します)。 仕入先の Web サイトでショッピング カートに追加される製品は、要求明細行に変換できます。 そのため、製品 ID、名前、価格などの正しい製品情報を取得することになります。

外部カタログを使用するには、従業員は [**自分の購買要求**] ページで要求を作成する必要があります。

要求を作成する従業員は、要求の作成者と呼ばれます。 作成者として、次のタスクを実行できます。

**外部カタログ** 明細行アクションを使用して、指定された要求者、購買組織、および受取作業単位に使用可能なすべての外部カタログを含むページを開きます。

アクセス許可に応じて、要求者、購買組織、および受取作業単位を変更します。 それらの値の変更により、要求者に使用可能な外部カタログのリストが変わる可能性があります。 使用可能な外部カタログは、購買組織あるいは受取作業単位の現在有効な購買ポリシーによって異なります。 これらのポリシーは、特定の調達カテゴリへのアクセスを許可したり禁止したりすることができます。 したがって、これらの調達カテゴリにマップされている外部カタログのリストが影響を受ける可能性があります。

ポリシーの詳細については、「[購買ポリシー](../procurement/purchase-policies.md)」を参照してください。

- 特定の調達カテゴリの外部カタログを検索するには、カタログ検索フィールドにテキストを入力します。
- 仕入先の Web サイトで仕入先の外部カタログから製品を追加するには、その外部カタログをクリックします。 その後、製品をショッピング カートに追加し、チェックアウトします。 ショッピング カート明細行が Microsoft Dynamics 365 に転送されます。

調達カテゴリの複数のオプションがある場合は、要求に明細行を追加する前に、正しい調達カテゴリを選択します。
明細行が要求に追加されると、外部カタログを使用せずにさらに明細行を追加することができます。 または、外部カタログを使用して明細行の追加を続行することができます。

要求が準備できたら、[**ワークフロー**] > [**送信**] アクションを使用して承認のためにその要求を送信します。
