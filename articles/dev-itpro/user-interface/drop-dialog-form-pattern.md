---
title: "ダイアログ削除のフォーム パターン"
description: "このトピックでは、ドロップ ダイアログ フォームのパターンについて説明します。 このパターンは、フィールド数が 7 以下の場合にアクションを開始するために使用されます。"
author: jasongre
manager: AnnBe
ms.date: 11/09/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 16041
ms.assetid: 94ffa218-de7d-4d13-9a8a-461cad0970b3
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 879eb9f2a63a8514791f74965005ed3e22bc0de7
ms.openlocfilehash: 3c93356b1e79b0714e05fb9f29857b8efae0c033
ms.contentlocale: ja-jp
ms.lasthandoff: 04/20/2018

---

# <a name="drop-dialog-form-pattern"></a>ダイアログ削除のフォーム パターン

[!include [banner](../includes/banner.md)]

このトピックでは、ドロップ ダイアログ フォームのパターンについて説明します。 このパターンは、フィールド数が 7 以下の場合にアクションを開始するために使用されます。 

<a name="usage"></a>用途
-----

ダイアログ削除パターンは、フィールド数が 7 以下の場合にアクションを開始するために使用されます。 ドロップ ダイアログはユーザーが使用するのが素早く簡単で、スライダーとして表示される完全なダイアログよりも軽量です。 ドロップ ダイアログは、メニューとして使うには軽量であることを示します。 このドキュメントでは、2 つのパターンについて説明します。

-   **ドロップ ダイアログ** - これは、基本的なドロップ ダイアログ パターンです。 ドロップ ダイアログが編集可能な場合は、これが使用する正しいパターンです。
-   **ドロップ ダイアログ (読み取り専用)** - このドロップ ダイアログ パターンは、編集できない情報フォーム用です。 このバリエーションには **OK** ボタンはありません。

## <a name="wireframe"></a>ワイヤーフレーム
### <a name="drop-dialog-basic"></a>ドロップ ダイアログ (basic)

[![DropDialog(1)](./media/dropdialog1.png)](./media/dropdialog1.png)

### <a name="drop-dialog-read-only"></a>ドロップ ダイアログ (読み取り専用)

[![DropDialog(2)](./media/dropdialog2.png)](./media/dropdialog2.png)

## <a name="pattern-changes"></a>パターンの変更
Microsoft Dynamics AX 2012 以降に加えられるこのパターンへの主な変更を次に示します。

-   エラー メッセージの手動処理が必要なくなりました。

## <a name="model"></a>モデル
### <a name="drop-dialog-basic--high-level-structure"></a>ドロップ ダイアログ (basic) – 高度なレベル構造

- デザイン

    - *SecondaryInstruction (StaticText) \[オプション\]*
    - DialogContent (Group)
    - DialogCommitContainer (ButtonGroup)

        - OKButton ($Button)

### <a name="drop-dialog-read-only--high-level-structure"></a>ドロップ ダイアログ (読み取り専用) – 高度なレベル構造

- デザイン

    - *SecondaryInstruction (StaticText) \[オプション\]*
    - DialogContent (Group)

### <a name="core-components"></a>コア コンポーネント

-   **Form.Design** にドロップ ダイアログ パターンを適用します。
-   BP 警告に対処します。
    -   **Design.Caption** は空ではありません。
    -   このフォームは少なくとも 1 つのメニュー項目で参照される必要があります。
    -   **StaticText.Text** は空ではありません。

### <a name="related-patterns"></a>関連するパターン

-   [ダイアログ](dialog-form-pattern.md)

### <a name="commonly-used-subpatterns"></a>一般的に使用されるサブパターン

-   [フィールドおよびフィールド グループ](fields-field-groups-subpattern.md)
-   [ツールバーおよびリスト](toolbar-list-subpattern.md)

## <a name="ux-guidelines"></a>UX ガイドライン
検証チェックリストには、フォームが UX ガイドラインに準拠しているかどうかを手動で確認する手順が示されています。 このチェックリストには、開発環境を通じて自動的に実施されるガイドラインは含まれていません。 ブラウザーでフォームを開いて、これらの手順を確認します。 **標準フォーム ガイドライン:**

-   標準フォーム ガイドラインは、[全般的なガイドライン](general-form-guidelines.md) ドキュメントに統合されました。

**ドロップ ダイアログ ガイドライン:**

