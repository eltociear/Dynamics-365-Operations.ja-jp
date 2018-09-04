---
title: "ナビゲーションの構築"
description: "このチュートリアルでは、ワークスペースとナビゲーション ウィンドウにナビゲーション要素を追加します。"
author: aneesmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 26031
ms.assetid: ad8ba47b-becb-4d13-a5af-8aca46075e82
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 879eb9f2a63a8514791f74965005ed3e22bc0de7
ms.openlocfilehash: 9465891276c31c8b112b85c4524388cd080ecc63
ms.contentlocale: ja-jp
ms.lasthandoff: 04/20/2018

---

# <a name="build-navigation"></a>ナビゲーションの構築

[!include [banner](../includes/banner.md)]

このチュートリアルでは、ワークスペースとナビゲーション ウィンドウにナビゲーション要素を追加します。

<a name="prerequisites"></a>前提条件
-------------

このチュートリアルでは、リモート デスクトップを使用して環境にアクセスし、インスタンスの管理者としてプロビジョニングされる必要があります。 詳細については、「[アクセス インスタンス](../dev-tools/access-instances.md)」を参照してください。

## <a name="key-concepts"></a>重要な概念
-   *ワークスペース*は、特定のサブジェクト領域固有の概要ページです。 ワークスペースはすべてのユーザーに共通です。 このチュートリアルでは、既存のワークスペースにコンテンツを追加します。
-   *ダッシュボード*は、ユーザーごとの既定のホーム ページです。
-   *タイル*はワークスペースまたはダッシュボードに表示できるセキュリティ保護可能なオブジェクトです。 これらは、メニュー項目を使用して保護できます。

## <a name="setup"></a>段取り
これが作業する最初のチュートリアルである場合は、[アクセス インスタンス](../dev-tools/access-instances.md)を確認し、ローカル VM で作業している場合に、管理者ユーザーを提供するかどうかを確認します。

### <a name="import-the-tutorial-project"></a>チュートリアル プロジェクトのインポート

フリート管理チュートリアル プロジェクトを既にインポートした場合は、次のセクションに進みます。

1.  フリート管理のサンプルを <https://github.com/Microsoft/FMLab> からダウンロードし、**C:\\** に保存してから解凍します。
2.  Visual Studio の **Finance and Operations** メニューで、**プロジェクトのインポート**をクリックします。
3.  **プロジェクトのインポート** ウィンドウで、**ファイル名**テキスト ボックスの隣にある、省略記号ボタンをクリックします。
4.  **インポートするファイルの選択**ウィンドウで、**C:\FMLab** を参照して **FMTutorialDataModel.axpp** をクリックしてから**開く**をクリックします。
5.  プロジェクト ファイルの場所テキスト ボックスに、**C:\FMLab** と入力します。
6.  **要素の上書き** オプションをオンにし、**OK** をクリックします。

### <a name="import-transactional-data"></a>トランザクション データのインポート

1.  Visual Studio で、**FMTutorial** プロジェクトを開きます。 **ファイル**メニューで、**開く**をポイントし、**プロジェクト/ソリューション**をクリックします。
2.  **プロジェクトを開く**ダイアログ ボックスで、C:\FMLab\FMTutorial を参照してから FMTutorial をクリックします。 **開く** をクリックします。 **FMTutorial** プロジェクトが**ソリューション エクスプローラー**に表示されます。
3.  フリート管理チュートリアルのデータを読み込むには、FMTDataHelper クラスを使用します。 **ソリューション エクスプローラー**の FMTutorial プロジェクトで、**クラス**を展開して、**FMTDataHelper** を右クリックしてから、**スタートアップ オブジェクトとして設定**をクリックします。
4.  **ビルド**メニューから、**ソリューションの再構築**をクリックします。 インポートされたアーティファクトのタイムスタンプを更新するには、リビルドを使用します。 **出力** ウィンドウでビルドの進行状況を表示できます。
5.  **Ctrl+F5** キーを押してプロジェクトを実行し、データを読み込みます。

## <a name="add-a-tile-to-the-tutorial-workspace"></a>チュートリアル ワークスペースへのタイルの追加
最初に、FMTClerkWorkspace のフォームに新しいタイルを追加します。

1.  **ソリューション エクスプローラー**で、**フォーム**を展開してから、**FMTClerkWorkspace** をダブルクリックします。
2.  デザイナーで、**PanoramaBody** を展開します。
3.  **TileContainer** を右クリックし、**新規** &gt; **ボタンを並べて表示** をクリックします。
4.  新しいタイル ボタンの次のプロパティを指定します。

    | **プロパティ** | **値**           |
    |--------------|---------------------|
    | テキスト         | タイルをテスト           |
    | タイル         | FMTAllCustomersTile |

    これにより、既存の**すべての顧客**タイルの複製が作成されます。
