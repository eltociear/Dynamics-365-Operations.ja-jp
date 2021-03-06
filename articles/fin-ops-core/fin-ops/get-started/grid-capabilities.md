---
title: グリッド機能
description: このトピックでは、グリッド コントロールのいくつかの強力な機能について説明します。 これらの機能にアクセスするには、新しいグリッド機能が有効になっている必要があります。
author: jasongre
manager: AnnBe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 7136edba828bf97b6e0c8d2a698b884640d680e5
ms.sourcegitcommit: 880f617d1d6e95eccbed762c7ea04398553c2ec0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036268"
---
# <a name="grid-capabilities"></a>グリッド機能

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

新しいグリッド コントロールは、ユーザーの生産性を高め、データのより興味深いビューを構築し、データの有意義な洞察を得るために使用できる多くの便利で強力な機能を提供します。 この記事では、次の機能について説明します。 

-  合計の計算
-  データのグループ化
-  システムの前に入力する
-  数式の評価 

## <a name="calculating-totals"></a>合計の計算
Finance and Operations アプリでは、ユーザーはグリッドの数値列の下に合計を表示することができます。 これらの合計は、グリッドの下部にあるフッター セクションに表示されます。 

### <a name="showing-the-grid-footer"></a>グリッド フッターの表示
Finance and Operations アプリでは、すべての表形式のグリッドの下部にフッター領域があります。 フッターには、グリッドに表示されるデータに関連する貴重な情報が表示されます。 この情報の例を次に示します。

- テーブルで選択された行の数 (複数のレコードが選択されている場合)
- 構成済の数値列の下の総計
- データセットの行数 

このフッターは、既定では非表示になっていますが、簡単にオンにすることができます。 グリッドのフッターを表示するには、グリッドの列ヘッダーを右クリックし、**フッターを表示**オプションを選択します。 特定のグリッドに対してフッターをオンにすると、ユーザーがそのフッターを非表示にするまでその設定が保持されますが、これは、列ヘッダーを右クリックして**フッターを非表示**を選択することで実行できます。  **フッターの表示/非表示**アクションの配置は、今後の更新で再配置される予定です。 

### <a name="specifying-columns-with-totals"></a>合計を含む列の指定
現時点では、既定で合計を表示するように列を構成することはできません。 代わりに、この操作は、グリッドで列の幅を調整する場合と同じように、1 回の設定操作と見なされます。 列の合計を表示するように指定すると、その設定は、次にページにアクセスしたときに記録されます。  

合計を表示する列を構成するには、次の 2 つの方法があります。 

- 合計を表示する列を右クリックし、**この列の合計**を選択します。 このアクションにより、次の 3 つのイベントが発生します。

    1. フッターが表示されます。 
    2. この列の合計を表示するための設定が保存されます。 
    3. この列と、合計を表示するために以前に構成した他のすべての列の合計計算が開始されます。 合計を表示するために必要な時間は、合計しているデータセットのサイズによって異なります。

- フッターが表示されたら、合計を表示する列の下部のフッター領域にある**合計の表示**を選択します。 構成された列がない場合は、すべての数値列で**合計の表示**ボタンが使用可能になります。 

    合計に対して少なくとも 1 つの列が構成された後は、**合計の表示**ボタンは、ポイント時またはフォーカス時にのみ使用できます。 **合計を表示する**を選択するアクションによって、この列の合計を表示するための設定が保存されるので、その設定は今後ページにアクセスするときに適用されます。 フッターでは、この状態は列に表示されるダッシュによって示されます。 (または、データセットが十分に小さい場合は、合計がすぐに表示されます。)

特定の列の合計を表示する必要がなくなった場合は、列を右クリックして、**合計を非表示**を選択するか、その列のフッターで**合計を非表示**ボタンを選択します。 この設定は、今後のページへのアクセスのために保存されます。 

### <a name="calculating-totals"></a>合計の計算
フッターが表示され、列がすでに合計に対して構成されているページにアクセスすると、フッターに合計が表示される場合と表示されない場合があります。 動作は、ページ上のデータセットのサイズによって異なります。 データセットが十分小さい場合は、合計が自動的にデータセットの行数と共に表示されます。 合計に対して構成した列の下のフッターにダッシュがある場合、データセットが大きすぎてシステムが合計をすぐに表示できないため、合計を計算するには明示的なアクションが必要です。 このためには、フッターの**計算**ボタンをクリックするか、合計を表示する列を右クリックし、**この列の合計**を選択します。  

計算に時間がかかりすぎる場合は、**キャンセル** ボタンを選択して操作を取り消すことができます。 ただし、データセットが大きすぎて合計を計算できない場合があり (組織によって課される制限)、代わりにデータをさらにフィルタ処理するように通知されます。

データセットの行を更新、削除、または作成すると、合計が自動的に更新されます。  

## <a name="grouping-data"></a>データのグループ化
多くの場合、ビジネス ユーザーは、データのアド ホック分析を実行する必要があります。 これは、Microsoft Excel にデータをエクスポートしてピボット テーブルを使用することで実行できますが、表形式グリッドの**グループ化**機能を使用すると、ユーザーは Finance and Operations アプリ内でデータを興味深い方法で整理できます。 この機能によって**合計**機能が拡張されるのに対し、**グループ化**では、グループ レベルで小計を提供することにより、データについて有意義な洞察を得ることができます。

この機能を使用するには、グループ化する列を右クリックし、**この列別にグループ化**を選択します。 このアクションにより、選択した列でデータが並べ替えられ、グリッドの先頭に新しいグループ化列が追加されてから、各グループの先頭に「ヘッダー行」が挿入されます。 これらのヘッダー行では、各グループについて次の情報が提供されます。 
-  グループのデータ値 
-  列ラベル (この情報は、複数のグループ化レベルがサポートされている場合に特に役立ちます。)
-  このグループのデータ行の数
-  合計を表示するように構成された列の小計

[保存されているビュー](saved-views.md) を有効にすると、このグループ化をビューの一部としてパーソナル化によって保存し、次回ページにアクセスするときに素早くアクセスできます。  

別の列で**この列別にグループ化**を選択すると、元のグループ化が置き換えられます。これは、プラットフォーム更新プログラム 33 を使用したバージョン 10.0.9 では 1 つのレベルのグループ化のみがサポートされているためです。

グリッドのグループ化を元に戻すには、グループ化列を右クリックして、**グループ化解除**を選択します。  


## <a name="evaluating-math-expressions"></a>数式の評価
生産性を高めるため、ユーザーはグリッドの数値セルに公式を入力できます。 システム外部のアプリで計算を行う必要はありません。 例えば、**=15\*4** と入力して、**タブ** キーを押してフィールドの外に移動すると、システムによって式が評価され、フィールドの値として **60** が保存されます。

値が式としてシステムで認識されるようにするには、値を等号 (**=**) で開始します。 サポートされている演算子と構文の詳細については、[サポートされている数式記号](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols) を参照してください。  
