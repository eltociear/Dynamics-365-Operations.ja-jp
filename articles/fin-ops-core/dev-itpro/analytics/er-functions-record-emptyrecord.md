---
title: EMPTYRECORD ER 機能
description: このトピックでは、EMPTYRECORD 電子申告 (ER) 関数の使用方法についての情報を提供します。
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
ms.openlocfilehash: a02cdd085a236065bb3622b36f7d3284144d96e5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041287"
---
# <a name="EMPTYRECORD">EMPTYRECORD ER 機能</a>

[!include [banner](../includes/banner.md)]

`EMPTYRECORD`関数は、指定されたリストまたはレコードと同じ構造を持つ*コンテナー (記録)* 値を返します。

## <a name="syntax"></a>構文

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a>引数

`list`: *レコード リスト*または*コンテナー (レコード)*

*レコード リスト*または*コンテナー (レコード)* タイプのデータ ソースの有効なパス。

## <a name="return-values"></a>戻り値

*コンテナー (レコード)*

結果レコード値。

## <a name="usage-notes"></a>使用上の注意

> [!NOTE] 
> null レコードは、すべてのフィールドが空の値があるレコードです。 空の値が数字の場合は **0** (ゼロ)、文字列の場合、空の文字列などです。

## <a name="example"></a>例

`EMPTYRECORD (SPLIT ("abc", 1))` は、`SPLIT` 関数で返ってきたリストと同じ構造を持つ新しい空のレコードを返します。 詳細については、[SPLIT](er-functions-list-split.md) をご覧ください。

## <a name="additional-resources"></a>追加リソース

[レコード機能](er-functions-category-record.md)