-   次の条件に当てはまる場合は、ドロップ ダイアログを使用する必要があります:
    -   7 つ以下のフィールドがあります。
    -   ユーザーは、簡単に情報を入力できます。
    -   最小限のフィールド検証が必要です。
    -   追加の子フォームを開くボタンはありません。
        -   **例外:** ルックアップ、拡張プレビュー、および表示の詳細のナビゲーション
    -   編集可能なグリッドはありません (選択専用のグリッドは使用できます)。
-   ドロップ ダイアログが最初に開いたときに、フォーカスは、ドロップ ダイアログの最初の編集可能なフィールドにある必要があります。
-   ドロップ ダイアログには、上部に**主な指示**がある必要があります。
    -   主な指示は、ユーザーがドロップ ダイアログで行うべきことを簡潔に説明するために使用する必要があります。 指示は、特定の明細書、命令的な指示、または質問でなければなりません。 適切な手順では、操作の仕組みにだけに重点を置くのではなく、ドロップ ダイアログを使用してユーザーの目的を伝達します。
    -   主な指示が明細書である場合、最終的な期間を含めません。 指示が質問である場合、疑問符が含まれる必要があります。
    -   主要な指示に加えて、ユーザへの二次命令が表示され、ユーザがドロップ ダイアログを理解または使用するのに役立つ追加情報を提示する必要があります。 2 番目の指示は、大文字小文字の完全な文で構成する必要があり、文末の句点を含める必要があります。
        -   **例外:** 追加指示が主要な指示をわずかに異なる言い方で単に繰り返す場合は、それを含めないでください。
-   ドロップ ダイアログには、**コンテンツ**領域が必要です。
    -   検証エラーを避けるために、制約された入力コントロールを使用する必要があります。 例には、選択リスト、チェック ボックス、オプション ボタン、およびコマンド リンクが含まれます。
    -   可能な場合は、入力ごとに適切な既定値を指定する必要があります。
-   ドロップ ダイアログには、次のような**コミット**ボタン領域が必要です:
    -   **キャンセル**ボタンを、**持たない**でください。
    -   ドロップ ダイアログの既定のボタンとしてマークされるボタンがあります (ボタンが存在する場合)。
    -   既定のボタンのラベルは、主な指示に記述されているアクションを実装する動詞でなければなりません。 たとえば、主要な指示が「新製品の作成」である場合、ボタン ラベルは**作成**となります。 ボタンの適切な動詞がない場合は、**OK** を使用します。
    -   コミット ボタン領域には、独自の意味を持ち、主な指示への応答である特定のコミット ボタン ラベルが必要です。

ドロップ ダイアログには、次の項目は**ありません**:

-   ドロップ ダイアログのツールバーまたは ActionPane の任意の場所。
-   別のページに移動するか、他のダイアログを開くボタン。 (拡張プレビューを使用できます。)
-   フィールド グループ。 ラジオ ボタンやチェック ボックス グループなどの例外があります。
-   タブ コントロール。
-   情報ボックス。
-   FastTabs。

## <a name="examples"></a>例
### <a name="drop-dialog-basic"></a>ドロップ ダイアログ (basic)

Form: **CustCollectionsNewActivityAction** (**売掛金勘定** &gt; **共通** &gt; **コレクション** &gt; **コレクション**の順にクリックし、詳細に移動する行を選択し、**アクション**をクリックします。) 

[![DropDialog(3)](./media/dropdialog3.png)](./media/dropdialog3.png)

### <a name="drop-dialog-read-only"></a>ドロップ ダイアログ (読み取り専用)

このパターンは現在製品で使用されていません。

## <a name="appendix"></a>付録
### <a name="frequently-asked-questions"></a>よく寄せられる質問

このセクションには、このガイドライン/パターンに関連するよくある質問への回答があります。

### <a name="open-issues"></a>未処理の問題

-   **垂直フィールドおよびフィールド グループのサブパターン はドロップ ダイアログに追加する必要がありますか。**
    -   いいえ、通常のフィールドおよびフィールド グループのパターンを使用する必要があります。
-   **ボタンは左揃えまたは右揃えにすべきですか。**
    -   右揃え。 パターンは現在はこれを実施しています。

### <a name="ax-2012-content"></a>AX 2012 コンテンツ

[![DropDialog(4)](./media/dropdialog4.png)](./media/dropdialog4.png)
