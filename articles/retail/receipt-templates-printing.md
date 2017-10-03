---
title: "レシートのテンプレートおよび印刷"
description: "この記事は、フォーム レイアウトを変更して、レシート、請求書、およびその他の文書の印刷方法を制御する方法について説明します。 Microsoft Dynamics 365 for Retail ではさまざまな種類のフォーム レイアウトを簡単に作成および変更するフォーム レイアウト デザイナーが用意されています。"
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 57841
ms.assetid: e530dd8e-95e2-4021-90bd-ce1235f9e250
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 6f1ec982522c6fe677b1921b69d5d04c4e783725
ms.contentlocale: ja-jp
ms.lasthandoff: 06/20/2017

---

# <a name="receipt-templates-and-printing"></a>レシートのテンプレートおよび印刷

[!include[banner](includes/banner.md)]


この記事は、フォーム レイアウトを変更して、レシート、請求書、およびその他の文書の印刷方法を制御する方法について説明します。 Microsoft Dynamics 365 for Retail ではさまざまな種類のフォーム レイアウトを簡単に作成および変更するフォーム レイアウト デザイナーが用意されています。

**重要:** Retail Modern POS とクラウド POS からレシートやその他の文書を印刷するために、フォーム レイアウトおよびレシート プロファイルを設定する必要があります。 レシート プロファイルに複数のフォーム レイアウトを含めることができます。 ハードウェア プロファイルを変更して、プリンタにレシート プロファイルを割り当てることができます。

## <a name="set-up-a-receipt-format"></a>受領書フォーマットの設定
1.  [**小売**] &gt; [**チャンネル設定**] &gt; [**POS 設定**] &gt; [**POS**] &gt; [**受領書フォーマット**] をクリックします。
2.  **受領書フォーマット**ページにて、[**新規**] をクリックし、新しいフォーム レイアウトを作成するか、既存のフォーム レイアウトを選択します。
3.  [**受領書フォーマット**] フィールドで、フォーム レイアウトの ID を入力して、このレイアウトを使用するレシート タイプを選択します。 また、[**タイトル**] フィールドにレシートの説明と短縮名を入力することもできます。
4.  [**概要**] クイック タブで、印刷動作を定義するオプションを選択します。
    -   **常に印刷する** – 必要に応じて、レシートが自動的に印刷されます。
    -   **印刷しない** – レシートは印刷されません。
    -   **ユーザーに確認する** – ユーザーはレシートを印刷するように求められます。
    -   **必要時** – このオプションは、ギフト レシートにのみ使用されます。 ギフト レシートが必要な場合は、このオプションを選択すると、ユーザーは**変更**ページからギフト レシートを印刷できます。

## <a name="design-a-receipt-format"></a>受領書フォーマットのデザイン
フォーム レイアウト デザイナーを使用して、フォーム文書のレイアウトをグラフィカルに作成します。 **受領書フォーマット デザイナー** ページには 3 つのセクションがあります。**ヘッダー**、**明細行**、および**フッター**です。 3 つのすべてのセクションの要素を使用するフォーム レイアウトもあれば、1 つまたは 2 つのセクションの要素しか使用しないフォーム レイアウトもあります。 各セクションで使用できる要素を表示するには、ページの左側のナビゲーション ウィンドウのボタンをクリックします。

1.  [**小売**] &gt; [**チャンネル設定**] &gt; [**POS 設定**] &gt; [**POS**] &gt; [**受領書フォーマット**] をクリックします。
2.  **受領書フォーマット**ページで、フォーム レイアウトを選択し、[**デザイナー**] をクリックします。
3.  小売デザイナー ホストのインストールを開始するには、[**実行**] をクリックします。
4.  ワンクリック デザイナーのインストールを開始する場合、Internet Explorer ウィンドウの下部に表示される通知バーの [**開始**] をクリックします。 (通知バーは、他のブラウザの別の場所に表示されることがあります。) 進行状況インジケータは、インストール プロセスの進行状況を示します。
5.  インストール完了後に、デザイナーを開始する場合、Dynamics 365 for Retail のユーザー名とパスワードを入力し、[**サインイン**] をクリックします。
6.  資格情報を検証しデザイナーを開始した後に、受領書フォーマットを作成するか、または既存のフォーマットを変更することができます。
7.  フォームの要素を作成するには、**ヘッダー**、**明細行**、または**フッター**セクションを選択し、セクションの要素をワークスペースにドラッグします。 ほとんどの要素は、データベースからデータが自動的に入力される変数で構成されます。 [**テキスト**] などのその他の要素は、カスタム テキストをレシートに印刷できます。 **注記:**それぞれのセクションで使用する行数は、そのセクションの右下隅にある数値を調整することで選択できます。 セクションを変更しやすいように、セクション下部のサイズ変更バーをドラッグして、その高さを増やします。 ワークスペースのセクションの高さは、実際のレシートの行数に影響しません。
8.  要素をワークスペースにドラッグした後、ページ下部にある [**オブジェクト情報**] ウィンドウでパーツのプロパティを設定します。 次の 1 つまたは複数の設定を入力します。
    -   [**配置**]: フィールドの配置を [**左**] または [**右**] に設定します。
    -   [**充填文字**] - 空白文字を指定します。 既定では、空白を使用しますが、任意の文字を入力できます。
    -   [**接頭語**] - フィールドの先頭に表示される値を入力します。 この設定は、レイアウトの [**明細行**] セクションにのみ適用されます。
    -   [**文字**] – 要素に変数が含まれている場合に、フィールドに含めることができる文字の最大数を指定します。 フィールドのテキストが指定した文字数よりも長い場合は、フィールドに合わせて切り詰められます。
    -   [**変数**] - 要素が変数を含むためにカスタマイズできない場合は、このチェック ボックスが自動的にオンになります。
    -   [**フォントの種類**] - フォント スタイルを [**通常**] または [**太字**] に設定します。 太字の文字は、通常の文字の 2 倍のスペースを使用します。 したがって、一部の文字が切り詰められる場合があります。
    -   [**フォント サイズ**] - フォント サイズを [**通常**] または [**大**] に設定します。 [大] の文字は [通常] の文字より 2 倍高くなります。 したがって、[大] の文字を使用すると、レシートでテキストが重なる可能性があります。
    -   [**削除**]: 選択したパーツをフォーム レイアウトから削除する場合は、このボタンをクリックします。

## <a name="assign-receipt-profiles"></a>レシート プロファイルの割り当て
ハードウェア プロファイルを通じてレシート プロファイルがプリンタへ直接割り当てられます。

1.  [**小売**] &gt; [**チャンネル設定**] &gt; [**POS 設定**] &gt; [**POS プロファイル**] &gt; [**ハードウェア プロファイル**] をクリックして、ハードウェア プロファイルを開きます。
2.  次に、プリンタを選択し、[**レシート プロファイル**] フィールドで、レジスターを使用してレシート プロファイルを割り当てます。

**注記:** 2 つのプリンタを使用する場合、１ つ目のプリンタでは標準の 40 列のサーマル レシートを使用できます。 2 番目のプリンタは、通常、詳細情報を要求する全ページのレシート タイプの印刷に使用されます。 これらのレシート タイプでは、顧客注文のレシートおよび顧客請求書が含まれます。



