---
title: "Intelligent Data Management Framework の削除オブジェクトの作成"
description: "このトピックでは、Microsoft Dynamics AX のアプリケーション テーブル間で階層関係ツリーを定義する IDMF パージ オブジェクトを作成する方法について説明します。"
author: kfend
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: 
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: AX 2012
ms.custom: 17951
ms.assetid: 2ecae3f6-1163-4a0f-8db3-8b53908961ce
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 
ms.dyn365.ops.version: 2012
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: bbf251403e2928302688d4a3d525d22f0c958642
ms.contentlocale: ja-jp
ms.lasthandoff: 08/09/2018

---

# <a name="create-purge-objects-for-the-intelligent-data-management-framework"></a>Intelligent Data Management Framework の削除オブジェクトの作成

[!include [banner](../../includes/banner.md)]

<a name="considerations-for-purge-objects-driver-tables-relations-and-rules"></a>削除オブジェクト、ドライバー テーブル、関係、およびルールに関する注意事項
---------------------------------------------------------------------

**注記**: 削除オブジェクトを使用する前に、Microsoft Dynamics AX アプリケーションとデータベースのメンテナンスと管理に精通している必要があります。 IDMF では、Microsoft Dynamics AX アプリケーション テーブル間の階層関係ツリーを定義する削除のオブジェクトを作成できます。 特定の条件に基づき選択したレコードにルールを適用することができます。 選択基準に一致するレコードは、削除タスクが実行されたときに削除オブジェクト内の関係ツリー全体から削除されます。 このフレームワークを不適切に使用すると、予期しない結果、データベース破損、データベース全体およびアプリケーションの復旧が必要となるアプリケーション ダウンタイムが発生する可能性があります。 実稼働環境で作業する前に、十分に注意を払い、テスト環境でリサイクル戦略を入念にテストする必要があります。 削除オブジェクトで作業する場合は、次の点を考慮してください。

-   一時的または中間的なデータを格納するテーブルは通常、削除オブジェクトの主な候補です。 こうしたテーブルで削除オブジェクトを作成する前に、データの依存関係とアプリケーションの機能を検証する必要があります。
-   削除オブジェクトのドライバー テーブルとして選択したテーブルが、**SalesParmTable** または **SalesQuotationTable** などのヘッダー テーブルであることを確認します。 必ずしもいつも正確ではありませんが、そのようなテーブルの **TableGroup** の値は、**WorkSheetHeader**、**Miscellaneous**、または **Transaction** です。
-   **TableGroup** 値が **Main**、**Parameter**、**Group**、**WorkSheetLine** のテーブルをドライバー テーブルにすることはできません。
-   ドライバー テーブルは、階層リレーションシップ ツリーのルート親になります。 IDMF は **XRefTableRelation** テーブルを照会して、親子関係を判別します。
-   削除オブジェクトからレコードを削除すると、次の条件では、アプリケーションでデータの不整合が発生する場合があります。
    -   ドライバー テーブルには既知の親テーブルがあります。
    -   ドライバー テーブルには、削除テーブルにリレーションとして追加されていない既知の子テーブルがあります。
-   常に削除オブジェクトを最小化し、実装に必要なルールおよび関係のみを保持します。 次の条件の 削除オブジェクトからテーブルを削除することを検討してください。
    -   このテーブルにはデータが含まれておらず、将来もデータが含まれない可能性があります。
    -   このテーブルには、**CustTransOpen** や **SpecTrans** などの一時データのみが格納されます。
    -   テーブルには未処理のトランザクションが格納されます。
    -   テーブルはネストされたリレーションシップを作成します。 テーブルが、同じ特定関係条件のもとまたは主キーのセットで、関係ツリー上の異なるレベルで複数回表示される場合、関係ツリーの最も低い番号のレベルでのみ表示されるように検討します。
    -   2 つのテーブル間に複数のリレーションシップが存在することがあります。 その場合、リレーションシップと機能を慎重に評価します。 削除オブジェクトでは単一のリレーションシップのみを使用することをお勧めします。 ただし、必要に応じて、複数のリレーションシップを使用できます。 有効なリレーションシップが存在する場合は固有インデックスまたは主キーを使用して、有効なリレーションシップを選択してください。
    -   テーブルは、ドライバー テーブルとは無関係で、独自の削除オブジェクトを作成します。 たとえば、**ProdTable** をドライバー テーブルとして使用する場合、**ProdJournalTable** が検出され、それ自体は別の削除オブジェクトです。 もう 1 つの例は PurchReqTable です。 **PurchReqTable** をドライバー テーブルとして使用する場合、**PurchParmTable** 削除オブジェクトの一部として、**PurchParmLine** が検出されます。
