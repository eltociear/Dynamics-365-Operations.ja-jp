---
title: 業績の確認の作成
description: このトピックでは、パフォーマンス レビューの作成方法を説明し、レビューの各セクションの目的について説明します。
author: andreabichsel
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EssWorkspace, HcmDiscussionNewDialog, HcmDiscussion, HcmDiscussionChangeSettings, HcmDiscussionAddGoalDialog, HcmTopicCreate, HcmMeasurementDetailDialog, HcmPerfJournalAdd
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3583f974d1768e0efefb80f0ad8aa011669c1301
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178766"
---
# <a name="create-performance-reviews"></a>業績の確認の作成

[!include [task guide banner](../../includes/task-guide-banner.md)]

このトピックでは、パフォーマンス レビューの作成方法を説明し、レビューの各セクションの目的について説明します。 この手順は、デモ データ会社 USMF を使用して作成されました。

1. ホーム ページで、**従業員セルフ サービス** ワークスペースを選択します。
2. **新しいレビュー**を選択して、新しいレビューを作成します。
3. **レビュー タイプ** フィールドで、値を入力または選択します。
4. **業績期間**フィールドで値を入力または選択します。
5. **終了日**フィールドに日付を入力します。
6. **OK** を選択します。 テンプレートから確認を作成することもできます。 これは、各セクションが確認を開始するために必要な情報が含まれるための確認を作成する最善の方法です。  
7. 添付ファイル タブなど、タブを表示または非表示にできます。

    1. アクション ウィンドウで、**セクションの表示**を選択してドロップ ダイアログを開きます。
    1. **添付ファイルの表示**フィールドで**はい**または**いいえ**を選択して、添付ファイル タブを表示または非表示にします。
    1. **保存** を選択します。

8. **レビューに目標を追加**を選択して、目標を追加します。 完了したら、**OK** を選択します。
9. **コンピテンシーの追加**を選択して、ドロップ ダイアログを開きます。
10. **タイトル** フィールドに値を入力します。
11. **説明**フィールドに、`Increase customer skills by working with the support team` を入力します。
12. **OK** を選択します。
13. **すべて折りたたみ**を選択します。
14. **すべて展開**を選択します。
15. **コメントの追加**を選択します。
16. **投稿**を選択します。
17. **測定**タブを選択します。
18. **測定の追加**を選択して、ドロップ ダイアログを開きます。
19. **測定**フィールドで、値を入力または選択します。
26. **目標額**フィールドに数値を入力します。
20. **OK** を選択します。
21. **活動**タブを選択します。
22. **追加**を選択します。
23. **タイトル** フィールドに値を入力します。
24. **説明**フィールドで、値を入力します。
25. **開始日**フィールドに日付を入力します。
26. **完了日**フィールドに日付を入力します。
27. **開発計画**フィールドで、**はい**を選択します。
28. **キーワード** フィールドに値を入力します。
29. **保存** を選択します。
30. **評価**タブを選択します。  

    - **評価の詳細**クイック タブを使用すると、従業員は自分自身と管理者を評価して従業員を評価することができます。 重量を使用する場合は、スコアの重量の値が自動的に計算されます。  
    - このセクションを表示するには、従業員の評価を表示するためのパラメータ設定を有効にします。  

31. **サインオフ** タブを選択します。確認でワークフローが使用されている場合は、ワークフローが完了した後にのみサインオフが表示されます。 ワークフローを使用しない場合は、作業者およびマネージャーの両方がここに表示されます。 必要なチェックボックスは、確認タイプの設定に基づいて選択されます。  
32. **一般**タブを選択します。

    - 業績期間が既定の開始日と終了日を作成します。 これらの日付は編集できます。  
    - ステータスがレビューへのアクセスを制御します。 **開始されていません**のステータスの場合、全員がレビューを編集できます。 **進行中**のステータスの場合、従業員のみがレビューの表示および編集をすることができます。 [確認準備完了] の場合、マネージャーのみがレビューの表示および編集ができます。 [最終確認] ステータスの場合、従業員と管理者双方がレビューの表示および編集も可能です。編集するにはレビュー タイプで設定されている必要があります。 **完了**、**否認済**、および**キャンセル** ステータスの場合は、レビューは読み取り専用になります。  

33. **概要**フィールドに値を入力します。
34. **レビュー** タブを選択します。レビューは実行ステータスに応じて、従業員およびマネージャーは、各目標またはコンピテンシーのコメントを追加できます。  
35. **サインオフ** タブを選択します。作業者およびマネージャーはレビューでサインオフできます。 すべての必要なサインオフが完了すると、ステータスは**完了**に変更され、それ以降は内容を変更することはできません。  
