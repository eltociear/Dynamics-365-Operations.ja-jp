---
title: 自動クリーンアップ タスクを使用したパフォーマンスの最適化
description: この記事では、バッチジョブ履歴をクリーンアップすることにより、Microsoft Dynamics 365 Human Resources での一部のパフォーマンスに関する問題を解決する方法について説明します。
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: a983fde8ba393ab25f2b330014e04a1379f0e4d0
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009635"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>自動クリーンアップ タスクを使用したパフォーマンスの最適化

**問題点**

Microsoft Dynamics 365 Human Resources では、バッチ ジョブ履歴が大きくなりすぎると、パフォーマンスの問題が発生する可能性があります。

**原因**

頻繁に実行されるバッチ ジョブにより、バッチ ジョブ履歴の持続不可能な増加につながる可能性があります。 これにより、パフォーマンスの問題が発生する可能性があります。 

**解像度**

バッチ ジョブ履歴をクリーンアップする自動タスクをスケジュールします。 タスクを毎週実行するよう設定することをお勧めしますが、環境によっては、クリーンアップの実行頻度を増減する必要がある場合もあります。 次の手順には推奨設定が含まれていますが、必要に応じてこれらを変更することもできます。

1. 人事管理では、**システム管理**を選択します。

2. **検索**バーで、**バッチ ジョブ履歴のクリーンアップ**を入力します。

   ![バッチ ジョブ履歴のクリーンアップを検索する](media/talent-batch-history-cleanup-search-bar.png)

3. **履歴の範囲 (日数)** で、**30** と入力します。

   ![履歴の範囲を 30 に設定](media/talent-batch-history-cleanup-history-limit.png)

4. **バックグラウンドで実行**を選択してから、**再実行**を選択します。

   ![再実行の設定](media/talent-batch-history-cleanup-recurrence.png)

5. **再実行の定義**で、**開始日**および**開始時刻**を時間外または週末に実行するよう設定してから、**終了日なし**を選択します。 

   ![再実行の開始日時の定義](media/talent-batch-history-cleanup-define-recurrence.png)

6. **再実行のパターン**で、**日数**を選択し、**指定した間隔で繰り返す**を **7** に設定します。

   ![クリーンアップを週単位で繰り返すよう設定する](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. **OK** を選択します。

8. 必要に応じて、**バックグラウンドで実行**でその他のパラメータを変更してから、**OK** を選択します。

