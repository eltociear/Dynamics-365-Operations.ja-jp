---
title: 製品分析コード
description: 4 つの製品分析コードがあります - 色、構成、サイズ、およびスタイルです。 分析コード グループで製品分析コードを組み合わせて、製品マスターに分析コード グループを割り当てます。 製品分析コードの組み合わせは、製品バリアントの定義方法を決定します。
author: cvocph
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f226329b774344a3de5c8f115ffb358611bf7d60
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570774"
---
# <a name="product-dimensions"></a>製品分析コード

[!include [banner](../includes/banner.md)]

4 つの製品分析コードがあります - 色、構成、サイズ、およびスタイルです。 分析コード グループで製品分析コードを組み合わせて、製品マスターに分析コード グループを割り当てます。 製品分析コードの組み合わせは、製品バリアントの定義方法を決定します。

製品分析コードは、製品バリアントを識別するために役立つ特性です。 製品バリアントを定義するために製品分析コードの組み合わせを使用できます。 製品バリアントを作成するには、製品マスターに対して少なくとも 1 つ製品分析コードを定義する必要があります。

## <a name="product-variants"></a>製品バリアント

製品バリアントは品目とも呼ばれます。 品目は、有形製品のことで、サービスとは異なるものです。 サービス タイプの製品マスターを定義することもできます。 [Service] タイプを使用して、サービスを含む製品バリアントを指定できます。 たとえば、上級顧問や若手のコンサルタントによって実行される、コンサルタント作業および作業の製品バリアントに、製品マスターを指定できます。

## <a name="product-dimensions"></a>製品分析コード
次の 4 つの製品分析コードがあります: 色、構成、サイズ、およびスタイルです。 製品バリアントは、製品分析コードの値に基づいて生成することができます。

サイズ、色およびスタイルなどの製品分析コード値は、**サイズ**、**色** および**スタイル**ページで作成できます。これらのページは、次の場所からアクセスできます: **製品情報管理** &gt; **設定** &gt; **分析コードおよびバリアント グループ** &gt; **サイズ / 色 / スタイル**。 [コンフィギュレーション分析コード] の製品分析コードの値は、通常、[製品コンフィギュレーター] または [分析コード ベースのコンフィギュレーター] を使用して作成されます。 製品分析コードは**製品分析コード** ページで作成および管理することもできます。以下の場所からアクセス可能です。
-   **製品情報管理** &gt; **製品** &gt; **製品マスター**の順にクリックします。 **アクション ペイン**で、**製品分析コード**をクリックします。
-   **製品情報管理** &gt; **製品** &gt; **すべての製品および製品マスター**の順にクリックします。 製品マスターを選択します。 **アクション ペイン**で、**製品分析コード**をクリックします。
-   **製品情報管理** &gt; **リリースされた製品**の順にクリックします。 製品マスターを選択します。 **アクション ペイン**で、**製品**をクリックします。 **製品マスター** グループで、**製品分析コード**をクリックします。

1 つの品目に対して作成できるバリアントの数は、可能な製品分析コードの組み合わせの数により制限されます。

| **ヒント**                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| たとえば、ある注文明細行上で製品を使用する場合、製品分析コードを選択して、使用する製品バリアントを特定します。 |

## <a name="example"></a>例
ある会社がデニム ジーンズを販売しています。 品目 "ジーンズ" には、色分析コードとサイズ分析コードが使用されます。 販売されるジーンズには、3 種類の色と 6 種類のサイズがあります。 色: 青、黒、茶。サイズ: XS、S、M、L、XL、XXL。すべてのサイズで 3 色すべてが用意されるわけではありません。 すべての組み合わせが使用可能な場合、18 タイプのジーンズを作成します。 この例では、次の 9 種類の製品バリアントの組み合わせのみ作成されます。

| 色 | サイズ |
|-------|------|
| 青  | XS   |
| 青  | S    |
| 青  | M    |
| 黒 | M    |
| 黒 | L    |
| 黒 | XL   |
| 茶 | L    |
| 茶 | XL   |
| 茶 | XXL  |





