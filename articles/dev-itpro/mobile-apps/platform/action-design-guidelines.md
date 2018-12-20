---
title: "アクション デザインのガイドライン"
description: "このトピックでは、モバイル アプリの設計に関する詳細な情報を示します。"
author: makhabaz
manager: AnnBe
ms.date: 08/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer, IT Pro
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 255544
ms.assetid: 
ms.search.region: Global
ms.author: makhabaz
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Platform update 3
ms.translationtype: HT
ms.sourcegitcommit: 879eb9f2a63a8514791f74965005ed3e22bc0de7
ms.openlocfilehash: 62e92ee3e50510fdce0f437c0434b69bd19a5e4b
ms.contentlocale: ja-jp
ms.lasthandoff: 04/20/2018

---

# <a name="action-design-guidelines"></a>アクション デザインのガイドライン

[!include [banner](../../includes/banner.md)]

アクションでユーザーはデータの作成、更新、または削除を行うことができ、そのデータ (*送信*、*確認*、および*転記*など) で業務プロセスを実行することもできます。 アクションを完了したユーザーは、アクションのデータを最初に提供します (アクションがデータ入力を受け入れる場合)。 ユーザーがデータの提供を完了すると、アクションは同様のアクションのキューに配置されます (これは *データ同期操作* と呼ばれることもあります)。 デバイスが接続されているまたはオンラインである場合は、キューがすぐに処理されます。 それ以外の場合、次回デバイスが接続されたときに処理されます。 キューは非同期で処理され、データ同期中にエラーが発生しない限り、ユーザーの注意を必要としません。 このタイプのエラーは、サーバー側のデータ入力規則が原因で発生します。 アクションは、タスク記録に似たサーバー側メカニズムによって強化されます。 このメカニズムはアクションからユーザーの入力を抽出し、ユーザーが入力した入力値を使用してビジネス プロセス ステップをサーバー上で自動的に実行します。 この仕組みは、自動的にフォームを開き、フォーム上のボタンをクリックし、ユーザーの入力をフォームのコントロールに入力します。 サーバー上のフォームに対してアクションを再生するこのプロセスは、「ヘッドレス」フォームとは非同期で行われます。 モバイル アプリは、プロセスが完了するとユーザーに通知し、フォームに記録された情報、警告、またはエラー メッセージをユーザーに表示します。 アクションをデザインするときは、アクションがどのようなエンティティに関連付けられているかを最初に検討することが重要です。 現在のフレームワークでは、アクションでエンティティを 1 つだけ操作する必要があります。 アクションは同時に複数のエンティティを更新するべきではありません。 たとえば、新しい販売注文を作成するアクションは、注文のヘッダーのみを作成する必要があります。 明細行は別々のエンティティであるため、明細行を作成しないようにする必要があります。 アクションを設計することを決定したときは、以下の質問を検討して、展開の方法を決定します。

### <a name="how-do-i-design-an-action-that-enables-an-entity-to-be-created"></a>エンティティが作成されるようにするアクションをどのように設計しますか。

1.  エンティティのリスト ビュー ページを識別または作成します。
2.  リスト ビュー ページに使用されるフォームに、新しいレコードをリストに追加するために使用できる**新規**ボタンが含まれていることを確認します。
3.  デザイナーを使用して、ページに新しいアクションを作成します。 アクションを作成するときは、不要なアクションを実行しないように注意します。 ユーザーが使用できるフィールドにのみデータを入力し、必要なボタンだけをクリックします (たとえば、**新規**ボタンおよび**保存**ボタン)。

### <a name="how-do-i-design-an-action-that-enables-an-entity-to-be-edited"></a>エンティティが編集されるようにするアクションをどのように設計しますか。

1.  エンティティの詳細ビュー ページを識別または作成します。
2.  詳細ビュー ページに使用されるフォームに、表示されているレコードを編集するために使用できる**編集**ボタンが含まれていることを確認します。
3.  詳細ビュー ページに使用されるフォームから、ユーザーがフィルター ウィンドウにフィルターを適用することで特定のレコードを開けることを確認します。
4.  デザイナーを使用して、ページに新しいアクションを作成します。 アクションを作成するときは、不要なアクションを実行しないように注意します。 ユーザーが使用できるフィールドにのみデータを入力し、必要なボタンだけをクリックします (たとえば、**編集**ボタンおよび**保存**ボタン)。

### <a name="how-do-i-design-an-action-that-enables-an-entity-to-be-deleted"></a>エンティティが削除されるようにするアクションをどのように設計しますか。

1.  エンティティの詳細ビュー ページを識別または作成します。
2.  詳細ビュー ページに使用されるフォームに、表示されているレコードを削除するために使用できる**削除**ボタンが含まれていることを確認します。
3.  詳細ビュー ページに使用されるフォームから、ユーザーがフィルター ウィンドウにフィルターを適用することで特定のレコードを開けることを確認します。
4.  デザイナーを使用してページの新しいアクションを作成し、アクションの設計プロセスの一部として **削除**をクリックします。

