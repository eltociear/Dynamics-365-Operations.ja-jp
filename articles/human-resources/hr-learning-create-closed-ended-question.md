---
title: 選択式の質問の作成
description: 選択式の質問には、回答者が選択できるためのオプションが用意されます。
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 55a41ae639970eb3324a5760af7f6dd5fb8f2ad5
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009719"
---
# <a name="create-a-closed-ended-question"></a>選択式の質問の作成



選択式の質問には、回答者が選択できるためのオプションが用意されます。 最初に、回答と回答グループを作成する必要があり、その後回答グループを使用する質問を作成します。 この手順の作成に使用するデモ データの会社は USMF です。


## <a name="create-an-answer-group"></a>回答グループの作成
1. [アンケート] > [設計] > [回答グループ] の順に移動します。
2. [新規] をクリックします。
3. [回答グループ] フィールドに値を入力します。
4. [説明] フィールドに値を入力します。
    * 回答グループが質問に使用されるたびに、必要に応じて別の順序で回答をランダムに設定するランダム化機能を使用します。  
5. [回答] をクリックします。
6. [新規] をクリックします。
    * ランダム化機能が回答グループに対して選択されている場合を除いて、番号順序は回答が表示される順序を制御します。  
    * アンケートの採点に対して回答するために、ポイントは支給できます。  
7. [点数] フィールドに数値を入力します。
    * 正解な回答をマークし、選択した回答が正しいものであることを表示できます。 これは、アンケートの採点に使用できます。  
8. [回答] フィールドに値を入力します。
    * 回答グループに対して選択できる回答オプションを作成し続けます。  
9. [新規] をクリックします。
10. [点数] フィールドに数値を入力します。
11. [回答] フィールドに値を入力します。
12. [新規] をクリックします。
13. [点数] フィールドに数値を入力します。
14. [回答] フィールドに値を入力します。
15. [新規] をクリックします。
16. [点数] フィールドに数値を入力します。
17. [回答] フィールドに値を入力します。
18. [新規] をクリックします。
19. [点数] フィールドに数値を入力します。
20. [回答] フィールドに値を入力します。
21. ページを閉じます。
22. ページを閉じます。

## <a name="create-the-question"></a>質問の作成
1. [アンケート] > [設計] > [質問] の順に移動します。
2. [新規] をクリックします。
3. [タイプ] フィールドを使用して、関連の質問をグループ化します。
    * 選択式の質問の場合は、チェック ボックス、代替ボタン、またはコンボ ボックスの入力タイプを使用できます。  
4. [入力タイプ] フィールドで、オプションを選択します。
5. [回答グループ] フィールドで、値を入力または選択します。
6. [テキスト] フィールドに値を入力します。

