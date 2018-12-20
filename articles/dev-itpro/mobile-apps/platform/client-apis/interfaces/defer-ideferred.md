---
title: "繰延タイプ<T>"
description: "繰延タイプ"
author: shadykdc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: 
ms.search.region: Global
ms.author: kashea
ms.search.validFrom: 
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ed6cabcc8c76fba3d4414cd4b564b720c54169e0
ms.openlocfilehash: 1c654bc705bfc5a45e38a255e2ffb567c9e4186b
ms.contentlocale: ja-jp
ms.lasthandoff: 08/09/2018

---

# <a name="deferred-typelttgt"></a>延期されたタイプ&lt;T&gt;

[!include [banner](../../../../includes/banner.md)]

### <a name="hierarchy"></a>階層

繰延 <br>

## <a name="index"></a>指数

### <a name="properties"></a>プロパティ

* [promise](defer-ideferred.md#promise)

### <a name="methods"></a>メソッド

* [否認](defer-ideferred.md#reject)
* [解決](defer-ideferred.md#resolve)

## <a name="properties"></a>プロパティ

### <a name="promise"></a>promise

promise: Promise &lt;T&gt;




## <a name="methods"></a>メソッド

### <a name="reject"></a>否認


reject(error?: any): void




#### <a name="parameters"></a>パラメーター

| 氏名 | 種類 | 説明 |
| ---- | ---- | ----------- |
| エラー?|any||

#### <a name="returns-void"></a>void を返します

### <a name="resolve"></a>解決


resolve(value?: T &#124; PromiseLike &lt;T&gt;): void




#### <a name="parameters"></a>パラメーター

| 氏名 | 種類 | 説明 |
| ---- | ---- | ----------- |
| value?|T &#124; PromiseLike &lt;T&gt;||

#### <a name="returns-void"></a>void を返します

