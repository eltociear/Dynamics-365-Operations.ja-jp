---
title: ENUMERATE ER 関数
description: このトピックでは、ENUMERATE 電子申告 (ER) 関数の使用方法についての情報を提供します。
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d34904571ee6de8b36a0840a9470f16858489163
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042147"
---
# <a name="ENUMERATE">ENUMERATE ER 関数</a>

[!include [banner](../includes/banner.md)]

`ENUMERATE` 関数は、指定されたリストの列挙されたレコードで構成される新しい*レコード リスト*値を返します。

## <a name="syntax"></a>構文

```vb
ENUMERATE (list)
```

## <a name="arguments"></a>引数

`list`: *レコード リスト*

*レコード リスト* データ型のデータ ソースの項目の有効なパス。

## <a name="return-values"></a>戻り値

*レコード リスト*

レコードの結果リスト。

## <a name="usage-notes"></a>使用上の注意

返される列挙されたレコードのリストによって、次の追加の要素が公開されます。

- フィールドのレコード (**値**コンポーネント)
- 現在のレコード インデックス (**番号 **コンポーネント)

## <a name="example"></a>例

次の図では、**列挙型** データ ソースは、VendTable テーブルを参照する **仕入先** データ ソースの仕入先レコードの列挙型リストとして作成されます。

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

次の図は、電子申告 (ER) 形式を示しています。 この形式では、XML 形式で出力を生成するために、バインディングが作成されます。 この出力では、個々の仕入先が列挙型ノードとして表示されます。

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

次の図は、設計された形式が実行される際の結果を示します。

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a>追加リソース

[リスト機能](er-functions-category-list.md)
