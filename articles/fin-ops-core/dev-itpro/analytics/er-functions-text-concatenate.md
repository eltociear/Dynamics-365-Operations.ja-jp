---
title: CONCATENATE ER 機能
description: このトピックでは、CONCATENATE 電子申告 (ER) 関数の使用方法についての情報を提供します。
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
ms.openlocfilehash: 04c7b32e2a9578f8864570a552817ec3ce28fa43
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041176"
---
# <a name="CONCATENATE">CONCATENATE ER 機能</a>

[!include [banner](../includes/banner.md)]

`CONCATENATE` 関数は、一つの文字列に結合された後、*文字列*値として指定されたすべてのテキスト文字列を返します。

## <a name="syntax"></a>構文

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>引数

`text 1`: *文字列*

*文字列*データ タイプのデータ ソースの参照。 この引数は必須です。

`text N`: *文字列*

*文字列*データ タイプのデータ ソースの参照。 これらの追加引数はオプションです。

## <a name="return-values"></a>戻り値

*文字列*

結果テキスト値。

## <a name="example"></a>例

`CONCATENATE ("abc", "def")`" は、**abcdef" を返します**。

## <a name="usage-notes"></a>使用上の注意

式 `"abc" & "def"` も、**"abcdef"** を返します。

## <a name="additional-resources"></a>追加リソース

[テキスト関数](er-functions-category-text.md)
