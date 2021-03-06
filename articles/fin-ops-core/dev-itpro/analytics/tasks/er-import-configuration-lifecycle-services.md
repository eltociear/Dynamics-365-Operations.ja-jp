---
title: Lifecycle Services からのコンフィギュレーションの ER インポート
description: 次の手順では、システム管理者または電子申告開発者の役割のユーザーが、新しいバージョンの電子申告 (ER) コンフィギュレーションを Microsoft Lifecycle Services (LCS) からインポートする方法を説明します。
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable,  ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0830707885e8ed52581aa789df0279d78e3a9c10
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184833"
---
# <a name="er-import-a-configuration-from-lifecycle-services"></a>Lifecycle Services からのコンフィギュレーションの ER インポート

[!include [task guide banner](../../includes/task-guide-banner.md)]

次の手順では、システム管理者または電子申告開発者の役割のユーザーが、新しいバージョンの電子申告 (ER) コンフィギュレーションを Microsoft Lifecycle Services (LCS) からインポートする方法を説明します。

この例では、ER コンフィギュレーションの必要なバージョンを選択し、サンプル会社の Litware, Inc. 用にインポートします。ER コンフィギュレーションは会社間で共有されるため、これらのステップはすべての会社で実行できます。 これらの手順を完了するには、先に「Lifecycle Services への ER コンフィギュレーションのアップロード」の手順の各ステップを完了する必要があります。 LCS へのアクセスは、次の手順の完了にも必要です。

1. [組織管理] > [ワークスペース] > [電子申告] の順に移動します。
2. [コンフィギュレーション] をクリックします。

## <a name="delete-a-shared-version-of-data-model-configuration"></a>データ モデルのコンフィギュレーションの共有バージョンの削除
1. ツリーで、「サンプル モデル コンフィギュレーション」を選択します。
    * サンプル データ モデルのコンフィギュレーションの最初のバージョンが作成され、「Lifecycle Services への ER コンフィギュレーションのアップロード」手順中に LCS に公開されました。 この手順では、ER コンフィギュレーションのこのバージョンを削除します。 サンプル データ モデルのコンフィギュレーションのこのバージョンは、LCS からインポートされます。  
2. 一覧で、目的のレコードを見つけ、選択します。
    * 「共有」状態にあるコンフィギュレーションのバージョンを選択します。 この状態は、コンフィギュレーションが LCS に公開されていることを示します。  
3. [状態の変更] をクリックします。
4. [中止] をクリックします。
    * 選択されたバージョンの状態を「共有」から「中止」に変更し、削除できるようにします。  
5. [OK] をクリックします。
6. 一覧で、目的のレコードを見つけ、選択します。
    * 「中止」状態にあるコンフィギュレーションのバージョンを選択します。  
7. [削除] をクリックします。
8. [はい] をクリックします。
    * 選択されたデータ モデルのコンフィギュレーションのドラフト バージョン 2 だけが使用できることに注意してください。  
9. ページを閉じます。

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a>データ モデルのコンフィギュレーションの共有バージョンを LCS からインポートする
1. 一覧で、選択された行をマークします。
    * 「Litware, Inc.」コンフィギュレーション プロバイダーのリポジトリの一覧を開きます 。  
2. [リポジトリ] をクリックします。
3. [開く] をクリックします。
    * LCS リポジトリを選択し、開きます。  
4. 一覧で、選択された行をマークします。
    * バージョンの一覧の「サンプル モデル コンフィギュレーション」の最初のバージョンを選択します。  
5. [インポート] をクリックします。
6. [はい] をクリックします。
    * LCS から 選択されたバージョンのインポートを確認します。  
    * 情報メッセージ (フォームの上部) により、選択されたバージョンのインポートが正常に完了したことを確認できることに注意してください。  
7. ページを閉じます。
8. ページを閉じます。
9. [コンフィギュレーション] をクリックします。
10. ツリーで、「サンプル モデル コンフィギュレーション」を選択します。
11. 一覧で、目的のレコードを見つけ、選択します。
    * 「共有」状態にあるコンフィギュレーションのバージョンを選択します。  
    * なお、選択されたデータ モデルのコンフィギュレーションの共有バージョン 1 も使用できようになっています。  

