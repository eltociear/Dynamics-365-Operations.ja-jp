---
title: データの選択
description: このトピックでは、X++ 言語での select ステートメントについて説明します。
author: robinarh
manager: AnnBe
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: 150273
ms.search.region: Global
ms.author: robinr
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 64c0dd40847a4e99f45aedff9d0a4b559ce93569
ms.sourcegitcommit: 4ba6817b7aa7735a291a021022b4c12c2de5f2eb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "3505948"
---
# <a name="select-data"></a>データの選択

[!include [banner](../../includes/banner.md)]

**select** ステートメントは、データベースからデータをフェッチまたは操作します。

+ すべての**選択**ステートメントではレコードをフェッチするためテーブル変数を使用します。 この変数は、**select** 文を実行する前に宣言する必要があります。
+ **select** ステートメントは、レコードを 1 つだけ、またはフィールドをフェッチします。 複数のレコードをフェッチまたは移動したりするには、**next** ステートメントまたは **[while select](xpp-while-select.md)** ステートメントを使用できます。
    + **next** ステートメントは、テーブルの次のレコードをフェッチします。 **選択**ステートメントの前に、**次**ステートメントがある場合、エラーが発生します。 **次**ステートメントを使用する場合、**firstOnly** 検索オプションを使用しません。
    + **while select** ステートメントを使用して複数のレコードを移動する方がより適切です。
+ **select** ステートメントの結果はテーブル バッファ変数に返されます。
+ **選択**ステートメントのフィールド リストを使用すると、これらのフィールドでは、テーブル変数が使用されます。

次の例では、**CustTable** テーブルの最初の行のすべての列をフェッチし、行の **AccountNum** 列を出力します。

```xpp
CustTable custTable;
select * from custTable;
info("AccountNum: " + custTable.AccountNum);
```

次の例では、**CustTable** テーブルで各行の **AccountNum** を出力します。

```xpp
CustTable custTable;
while select * from custTable
{
    info("AccountNum: " + custTable.AccountNum);
}
```

次の例では、**select** ステートメントによって返された最初の 2 つの行の **AccountNum** を出力します。

```xpp
CustTable custTable;
select * from custTable;
info("AccountNum: " + custTable.AccountNum);

next custTable;
info("AccountNum: " + custTable.AccountNum);
```

詳細については、[select ステートメント](xpp-select-statement.md)を参照してください。