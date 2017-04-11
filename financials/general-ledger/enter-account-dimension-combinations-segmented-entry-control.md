---
title: "勘定と分析コードの組み合わせの入力 (セグメント化されたエントリのコントロール)"
description: "この記事は、勘定と分析コードの組み合わせまたは勘定科目を入力する方法について説明します。 入力経験は、多くの場合、セグメント化されたエントリのコントロールと呼ばれます。"
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14071
ms.assetid: e6fce826-c403-4d91-a78b-e9a58c44ac03
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: db4b05bc55d735513d7580ca5908a1e84eb760c6
ms.openlocfilehash: 96e3e774437592580a88dfbdf270d4bc7cdfc4e4
ms.lasthandoff: 03/31/2017


---

# <a name="enter-account-and-dimension-combinations-segmented-entry-control"></a>勘定と分析コードの組み合わせの入力 (セグメント化されたエントリのコントロール)

この記事は、勘定と分析コードの組み合わせまたは勘定科目を入力する方法について説明します。 入力経験は、多くの場合、セグメント化されたエントリのコントロールと呼ばれます。

ユーザーは割り当て、定義を転記する一般仕訳帳のページなどの複数のページの勘定と分析コードの組み合わせを入力します。 有効な勘定と分析コードの組み合わせは、元帳に割り当てられた勘定構造と勘定構造に割り当てられた詳細ルールによって異なります。 ユーザーが組み合わせを入力すると、手動で入力するか、またはリッチ、参照の経験を使用することもできます。 フィールドを入力すると、入力を開始すると、値と説明を検索します。 たとえば、"180、その番号の組み合わせで始まるすべての値を取得します。 または現金を入力することができ、現金で始まるすべての説明を持つ値を取得します。 値または説明が検索条件が含まれている場合、検索している場合でも、\*現金または \*180などのワイルドカードを使用できます。 

次の表に、ルックアップが閉じているときに使用できるキーボード ショートカットを示します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>キーボード ショートカット</th>
<th>アクション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Alt + 下方向キー</td>
<td>ルックアップを開きます。 2 回目に Alt + 下方向キーを押した場合、フォーカスがポップアップのセグメントに移動します。</td>
</tr>
<tr class="even">
<td><ul>
<li>Enter キーおよび Shift + Enter キー</li>
<li>勘定科目表の区切り記号</li>
<li>右方向キーおよび左方向キー</li>
</ul></td>
<td>前後のセグメントへ移動します。</td>
</tr>
<tr class="odd">
<td>タブ</td>
<td>グリッド内で次のフィールドに移動します。</td>
</tr>
</tbody>
</table>

次の表に、ルックアップが開いているときに使用できるキーボード ショートカットを示します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>キーボード ショートカット</th>
<th>アクション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Esc キー</td>
<td>ルックアップを閉じます。</td>
</tr>
<tr class="even">
<td><ul>
<li>上方向キーおよび下方向キー</li>
<li>Page Up キーおよび Page Down キー</li>
<li>Home キーおよび End キー</li>
</ul></td>
<td>一覧での前後の値、値の前後のグループ、またはルックアップの最初または最後の要素に移動します。</td>
</tr>
<tr class="odd">
<td><ul>
<li>勘定科目表の区切り記号</li>
<li>右方向キーおよび左方向キー</li>
</ul></td>
<td>前後のセグメントへ移動します。</td>
</tr>
<tr class="even">
<td>タブ</td>
<td>グリッド内で次のフィールドに移動します。</td>
</tr>
<tr class="odd">
<td>Alt + W キー</td>
<td>[<strong>すべて表示l</strong>] と [<strong>有効なものを表示</strong>] を切り替えます。</td>
</tr>
</tbody>
</table>

 

