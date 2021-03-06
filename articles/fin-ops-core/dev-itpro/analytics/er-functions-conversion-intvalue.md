---
title: INTVALUE ER 関数
description: このトピックでは、INTVALUE 電子申告 (ER) 関数の使用方法についての情報を提供します。
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 5e06236bf1d158a4cf579b8b89cc0a5f7d815c38
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042656"
---
# <a name="INTVALUE">INTVALUE ER 関数</a>

[!include [banner](../includes/banner.md)]

`INTVALUE` 関数は、指定された文字列を表す *Int* 値を返します。

## <a name="syntax-1"></a>構文 1

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a>構文 2

```vb
INTVALUE (number)
```

## <a name="arguments"></a>引数

`text`: *文字列*

*Int* 数に変換する必要があるテキスト値。

`number`: *実数*または*整数*

*Int* 数に変換する必要がある数値の*実数*または*整数*値。

## <a name="return-values"></a>戻り値

*Int*

結果数値。

## <a name="usage-notes"></a>使用上の注意

任意の小数点以下の桁数が切り捨てられます。

## <a name="example-1"></a>例 1

`INTVALUE ("100.77")` は、*Int* の値 **100** を返します。

## <a name="example-2"></a>例 2

`INTVALUE (-100.77)` は、*Int* の値 **-100** を返します。

## <a name="additional-resources"></a>追加リソース

[型変換関数](er-functions-category-type-conversion.md)
