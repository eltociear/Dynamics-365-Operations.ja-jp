---
title: Microsoft Flow を使用してビジネス イベントを消化する
description: このトピックでは、Finance and Operations コネクタを介して Microsoft Flow で使用可能となるビジネス イベントに関する情報を提供します。
author: ibenbouzid
manager: AnnBe
ms.date: 07/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global for most topics. Set Country/Region name for localizations
ms.author: imbenbou
ms.search.validFrom: Platform update 27
ms.dyn365.ops.version: 2019-6-30
ms.openlocfilehash: 7f0be999d0a64d1eb6f15f96dbcf0e0f008a2876
ms.sourcegitcommit: 0db7759947bd5fa20a6f4965e4eb4b48401f1299
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "1723208"
---
# <a name="consume-business-events-with-microsoft-flow"></a>Microsoft Flow を使用してビジネス イベントを消化する

[!include[banner](../../includes/banner.md)]

このトピックでは、 Microsoft Flow エンドポイントから Microsoft Dynamics 365 for Finance and Operations ビジネスイベントを設定・使用する手順を示します。

このトピックでは、以下のタスクを実行する方法について説明します:

-   新規 Microsoft Flow の作成
-   ビジネス イベントのトリガー

## <a name="create-a-new-microsoft-flow"></a>新しい Microsoft Flow の作成

1.  Microsoft Flow portal にサインインします。

2.  フローリソースを作成するために必要なアクセス権限のある既存の環境を選択します。 既定の環境は、すべての会社に対して開かれています。

3.  **空白から新規 \> を作成する**選択します。

4.  **Dynamics 365 for Finance and Operations** を検索して、コネクタを選択します。
     
5.  **ビジネス イベントが発生した場合** という名称の Finance and Operations のトリガーが確認できるかと思います。 このトリガーを選択します。

6.  環境インスタンス、カテゴリ、イベント名称、法的エンティティを選択します。

    <img src="../../media/BEF-Howto-Flow-04.png" width="50%">

7.  **新規ステップ** ボタンを選択して新しいアクションを追加します。

8.  **JSON解析** データ処理を検索します。 この手順は、Finance and Operationsから提供されるデータコントラクトのスキーマを使用してメッセージを解析するために必要となります。

    <img src="../../media/BEF-Howto-Flow-06.png" width="50%">

9.  **Jsonの解析** アクションの コンテンツ フィールドを選択すると、前のステップの **Body** がオプションとして表示されます。 **Body** を選択します。

    <img src="../../media/BEF-Howto-Flow-07.png" width="50%">

10. Finance and Operationsから受け取る契約のスキーマを入力します。 Finance and Operationsではサンプルのペイロードしか提供されないため、ペイロードからスキーマを生成する Microsoft Flow の機能を使用することができます。 Finance and Operations へと戻り、カタログ内のイベント (顧客支払など) を選択し、 **スキーマのダウンロード** のリンクを選択します。 テキストファイルがダウンロードされます。 テキストファイルを開き、内容をコピーします。

    <img src="../../media/BEF-Howto-Flow-08.png" width="50%">

11. Microsoft Flow に戻り、 **サンプル ペイロードを使用してスキーマを生成する** リンクを選択します。 テキストファイルの内容を貼り付け、 **完了** を選択します。

    <img src="../../media/BEF-Howto-Flow-09.png" width="70%">

12. サンプル ペイロードの品質によっては、自動生成機能が数値を認識できない場合があります。 これは、サンプル ペイロードに実数が整数として提供される場合に該当します。 生成されたスキーマを確認し、「整数」を「数値」に変更する必要があるかどうかを確認します。 (JSONでは、"数値" データ型は実数値を意味します)。

    <img src="../../media/BEF-Howto-Flow-10.png" width="100%">

13.  ビジネス イベント コンテンツを使用するための最終アクションを選択します。 たとえば、電子メールで (または、テキストメッセージをチームに共有する) 支払の詳細を顧客に送信することができます。 **電子メールの送信** アクションを検索し、自分の Office 365 アカウントにログインします。

14.  メッセージの本文および、必須項目を入力します。

   <img src="../../media/BEF-Howto-Flow-12.png" width="70%">

15. フローを保存します。

## <a name="trigger-a-business-event"></a>ビジネス イベント の トリガー

Microsoft Flow は、自動的にFinance and Operationsを設定することができます。 フローを保存すると、Finance and Operations にてエンドポイントが作成され、ビジネスイベントが有効となります。 イベントを起動する前にエンドポイントが正しく構成されていることを確認する以外に、Finance and Operationsに必要とされる構成手順はありません。

1. Finance and Operations クライアントにログインします

2.  **システム管理 \> 設定 \> システム パラメーター** の順に移動します。

3.  **ビジネス イベント**  タブを選択します。

4.  **ビジネス イベント**を選択します。

5.  **エンドポイント**をクリックします。

6.  新たなエンドポイントが作成され、名称にGUIDが追加されていることを確認します。

    <img src="../../media/BEF-Howto-Flow-13.png" width="100%">

7.  **有効なイベント** タブをオンにした場合は、法的エンティティGBSIに対し **支払転記済** が有効化されていることも確認することができます。

    <img src="../../media/BEF-Howto-Flow-14.png" width="100%">

8.  最後の手順では、転記された顧客支払のビジネス イベントをトリガーし、フローの実行と顧客の支払詳細を含む電子メールを受信するかどうかをチェックします。