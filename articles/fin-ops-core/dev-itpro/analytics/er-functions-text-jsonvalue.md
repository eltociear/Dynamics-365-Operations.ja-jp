---
title: JSONVALUE ER 関数
description: このトピックでは、JSONVALUE 電子申告 (ER) 関数の使用方法についての情報を提供します。
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 75f20632074cb4dead98991fd6522ab9b20b9965
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041231"
---
# <a name="JSONVALUE">JSONVALUE ER 関数</a>

[!include [banner](../includes/banner.md)]

`JSONVALUE` 関数は指定した ID を持つスカラー値を抽出し、指定したパスでアクセスする JavaScript Object Notation (JSON) 形式で、データを解析します。 次に、抽出したスカラー値を*文字列*値として返します。

## <a name="syntax"></a>構文

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>引数

`input`: *文字列*

JSON データを含む*文字列*型のデータ ソースの有効なパス。

`path`: *文字列*

JSON データのスカラー値の識別子。

## <a name="return-values"></a>戻り値

*文字列*

結果テキスト値。

## <a name="example"></a>例

**JsonField** データ ソースは、JSON 形式の次のデータを含みます: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**。 この場合、`JSONVALUE (JsonField, "BuildNumber")` 式は*文字列*データ型の次の値を返します: **"7.3.1234.1"**。

## <a name="additional-resources"></a>追加リソース

[テキスト関数](er-functions-category-text.md)
