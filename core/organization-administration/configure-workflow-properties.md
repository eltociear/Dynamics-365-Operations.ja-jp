---
title: "ワークフローのプロパティをコンフィギュレーション"
description: "このトピックでは、ワークフローの各種プロパティをコンフィギュレーションする方法について説明します。"
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 263ebaf1cf509589a745f1a9ec3384f97e854519
ms.contentlocale: ja-jp
ms.lasthandoff: 05/25/2017


---

# <a name="configure-the-properties-of-a-workflow"></a>ワークフローのプロパティをコンフィギュレーション

[!include[banner](../includes/banner.md)]


このトピックでは、ワークフローの各種プロパティをコンフィギュレーションする方法について説明します。

ワークフローのプロパティをコンフィギュレーションするには、ワークフロー エディターでワークフローを開きます。 ワークフロー エディターのキャンバスをクリックし、[**プロパティ**] をクリックして、[**プロパティ**] ページを開きます。 ワークフローの各種プロパティをコンフィギュレーションするには、次の手順を使用できます。

## <a name="name-the-workflow"></a>ワークフローに名前を付ける
次の手順でワークフローの名前を入力します。

1.  左ウィンドウで [**基本設定**] をクリックします。
2.  [**名前**] フィールドに、ワークフローの固有の名前を入力します。 たとえば、事業を行っている国または地域ごとに購買要求ワークフローを作成する場合には、購買要求ワークフローの名前を「**購買要求 (デンマーク)**」、または「**購買要求 (スペイン)**」のようにすることができます。

## <a name="specify-the-workflow-owner"></a>ワークフローの所有者の指定
ワークフローの所有者とは、そのワークフローの管理と保守を行う人のことです。 次の手順でワークフローの所有者を指定します。

1.  左ウィンドウで [**基本設定**] をクリックします。
2.  [**所有者**] 一覧で、ワークフローの管理を行う人の名前を選択します。

## <a name="select-an-email-template"></a>電子メール テンプレートの選択
このワークフローに関する通知メッセージを生成するのに使用する電子メール テンプレートを選択するには、次の手順に従います。

1.  左ウィンドウで [**基本設定**] をクリックします。
2.  [**ワークフロー通知の電子メール テンプレート**] 一覧で、テンプレートを選択します。

## <a name="enter-instructions-for-users"></a>ユーザーに対する指示の入力
処理と承認を求めてドキュメントを送信するユーザーに指示を入力できます。 これらのユーザーは、[*作成者*] とも呼ばれます。 たとえば、購買要求ワークフローを作成しており、指示を入力するとします。 これらの指示は、[**購買要求**] ページで、購買要求を入力するユーザーに対して表示できます。 指示を表示するには、作成者がワークフロー メッセージ バーのアイコンをクリックします。 次の手順に従って、ユーザーに対する指示を入力します。

1.  左ウィンドウで [**基本設定**] をクリックします。
2.  [**送信指示**] フィールドで、指示を入力します。
3.  指示を個人向けのものにするには、プレースホルダーを挿入します。 プレースホルダーは、指示行がユーザーに表示されるときに、適切なデータに置き換えられます。 プレースホルダーを挿入するには、次の手順に従います。
    1.  [**送信指示**] フィールドをクリックして、プレースホルダを表示する場所を指定します。
    2.  [**プレースホルダーの挿入**] をクリックします。
    3.  表示されるリストで、挿入するプレースホルダーを選択します。
    4.  [**挿入**] をクリックします。

4.  指示行の翻訳を追加するには、次の手順に従います。
    1.  [**翻訳**] をクリックします。
    2.  表示されるページで、[**追加**] をクリックします。
    3.  表示される一覧で、テキストを入力する言語を選択します。
    4.  [**翻訳テキスト**] フィールドで、テキストを入力します。
    5.  テキストをカスタマイズするには、プレースホルダーを挿入します。 プレースホルダーを入力する方法については、ステップ 3 を参照してください。
    6.  [**閉じる**] をクリックします。

## <a name="specify-when-this-workflow-is-used"></a>このワークフローが使用される条件の指定
同じタイプに基づく複数のワークフローを作成できます。 たとえば、事業を行っている国や地域ごとの購買要求ワークフロー ("購買要求 (デンマーク)" および "購買要求 (スペイン)" など) を作成できます。 同じタイプに基づくワークフローが複数ある場合は、各ワークフローが使用される条件を指定する必要があります。 前の例では、次のような条件を指定することになります。

-   購買要求 (デンマーク) は、国/地域 = DK の場合に使用する
-   購買要求 (スペイン) は、国/地域 = ES の場合に使用する

次の手順を実行して、コンフィギュレーション内のワークフローをいつ使用するかを指定します。

