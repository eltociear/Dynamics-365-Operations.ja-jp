---
title: 入庫および出庫資産
description: このトピックでは、資産管理で入庫および出庫資産を登録する方法について説明します。
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 53100a897dc71758b8920672fea1e684817cb4b7
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812286"
---
# <a name="inbound-and-outbound-assets"></a>入庫および出庫資産

[!include [banner](../../includes/banner.md)]

 

会社が他の場所または顧客から受け取った資産の修復作業またはメンテナンス作業をする場合、資産管理は、会社に向かう途中の入庫資産と返される出庫資産の両方を追跡できます。

> [!NOTE]
> 入庫および出庫のライフサイクル状態を使用して、入庫および出庫される資産を管理する場合は、これらのアクションをサポートするライフスタイル モデルを設定する必要があります。 詳細については、[メンテナンス要求](../setup-for-maintenance-requests/requests.md) を参照してください。

資産管理の設定によって、入庫資産と出庫資産を操作できるかどうかが決まります。

## <a name="register-assets-as-inbound"></a>資産を入庫として登録する

1. **資産管理**\>**共通**\>**メンテナンス要求**\>**有効なメンテナンス要求**を選択します。
2. メンテナンス要求を選択します。
3. **メンテナンス要求の状態の更新**を選択します。
4. **入庫** (または入庫資産用に作成した別のライフサイクル状態) を選択し、**OK** を選択します。

![資産を入庫として登録する](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>入庫資産を入庫済として登録する

1. **資産管理**\>**共通**\>**入庫/出庫資産**\>**入庫資産**を選択します。
2. 資産またはメンテナンス要求を選択します。
3. **資産の受入**を選択します。
4. **受入済**フィールドで、日時を入力します。 その後、**OK** を選択します。 レコードは、**入庫資産**リスト ページから削除されます。

![入庫資産を入庫済として登録する](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>資産を出庫として登録する

メンテナンス作業または修理作業が完了したら、資産を返却済として登録できます。

1. **資産管理**\>**共通**\>**メンテナンス要求**\>**有効なメンテナンス要求**を選択します。
2. メンテナンス要求を選択します。
3. **メンテナンス要求の状態の更新**を選択します。
4. **出庫** (または出庫資産用に作成した別のライフサイクル状態) を選択し、**OK** を選択します。

## <a name="register-outbound-assets-as-delivered"></a>出庫資産を配送済として登録する

1. **資産管理**\>**共通**\>**入庫/出庫資産**\>**出庫資産**を選択します。
2. 資産またはメンテナンス要求を選択します。
3. **資産を配送**を選択します。
4. **配送済**フィールドで、日時を入力します。 その後、**OK** を選択します。 レコードは、**出庫資産**リスト ページから削除されます。
