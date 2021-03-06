---
title: ギフト カードとクレジット メモ操作のシームレスなオフライン切り替え
description: このトピックでは、特定の支払タイプに対してシームレスなオフライン切り替えを提供する改善の概要について説明します。
author: rubendel
manager: AnnBe
ms.date: 02/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 20120-02-28
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 3c2a644fd7096668fcefc73c67068fccde6894b0
ms.sourcegitcommit: 472f8bfc02acf80b07caf7c53bbb397411e946cc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "3040236"
---
# <a name="seamless-offline-switch-for-gift-card-and-credit-memo-operations"></a>ギフト カードとクレジット メモ操作のシームレスなオフライン切り替え

[!include [banner](../includes/banner.md)]

販売時点管理 (POS) デバイスがチャネル データベースへの接続を失った場合、処理中だったほとんどの POS 操作およびトランザクションは、レジ担当者が接続が切断されたことを示す警告メッセージを受信した後、処理を進めることができます。 ただし、場合によっては、トランザクションが Retail Real-time Service に依存する要素を持つため、これらの要素は POS がオフラインのときにはサポートされません。 このトピックでは、これらのシナリオで接続の切断による影響を軽減するために役立ついくつかの機能について説明します。

## <a name="completing-gift-card-transactions-in-offline-mode"></a>オフライン モードにおけるギフト カード トランザクションを完了する

ギフト カードの残高は Microsoft Dynamics 365 Commerce 本社で集中管理する必要があるため、内部ギフト カードは Real-time Service に依存します。 不正またはその他の同期の問題を防ぐために、ギフト カードはトランザクションに追加されるとすぐにロックされます。 ロック機能を使用すると、ギフト カードを複数のターミナルで同時に使用することはできなくなります。 トランザクションが完了すると、ギフト カードは更新されロック解除されます。

ただし、ギフト カードがトランザクションに追加された後に POS が接続を失った場合、ギフト カードは使用できなくなる場合があります。 この状況を回避するため、Dynamics 365 Commerce には POS がオフラインの間にギフト カード明細行を含むトランザクションを完了できるようにするパラメーターがあります。 このパラメーターがオンになっている場合は、強制的にオフラインにされたギフト カード トランザクションは、オフライン トランザクションと共に保存され、オフライン トランザクションが同期されるとコマース本社に同期されます。 また同期により、ギフト カードのロックは解除され、別のターミナルで使用できるようになります。

オフライン モードに切り替えた後にギフト カード トランザクションを完了する機能を有効にするには、**コマース パラメーター**の**転記**タブに移動します。 このタブで、**ギフトカード** クイック タブを見つけ、**オフライン モードにおけるギフト カード トランザクションの実行を許可する**を**はい**に設定します。

![オフラインのギフト カード設定](../media/gift.png)

通常、コマース パラメーターはキャッシュされます。 したがって、このパラメーターの設定が更新され、チャネルに変更を同期するために配布スケジュールが開始された後、変更が有効になるまでに最大 24 時間かかることがあります。 変更を直ちに有効にするには、Microsoft インターネット インフォメーション サービス (IIS) をリセットします。

## <a name="completing-credit-memo-transactions-in-offline-mode"></a>オフライン モードにおけるクレジット メモ トランザクションを完了する

内部ギフト カードと同様に、クレジット メモはコマース本社で集中管理されます。 コマースには、POS がオフラインの間にクレジット メモ トランザクションを完了するためのパラメーターがあります。 このパラメーターは、前のセクションで説明したギフト カード パラメーターのように機能します。 パラメーターがオンになっている場合は、強制的にオフラインにされたクレジット メモ トランザクションが、POS がオフラインの間に実行された他のトランザクションと共に、チャンネル データベースに同期されます。

オフライン モードに切り替えた後にクレジット メモ トランザクションを完了する機能を有効にするには、**コマース パラメーター** ページの**転記**タブに移動します。 このタブで、**クレジット メモ** クイック タブを見つけ、**オフライン モードにおけるクレジット メモ トランザクションの実行を許可する**を**はい**に設定します。

![オフラインのクレジット メモの設定](../media/creditmemo.png)

通常、コマース パラメーターはキャッシュされます。 したがって、このパラメーターの設定が更新され、チャネルに変更を同期するために配布スケジュールが開始された後、変更が有効になるまでに最大 24 時間かかることがあります。 変更を直ちに有効にするには、IIS をリセットしてください。

## <a name="related-topics"></a>関連トピック

- [オフライン販売時点管理 (POS) の機能](https://docs.microsoft.com/dynamics365/retail/pos-offline-functionality)
- [オンラインおよびオフラインでの販売時点管理 (POS) の操作](https://docs.microsoft.com/dynamics365/retail/pos-operations)