5.  **ソリューション エクスプローラー**で、**フォーム** &gt; **FMTClerkWorkspace** とクリックし、右クリックしてから**スタートアップ オブジェクトとして設定**を選択します。 スタートアップ オブジェクトを設定することは、手順 7 で Ctrl + F5 キーを押すと Visual Studio が起動するために必要です。 起動オブジェクトとしてこのフォームを設定すると、Ctrl + F5 キーを押した後に、進行中のフリート管理係ワークスペースが表示されます。 後で再度このフォームを詳細にプレビュー表示します。
6.  **FMTutorial** を右クリックし、**再ビルド** をクリックします。
7.  **Ctrl+F5** キーを押してプロジェクトを実行します。

プロジェクトをビルドして実行すると、フリート管理係ワークスペースが起動します。 作成した **テスト タイル** という名前の新しいタイルは、タイルのセットの最後にある、ワークスペースの最初のセクションに含まれます。 

[![Nav1](./media/nav1.png)](./media/nav1.png) 

> [!NOTE]
> タイルがクリックされたとき、どこにも移動しません。 これを有効にするには、**ソリューション エクスプローラー** の**タイル**の下にあるメニュー項目名を FMTAllCustomersTile に定義します。

## <a name="add-a-new-workspace-to-the-navigation-pane"></a>ナビゲーション ウィンドウへの新しいワークスペースの追加
次に、FMTClerkWorkspace フォームをナビゲーション ウィンドウに追加します。 これを次の 2 つの場所で実行します。

-   **すべてのワークスペース** リスト。
-   ワークスペースを示すメニュー構造を含む領域のリストにある新しい項目。

### <a name="create-a-menu-item-that-points-to-the-fmtclerkworkspace-workspace"></a>FMTClerkWorkspace ワークスペースを指すメニュー項目を作成します

1.  **FMTutorial** を右クリックして **追加** をポイントしてから **新しい項目** をクリックします。
2.  **AX アーティファクト** &gt; **ユーザー インターフェイス** &gt; **表示メニュー項目**とクリックします。 **名前**プロパティで、**FMTClerkWorkspace** と入力します。
3.  **追加** をクリックします。
4.  新しいメニュー項目の次のプロパティを指定します。

    | **プロパティ** | **値**                       |
    |--------------|---------------------------------|
    | ラベル        | 予約管理チュートリアル |
    | オブジェクト       | FMTClerkWorkspace               |

### <a name="create-a-tile-that-points-to-the-fmtclerkworkspace-workspace-menu-item"></a>FMTClerkWorkspace ワークスペース メニュー項目をポイントするタイルを作成する

1.  **FMTutorial** を右クリックして **追加** をポイントしてから **新しい項目** をクリックします。
2.  **AX アーティファクト** &gt; **ユーザー インターフェイス** &gt; **タイル**とクリックします。 **名前**プロパティで、**FMTClerkWorkspace** と入力します。
3.  **追加** をクリックします。
4.  新しいタイルの次のプロパティを指定します。

    | **プロパティ** | **値**         |
    |--------------|-------------------|
    | MenuItemName | FMTClerkWorkspace |

### <a name="add-a-menu-extension-for-the-navigation-pane"></a>ナビゲーション ウィンドウのメニューの拡張機能を追加します。

1.  **アプリケーション エクスプローラー**で、**ユーザー インターフェイス** &gt; **メニュー**とクリックし、**NavPaneMenu** を右クリックしてから**拡張機能を作成**をクリックします。
2.  **ソリューション エクスプローラー**で、**NavPaneMenu.Extension** をダブルクリックします。
3.  デザイナーで、**NavPaneMenu.Extension** を右クリックし、**新規**をポイントしてから**サブメニュー**をクリックします。
4.  新しいサブメニューを選択します。 **名前**プロパティで、**NavPaneMenuFleetTutorial** と入力します。
5.  **ソリューション エクスプローラー**または**アプリケーション エクスプローラー**で、**FMTClerkWorkspace** タイルを探し、新しく作成されたサブメニューにドラッグします。 **保存** をクリックします。
6.  **FMTutorial** を右クリックし、**再ビルド** をクリックします。
7.  **Ctrl+F5** キーを押してプロジェクトを実行します。 プロジェクトをビルドして実行すると、ナビゲーション ウィンドウに新しいワークスペースへのリンクが含まれます。 アプリケーション ウィンドウの右上にある、ナビゲーション ウィンドウのボタン (3 つの明細行) をクリックして、ナビゲーション ウィンドウを開きます。 

    [![Nav2](./media/nav2.png)](./media/nav2.png)

