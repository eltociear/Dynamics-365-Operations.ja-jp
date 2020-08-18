---
title: ValidateFieldValueEventArgs クラス
description: このトピックでは、ValidateFieldValueEventArgs クラスについて説明します。
author: robinarh
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15254286b71ebb062c677d1ed563bfb6524df2ff
ms.sourcegitcommit: 7b0cec2e898ef8ee33baf72f18cdd9cba0e9399c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2020
ms.locfileid: "3502690"
---
# <a name="class-validatefieldvalueeventargs"></a>クラス ValidateFieldValueEventArgs

[!include [banner](../../includes/banner.md)]

```xpp
class ValidateFieldValueEventArgs extends ValidateEventArgs
```

## <a name="remarks"></a>備考

## <a name="examples"></a>例

## <a name="methods"></a>メソッド

| 方法                                                         | 説明 |
|----------------------------------------------------------------|-------------|
| public str parmFieldName()                                     |             |
| public int parmArrayIndex()                                    |             |
| public void new(str fieldName, int arrayIndex, boolean result) |             |

## <a name="method-parmfieldname"></a>メソッド parmFieldName

```xpp
public str parmFieldName()
```

### <a name="return-value---parmfieldname"></a>戻り値 - parmFieldName

## <a name="method-parmarrayindex"></a>メソッド parmArrayIndex

```xpp
public int parmArrayIndex()
```

### <a name="return-value---parmarrayindex"></a>戻り値 - parmArrayIndex

## <a name="method-new"></a>メソッド new

```xpp
public void new(str fieldName, int arrayIndex, boolean result)
```

### <a name="parameters---new"></a>パラメーター - new

fieldName  

<!-- -->

arrayIndex  

<!-- -->

件の結果  
