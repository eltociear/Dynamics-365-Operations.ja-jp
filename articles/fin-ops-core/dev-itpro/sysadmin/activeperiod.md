---
title: 有効なバッチ期間
description: このトピックでは、有効なバッチ期間のセットアップおよび作業に関する情報を説明します。
author: hasaid
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 62333
ms.assetid: 6135bcf7-bf8f-42ae-b2c6-458f6538e6a4
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Platform update 21
ms.openlocfilehash: 7985ba87fbdb82e1bf8ab8485f6f9d79aacfb8df
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191802"
---
# <a name="active-batch-periods"></a>有効なバッチ期間

[!include [banner](../includes/banner.md)]

プラットフォーム更新 21 のリリースでは、バッチ ジョブがいつ実行されるかの制御の追加レベルが使用できるようになりました。 以前は、一定の時間数または特定の日付までの 1 時間ごとにバッチ ジョブが実行されるようにスケジュールすることのみ可能でした。 管理者は、次のシナリオなど、追加のアクティブ期間の情報を指定できるようになりました。
- バッチ グループ内のジョブが実行を開始できる期間を指定します。 
- 営業時間外にのみバッチ ジョブを実行する場合に選択します。 
- アクティブ期間内で任意の回数の繰り返しを設定します。 たとえば、管理者は、午後 6 時から午前 8 時の間のみ、毎時間バッチ ジョブを実行することを選択できます。

> [!NOTE] 
> この機能は、Platform update 21 以降で利用できます。

## <a name="set-up-active-periods-for-batch-jobs"></a>バッチ ジョブの有効期間の設定 

1.  **システム管理** > **設定** > **バッチ ジョブの有効期間** に移動します。
2.  バッチ ジョブの名前を入力し、バッチ ジョブが有効な開始日と終了日を指定します。 
4.  **保存** をクリックします。

![有効期間フォーム](./media/active-periods.png)

## <a name="assign-active-periods-to-batch-jobs"></a>バッチ ジョブの有効期間の割り当て

1.  **システム管理** > **照会** > **バッチ ジョブ** の順に移動します。
2.  期間を割り当てるバッチ ジョブを選択し、**編集** をクリックします。
3.  **有効期間** フィールドで、割り当てる有効期間を選択し、**保存** をクリックします。

![有効期間の割り当て](./media/assign-active-period.png)
 
