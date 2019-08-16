---
title: ER コンフィギュレーションを使用したアプリケーション メタデータへのアクセス
description: このトピックの手順では、Regulatory Configuration Service (RCS) のユーザーが Finance and Operations のメタデータを使用して、新しい電子申告 (ER) モデルのマッピングをデザインする方法について説明します。
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b95b41b27cecd4c71ed7646f329cf5736a01b561
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/04/2019
ms.locfileid: "1727032"
---
# <a name="access-application-metadata-by-using-er-configuration"></a>ER コンフィギュレーションを使用したアプリケーション メタデータへのアクセス

[!include [task guide banner](../../includes/task-guide-banner.md)]

次の手順では、システム管理者または電子申告開発者ロールの Regulatory configuration service (RCS) ユーザーが、Dynamics 365 for Finance and Operations アプリケーションのメタデータを使用して、電子申告 (ER) モデルのマッピングをデザインする方法を説明します。 アプリケーション メタデータには、対外貿易トランザクションにアクセスするためのサンプル メタデータ セットを含む ER メタデータ コンフィギュレーションを使用してアクセスされます。 これらの手順を完了するには、RCS で最初に[コンフィギュレーション プロバイダーを作成して有効とマークする](er-configuration-provider-mark-it-active-2016-11.md)のトピックにある手順を実行する必要があります。 次に、Finance and Operations で、トピック [(ER) RCS で使用するアプリケーション メタデータの準備](prepare-application-metadata-rcs.md)の手順を完了します。

## <a name="prerequisites"></a>必要条件
1. **すべてのワークスペース** > **電子申告**の順に移動します。 
2. サンプル会社 Litware, Inc. のコンフィギュレーション プロバイダーが使用可能であり、**アクティブ**としてマークされていることを確認します。 このコンフィギュレーション プロバイダーが表示されない場合は、[コンフィギュレーション プロバイダーを作成し、有効としてマークする](er-configuration-provider-mark-it-active-2016-11.md) という手順のステップを完了する必要があります。 

## <a name="import-metadata-configuration"></a>メタデータ コンフィギュレーションのインポート 
1. **メタデータ コンフィギュレーション**をクリックします。 
2. Finance and Operations アプリケーションからメタデータを含む ER メタデータ コンフィギュレーションをインポートします。これは対外貿易ビジネスのための電子申告を生成するようコンフィギュレーションされています。 この ER メタデータ コンフィギュレーションは、[(ER) RCS で使用されるアプリケーション メタデータを準備する](prepare-application-metadata-rcs.md) の手順が完了した時に、XML ファイルとしてエクスポートされました。 
3. **交換**をクリックします。 
4. **XML ファイルから読み込む**をクリックします。 
5. **参照**をクリックし、「対外貿易 metadata.xml」ファイルを選択します。 
6. **OK**をクリックします。 
7. ページを閉じます。 

## <a name="create-data-model-configuration"></a>データ モデル コンフィギュレーションの作成
1. **コンフィギュレーションをレポートする**をクリックします。 
2. **コンフィギュレーションの作成**をクリックして、ドロップ ダイアログを開きます。 
3. **名前**フィールドに、「対外貿易モデル」と入力します。 
4. **コンフィギュレーションの作成**をクリックします。 
5. **デザイナー** をクリックします。 
6. **新規**をクリックすると、ドロップ ダイアログが開きます。 
7. **名称**のフィールドに、「Root」と入力します。 
8. **追加**をクリックします。 
9. **新規**をクリックすると、ドロップ ダイアログが開きます。 
10. **名前**フィールドに、「トランザクション」と入力します。 
11. **品目タイプ** フィールドで、**レコード リスト**を選択します。 
12. **追加**をクリックします。 
13. **新規**をクリックすると、ドロップ ダイアログが開きます。 
14. **名前**フィールドに、「コモディティ コード」と入力します。 
15. **品目タイプ**フィールドで、**文字列**を選択します。 
16. **追加**をクリックします。 
17. **新規**をクリックすると、ドロップ ダイアログが開きます。 
18. **名前**フィールドに、「請求金額」と入力します。 
19. **品目タイプ** フィールドで、**実数**を選択します。 
20. **追加**をクリックします。 
21. **新規**をクリックすると、ドロップ ダイアログが開きます。 
22. **名前**フィールドに、「日付」と入力します。 
23. **品目タイプ** フィールドで、**日付**を選択します。 
24. **追加**をクリックします。 
25. **ルート参照**をクリックします。 
26. **OK**をクリックします。 
27. **保存**をクリックします。 
28. ページを閉じます。 
29. **状態の変更**をクリックします。 
30. **完了**をクリックします。 
31. **OK**をクリックします。 

