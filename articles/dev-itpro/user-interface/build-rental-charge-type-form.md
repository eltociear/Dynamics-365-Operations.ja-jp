---
title: "レンタル料金のタイプ フォームの構築"
description: "このラボでは、簡易リストのフォームを作成します。 シンプル リスト フォームでは、参照データまたは 6 つ以下のフィールドが含まれるセカンダリ データを表示できます。 たとえば、作成するフォームは、レンタル料金のタイプについて一覧表示して説明します。"
author: jasongre
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 13671
ms.assetid: 9b4f244c-f058-416c-b3c2-6f4ca29c8db8
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 879eb9f2a63a8514791f74965005ed3e22bc0de7
ms.openlocfilehash: 9216e0379535c0374619f61f7a9953c69a197dc2
ms.contentlocale: ja-jp
ms.lasthandoff: 04/20/2018

---

# <a name="build-the-rental-charge-type-form"></a>レンタル料金のタイプ フォームの構築

[!include [banner](../includes/banner.md)]

このラボでは、簡易リストのフォームを作成します。 シンプル リスト フォームでは、参照データまたは 6 つ以下のフィールドが含まれるセカンダリ データを表示できます。 たとえば、作成するフォームは、レンタル料金のタイプについて一覧表示して説明します。 

<a name="prerequisites"></a>前提条件
-------------

このチュートリアルでは、リモート デスクトップを使用して環境にアクセスし、インスタンスの管理者としてプロビジョニングされる必要があります。 詳細については、「[アクセス インスタンス](../dev-tools/access-instances.md)」を参照してください。

## <a name="overview"></a>概要
フォームを作成するには、既存のフォーム **FmtChargeType** から開始します。 このフォームは、簡易リストのパターンを使用します。 次の図は、**FmtChargeType** フォームと簡易リスト パターンからの必要なコントロールを示しています。 

[![rentalcharge1](./media/rentalcharge1.png)](./media/rentalcharge1.png) 

フォーム パターンに従うことによって、この簡易リストのフォームは、他の簡易リストのフォームと同じ構造とレイアウトを持つようになります。

## <a name="key-concepts"></a>重要な概念
-   パターンを使用して簡易リストのフォームを作成します。
-   テーブルをフォームにバインドします。
-   フォームにコントロールを追加します。
-   Visual Studio とブラウザーを使用してフォームを表示します。

## <a name="setup"></a>段取り
### <a name="import-the-tutorial-project-and-transactional-data"></a>チュートリアル プロジェクトおよびトランザクション データのインポート

Visual Studio を使用して、チュートリアル プロジェクトをインポートします。 チュートリアル プロジェクトには、このチュートリアルを完了するために使用する成果物が含まれています。 Visual Studio を使用して FMTutorial プロジェクトを開き、チュートリアル用のデータを読み込みます。 フリート管理チュートリアルのデータを読み込むために、FMTDataHelper クラスを使用します。 これが作業する最初のチュートリアルである場合は、[アクセス Microsoft インスタンス](../dev-tools/access-instances.md)を確認し、ローカル VM で作業している場合に、管理者ユーザーを提供するかどうかを確認します。

1.  フリート管理のサンプルを <https://github.com/Microsoft/FMLab> からダウンロードし、**C:\\** に保存してから解凍します。
2.  デスクトップで、Visual Studio ショートカットをダブルクリックして、開発環境を開きます。
3.  **Finance and Operations** メニューで、**プロジェクトのインポート**をクリックします。
4.  **プロジェクトのインポート** ウィンドウで、**ファイル名**テキスト ボックスの隣にある、省略記号ボタンをクリックします。
5.  **インポートするファイルの選択**ウィンドウで、C:\FMLab を参照して FMTutorialDataModel.axpp をクリックしてから**開く**をクリックします。
6.  **プロジェクト ファイルの場所**テキスト ボックスに、C:\FMLab と入力します。
7.  **要素の上書き** オプションをオンにし、**現在のソリューション** ラジオ オプションをオンにします。 次の図は、完了した **インポート プロジェクト** ダイアログ ボックスを示しています。 

    [![rentalcharge2](./media/rentalcharge2.png)](./media/rentalcharge2.png)

8.  **OK** をクリックします。
9.  デザイナー**ソリューション エクスプローラー**で、**クラス**を展開して、**FMTutorial** プロジェクトで **FMTDataHelper** を右クリックしてから、**スタートアップ オブジェクトとして設定**をクリックします。
10. **ビルド**メニューで、**ソリューションの再構築**をクリックします。 タイムスタンプに関係なく、プロジェクトのすべてのファイルを確実に作成するには、リビルドを使用します。 **出力** ウィンドウでビルドの進行状況を表示できます。
11. ビルドが完了すると、**Ctrl + F5** を押してプロジェクトを実行します。 ブラウザーが開き、データをインポートするクラスが実行されます。

## <a name="open-the-fmtutorial-project"></a>FMTutorial プロジェクトを開く
Visual Studio を使用して、FMTutorial プロジェクトを開きます。 Visual Studio を開き、FMTutorial プロジェクトが既に読み込まれている場合は、次のセクションに続行することができます。

