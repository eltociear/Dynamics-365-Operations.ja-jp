---
title: TABLENAME2ID ER 関数
description: このトピックでは、TABLENAME2ID 電子申告 (ER) 関数がどのように使用されるかについての情報を提供します。
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
ms.openlocfilehash: 951de1d1505508ebb6abeff5b80ecef10573e117
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041270"
---
# <a name="TABLENAME2ID">TABLENAME2ID ER 関数</a>

[!include [banner](../includes/banner.md)]

`TABLENAME2ID` 関数は、*整数*値として指定されたテーブル名に対応するテーブル ID の数値表現を返します。

## <a name="syntax"></a>構文

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a>引数

`text`: *文字列*

有効なテーブル名を表すテキスト値。

## <a name="return-values"></a>戻り値

*整数*

結果数値。

## <a name="usage-notes"></a>使用上の注意

この関数を実行すると、同じ会社名が使用されている場合でも、Microsoft Dynamics 365 Finance の異なるインスタンスに結果を得ることができます。

## <a name="example"></a>例

`TABLENAME2ID ("Intrastat")` は、**1510** を返します。

## <a name="additional-resources"></a>追加リソース

[その他 (ビジネス ドメインの特定の) 関数](er-functions-category-other.md)
