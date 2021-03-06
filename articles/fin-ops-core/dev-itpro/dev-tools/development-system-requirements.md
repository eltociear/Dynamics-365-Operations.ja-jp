---
title: 開発システム要件
description: このトピックでは、開発のシステム要件を一覧表示します。
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: 33221
ms.assetid: f39dbe39-7dc3-463c-923e-f22af231b979
ms.search.region: Global
ms.author: jorisde
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d025604f7266f224d2e159ffb53177ef443744cf
ms.sourcegitcommit: 759325234a763e14071348a6f5399999a92f8264
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2020
ms.locfileid: "2983685"
---
# <a name="development-system-requirements"></a>開発システム要件

[!include [banner](../includes/banner.md)]

このトピックでは、開発のシステム要件を一覧表示します。

開発環境は、ローカルまたは Microsoft Azure でホストできます。 ビルド プロセス、X++ コンパイル、および相互参照情報の生成は、通常、16 GB のメモリと 2 つの CPU コアを搭載したマシンでは十分に動作します。 ただし、コンパイラではリソースが使用されるため、特に同時実行されているその他のプロセスからのリソースの競合がある場合、より多くの RAM とコアが高速のコンパイルに変換される可能性があります。 このような場合、4 コアで 24 GB のメモリをお勧めします。 開発環境には AOS Web アプリケーション、Visual Studio、Management Reporter、および SQL Server など同時に実行される可能性がある多数のコンポーネントが含まれているため、少なくとも、 2 つの CPU コアを推奨します。