### <a name="how-do-i-design-an-action-that-enables-a-business-action-to-be-performed-on-an-entity"></a>エンティティで実行される事業活動を有効にするアクションをどのように設計しますか。

1.  エンティティの詳細ビュー ページを識別または作成します。
2.  詳細ビュー ページに使用されるフォームに、表示されているレコードを削除するために使用できる**削除**ボタンが含まれていることを確認します。
3.  詳細ビュー ページに使用されるフォームから、ユーザーがフィルター ウィンドウにフィルターを適用することで特定のレコードを開けることを確認します。
4.  デザイナーを使用してページの新しいアクションを作成し、ビジネス アクションに必要な手順を実行します。 アクションの一部として、必ずしもフィールドにデータを入力する必要があるわけではありません。 *送信*などのアクションについては、単に**送信**ボタン (および任意の確認書が表示されることを確認します) をクリックする必要があります。

### <a name="how-do-i-design-an-action-that-enables-a-field-value-to-be-set-via-a-rich-lookup"></a>豊富なルックアップを介して設定するフィールド値を有効にするアクションをどのように設計しますか。

モバイル アプリでのフィールドのルックアップには、Finance and Operations の高度なルックアップ動作との相関関係はありません。 Finance and Operations にカスタム ルックアップがあるのか、単純なクエリを使用する自動ルックアップがあるのかに関係なく、モバイル アプリはユーザーに表示される UI を決定する必要があるときに既存のルックアップ コードを実行しません。 (ユーザーがアプリケーションを使用している間はオフラインになっている可能性があり、アクションが同期されるまでサーバー側のコードは実行されないことに注意してください。) ただし、アクションからのデータを同期させるので、値がモバイル バック エンドによって設定される場合、*変更*などのルックアップ/コントロールの上書きは実行されます。 モバイル アプリは、アクションのフィールドがフォームのルックアップ フィールドから選択されたことを検出すると、デバイス ネイティブ コンボ ボックス / リスト選択コントロールを表示して、そのルックアップ フィールドのサポート テーブルを直接照会して項目を実装します。 リスト内の項目は、そのテーブルのレコードの TitleField のユーザー データを示します。 アクションに豊富なルックアップ エクスペリエンスを追加するには、これらの手順に従います。 このルックアップ エクスペリエンスには、フルページの複数列のルックアップ セレクターがあり、オフライン検索が可能です。

1.  ルックアップの背後にあるエンティティの詳細ビュー ページを識別または作成します。 既に作成済みの既存のリスト ビュー ページを再利用することができます。
2.  アクションのデザインが終了した後、フィールドを選択して豊富なルックアップ機能を追加し、**プロパティ**をクリックします。
3.  **コントロールのプロパティ** ダイアログ ボックスで、手順 1 で指定または作成したリスト ビュー ページを選択し、その他の関連するプロパティを設定します。 

![コントロール プロパティの設定](media/lookupdesigner.png)

4.  アクションに変更内容を保存して公開します。

既存のリスト ビュー ページのプロパティが表示されていない、または**コントロールのプロパティ** ダイアログ ボックスにアクセスできない場合、Finance and Operations のより古いビルドを使用している可能性があります。 この場合、ビジネス ロジック ファイルを使用して、豊富なルックアップ機能を追加できます。

    function main(metadataService, dataService, cacheService, $q) { 
        return { 
            appInit: function (appMetadata) { 
                metadataService.configureLookup(
                    // specify the name of the Action to add the lookup to
                    'Add-Reservation',                      
                    // specify the name of the Action’s field to add the lookup to
                    'FMRental_Customer',                    
                    { 
                        // specify the name of the Page for the Entity for the lookup
                        lookupPage: 'All-Customers',          
                        // specify the Page’s field which contains the value to set on the lookup
                     // this value should be the same value you can type into the field on the Form
                        valueField: 'FMCustomer_RecId',        
                        // specify the Page’s field which contains the value to display to the user
                        // this value is only used for display. The value field is passed to the Form
                        displayField: 'FMCustomer_FullName',  
                        // set this to true to enable the rich lookup
                        showLookupPage: true                  
                    }
                );
            }, 
        }; 
    }

### <a name="how-do-i-prevent-an-action-from-appearing-in-the-list-of-actions-for-a-page"></a>アクションを、ページのアクションの一覧に表示されないようにするにはどうすればよいですか。

ページのアクション一覧にアクションが表示されないようにするには、ビジネス ロジックの **appInit()** セクションから次のコードを呼び出します。 このコードでは、**アクション名**はアクションの名前です (デザイナーの**アクション名**フィールドで指定したとおり)。

    function main(metadataService, dataService, cacheService, $q) { 
        return { 
            appInit: function (appMetadata) { 
                metadataService.configureAction('action-name', { visible: false });
            }, 
        }; 
    }
