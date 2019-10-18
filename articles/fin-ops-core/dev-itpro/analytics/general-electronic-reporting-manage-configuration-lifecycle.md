---
title: 電子申告 (ER) コンフィギュレーション ライフサイクルの管理
description: このトピックでは、Microsoft Dynamics 365 Finance ソリューションの電子申告 (ER) コンフィギュレーションのライフ サイクルを管理する方法について説明します。
author: NickSelin
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERMappedFormatDesigner, ERModelMappingDesigner, ERModelMappingTable, ERSolutionImport, ERSolutionTable, ERVendorTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58801
ms.assetid: 35ad19ea-185d-4fce-b9cb-f94584b14f75
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6206b3a1ac298af98e4b69b6800b9a493658c4ea
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181292"
---
# <a name="manage-the-electronic-reporting-er-configuration-lifecycle"></a>電子申告 (ER) コンフィギュレーション ライフサイクルの管理

[!include [banner](../includes/banner.md)]

このトピックでは、Microsoft Dynamics 365 Finance の電子申告 (ER) コンフィギュレーションのライフ サイクルを管理する方法について説明します。

## <a name="overview"></a>概要

電子申告 (ER) は、法律の要件および国固有の電子ドキュメントをサポートするエンジンです。 一般に、ER は、各電子ドキュメントに関して次のタスクの実行を想定しています。 詳細については、「[電子申告の概要](general-electronic-reporting.md)」を参照してください。

- 電子ドキュメントのテンプレートを設計します:

    - ドキュメントに表示できるデータのソースを識別します:

        - データ テーブル、データ エンティティ、クラスなど基になるデータ。
        - 実行日および時刻、タイム ゾーンなどプロセス固有のプロパティ。
        - 実行時にエンドユーザーが指定するユーザー入力パラメーター。

    - 必要なドキュメントの要素、および最終ドキュメントの形式を指定するトポロジを定義します。
    - データソース経由でドキュメントの形式コンポーネントにバインドされ、定義されたドキュメント要素に選択したデータ ソースから要求されるデータ フローのコンフィギュレーションを行い、プロセスの制御ロジックを指定します。

- 他のインスタンスでテンプレートが使用できるようにします。

    - 作成したドキュメント テンプレートを ER のコンフィギュレーションに変換し、現在のアプリケーション インスタンスからコンフィギュレーションをローカルまたは LCS に保存できる XML パッケージとしてエクスポートします。
    - ER コンフィギュレーションをアプリケーション ドキュメント テンプレートに変換します。
    - ローカルまたは LCS に保存されている XML パッケージを、現在のインスタンスにインポートします。

- 電子ドキュメント テンプレートをカスタマイズします:

    - LCS からテンプレートを ER コンフィギュレーションとして現在のインスタンスに取り込みます。
    - 基本バージョンを参照しながら、カスタム バージョンの ER コンフィギュレーションを設計します。

- アプリケーションで使用できるように、特定の業務プロセスを含むテンプレートを連結します。

    - 設定をコンフィギュレーションし、プロセスに関連したパラメーターでそのコンフィギュレーションを参照して、アプリケーションで ER コンフィギュレーションの使用を開始できるようにします。 たとえば、特定の買掛金勘定の支払方法の ER コンフィギュレーションを参照して、請求書の処理についての電子支払メッセージを生成します。

- 特定の業務プロセスでテンプレートを使用します:

    - 特定の業務プロセスで ER コンフィギュレーションを実行します。 たとえば、ER コンフィギュレーションを参照する支払方法が選択された場合の請求書の処理についての電子支払メッセージの生成。

## <a name="concepts"></a>概念
次のロールおよび関連活動が、ER コンフィギュレーション ライフサイクルに関連付けられます。

| 役割                                       | 活動                                                      | 説明 |
|--------------------------------------------|-----------------------------------------------------------------|-------------|
| 電子申告機能コンサルタント | ER コンポーネントを作成および管理します (モデル、形式)。           | ER のドメイン固有のデータ モデルを設計し、電子ドキュメントの必須のテンプレートを作成し、それらを結合するビジネス ユーザー。 |
| 電子申告開発者             | データ モデルのマップを作成および管理します。                          | 必要な財務データ ソースを選択し、ER のドメイン固有のデータ モデルに結合する専門家。 |
| 会計監修者                      | ER のコンポーネントを参照するプロセス関連の設定を構成します。 | たとえば、特定の買掛金勘定支払方法で使用して請求書処理用に電子支払メッセージを生成する ER のコンフィギュレーション設定を許可する**会計監修者**のロール。 |
| 買掛金勘定支払係            | 特定の業務プロセスで ER コンポーネントを使用します。                | たとえば、特定の支払方法に対して構成されている ER 形式に基づいて請求書処理用に電子支払のメッセージが生成されるようにするのを許可する**買掛金勘定支払の担当者**ロール。 |

## <a name="er-configuration-development-lifecycle"></a>ER コンフィギュレーションの開発ライフサイクル
ER に関連する次の理由から、個別の Finance and Operations インスタンスとしての開発環境で、ER コンフィギュレーションを作成することをお勧めします:

- **電子申告開発者**ロールまたは**電子申告機能コンサルタント**ロールのユーザーは、テスト目的でコンフィギュレーションを編集し、実行できます。 このシナリオでは、インスタンスで使用する業務データと業績について有害なおそれがあるテーブルおよびクラス メソッドが呼び出されることがあります。
- ER コンフィギュレーションの ER データ ソースとしてのクラスおよびテーブル メソッドの使用は、エントリ ポイントおよび記録された会社の内容によって制限されません。 **電子申告開発者**ロールまたは**電子申告機能コンサルタント**ロールのユーザーは、機密情報にアクセスできます。

開発環境で設計された ER コンフィギュレーションは、コンフィギュレーション評価 (適切な統合プロセス、結果の正確性、パフォーマンス)、およびロールにおけるアクセス権の正確性、職務分掌など品質保証のために、テスト環境にアップロードできます。 ER コンフィギュレーションの交換を可能にする機能は、この目的に使用できます。 最後に、次の図に示すように、認定された ER コンフィギュレーションは、サービスのサブスクライバーと共有する LCS に、あるいは内部で使用する実稼働環境にアップロードできます。

![ER コンフィギュレーション ライフサイクル](./media/ger-configuration-lifecycle.png)

## <a name="additional-resources"></a>その他のリソース

[電子申告の概要](general-electronic-reporting.md)