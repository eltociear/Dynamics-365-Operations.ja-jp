---
title: 演算子の優先順位
description: このトピックでは、演算子の優先順位について説明します。
author: pvillads
manager: AnnBe
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: 6174
ms.assetid: dd4a4971-c35a-466d-9c24-244cd75f9020
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97d957d20d53e00ddfddaf24fe5e04f28034756e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191595"
---
# <a name="operator-precedence"></a>演算子の優先順位

[!include [banner](../includes/banner.md)]

このトピックでは、演算子の優先順位について説明します。

複合式を評価する順番は重要です。 たとえば、(x + y / 100) は追加または区分を最初に実行するかどうかによって、結果が異なります。 かっこ () を使用すると、式の評価方法を明示的に X++ コンパイラに指示することができます。 例えば、(x + y)/ 100。 オペレーションを実行する順序をコンパイラーに明示的に伝えていない場合、順序はオペレーターに割り当てられた優先順位に基づいています。 たとえば、除算演算子には、加算演算子より高い優先順位があります。 x + y / 100 については、コンパイラは y/100 を最初に評価します。 つまり、x + y/100 は x + (y/100) と等しくなります。 コードを読みやすく管理しやすくするために、明示的に記述します。 最初に評価すべき演算子をかっこで示します。

## <a name="order-of-operator-precedence"></a>演算子の優先度順
次のテーブルの演算子は、優先順位の順に並べられています。 テーブルの演算子は高いほど、その優先順位が高くなります。 高い優先順位がある演算子は、低い優先順位がある演算子より前に評価されます。 X++ の演算子の優先順位は、C\# および Java などの他の言語と同じではないことに注意してください。


|              演算子 (優先順位)               |                 構文                 |
|----------------------------------------------------------|----------------------------------------|
|                     単項演算子                      |                 - ～ !                  |
| 乗算、シフト、AND、ビット演算排他的 OR |    \* / % DIV &lt;&lt; &gt;&gt; & ^    |
|              加法、ビット演算包括的 OR              |                  + -                   |
|                   リレーショナル、同等                   | &lt; &lt;= == != &gt; &gt;= 現状のとおり |
|               論理演算子 (AND、OR)                |            && &#124;&#124;             |
|                       条件付                        |                  ? :                   |

同じ行の演算子には、同等な優先順位があります。 式にあるこれらの演算子が 1 つ以上ある場合、代入演算子が使用されていない限り、式は左から右に評価されます (これらは右から左に評価されます)。 たとえば、&& (論理的 AND) および || (論理的 OR) は、優先順位が等しく、左から右に評価されます。 つまり、0&&0||1 == 1、および 1||0&&0 == 0 です

## <a name="additional-resources"></a>その他のリソース
[代入演算子](https://msdn.microsoft.com/library/d4e86b9c-be82-4f19-ad86-7722344a05f3(AX.60).aspx)

[算術演算子](https://msdn.microsoft.com/library/cffbc613-3875-4520-9dea-046dc99aab99(AX.60).aspx)

[リレーショナル演算子](https://msdn.microsoft.com/library/702af366-4d46-445e-bd4b-722c9845199f(AX.60).aspx)