1.  左ウィンドウで、[**有効化**] をクリックします。
2.  [**このワークフローを実行する条件を設定する**] のチェック ボックスをオンにします。
3.  [**条件の追加**] をクリックします。
4.  条件を入力します。
5.  必要に応じて、追加条件を入力します。
6.  入力した条件が正しく設定されていることを確認するには、次の手順を実行します。
    1.  [**テスト**] をクリックします。
    2.  [**ワークフロー条件のテスト**] ページで、[**条件の検証**] 領域で、レコードを選択します。
    3.  [**テスト**] をクリックします。 システムによってレコードが評価され、指定した条件を満たすかどうかが判定されます。 たとえば、スペイン向けの購買要求ワークフローを作成している場合、ページの [**条件の検証**] 領域に、購買要求の一覧が表示されます。 [**テスト**] をクリックすると、選択した購買要求が評価され、国/地域 = ES (スペイン) であるかどうかが確認されます。
    4.  [**OK**]、または [**キャンセル**] をクリックして、[**プロパティ**] ページに戻ります。

## <a name="specify-when-notifications-are-sent"></a>いつ通知を送信するかを指定する
処理のためにドキュメントが送信されると、ワークフロー インスタンスが作成されます。 このワークフローに基づくワークフロー インスタンスが開始、完了、打ち切り、またはエラーによって停止されたときに、ユーザーに通知を送信できます。 いつ通知を送信するかを指定するには、次の手順に従います。

1.  左ウィンドウで、[**通知**] をクリックします。
2.  通知をトリガーする各イベントのチェック ボックスをオンにします。
    -   [**開始済**] – ワークフロー インスタンスが開始されたときに通知を送信します。
    -   [**停止済**] – ワークフロー インスタンスがエラーで停止したときに通知を送信します。
    -   [**完了**] – ワークフロー インスタンスが完了したときに通知を送信します。
    -   [**修復不可能**] – ワークフロー インスタンスが、修復不可能なエラーで停止したときに通知を送信します。
    -   [**終了**] – ワークフロー インスタンスが打ち切られたときに通知を送信します。

3.  ステップ 2 で選択したイベントの行を選択します。
4.  [**通知テキスト**] タブで、通知のテキストを入力します。
5.  テキストをカスタマイズするには、プレースホルダーを挿入します。 プレースホルダーは、テキストがユーザーに表示されるときに、適切なデータに置き換えられます。 プレースホルダーを挿入するには、次の手順に従います。
    1.  フィールド内でクリックして、プレースホルダーを表示する場所を指定します。
    2.  [**プレースホルダーの挿入**] をクリックします。
    3.  表示されるリストで、挿入するプレースホルダーを選択します。
    4.  [**挿入**] をクリックします。

6.  テキストの翻訳を追加するには、次の手順に従います。
    1.  [**翻訳**] をクリックします。
    2.  表示されるページで、[**追加**] をクリックします。
    3.  表示される一覧で、テキストを入力する言語を選択します。
    4.  [**翻訳テキスト**] フィールドで、テキストを入力します。
    5.  テキストをカスタマイズするには、プレースホルダーを挿入します。 プレースホルダーを入力する方法の指示については、ステップ 5 を参照してください。
    6.  [**閉じる**] をクリックします。

7.  [**受信者**] タブで、次のオプションを使用して、通知の受信者を指定します。
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>オプション</th>
    <th>通知はこれらのユーザーに送信されます。</th>
    <th>通知を送信するには、次の手順に従います。</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>参加者</td>
    <td>特定のグループまたはロールに割り当てられたユーザー</td>
    <td><ol>
    <li>[<strong>受信者</strong>] タブで [<strong>参加者</strong>] をクリックします。</li>
    <li>[<strong>参加者のタイプ</strong>] 一覧の、[<strong>ロール ベース</strong>] タブで、通知の送信先のグループまたはロールのタイプを選択します。</li>
    <li>[<strong>参加者</strong>] の一覧で、通知の送信先のグループまたはロールのタイプを選択します。</li>
    </ol></td>
    </tr>
    <tr class="even">
    <td>ワークフロー ユーザー</td>
    <td>このワークフローの参加者であるユーザー</td>
    <td><ol>
    <li>[<strong>受信者</strong>] タブの、[<strong>ワークフロー ユーザー</strong>] をクリックします。</li>
    <li>[<strong>ワークフロー ユーザー</strong> の一覧の、[<strong>ワークフロー ユーザー</strong>] タブで、このワークフローの参加者を選択します。</li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td>ユーザー</td>
    <td>特定の Dynamics 365 for Operations ユーザー</td>
    <td><ol>
    <li>[<strong>受信者</strong>] タブの、[<strong>ユーザー</strong>] をクリックします。</li>
    <li>[<strong>ユーザー</strong>] タブの [<strong>利用可能なユーザー</strong>] 一覧には、すべての Dynamics 365 for Operations ユーザーが含まれます。 通知の送信先のユーザーを選択して、それらのユーザーを [<strong>選択されたユーザー</strong>] リストに移動します。</li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  ステップ 2 で選択したイベントごとに、ステップ 3～7 を繰り返します。

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a>ワークフローに加えた変更に関するコメントを入力します。
このワークフローに加えた変更に関するコメントを入力するには、次の手順に従います。

1.  左ウィンドウで、[**メモ**] をクリックします。
2.  [**ワークフローに関するコメントの入力**] フィールドにコメントを入力します。
3.  入力したコメントを確認します。 追加したコメントは変更できません。
4.  [**追加**] をクリックして、[**コメントの履歴**] 領域にコメントを追加します。




