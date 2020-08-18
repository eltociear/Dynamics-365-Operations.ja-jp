---
title: IISStringList クラス
description: このトピックでは、IISStringList クラスについて説明します。
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
ms.openlocfilehash: 087be3b8f22903ca6175d197e2d081f30d725e69
ms.sourcegitcommit: 7b0cec2e898ef8ee33baf72f18cdd9cba0e9399c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2020
ms.locfileid: "3502904"
---
# <a name="class-iisstringlist"></a>クラス IISStringList

[!include [banner](../../includes/banner.md)]

```xpp
class IISStringList extends Object
```

IISStringList クラスは、インターネット インフォメーション サービス (IIS) によって提供される StringList オブジェクトをラップします。

## <a name="remarks"></a>備考

IISStringList クラスのメソッドと、IIS によって提供される StringList オブジェクトのメソッドとの間には、1 対 1 の接続があります。 したがって、IISStringList クラスのメソッドの詳細については、IIS の Microsoft ドキュメントを参照してください。 IISStringList クラスの使用は、IIS がインターネット コネクタによって実行されている場合にのみ有効です。

## <a name="examples"></a>例

## <a name="methods"></a>メソッド

| 方法                           | 説明                                     |
|----------------------------------|-------------------------------------------------|
| public int count()               |                                                 |
| public COMEnum2Variant getEnum() |                                                 |
| public ComInterface interface()  |                                                 |
| public str item(\[str item\])    |                                                 |
| public void finalize()           |                                                 |
| public void new(COM stringList)  | Object クラスの新しいインスタンスを初期化します。 |

## <a name="method-count"></a>メソッド count

```xpp
public int count()
```

### <a name="return-value---count"></a>戻り値 - count

## <a name="method-getenum"></a>メソッド getEnum

```xpp
public COMEnum2Variant getEnum()
```

### <a name="return-value---getenum"></a>戻り値 - getEnum

## <a name="method-interface"></a>メソッド interface

```xpp
public ComInterface interface()
```

### <a name="return-value---interface"></a>戻り値 - interface

## <a name="method-item"></a>メソッド item

```xpp
public str item([str item])
```

### <a name="parameters---item"></a>パラメーター - item

品目  

### <a name="return-value---item"></a>戻り値 - item

## <a name="method-finalize"></a>メソッド finalize

```xpp
public void finalize()
```

## <a name="method-new"></a>メソッド new

Object クラスの新しいインスタンスを初期化します。

```xpp
public void new(COM stringList)
```

### <a name="parameters---new"></a>パラメーター - new

stringList  
