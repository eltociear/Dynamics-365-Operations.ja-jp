---
title: 承認テスト ライブラリのベスト プラクティス
description: このトピックは承認テスト ライブラリのベスト プラクティスについて説明します。
author: MichaelFruergaardPontoppidan
manager: AnnBe
ms.date: 03/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: MichaelFruergaardPontoppidan
ms.search.validFrom: 2018-XX-XX
ms.dyn365.ops.version: App Update 10.0.2
ms.openlocfilehash: 5dcfd0a667bfc0ded7855a6b1deb42d84d18a15e
ms.sourcegitcommit: 9f90b194c0fc751d866d3d24d57ecf1b3c5053a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2020
ms.locfileid: "3033041"
---
# <a name="best-practices-for-the-acceptance-test-library"></a>承認テスト ライブラリのベスト プラクティス

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]


## <a name="use-var-and-declare-variables-inline"></a>var を使用して変数をインラインで宣言する

+ `var` キーワード (型推論) を使用します。
+ 離れたステートメントではなくインラインで変数を宣言します。

### <a name="do-this"></a>操作

```xpp
var item = items.default(); 
var salesOrder = data.sales().salesOrders().createDefault();
var salesLine = salesOrder.addLine().setItem(item).setInventDims([warehouse]).setQuantity(10).save();
```

### <a name="dont-do-this"></a>このようにしない

```xpp
InventTable item; 
AtlEntitySalesOrder salesOrder;
AtlEntitySaleOrderLine salesLine;
…
item = items.default(); 
salesOrder = data.sales().salesOrders().createDefault();
salesLine = salesOrder.addLine().setItem(item).setInventDims([warehouse]).setQuantity(10).save();
```

### <a name="justification"></a>両端揃え

`var` を使用する利点は記述するコードを減らし、正確な型名を覚える必要がなく、テストロジックが重要でない情報で散らかっていないことです。 全体的にテストコードが読みやすくなります。

前の例で、`item` が `ItemId`、`InventlTable`、`AtlEntityInventItem` 型かどうかは関係ありません。 重要な詳細は、一般的な既定のアイテムを含む販売明細行を作成しているということです。 `salesOrder` や `salesLine` 変数の正確な型は重要ではありません。 これらの型の契約は、命名と使用法から明らかです。

### <a name="considerations"></a>注意事項

- メソッドの戻り値の型が変わったらコンパイルを失敗させる場合は、型推論を使用しないでください。
- 意味のある変数名やメソッド名を作成できない場合は、型推論を使用しないでください。

## <a name="use-entities-instead-of-ids-as-method-parameters"></a>メソッド パラメータとして ID ではなくエンティティを使用する

一般的なデータ メソッド、作成者メソッド、および `init` メソッドは、通常 ID の代わりにレコードやエンティティを返します。 メソッドのパラメーターにレコードやエンティティを使用することをお勧めします。

### <a name="do-this"></a>操作

```xpp
var salesLine = salesOrder.addLine().setItem(item).save();
```

### <a name="dont-do-this"></a>このようにしない

```xpp
var salesLine = salesOrder.addLine().setItemId(item.ItemId).save();
```

### <a name="justification"></a>両端揃え

重要ではない専門語が散らばっていないので、コードが読みやすくなります。

### <a name="considerations"></a>注意事項

ID しかわからない場合は、ID を引数に取るメソッドを使用してください。

## <a name="use-navigation-node-shortcuts"></a>ナビゲーション ノードのショートカットを使用する

新しいドメイン領域を自動化するときは、その領域で最も頻繁に使用されるナビゲーション オブジェクトのショートカットを保持する基本クラスを導入します。

たとえば、倉庫管理エリアには `AtlWHSTestCase` という名前の基本クラスがあります。 `data.whs()`、`data.invent()`、`data.invent().items()`、`data.invent().units()` そして他のナビゲーション オブジェクトのショートカットが含まれます。 ショートカットはテスト コードを単純にします。

```xpp
class AtlWHSTestCase extends SysTestCase
{
    AtlDataRootNote          data;
    AtlDataInvent            invent;
    AtlDataInventOnHand      onHand;
    AtlDataProductItems      items;
    AtlDataWHS               whs;

    protected void initDataSetupReferences()
    {
        data = new AtlDataRootNode();
        invent = data.invent();
        onHand = data.invent().onHand();
        items = data.invent().items();
        whs = data.whs();
```

同じクラスの多くのテスト メソッド間で共有されるショートカットを導入するのも便利です。

### <a name="do-this"></a>操作

```xpp
class WHSMinMaxReplenishmentScenarioTest extends AtlWHSTestCase
…
    var item = items.default(); 
    var warehouse = invent.warehouses().default(); 
```

### <a name="dont-do-this"></a>このようにしない

```xpp
class WHSMinMaxReplenishmentScenarioTest extends SysTestCase
…
    var item = data.invent().items().default(); 
    var warehouse = data.invent().warehouses().default(); 
```

### <a name="considerations"></a>注意事項

必要なナビゲーション ノードすべてにショートカットを作成する必要はありません。 ただし、頻繁に使用されるナビゲーション ノードに対してそれらを作成することを検討してください。
