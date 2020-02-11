---
title: 製品データ エンティティ
description: このトピックでは、製品データをインポートおよびエクスポートするのに使用できる異なるエンティティに関する情報を提供します。
author: cvocph
manager: AnnBe
ms.date: 01/07/2020
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
ms.author: conradv
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: 83191ea3d07ec9e2ed6261ee997e06b802ee7645
ms.sourcegitcommit: b806f0c94d703bec39680fead827733361d47045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935942"
---
# <a name="product-data-entities"></a>製品データ エンティティ

[!include [banner](../includes/banner.md)]

製品データをインポートおよびエクスポートするには、データ エンティティを使用する必要があります。 次の表は、製品関連のデータ エンティティの詳細と、それぞれの目的に関する詳細を示します。

| エンティティ | アプリケーション オブジェクト ツリー (AOT) 名 (型) | 摘要 |
|--------|-------------------------------------------|-------|
| 製品 V2 | EcoResProductV2Entity | このエンティティは、共有製品 (特徴的製品と製品マスター) をインポートおよびエクスポートするのに使用されます。 更新が可能になります。 セット ベースの SQL 操作をサポートしていません。 データ プロトコル (OData) を開くに対して有効になっています。 |
| リリース済製品 V2 | EcoResReleasedProductV2Entity | このエンティティは、リリース済製品 (特徴的製品と製品マスター) をインポートおよびエクスポートするのに使用されます。 更新が可能になります。 共有製品が既に作成されている必要があります。 新しいリリース済製品をインポートする場合、共有製品がリリースされます。 リリース済製品マスターおよびリリース済特徴的バリアントをインポートおよびエクスポートするのに使用できる個別のエンティティもあります。 このエンティティは、セット ベースの SQL 操作または削除操作をサポートしていません。 OData に対して有効になっています。 |
| リリース済製品の作成 V2 | EcoResReleasedProductCreationV2Entity | このエンティティは、共有製品とリリース済製品を 1 つのステップでインポートするのに使用されます。 エクスポートはサポートされていますが、エンティティの目的は製品の作成であるため、これを使用しないようお勧めします。 更新はサポートされていません。 一部のフィールド (製品作成ダイアログ ボックスで使用できるフィールド) のセットはサポートされます。 セット ベースの SQL 操作をサポートしていません。 OData を通じて公開されることはありません。 |
| 製品バリアント | EcoResProductVariantEntity | このエンティティは、共有製品バリアントをインポートおよびエクスポートするのに使用されます。 更新が可能になります。 分析コード値が既に作成されている必要があります。 統合キーは、製品マスターと製品分析コードです。 このエンティティはセット ベースの SQL 操作をサポートしていません。 OData に対して有効になっています。 削除操作はサポートされます。 新しい製品分析コードの追加を使用して拡張することはできません。 |
| 製品番号 ID 別製品バリアント | EcoResProductNumberIdentifiedProductVariantEntity | このエンティティは、共有製品バリアントをインポートおよびエクスポートするのに使用されます。 更新が可能になります。 分析コード値が既に作成されている必要があります。 統合キーは製品番号 (一方、**製品バリアント** エンティティの統合キーは、製品マスターと製品分析コードです) となります。 |
| リリース済製品バリアント | EcoResReleasedProductVariantEntity | このエンティティは、リリース済製品バリアントをインポートおよびエクスポートするのに使用されます。 更新が可能になります。 共有製品バリアントが既に作成されている必要があります。 新しいリリース済製品バリアントをインポートする場合、共有製品バリアントがリリースされます。 このエンティティはセット ベースの SQL 操作をサポートしていません。 OData に対して有効になっています。 削除操作はサポートされていますが、現在のプラットフォームのバグが原因で、この使用によるデータの破損が生じています。 このエンティティは新しい製品分析コードの追加を使用して拡張することはできません。 |
| 製品番号 ID 別リリース済製品バリアント | EcoResProductNumberIdentifiedReleasedProductVariantEntity | このエンティティは**リリース済製品バリアント** エンティティに似ていますが、統合キーは製品マスターと製品分析コードの代わりに製品番号となります。 新しい製品分析コードの追加を使用して拡張することができます。 |
| 販売可能なリリース済製品 | EcoResSellableReleasedProductEntity | このエンティティは、販売可能な製品のみをエクスポートするのに使用されます。 販売可能な製品には、販売注文で使用する必要のある情報があります。 **リリース済製品**ページで**検証**機能を使用して製品を検証する場合も、同じルールが適用されます。 |
| リリース済特徴的製品 V2 | EcoResDistinctProductV2Entity | このエンティティは、特徴的製品をエクスポートするのに使用されます。 これらの特徴的製品は、製品、サブタイプ製品、および製品バリアントである場合があります。 |
| リリース済製品マスター V2 | EcoResProductMasterV2Entity | このエンティティは、製品マスターをインポートおよびエクスポートするのに使用されます。 データ管理には有効ではありません。 |
| 品目 - バーコード | EcoResProductBarcodeEntity | このエンティティは、製品およびバーコードをエクスポートするのに使用されます。 |
| 製品ライフサイクル状態 | EcoResProductLifecycleSateEntity | このエンティティは、製品に割り当てることができるさまざまな製品ライフサイクルの状態をインポートおよびエクスポートするのに使用されます。 |

> [!NOTE]
> **リリース済製品 V2** データ エンティティを使用して製品をシステムにインポートできるのは、共有製品が既に作成されている場合のみです。 それ以外の場合は、システムに製品をインポートするために、**製品の作成**データ エンティティを使用する必要があります。