## <a name="create-model-mapping-configuration"></a>モデル マッピング コンフィギュレーションの作成 
1. **コンフィギュレーションの作成**をクリックして、ドロップ ダイアログを開きます。 
2. **新規**フィールドに、「データ モデル対外貿易モデルに基づいたモデル マッピング」と入力します。 
3. **名前**フィールドに、「対外貿易マッピング」と入力します。 
4. **コンフィギュレーションの作成**をクリックします。 
5. **前提条件**セクションを展開します。 
6. **編集** をクリックします。 
7. **新規** をクリックします。 
8. 一覧で、選択された行をマークします。 
9. **必要条件のコンポーネント タイプ** フィールドで、**コンフィギュレーション**を選択します。 
10. **対外貿易メタデータ** コンフィギュレーションを選択します。 
11. **保存**をクリックします。 
12. 「対外貿易メタデータ」 コンフィギュレーションのバージョン 1 への参照を追加しました。 このコンフィギュレーションのアプリケーション メタデータは、このモデル マッピングをデザインするときに提供されます。 
13. ページを閉じます。 
14. **デザイナー** をクリックします。 
15. **デザイナー** をクリックします。 
16. ツリーで、**Dynamics 365 for Operations\ テーブル レコード**を選択します。 
17. **ルートの追加**をクリックします。 
18. **名前**フィールドに、「イントラスタット」と入力します。 
19. **イントラスタット** テーブル レコードを選択します。 
20. **OK**をクリックします。 

> [!NOTE]
> 現在使用されているメタデータ セットに追加されたテーブルは 2 つだけなので、2 つのテーブルのみが提供されています。 

21. **バインド**をクリックします。 
22. ツリーで、**イントラスタット**を展開します。 
23. ツリーで、**イントラスタット \AmountMST** を選択します。 
24. ツリーで、**トランザクション = イントラスタット**を展開します。 
25. ツリーで、**トランザクション = イントラスタット \Invoiced amount** を選択します。 
26. **バインド**をクリックします。 
27. ツリーで、**イントラスタット \TransDate** を選択します。 
28. ツリーで、**トランザクション = イントラスタット \Date** を選択します。 
29. **バインド**をクリックします。 
30. ツリーで、**イントラスタット\>リレーション**を展開します。 
31. ツリーで、**イントラスタット\>リレーション\イントラスタットコモディティ**を展開します。 
32. ツリーで、**イントラスタット\>リレーション\イントラスタットコモディティ\コード**を選択します。 
33. ツリーで、**トランザクション = イントラスタット\コモディティ コード**を選択します。 
34. **バインド**をクリックします。 
35. **検証**をクリックします。 

> [!NOTE]
> 参照された ER メタデータ コンフィギュレーションのアプリケーション メタデータの詳細を使用して説明されているデータ ソース項目によって、データ モデルの要素が正常にバインドされました。 
36. **保存**をクリックします。 
37. ページを閉じます。 
38. ページを閉じます。 
39. 既存のメタデータ セットを拡張する必要がある場合は、Finance and Operations で行うことができます。 その後、Finance and Operation から新しい完了版の ER メタデータ コンフィギュレーションをエクスポートし、それを RCS にインポートして、インポートされたメタデータ コンフィギュレーションの新しいバージョンを参照してコンフィギュレーション済みモデル マッピングの前提条件を更新することができます。 

> [!NOTE]
> アプリケーション メタデータに関する情報を取得するこの方法は、ローカルに展開されたアプリケーションで利用できる唯一の方法です (ローカル ビジネス データ (LBD)、またはオンプレミスの場合、配置モデルは Dynamics 365 for Finance and Operations に使用されます)。
        