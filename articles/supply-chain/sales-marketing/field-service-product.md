---
title: Supply Chain Management の製品と Field Service の製品との同期
description: このトピックでは、Dynamics 365 Supply Chain Management から Dynamics 365 Field Service に製品を同期させるために使用されるテンプレートと基本的なタスクについて説明します。
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: c87e4cbfa375ef99d00c9a145c190af78e912d56
ms.sourcegitcommit: d8a2301eda0e5d0a6244ebbbe4459ab6caa88a95
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029408"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>Supply Chain Management の製品と Field Service の製品との同期

[!include[banner](../includes/banner.md)]

このトピックでは、Dynamics 365 Supply Chain Management から Dynamics 365 Field Service に製品を同期させるために使用されるテンプレートと基本的なタスクについて説明します。

使用されている **Field Service 製品 (Supply Chain Management から Field Service)** テンプレートは、見込顧客を現金化の**製品 (Supply Chain Management から Sales) – 直接**テンプレートに基づきます。 詳細については、[製品 (Supply Chain Management から Sales) - 直接](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct) を参照してください。

このトピックでは、**Field Service 製品 (Supply Chain Management から Field Service)** および**製品 (Supply Chain Management から Sales) – 直接**テンプレートの間の違いのみを説明します。

## <a name="templates-and-tasks"></a>テンプレートおよびタスク

**データ統合でのテンプレートの名前**

- Field Service 製品 (Supply Chain Management から Field Service)

**データ統合プロジェクトのタスク名**

- 製品 - 製品

**Field Service 製品 (Supply Chain Management から Field Service)** テンプレートは、**製品 (Supply Chain Management から Sales) – 直接**テンプレートに含まれていないマッピングに基づきます。 このマッピングは、必要な Field Service 固有のフィールド **サービス製品タイプ** が正しく設定されるようにします。

```Text
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

次の値マッピングが使用されます。

```Text
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

Supply Chain Management で、**販売可能なリリース済製品**データ エンティティ上の **Field Service 製品タイプ**の値は次のように計算されます。

- **在庫:** 製品タイプ = 製品および品目モデル グループ、在庫製品 = True
- **在庫なし:** 製品タイプ = 製品および品目モデル グループ、在庫製品 = False
- **サービス:** 製品タイプ = サービス

## <a name="template-mapping-in-data-integration"></a>データ統合のテンプレートのマッピング

次の図は、データ統合のテンプレート マッピングを示しています。

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a>Field Service 製品 (Supply Chain Management から Field Service) : 製品 - 製品

[![データ統合のテンプレートのマッピング](./media/FSProduct.png)](./media/FSProduct.png)