8.  ナビゲーション ウィンドウを開いたら、**すべてのワークスペース** を選択し、それを開いた後、一覧を下方向にスクロールします。 以下の新しい予約管理チュートリアル ワークスペースが一覧に表示されます。 

    [![Nav3](./media/nav3.png)](./media/nav3.png)

### <a name="add-the-form-to-the-main-menu-structure"></a>メイン メニュー構造へのフォームの追加

ここで、チュートリアル ワークスペースを示すタイルを含む新しいメイン メニュー セクションを追加します。 次に、このセクションの同じフォームにリンクを追加します。 これは、非ワークスペースのフォーム リンクの外観を示します。

1.  Visual Studio の**ソリューション エクスプローラー**で、**FMTutorial** を右クリックして**追加**をポイントしてから**新しい項目**をクリックします。
2.  **AX アーティファクト** &gt; **ユーザー インターフェイス** &gt; **メニュー**とクリックします。 **名前**プロパティで、**FleetManagementTutorial** と入力します。
3.  **追加** をクリックします。
4.  **ソリューション エクスプローラー**で、新しいメニュー **FleetManagementTutorial** をまだ開いていない場合はダブルクリックします。
5.  プロパティ リストで、**ラベル** プロパティを**フリート管理のチュートリアル**に設定します。
6.  デザイナーで、**FleetManagementTutorial** を右クリックして、**新規** &gt; **サブメニュー**をクリックします。
7.  新しいサブメニューの次のプロパティを指定します。

    | **プロパティ** | **値**  |
    |--------------|------------|
    | 氏名         | ワークスペース |
    | ラベル        | ワークスペース |

8.  **ソリューション エクスプローラー**または**アプリケーション エクスプローラー**で、**FMTClerkWorkspace** 表示メニュー項目を探し、新しい**ワークスペース** サブメニューにドラッグします。
9.  デザイナーで、**FleetManagementTutorial** を右クリックしてから、**新規** &gt; **サブメニュー**をクリックします。
10. 新しいサブメニューの次のプロパティを指定します。

    | **プロパティ** | **値** |
    |--------------|-----------|
    | 氏名         | 共通    |
    | ラベル        | 共通    |

11. **ソリューション エクスプローラー**または**アプリケーション エクスプローラー**で、**FMTClerkWorkspace** 表示メニュー項目を探し、新しい**共通**サブメニューにドラッグします。
12. **アプリケーション エクスプローラー**で、**ユーザー インターフェイス** &gt; **メニュー** &gt; **MainMenu** とクリックします。 **MainMenu** を右クリックし、**拡張子の作成** をクリックします。
13. **ソリューション エクスプローラー**で新しい拡張機能を探して開きます。 **MainMenu.Extension** を選択し、ダブルクリックして開きます。
14. デザイナーで、**MainMenu.Extension** を右クリックし、**新規**をポイントしてから**メニュー参照**をクリックします。
15. 新しいメニュー参照の次のプロパティを指定します。

    | **プロパティ** | **値**               |
    |--------------|-------------------------|
    | 氏名         | FleetManagementTutorial |
    | メニュー名    | FleetManagementTutorial |

16. **保存** をクリックします。
17. **FMTutorial** を右クリックし、**ビルド** をクリックします。
18. **Ctrl+F5** キーを押してプロジェクトを実行します。
19. 変更したメイン メニューのセクションに移動します。 ナビゲーション ウィンドウを開いて、新しいトップレベルの**フリート管理のチュートリアル**メニューが表示されるまでスクロールします。 **Ctrl+F5** を押して、ブラウザー キャッシュをクリアすることが必要な場合があります。 

    [![Nav4](./media/nav4.png)](./media/nav4.png)

20. そのサブメニューを展開するには、**フリート管理のチュートリアル** &gt; **ワークスペース**とクリックします。 ナビゲーション ウィンドウは、次のようになります。 

    [![Nav5](./media/nav5.png)](./media/nav5.png) 

    **一般的な** サブメニューをクリックすると、モデル化されているメニュー項目が表示されます。 これらのリンクのいずれかをクリックして、参照を正しく設定したか確認することができます。 参照を正しく設定した場合は、作成中のチュートリアル ワークスペースをクリックすると、開きます。




