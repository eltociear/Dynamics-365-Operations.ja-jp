---
title: ISVALIDCHARACTERISO7064 ER 関数
description: このトピックでは、ISVALIDCHARACTERISO7064 電子申告 (ER) 関数がどのように使用されるかについての情報を提供します。
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: c858ad72db7afe63baca8288f312548c4fc37d5c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041403"
---
# <a name="ISVALIDCHARACTERISO7064">ISVALIDCHARACTERISO7064 ER 関数</a>

[!include [banner](../includes/banner.md)]

`ISVALIDCHARACTERISO7064` 機能は、指定された文字列が有効な国際銀行番号 (IBAN) を表す場合、**TRUE** の*ブール*値を返します。 それ以外の場合は、**FALSE** の*ブール*値が返されます。

## <a name="syntax"></a>構文

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>引数

`text`: *文字列*

IBAN を表すテキスト値。

## <a name="return-values"></a>戻り値

*文字列*

結果テキスト値。

## <a name="example"></a>例

`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` は、**TRUE** を返します。 

`ISVALIDCHARACTERISO7064 ("AT61")` は、**FALSE** 返します。

## <a name="additional-resources"></a>追加リソース

[その他 (ビジネス ドメインの特定の) 関数](er-functions-category-other.md)
