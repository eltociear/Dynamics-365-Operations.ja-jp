---
title: テンプレートを使用した仕訳入力の作成
description: 転記済みの仕訳帳伝票は伝票テンプレートとして保存され、新しい仕訳伝票に適用できます。
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransVoucherTemplate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: babbc5ee067743d368680970556f8e5d3d8585f0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178604"
---
# <a name="create-a-journal-entry-using-template"></a>テンプレートを使用した仕訳入力の作成

[!include [task guide banner](../../includes/task-guide-banner.md)]

転記済みの仕訳帳伝票は伝票テンプレートとして保存され、新しい仕訳伝票に適用できます。 この手順では、USMF というデモ会社を使用します。

1. **ナビゲーション ウィンドウ > モジュール > 総勘定元帳 > 仕訳入力 > 一般仕訳帳**の順に移動します。
2. **アクション ウィンドウ**で、**新規**をクリックします。 この手順は、仕訳伝票の作成および転記によって開始されますが、以前に転記された仕訳伝票をテンプレートとして保存できます。  
3. **名前**フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
4. 一覧で、目的のレコードを見つけ、選択します。
5. 一覧で、選択された行のリンクをクリックします。
6. **行** をクリックします。
7. **勘定タイプ** フィールドに値を入力します。
8. **説明**フィールドで、値を入力します。
9. **借方**フィールドに値を入力します。
10. **新規** をクリックします。
11. **勘定タイプ** フィールドに値を入力します。
12. **説明**フィールドで、値を入力します。
13. **借方**フィールドに値を入力します。
14. **新規** をクリックします。
14. **勘定**フィールドで、目的の値を指定します。
15. **説明**フィールドで、値を入力します。
16. **貸方**フィールドで、値を入力して伝票の収支を合わせます。
17. **アクション ウィンドウ**で、**転記**をクリックします。
18. **機能**をクリックします。
19. **伝票の保存**テンプレートをクリックします。
20. この手順は、**パーセント テンプレート** タイプとします。 [OK] をクリックします。
    - 割合: 伝票の金額が比率係数に変換されるため、伝票テンプレートが選択されている場合に、全ての金額が適用可能となります。
    - 金額: 実際の金額は保存され、適用されます。  
21. **一般仕訳帳**をクリックします。
22. **新規** をクリックします。
23. **名前**フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
24. 一覧で、選択された行のリンクをクリックします。
25. **行** をクリックします。
26. **機能**をクリックします。
27. **伝票テンプレートの選択**をクリックします。
28. 先ほど作成したテンプレートを見つけます。 **OK**をクリックします。 **前のステップ**をクリックし、他のテンプレートが見つかる場合、適切なテンプレートを選択する必要があります。  
29. **金額**フィールドに、伝票に適用する金額を入力します。 伝票テンプレートが割合タイプの場合にのみ、**金額**フィールドが表示されます。  
30. **OK**をクリックします。
