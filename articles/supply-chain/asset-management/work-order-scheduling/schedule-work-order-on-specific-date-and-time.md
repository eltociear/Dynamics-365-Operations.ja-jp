---
title: 特定の日時のワーク オーダーのスケジュール設定
description: このトピックでは、資産管理で特定の日時にワーク オーダーのスケジュール設定をする方法について説明します。
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 634bbb4326d560848d36f579a1179187d8369087
ms.sourcegitcommit: fb66731f05207094149a6bc7b8549a4dabbb071a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "2652037"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a>特定の日時のワーク オーダーのスケジュール設定

[!include [banner](../../includes/banner.md)]

 

ワーク オーダーを特定の日*および*時間にスケジュール設定する必要がある場合は、資産管理の標準スケジューリング プロセスを上書きして、特定のスケジュールを作成できます。

1. **資産管理** > **共通** > **作業指示書** > **すべての作業指示書**または**有効な作業指示書**の順にクリックします。

2. ワーク オーダーの一覧で、**ワーク オーダー**列のワーク オーダー ID をクリックします。

3. **編集** をクリックします。

4. **ワーク オーダー ヘッダー** クイック タブで、**予定開始**および**予定終了**フィールドに、開始日時と終了日時を挿入します。

    ![図 1](media/05-work-order-scheduling.png)

5. **全般**タブで、**スケジュール**をクリックして標準スケジュール プロセスを使用するか、特定の作業者にワーク オーダーを割り当てる場合は、**派遣**をクリックします。

6. 既定の確保済能力を上書きして、ワーク オーダーが予定期間内にスケジュールされるようにするには、**ワーク オーダーのスケジュール設定**ダイアログ > **無限能力**セクションで下の図が示すように選択を行います。 これは、予定された開始時刻にワーク オーダーを開始する必要があるため、スケジューリング プロセスは既存の確保済能力を無視することを意味します。

    ![図 2](media/06-work-order-scheduling.png)

7. **OK** をクリックしてスケジューリングを開始します。

8. スケジューリング プロセスの結果、ダブル ブッキングが発生した場合は、画面にメッセージが表示され、関連するワーク オーダーを調整することができます。

>[!NOTE]
>ワーク オーダーのメンテナンス作業者スケジューリングするには、そのメンテナンス作業者が予定されている開始日時に対応可能である必要があります。 作業者の使用可能性は、[作業者カレンダー](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md)で設定されます。 