1.  開発環境がまだ開いていない場合は、デスクトップで開発環境への Visual Studio ショートカットをダブルクリックします。
2.  **ファイル**メニューで、**開く** &gt; **プロジェクト/ソリューション**をクリックします。
3.  **プロジェクトを開く**ダイアログ ボックスで、C:\FmLab\FMTutorial を参照し、**FMTutorial** ソリューションを選択してから**開く**をクリックします。
4.  FMTutorial プロジェクトが**ソリューション エクスプローラー**に表示されます。

## <a name="use-a-template-to-create-the-form"></a>テンプレートを使用してフォームを作成
Visual Studio を使用し、**FmtChargeType** フォームを作成します。 簡易リスト フォームを構築ためのテンプレートを使用します。 また、フォームにデータ ソースを追加し、データ グリッドにフィールドを追加します。

1.  **ソリューション エクスプローラー**で、**FMTutorial** プロジェクトを右クリックして**追加**をポイントしてから**既存の項目**をクリックします。
2.  **既存の品目を追加**ウィンドウで、C:\FmLab を参照し、**AxForm\_FmtChargeType** をクリックしてから**追加**をクリックします。 **ソリューション エクスプローラー**の **FMTutorial** プロジェクトの下に **FmtChargeType** フォームが表示されます。
3.  **ソリューション エクスプローラー**で、**FmtChargeType** をダブルクリックします。 フォーム デザイナーで、フォームを開きます。
4.  フォームのデータ ソースとして **FmtChargeType** テーブルを追加します。 **データ ソース** を右クリックし、**新しいデータ ソース** をクリックします。 データ ソース ノードが追加されます。
5.  前の手順でデータ ソース ノードをクリックします。 **プロパティ** ウィンドウで、次のプロパティに指定された値を設定します。

    | **プロパティ** | **値**|
    |--------------|------|
    | テーブル        | FMTChargeType|
    | 氏名         | FMTChargeType *まず Table プロパティの値を指定してください。このプロパティは、同じ値を使用するよう自動的に更新されます。* |

    次の図は、**FMTChargeType** テーブルを追加した後の **データソース**を示しています。 

    [![rentalcharge3](./media/rentalcharge3.png)](./media/rentalcharge3.png)

6.  フォーム デザイナーで、**デザイン**をクリックします。 **プロパティ** ウィンドウで、次のプロパティに指定された値を設定します。

    | **プロパティ** | **値**                                                                    |
    |--------------|------------------------------------------------------------------------------|
    | キャプション      | レンタル料金のタイプ *これは、フォームの上部に表示されるラベルです。* |
    | データ ソース  | FMTChargeType *フォームのデータ ソースを指定するには、このプロパティを使用します。*   |

7.  フォーム デザイナーで、**デザイン** &gt; **グリッド**をクリックします。
8.  FMTChargeType データ ソースを簡易リスト フォームで表示されているグリッドにバインドします。 **プロパティ** ウィンドウの**データ ソース**に、**FMTChargeType** を入力します。
9.  グリッドにフィールドを追加する前に、データ ソースを指定する必要があります。 次に、データ ソースからのフィールドを使用して、グリッドに列を追加することができます。 グリッドにデータ ソースから 2 つのフォームを追加します。 追加するフィールドは、簡易リスト フォームの列として表示されます。 左側のウィンドウで、FMTChargeType データ ソース**フィールド**ノードを展開します。 **Ctrl** を押し、次のフィールドをクリックします。
    -   ChargeType
    -   説明

10. 選択したフィールドを右ウィンドウの**デザイン** &gt; **グリッド**にドラッグします。 次の図は、グリッド ノードが展開され、2 つのフィールドが追加された後のグリッドを示しています。 

    [![rentalcharge4](./media/rentalcharge4.png)](./media/rentalcharge4.png)

11. フォーム デザイナーで、**デザイン &gt; CustomFilterGroup &gt; QuickFilter** をクリックします。
12. **プロパティ** ウィンドウで、**TargetControl** をクリックしてから**グリッド**を選択して **QuickFilter** コントロールをフォームのグリッドにバインドします。
13. **ファイル** &gt; **保存** **FmtChargeType** とクリックします。

## <a name="view-the-form"></a>フォームの表示
Visual Studio を使用し、**FmtChargeType** フォームをビルドして実行します。

1.  **ソリューション エクスプローラー**で、**FmtChargeType** フォームを右クリックしてから、**スタートアップ オブジェクトとして設定**をクリックします。
2.  Ctrl+F5 キーを押して、フォームをビルドおよび実行します。
3.  Internet Explorerで、フォームを開きます。
4.  レンタル料金タイプを追加するには、フォームの上部にあるアクション ペインで **新規** をクリックします。 次の情報を追加します。

    | **レンタル料金のタイプ** | **説明** |
    |------------------------|-----------------|
    | クリーニング               | クリーニング代    |

5.  アクション ウィンドウで、**保存**をクリックします。
6.  ブラウザーを更新して、一覧に新しいレコードを表示します。 次の図は、フォームの外観を示しています。

    [![rentalcharge5](./media/rentalcharge5.png)](./media/rentalcharge5.png)

7.  表示モードでフォームを開きます。 アクション ウィンドウの**編集**をクリックして、フォームを編集モードに切り替えます。 表示モードに戻るには、**オプション** をクリックしてから **読み取りモード** をクリックします。