-   削除オブジェクトに作成したリレーションシップ ツリーがシステムから目的のデータを実際に削除していることを確認します。 作成された削除オブジェクトは、関連するすべてのレコードを参照する必要があります。 不足している関係は、データの孤立を引き起こします。
-   実稼働環境テスト環境でのデータベースとアプリケーションには、削除の影響を十分にテストします。運用環境に似たテスト環境でデータベースとアプリケーションに対するパージの影響を完全にテストします。 すべての業務プロセスをテストし、実稼働環境に削除オブジェクトを実装する前にユーザーの承認を得ます。
-   IDMF に含まれている削除テンプレートから削除オブジェクトを作成するときは、テスト環境で、削除オブジェクトを検証して徹底的にテストします。 これらのテンプレートは標準の Microsoft Dynamics AX アプリケーションで作成され、実装と一致しない場合があります。 検出プロセスを使用して独自の削除オブジェクトまたはアーカイブ オブジェクトを作成し、適合しているテンプレートを使用できる場合は、プロセスそれらのオブジェクトをそのテンプレートと比較することをお勧めします。 探索プロセスで作成したオブジェクトとテンプレートの違いを慎重に分析し、その違いの原因を特定します。 要件に合わせるために、削除オブジェクトとアーカイブ オブジェクトの関係およびルールを手動で追加または削除します。
-   検出プロセスに関連するすべてのテーブルを取得できるように、TableGroup プロパティが Microsoft Dynamics AX ですべてのカスタム テーブルに対して設定されていることを確認します。
-   アプリケーション オブジェクト ツリー (AOT) でのテーブルの追加、削除、更新や、IDMF を使った Microsoft Dynamics AX メタデータでのデータ ディクショナリ同期など、変更を同期します。 メタデータを同期するため、インストール後の作業を実行します。 詳細については、[データ管理フレームワークのインストール ガイド](http://www.microsoft.com/en-us/download/details.aspx?id=16111) の「インストール後の作業」セクションを参照してください。

| **注意**                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| トランザクション タイプのテーブル グループを持つテーブルが、これらのテーブルからデータをパージできる場合にのみ、パージ オブジェクトの一部であることを確認します。 |

## <a name="create-a-new-purge-object"></a>新しい削除オブジェクトを作成します
削除オブジェクトを作成するには、これらの手順に従います。
1.  ツールバーで、**削除オブジェクトの作成**をクリックします。
2.  **削除オブジェクトの作成**ダイアログ ボックスで、**ドライバー テーブル** リストからテーブルを選択します。 このリストは例外リストのテーブルを除外します。 **PurchParmTable** に移動して選択します。 ドライバー テーブルは、特定の削除オブジェクトのリレーションシップ ツリーを定義する親テーブルです。 削除オブジェクトでは、ドライバー テーブルに子エンティティがある場合がありますが、リレーションシップ ツリーに親エンティティはありません。
3.  続行するには、テーブルの最もユニークなインデックスを選択します。 このインデックスは、削除オブジェクトに親子関係を作成するために使用されます。 **固有のキー** フィールドで、**ParmId** を選択します。 **ParmTableRefIdx** インデックスは、**ParmID** および **TableRefID** フィールドを使用して作成されます。 **ParmID** を選択して部分的なキーを選択していることに注意します。 固有インデックスを使用すると、探索プロセスは、Finance などの同じ機能エリアに関連するテーブルを識別できます。 固有のインデックスを選択しない場合、検出プロセスですべての機能領域から関連テーブルが検索されます。 探索プロセスにより、Microsoft Dynamics AX 実装の正しい機能関係を識別できるようにする必要があります。
4.  **検出**をクリックします。 IDMF は、Microsoft Dynamics AX データベースからインポートされたメタデータと例外パラメーター リストを使用して、関係ツリーを生成します。 リレーションシップ ツリーはドライバー テーブルで始まり、親子関係の階層を作成します。 削除オブジェクトが次の図のようになっていることを確認します。

![IDMF 削除オブジェクト](./media/idmfpurgeobject.png) 

この削除オブジェクトのリレーションシップ ツリーは 3 階層の深さです。 最上位レベルのレベル 0 には、ドライバー テーブル PurchParmTable が含まれています。 レベル 1 には、ドライバー テーブルの子エンティティが含まれています。 レベル 2 の最後のレベルには、レベル 1 のテーブルの子エンティティが含まれています。 この関係ツリーは、以下の情報に基づいて作成されます。
-   Microsoft Dynamics AX メタデータ。 検出プロセスは、メタデータを使用して、ドライバー テーブルに基づいて親子階層を形成する関連テーブルのリストを作成します。
-   例外パラメーター。 例外パラメーターの一覧に属しているテーブルは関係ツリーから除外されます。 **管理** メニューを使用して、例外パラメーターを設定します。

リレーションシップ ツリーを確認し、Microsoft Dynamics AX アプリケーション上でそのツリーの機能的効果を評価します。 評価の結果、一部の関係やルールを手動で追加または削除することができます。 たとえば、**プロパティ**ウィンドウで**復元**をクリックすると、IDMF で出荷する既定のテンプレートから削除オブジェクトが復元されます。 この場合の復元されたリレーションシップ ツリーは、ディスカバリ テーブルとして **PurchParmTable** を使用して作成した削除オブジェクトとは異なります。 これは、標準の Microsoft Dynamics AX アプリケーションの機能評価に基づいて IDMF の既定のテンプレートが変更されるためです。 検出テーブルにいずれかが存在する場合、検索で作成した削除オブジェクトは、IDMF に含まれている既定のテンプレートと一致しない場合があります。 ドライバー テーブルの選択には注意が必要です。 **ProdTable** テーブルなどのテーブルを選択すると、各レベルの多数のテーブルにまたがっている数多くのレベルの関係ツリーが表示されます。 そのような削除オブジェクトは、複雑な関係ツリーを作成し、エラーが発生する可能性を高くします。 IDMF に含まれている既定のテンプレートは、Microsoft Dynamics AX 実装のメタデータと一致しない場合があります。 生産データベースのメタデータに見つからない既定テンプレートのテーブルは、無効とマークされます。 無効なテーブルに破線の赤い点線の枠線が表示されます。 削除オブジェクトからすべての無効なテーブルを削除する必要があります。 有効なテーブルからリレーションおよびルールを作成するために使用するフィールドも検証されます。 無効なコンフィギュレーション キーが設定されたフィールドは無効と見なされます。 無効なフィールドを持つ有効なテーブルは、図 2 に示すように、黄色の点線の枠線で表示されます。 無効フィールドで定義された削除オブジェクトのルールや関係を、すべて削除する必要があります。 無効なテーブル、または無効なフィールドを含むテーブルを削除した後、オブジェクトの使用を続行することができます。 

![無効なテーブルを含む IDMF 削除オブジェクト](./media/idmfpurgeobjectwithinvalidtables.png)

## <a name="navigation-of-the-create-purge-object-workspace"></a>削除オブジェクトの作成ワークスペースのナビゲーション

次のテーブルで、このワークスペースのコントロールについて説明します。
### <a name="panes"></a>ウィンドウ

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>ウィンドウ</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>リレーションシップ ツリー ウィンドウ</strong></td>
<td>削除オブジェクトにすべてのテーブルのグラフィック ビューを提供します。 次のリストでは、リレーションシップ ツリー ウィンドウを移動するために使用できるコントロールとコマンドについて説明します。
<ul>
<li><strong><span class="ui">レベル</span></strong> スライダーでは、レベルを選択して、選択したレベルおよび上位レベルにあるテーブルのみを表示することができます。</li>
<li><strong><span class="ui">ズーム</span></strong> スライダーでは、図のサイズを変更することができます。</li>
<li>ドライバー テーブルを右クリックし、無効なすべてのテーブルを、関連するすべてのテーブルとともに入れ子になった階層で削除するには、<strong><span class="ui">無効なテーブルをすべて削除する</span></strong> をクリックします。</li>
<li>次のオプションを含むメニューを表示するテーブルを右クリックします。
<ul>
<li>選択したテーブル、およびその関連テーブルを階層ツリーから削除するには、<strong><span class="ui">削除</span></strong>をクリックします。 たとえば、<strong>SpecTrans</strong> テーブルはレベル 2 とレベル 3 で表示されます。 レベル 2 のテーブルを右クリックし、<strong><span class="ui">削除</span></strong>を選択すると、レベル 2 からテーブルが、入れ子になった子関係と共に削除されます。 テーブルの発生はレベル 3 のままです。</li>
<li><strong><span class="ui">すべての発生を選択</span></strong>をクリックすると、選択したテーブルとその関連テーブルのすべての出来事が緑色の点線の枠内に表示されます。 この場合、テーブル <strong>SpecTrans</strong> は入れ子になった子関係すべてと共にレベル 2 と 3 で選択されます。</li>
<li>選択したテーブル、およびその関連テーブルのすべての内容を削除するには、<strong><span class="ui">すべてを削除</span></strong>をクリックしてください。 この場合、テーブル <strong>SpecTrans</strong> は入れ子になった子関係すべてと共にレベル 2 と 3 から削除されます。 削除されたテーブルが赤い実線の入った灰色の図形に表示されます。</li>
</ul></li>
<li>選択したテーブルの親子関係階層を再生成するには、<strong><span class="ui">検出</span></strong>をクリックします。 このコマンドは、<strong><span class="ui">WorkSheetHeader</span></strong> の <strong><span class="ui">TableGroup</span></strong> 値を持つテーブルを選択した場合にのみ使用できます。</li>
</ul></td>
</tr>
<tr class="even">
<td><strong><span class="ui">プロパティ</span></strong></td>
<td>選択したテーブルのプロパティを表示し、選択したテーブルに使用できるコマンドを提供します。 削除オブジェクト内のテーブルに複数のリレーションが存在するときは、ツリー ビューの <span class="ui">Relations</span> ノードを使用して、このトピックで後で詳しく説明しているように、1 つまたは複数のリレーションを無効にすることができます。</td>
</tr>
<tr class="odd">
<td><strong><span class="ui">テーブルの削除</span></strong></td>
<td>関係ツリーから削除するテーブルを選択するために使用できるデータ グリッドを提供します。 このペインには、データ グリッドをフィルタリングするために使用できる<span class="ui">高度なフィルタ</span>コントロールもあります。</td>
</tr>
<tr class="even">
<td><strong><span class="ui">関連情報</span></strong></td>
<td>一部のテーブルの追加情報を提供します。 関連する情報が指定された場合は、テーブルのリサイクルの妥当性を理解するために慎重に読んでください。</td>
</tr>
</tbody>
</table>

### 

### <a name="buttons"></a>ボタン

| ボタン                     | 説明                                                                                                                                                                                                                                                                                                 |
|----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **削除**                 | [テーブルの削除] ウィンドウのデータ グリッドで選択されているテーブルを削除します。 テーブルを削除すると、選択したテーブルのすべての子テーブルが削除されます。 削除すると、リレーションシップ ツリー全体が削除され、選択したテーブルの子テーブルのすべてのネストされた親子リレーションが削除されます。 |
| **元に戻す**                 | 削除オブジェクトに行われた変更を前回の変更まで戻します。 これは、「元に戻す」のようなものです。                                                                                                                                                                                                  |
| **すべて表示/選択されたものを表示** | すべてのテーブルまたは選択したテーブルを表示し、コマンド ボタンのラベルを切り替えます。 削除されたテーブルが、周囲に赤い点線付きで表示されます。                                                                                                                                                                   |
| **復元**                | 作成時に使用した元のソースに削除オブジェクトを戻します。 削除テンプレートを使用していた場合、削除オブジェクトは IDMF に同梱されているテンプレートに戻ります。 検出プロセスを使用していた場合、削除オブジェクトは、検出し保存した最初の削除オブジェクトに戻ります。           |

### 

### <a name="fields-remove-table-pane"></a>フィールド (テーブルの削除ウィンドウ)

| フィールド                 | 説明                                                           |
|-----------------------|-----------------------------------------------------------------------|
| **チェック ボックス**       | 関係ツリーから削除するテーブルを選択します。 |
| **テーブル名**        | テーブルの名前。                                                |
| **コンフィギュレーション キー** | このテーブルのコンフィギュレーション キー。                                   |
| **レベル**             | リレーションシップ ツリー内のテーブルのレベル。                      |
| **行数**         | テーブルの行数。                                      |

## <a name="walkthrough-create-a-purge-object"></a>チュートリアル: 削除オブジェクトの作成
このセクションでは、削除オブジェクトの操作に関するチュートリアルを提供します。
1.  削除オブジェクトをまだ作成していない場合は、作成します。
2.  **ズーム** スライダーを使用して、テーブル名を簡単に読み取れるように図のサイズを変更します。
3.  リレーションシップ ツリーで、テーブル **PurchParmTable** にマウス ポインターを移動し、ツール ヒントに表示される情報を確認します。 リレーションシップ ツリーで、**PurchParmLine** テーブルの上の **1:N 関係の説明**にマウス ポインターを移動し、ツール ヒントに表示される情報を確認します。
4.  **プロパティ** ウィンドウで、ツリー ビューの各ノードを展開して指定されている情報を表示します。
5.  **高度なフィルター** コントロールでの選択基準が表示されない場合、**高度なフィルター**矢印をクリックします。 レベル ボックスに 1 と入力してから、**検索** をクリックします。 これにより、レベル 1 にあるテーブルのみが表示されるようにグリッドが変更されます。
6.  横にあるチェック ボックスをオンにして **PurchParmLine** テーブルを選択します。
7.  **プロパティ** ウィンドウで**削除**をクリックします。 テーブル **PurchParmLine**、およびレベル 1 および 2 のすべての子テーブルが赤い枠線でマークされていることを確認します。これらのテーブルはリレーションシップ ツリーから削除されたことを示します。
8.  **プロパティ** ウィンドウの**すべて表示**ボタンをクリックします。 図にはすべてのテーブルが表示され、削除されたテーブルは灰色の形で赤い線で表示されます。
9.  **元に戻す**をクリックし、元の削除オブジェクトを復元します。 この図は、手順 7で **PurchParmLine** を削除する前の状態に戻ります。
10. 手順 6、7、8 を繰り返して、もう一度テーブルを削除します。 赤い実線の入った灰色の図形に、削除されたすべてのテーブルが表示されます。
11. **プロパティ** ウィンドウ内の**選択項目の表示**をクリックし、改訂された削除オブジェクトを表示します。 削除したテーブルが削除オブジェクトに存在しないことを確認します。
12. 削除オブジェクトを保存します。 ツール バーの **保存** をクリックします。
13. 警告が表示されます。 警告を慎重に読みます。 IDMF では、Microsoft Dynamics AX アプリケーション テーブル間の階層関係ツリーを定義する削除のオブジェクトを作成できます。 特定の条件に基づき選択したレコードにルールを適用することができます。 選択基準に一致するレコードは、削除オブジェクト内の関係ツリー全体から削除されます。 IDMF を不適切に使用すると、予期しない結果、データベース破損、データベース全体およびアプリケーションの復旧が必要となるアプリケーション ダウンタイムが発生する可能性があります。 実稼働環境で作業する前に、十分に注意を払い、テスト環境でリサイクル戦略を入念にテストする必要があります。 削除オブジェクトの保存を続ける場合は**はい**を 、保存操作をキャンセルする場合は**いいえ**をクリックします。 チュートリアルを続行するには、**はい**をクリックします。
14. **名前を付けて保存**ダイアログ ボックスで、名前が **PurchParmTable** であることを確認します。 **保存** をクリックします。
15. **削除オブジェクトの上書き**ダイアログ ボックスで、**はい**をクリックして新しいバージョンで削除オブジェクトを上書きします。 **保存状態**ダイアログ ボックスで **OK** をクリックして続行します。
16. ツールバーで、**削除テンプレート/削除オブジェクト**をクリックし、**PurchParmTable** をクリックします。 削除オブジェクトのアイコンが変更されたことに注意してください。 このアイコンの変更により、削除オブジェクトと削除テンプレートが区別されます。
17. 削除オブジェクト図に手順 10 で削除したテーブルが含まれていないことを確認します。 **すべての表示/選択項目の表示** を切り替えて、削除したテーブルが赤い境界線に引き続き表示されることを確認します。
18. **プロパティ** ウィンドウで**元に戻す**をクリックします。 削除オブジェクトは変化しません。 削除オブジェクトが保存されているため、元に戻す操作で変更を元に戻すことはできません。
19. **プロパティ** ウィンドウで、**復元**をクリックして削除オブジェクトを元に戻します。 削除オブジェクトは、いずれかが存在する場合、IDMF に含まれる削除テンプレートに戻ります。 既定の削除テンプレートがない場合は、削除オブジェクトは検索プロセスで作成した最初のバージョンに戻ります。 復元された削除オブジェクトは、手順 1 で作業を開始した削除オブジェクトと同じか、異なる場合があります。 既定の削除テンプレートには、Microsoft Dynamics AX アプリケーションの機能評価に基づいて変更または調整されたリレーションシップ ツリーが含まれています。
20. ツール バーの **保存** をクリックします。 オブジェクトを上書きするには、**はい**をクリックします。 **保存状態**ダイアログ ボックスで **OK** をクリックします。 次のセクションでも使用するため、削除オブジェクトを開いたままにします。

## <a name="walkthrough-disable-a-relation"></a>チュートリアル: リレーションの無効化
このセクションでは、複数の関係を持つテーブル内の関係を無効にするためのチュートリアルを提供します。
1.  **コンフィギュレーション** メニューをクリックします。 ツールバーで、**削除テンプレート/削除オブジェクト**をクリックし、リストから **InventJournalTable** を選択します。
2.  リレーションシップ ツリーで、**InventJournalTrans** テーブルの上の **1:N 関係の説明**にマウス ポインターを移動し、ツール ヒントに表示される情報を確認します。 このテーブルに関係が 1 つだけあることを確認します。
3.  リレーションシップ ツリーで、**WMSJournalTable** テーブルの上の **1:N 関係の説明**にマウス ポインターを移動し、ツール ヒントに表示される情報を確認します。 このテーブルに多くの関係があることを確認します。
4.  リレーションシップ ツリーで、**WMSJournalTable** を選択します。
5.  **プロパティ** ウィンドウで **WMSJournalTable**&gt; **関係**と展開します。 このテーブルには多くのリレーションが含まれていて、**プロパティ** ウィンドウを使用して、1 つまたは複数のリレーションを無効にすることができます。 **InventBOM** 関係を右クリックして **関係の無効化** メニューを開きます。 **関係の無効化** メニューは、テーブルが複数の関係を持つ場合にのみ表示されます。
6.  **関係**ノードで、**InventCount** を右クリックして**関係の無効化**を選択します。 無効な関係が赤色で表示されていることに注意します。 **InventCount** を右クリックし、**関係の有効化** を選択します。 有効な関係が黒色で表示されていることに注意します。 除外された関係は削除オブジェクトの一部にはなりません。 複数の有効な関係が削除オブジェクトが生成する SQL ステートメントで「or」句を形成します。
7.  削除テンプレートを保存しないでください。

    | **注意**                                                                                                            |
    |------------------------------------------------------------------------------------------------------------------------|
    | 除外された関係を徹底的にテストし、慎重に行います。 誤ったまたは間違った除外はデータの破損を引き起こします。 |

## <a name="purge-templatepurge-objects"></a>テンプレートの削除/オブジェクトの削除
このコマンドは、システム内の削除テンプレートと削除オブジェクトのリストを提供します。 削除テンプレートは、事前定義されたリレーションシップ ツリーで IDMF に含まれているテンプレートです。 出発点として削除テンプレートを使用し、削除オブジェクトを作成することができます。 削除タスクの使用前に、要件を満たしているかどうか確認するために削除テンプレートを確認して保存する必要があります。
### <a name="walkthrough-work-with-a-purge-template"></a>チュートリアル: 削除テンプレートの操作

このセクションでは、削除テンプレートの操作に関するチュートリアルを提供します。
1.  ツールバーで、**削除テンプレート/削除オブジェクト**をクリックし、リストから **InventJournalTable** を選択します。
2.  テーブル、テーブルのプロパティ、関係ツリーを確認し、**PurchReqTable** での削除アクションが削除テンプレートの関係ツリーを通じてカスケードする方法を理解します。 このリレーションシップ ツリーに、アプリケーションと、Microsoft Dynamics AX アプリケーションに対して行ったすべてのカスタマイズが含まれていることを確認します。
3.  ツール バーの **保存** をクリックします。 同じ名前を保持するか、名前を変更することができます。 名前を PurchReqTable\_ オブジェクトに変更し、この保存されたオブジェクトを削除オブジェクトとして識別します。 **保存** をクリックします。
4.  続行するにはダイアログ ボックスで **OK** をクリックします。
5.  ツールバーで、**削除テンプレート/削除オブジェクト**をクリックし、**PurchReqTable** と **PurchReqTable \_オブジェクト**のアイコンを比較します。
6.  手順 1 ～ 3 を繰り返しますが、オブジェクトを元の名前 **PurchReqTable** で保存します。
7.  **削除オブジェクトの上書き**ダイアログ ボックスで、**はい**をクリックして新しいバージョンでオブジェクトを上書きします。 **OK** をクリックして続行します。
8.  ステップ 5 を繰り返します。 削除オブジェクトと保存された削除テンプレートのアイコンが同じであることを確認します。 これは、削除テンプレートを保存すると削除オブジェクトになるためです。





