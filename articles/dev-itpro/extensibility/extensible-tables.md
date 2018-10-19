---
title: "拡張可能なテーブルの書き込み"
description: "このトピックでは、拡張可能テーブルを書き込む方法について説明します。"
author: MichaelFruergaardPontoppidan
manager: AnnBe
ms.date: 09/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 268724
ms.assetid: 
ms.search.region: Global
ms.author: mfp
ms.search.validFrom: 2018-09-09
ms.dyn365.ops.version: Platform update 20
ms.translationtype: HT
ms.sourcegitcommit: d8a0183faf93ea87c39e8d3ed3b4b454ebb16a3d
ms.openlocfilehash: 358ccdda7c16056afdcab11804bd3e7485d35b7f
ms.contentlocale: ja-jp
ms.lasthandoff: 09/10/2018

---

# <a name="write-extensible-tables"></a><span data-ttu-id="3e1f6-103">拡張可能なテーブルの書き込み</span><span class="sxs-lookup"><span data-stu-id="3e1f6-103">Write extensible tables</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="3e1f6-104">テーブルには、拡張担当者がフィールド、フィールド グループ、インデックス、関係、メソッドなどを追加できる豊富な拡張モデルがあります。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-104">Tables have a rich extension model that lets extenders add fields, field groups, indexes, relations, methods, and more.</span></span>

## <a name="unique-indexes"></a><span data-ttu-id="3e1f6-105">一意のインデックス</span><span class="sxs-lookup"><span data-stu-id="3e1f6-105">Unique indexes</span></span>
<span data-ttu-id="3e1f6-106">拡張により固有のインデックスを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-106">Unique indexes can't be changed by an extension.</span></span> <span data-ttu-id="3e1f6-107">固有のインデックスは、テーブルの制約を定義し、多くの場合、テーブルにおける行のキーも定義します。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-107">Unique indexes define a table constraint, and they often also define the key of the rows in the tables.</span></span> <span data-ttu-id="3e1f6-108">このような変更はテーブルの内容を変更するため、固有のインデックスを変更することは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-108">You aren't allowed to change unique indexes, because such changes change the nature of the table.</span></span> <span data-ttu-id="3e1f6-109">したがって、テーブルを定義するソリューションの将来のバージョン、またはテーブルを消費する他のソリューションと論理競合が発生する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-109">Therefore, there is a high risk that the changes will cause logical conflicts with future versions of the solution that defines the table, or with other solutions that consume the table.</span></span>

<span data-ttu-id="3e1f6-110">現在または将来、変更されると考えられる固有のインデックスを避けてください。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-110">Avoid unique indexes that are likely to be changed either now or in the future.</span></span> <span data-ttu-id="3e1f6-111">たとえば、色、サイズ、スタイル、およびコンフィギュレーションなど、製品分析コードに固有のインデックスを作成しないでください。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-111">For example, don't create a unique index on product dimensions such as color, size, style, and configuration.</span></span> <span data-ttu-id="3e1f6-112">代わりに、新しい製品分析コードが追加された場合にインデックスを変更しなくてもかまわないように、特徴的製品バリアントに固有のインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-112">Instead, create a unique index on a distinct product variant, so that the index doesn't have to be changed if new product dimensions are added.</span></span>

<span data-ttu-id="3e1f6-113">複数の列で拡張可能な一意制約を必要とする場合、列の値のハッシュを作成することを検討します。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-113">If you require an extensible uniqueness constraint on multiple columns, consider creating a hash of the column's values.</span></span> <span data-ttu-id="3e1f6-114">例については、NumberSequenceScope テーブルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-114">For an example, see the NumberSequenceScope table.</span></span>

## <a name="data-events"></a><span data-ttu-id="3e1f6-115">データ イベント</span><span class="sxs-lookup"><span data-stu-id="3e1f6-115">Data events</span></span>
<span data-ttu-id="3e1f6-116">テーブルには、自動的に発生する多くの事前定義データ イベントがあります。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-116">Tables have many predefined data events that are automatically raised.</span></span>

<span data-ttu-id="3e1f6-117">**doInsert()**、**doUpdate()**、**doDelete()** の呼び出しを回避してください。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-117">Avoid calling **doInsert()**, **doUpdate()**, and **doDelete()**.</span></span> <span data-ttu-id="3e1f6-118">これらのメソッドは、データ イベントが発生することを防ぎ、テーブルの拡張が困難になります。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-118">These methods prevent the data events from being raised and make your table harder to extend.</span></span> <span data-ttu-id="3e1f6-119">代わりに、**insert()**、**update()**、**delete()** を呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-119">Instead, call **insert()**, **update()**, and **delete()**.</span></span>

## <a name="field-groups"></a><span data-ttu-id="3e1f6-120">フィールド グループ</span><span class="sxs-lookup"><span data-stu-id="3e1f6-120">Field groups</span></span>
<span data-ttu-id="3e1f6-121">必ず、関連するフィールドをグループ化するため、フォームおよびレポートを構築するために、フィールド グループを使用します。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-121">Always use field groups to group related fields, and to build forms and reports.</span></span> <span data-ttu-id="3e1f6-122">一貫してこの方法を使用することで、フィールド グループを拡張することによって、追加フィールドをフォームやレポートに表示する拡張を有効にします。</span><span class="sxs-lookup"><span data-stu-id="3e1f6-122">By consistently using this approach, you enable the extension to surface additional fields in forms and on reports by extending the field group.</span></span>
