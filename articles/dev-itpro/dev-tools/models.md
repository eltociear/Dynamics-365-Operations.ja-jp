---
title: "モデルとパッケージ"
description: "この記事では、モデルとパッケージの概念について説明します。 また、新しいモデルを作成するために Microsoft Visual Studio の開発ツールを使用する方法、既存のモデルのパラメーターを更新する方法、およびモデル間の依存関係を表示する方法についても説明します。"
author: robadawy
manager: AnnBe
ms.date: 05/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 83351
ms.assetid: 66a32ee2-8c4f-4ae5-b022-ad1bb4f97e59
ms.search.region: Global
ms.author: robadawy
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: b96446b19fe9559b3f04fc7451ade16140e8f679
ms.contentlocale: ja-jp
ms.lasthandoff: 08/09/2018

---

# <a name="models-and-packages"></a>モデルとパッケージ

[!include [banner](../includes/banner.md)]

この記事では、モデルとパッケージの概念について説明します。 また、新しいモデルを作成するために Microsoft Visual Studio の開発ツールを使用する方法、既存のモデルのパラメーターを更新する方法、およびモデル間の依存関係を表示する方法についても説明します。

モデル ストアのモデルを操作するには、Microsoft Visual Studio のツールを使用します。 新しいモデルを作成、および既存のモデルのパラメータを変更することができます。

## <a name="conceptual-overview"></a>概念に関する概要
モデルは、通常、配布可能なソフトウェア ソリューションを構成するメタデータとソース ファイルなどの要素のグループであり、既存のソリューションのカスタマイズを含みます。 モデルは、倉庫管理モデルやプロジェクト会計モデルなどのデザイン時概念です。 モデルは、常に 1 つのパッケージに属しています。 パッケージは、1 つまたは複数のモデルの配置およびコンパイル単位です。 これには、モデル メタデータ、バイナリ、およびその他の関連するリソースが含まれます。 1 つ以上のパッケージは、ランタイム環境の配置に使用する車両の配置可能パッケージにパッケージすることができます。

<!--The [Packages, models, and projects](https://mix.office.com/watch/ies6lyit6773) Office Mix describes models and packages and how they relate to each other.-->

## <a name="creating-a-new-model"></a>新しいモデルを作成しています
**モデルの作成** ウィザードを使用して、新しいモデルを作成します。 このウィザードには **Dynamics 365** メニューの **モデル管理** からアクセスすることができます。 モデルは 2 種類作成することができます。

-   **固有のパッケージに配置されているモデル** - このタイプのモデルを使用して、新しいモデル要素を作成し、参照モデルのメタデータとビジネス ロジックを拡張することができます。 このウィザードでは、参照モデルを選択できます。 このタイプのモデルは、独自のアセンブリとバイナリにコンパイルされるため、一般的なアップグレード、展開、アプリケーション ライフサイクル管理のコストが削減され、簡素化されます。
-   **既存のパッケージの一部であるモデル** - このタイプのモデルを使用して、ソース コードおよびメタデータのオーバーレイなどの高度なカスタマイズを実行することができます。

**モデルの作成** ウィザードが完了したとき、新しいプロジェクトの作成を選択した場合、名前とその場所を指定するための入力を要求されます。

## <a name="updating-model-parameters"></a>モード パラメーターの更新
モデルのパラメーターを変更する必要がある場合は、**更新モデル パラメーター** ダイアログ ボックスを使用できます。

1.  **Dynamics 365** メニューで、**モデル管理**をポイントし、**モデルのパラメーターの更新**をクリックします。
2.  **モデル名**フィールドで、パラメーターを更新するモデルを選択します。
3.  必要に応じてパラメーターを更新します。
4.  **次へ** をクリックします。
5.  変更が必要な場合は、現在のモデルの依存関係情報を更新します。
6.  **次へ** をクリックします。 モデルの要約情報が表示されます。
7.  **完了** をクリックします。

更新されたモデル パラメーターは、Visual Studio を再起動した後にのみ有効になります。

## <a name="viewing-package-dependencies"></a>パッケージの依存関係の表示
どのパッケージとそのモデルに他のパッケージへの依存関係があるかを示す、グラフィック表現を作成することができます。 **Dynamics 365** メニューで、**モデル管理**をポイントし、**パッケージの依存関係の表示**をクリックします。 現在のパッケージとそのモデルについて、有向グラフ マークアップ言語 (DGML) 図が生成されます。 この図は、それぞれがパッケージを表す相互依存ノードの集合です。 各ノードでは、パッケージに属するすべてのモデルを表示します。 追加のツールは、強化または図を簡略化できます。 たとえば、コメントを追加したり、ノードをあちこちに移動したり、またはノードを削除できます。 また、次の手順で、単一モデルのパッケージ依存関係を表示することもできます。

1.  アプリケーション エクスプローラーがモデル ビューになっていることを確認します。AOT ノードを右クリックし、モデル ビューを選択します。
2.  任意のモデルを右クリックし、**パッケージの依存関係を表示** > **送信参照を表示** を選択します。

選択したモデルが依存するすべてのパッケージのグラフが生成されます。 

![ビューの相互関係](./media/viewdependencies2.png) 

![ディレクトリ依存関係](./media/directorydependencies.png)

## <a name="deleting-a-model"></a>モデルの削除
開発またはテスト環境では、次の手順に従ってモデルを削除します。

次の手順では、ローカル モデル ストア フォルダーが C:\AOSService\PackagesLocalDirectory であり、モデルの名前が MyModel1 であると想定しています。

モデルがそれ自身のパッケージに属している場合 (たとえば: パッケージに他のモデルがない拡張機能パッケージ):
1. 次のサービスを停止: AOS Web サービスおよびバッチ管理サービス
2. パッケージ フォルダー  C:\AOSService\PackagesLocalDirectory\MyModel1 を削除します
3. 手順 1 からサービスを再開
4. Visual Studio を実行している場合、モデルを更新します (Visual Studio > Dynamics 365 > モデル管理 > モデルの更新)
5. Visual Studio で、完全なデータベース同期を実行します (Visual Studio > Dynamics 365 > データベースの同期...)

モデルが、複数のモデルを持つパッケージに属している場合 (MyModel1 がアプリケーション スイートにオーバーレイする場合など):
1. 次のサービスを停止: AOS Web サービスおよびバッチ管理サービス
2. モデル フォルダー  C:\AOSService\PackagesLocalDirectory\<PackageName>\MyModel1 (In this example PackageName=ApplicationSuite) を削除します
3. 手順 1 からサービスを再開
4. Visual Studio で、モデルを更新します (Visual Studio > Dynamics 365 > モデル管理 > モデルの更新)。
5. Visual Studio で、削除したモデルが属しているパッケージをビルドします (Visual Studio > Dynamics 365 > モデルをビルド...)
6. Visual Studio で、完全なデータベース同期を実行します (Visual Studio > Dynamics 365 > データベースの同期...)

## <a name="additional-resources"></a>その他のリソース

[開発ツールの概要](development-tools-overview.md)

[開発者ホーム ページ](developer-home-page.md)

[モデルの配分: モデル ファイルをエクスポートおよびインポートする方法](models-export-import.md)



