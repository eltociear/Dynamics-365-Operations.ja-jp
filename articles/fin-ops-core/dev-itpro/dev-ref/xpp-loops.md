---
title: X++ ループ ステートメント
description: このトピックでは、X++のループ ステートメントについて説明します。
author: RobinARH
manager: AnnBe
ms.date: 06/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: 150213
ms.assetid: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 75668d97d407c0c95490dd238f0d824b7221818d
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550121"
---
# <a name="x-loop-statements"></a>X++ ループ ステートメント

[!include [banner](../includes/banner.md)]

このトピックでは、X++のループ ステートメントについて説明します。 ループ ステートメントは、**for**、**while**、**do**、**while** の 3 つがあります。 ループでは、ループに設定された条件が **false** になるまで、そのステートメントを繰り返します。 loop ステートメント内では、**break** および **continue** ステートメントを使用することができます。

## <a name="for-loops"></a>for ループ

**for** ループの構文は次のとおりです。

**(** *初期化* **;** *テスト* **;** *増分* **) {** *明細書* **}** 対象

**for** ループは、条件式 *テスト* が **true** である限り、 **ステートメント** を繰り返し実行します。 *ステートメント* はステートメントのブロックにすることができます。 *テスト* の結果に応じて、 **for** ループの本文 (*ステートメント*) は、 0 回以上実行されることがあります。 **for** ループは、制御変数に初期値を割り当て、また変数の増減ステートメントがあるために、他のループとは異なります。 これらの追加は **for** ループを作成します。これは、リスト、コンテナー、配列をトラバースする場合に特に便利です。 また、明細書を各要素に適用して、要素全体を増分し、最後の要素をテストする条件を設定することができます。

### <a name="example-of-a-for-loop"></a>For loop の例

次のコード例では、整数の配列内の項目が出力されます。

```X++
int integers[10];
for (int i = 0; i < 10; i++)
{
    info(int2str(integers[i]));
}
// The output is a series of 0's.
```

## <a name="while-loops"></a>while loops

**while** ループの構文は次のとおりです。

**(** *式* **)** のとき、*明細書*

**while** ループは、条件 *式* が **true** である限り、 *ステートメント* を繰り返し実行します。 *ステートメント* はステートメントのブロックで置き換えることができます。 *ステートメント* は、条件が満たされた回数 (ゼロから多数) 実行されます。 

### <a name="example-of-a-while-loop"></a>While loop の例

次のコード例は、コンテナーを走査してコンテナーの内容を出力する **while** ループを示します。

```X++
container cont = ["one", "two", "three"];
int no = 0;
while (no <= conlen(cont))
{
    info(conPeek(cont, no));
    no++;
}
// The output is "one", "two", "three".
```

## <a name="dowhile-loops"></a>do...while ループ

**do...while*** ループの構文は次のとおりです。

**do {** *ステートメント* **} while (** *式* **) ;**

**do**...**while** ループは、 **while** ループと似ていますが、条件は実行する必要がある *ステートメント* の後に表示されます。 *ステートメント* はステートメントのブロックにすることができます。 *ステートメント* は、 *ステートメント* の実行後にテストされるため、少なくとも 1 回は常に実行されます。 **do**...**while** ループは、レポートのパラメーターの取得など、必ず 1 回以上実行する必要があるタスクに適しています。 

### <a name="example-of-a-dowhile-loop"></a>Do の例...while loop

次のコード例では、 `realNumber` より大きい10の最小累乗を検索します。

```X++
int FindPower(real realNumber)
{
    int exponent = -1;
    real curVal;

    do
    {
        exponent++;
        curVal = power(10, exponent);
    }
    while (realNumber > curVal);

    return exponent;
}
```

## <a name="continue-statement"></a>ステートメントの続行

**continue** ステートメントは、**for**、**while**、または **do**...**while** ループの次の反復処理に直接移動する実行を発生させます。 **実行**または**途中**で、すぐにテストを実行します。 **対象**ステートメントで、増分手順を実行します。 

### <a name="example-of-a-continue-statement"></a>続行明細書の例

次のコード例では、 `Iarray[i] <= 0` の場合、ループ内の残りのステートメントは実行されず、 **if** ステートメントが再度試行される前に `i` が増分されます。

```X++
int Iarray[100];
for (int i = 0; i < 100; i++)
{
    if (Iarray[i] <= 0)
    {
        Info("Will continue.");
        continue;
    }

    info("Did not continue.");
}
// The output is "Will continue." for all 100 interations.
```

## <a name="break-statement"></a>break ステートメント

ループ内の **break** ステートメントは、そのループを終了するために使用されます。 実行後、ループの後の最初のステートメントに移動します。

### <a name="example-of-a-break-statement"></a>break ステートメントの例

**while** ループにおけるbreak ステートメントの例 ループ内で使用すると、ループは終了し、ループに続くステートメントから実行が継続します。 これは、 **do... while** と **for** ループでも機能します。 

```X++
var mainMenu = SysDictMenu::newMainMenu();
var enum = mainMenu.getEnumerator();
var found = false;
while (enum.moveNext())
{
    var menuItem = enum.current();
    if (menuItem.label() == "StringOfInterest")
    {
        found = true;
        break;
    }
}
if (found) 
{
    // do something
}
```