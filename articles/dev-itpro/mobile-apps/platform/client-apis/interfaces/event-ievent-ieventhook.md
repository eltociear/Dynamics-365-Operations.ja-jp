---
title: "EventHook タイプ<T>"
description: "EventHook タイプ"
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
ms.openlocfilehash: a08a44a7c107d4c4207711a28ee855b91c5616df
ms.contentlocale: ja-jp
ms.lasthandoff: 08/09/2018

---

# <a name="eventhook-typelttgt"></a>EventHook タイプ&lt;T&gt;

[!include [banner](../../../../includes/banner.md)]

### <a name="hierarchy"></a>階層

EventHook <br>

## <a name="index"></a>指数

### <a name="methods"></a>メソッド

* [サブスクライブ](event-ievent-ieventhook.md#subscribe)
* [unsubscribe](event-ievent-ieventhook.md#unsubscribe)
* [unsubscribeAll](event-ievent-ieventhook.md#unsubscribeall)

## <a name="methods"></a>メソッド

### <a name="subscribe"></a>subscribe


subscribe(listener: [IEventListener](../modules/event-ievent.md#ieventlistener) &lt;T&gt;): void

このイベントにリスナーをサブスクライブします。


#### <a name="parameters"></a>パラメーター

| 氏名 | 種類 | 説明 |
| ---- | ---- | ----------- |
| listener|[IEventListener](../modules/event-ievent.md#ieventlistener) &lt;T&gt;||

#### <a name="returns-void"></a>void を返します

### <a name="unsubscribe"></a>unsubscribe


unsubscribe(listener: [IEventListener](../modules/event-ievent.md#ieventlistener) &lt;T&gt;): void

このイベントからリスナーを解除します。


#### <a name="parameters"></a>パラメーター

| 氏名 | 種類 | 説明 |
| ---- | ---- | ----------- |
| listener|[IEventListener](../modules/event-ievent.md#ieventlistener) &lt;T&gt;||

#### <a name="returns-void"></a>void を返します

### <a name="unsubscribeall"></a>unsubscribeAll


unsubscribeAll(): void

このイベントからすべてのリスナーを削除します。

#### <a name="returns-void"></a>void を返します

