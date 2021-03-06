---
title: 元伝票の監査ポリシーの定義
description: このトピックでは、監査ポリシー ルールを設定および実行する方法について説明します。
author: ryansandness
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a6b0fa28d778a4d9fa1f718b1d50bf1dce00be00
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186121"
---
# <a name="define-audit-policies-for-source-documents"></a>元伝票の監査ポリシーの定義

[!include [task guide banner](../../includes/task-guide-banner.md)]

このトピックでは、監査ポリシー ルールを設定および実行する方法について説明します。 この例では、ホテル経費タイプの経費精算書を使用しています。 この手順では、USMF というデモ会社を使用します。 監査担当者ロールには、これらのタスクを実行する適切なアクセス許可があります。

1. ナビゲーション ウィンドウで、**モジュール > 監査ワークベンチ > 設定 > ポリシー ルール タイプ**の順に移動します。
2. **新規** を選択します。
3. **ルール名**フィールドに値を入力します。
4. **説明**フィールドで、値を入力します。
5. **クエリ名**フィールドで**経費精算書の明細行**を選択する
6. **クエリ タイプ** フィールドで、**集計**を選択する
7. **法人**フィールドで**法人**を選択する
8. **文書日付の参照**フィールドで、**変更日時**を選択する
9. **保存** を選択します。
10. ナビゲーション ウィンドウで、**モジュール > 監査ワークベンチ > 設定 > 監査ポリシー**の順に移動します。
11. **新規** を選択します。
12. **名前**フィールドに値を入力します。
13. **ポリシーの組織**セクションを展開します。
14. ツリーで、**Contoso Entertainment System USA** を選択してから、**追加**を選択します。
15. ツリーで、**Contoso Consulting USA** を選択してから、**追加**を選択します。
16. ツリーで、**Contoso Retail USA** を選択してから、**追加**を選択します。
17. **ポリシーの組織**セクションを折りたたみます。
18. **ポリシー ルール** セクションを展開します。
19. 一覧で、以前に作成したポリシー ルールを見つけて選択します。
20. **ポリシー ルールの作成**を選択します。
21. **有効日**フィールドに日時を入力します。
22. **フィルター**を選択します。
23. 一覧で、**経費カテゴリ**の行を選択し、詳細を**ホテル**に設定します。
24. **基準**フィールドで、値を入力または選択します。
25. **集計**タブを選択します。
26. **追加**を選択します。
27. 一覧で、**トランザクション金額**の値を選択します。
28. **フィールド** フィールドで、値を入力または選択します。
29. **集計関数**フィールドで、**合計**を選択します。
30. **グループ化**タブを選択します。
31. **追加**を選択します。
32. 一覧で、**従業員**の値を選択します。
33. **追加**を選択します。
34. 一覧で、**経費カテゴリ**の値を選択します。
35. **フィールド** フィールドで、値を入力または選択します。
36. **HAVING** タブを選択します。
37. **追加**を選択します。
38. **トランザクション金額**を選択します。
39. **フィールド** フィールドで、値を入力または選択します。
40. **集計関数**フィールドで、**合計**を選択します。
41. **基準**フィールドで、`>2000` と入力します。
42. **OK** を選択します。
43. **テスト**を選択します。
44. **ドキュメントの選択の開始日**フィールドで、日時を入力します。
45. **ドキュメントの選択の終了日**フィールドで、日時を入力します。
46. **テストの実行**を選択します。
47. アクション ウィンドウで、**監査ポリシー**を選択します。
48. **追加オプション**を選択します。
49. **開始日**フィールドで、日時を入力します。
50. **終了日**フィールドで、日時を入力します。
51. **バッチ**を選択します。
52. **バックグラウンドで実行**セクションを展開します。
53. **バッチ処理**フィールドで**はい**を選択します。
54. **OK** を選択します。
55. ナビゲーション ウィンドウで、**モジュール > 監査ワークベンチ > 設定 > 監査ケース**の順に移動します。
56. 一覧で、目的のレコードを見つけ、選択します。
57. **関連**セクションを展開します。
58. 一覧で、目的のレコードを見つけ、選択します。

