---
title: アプリケーション データを含むドキュメントを生成するための形式の変更
description: この手順のステップを完了するには、まず「ER アプリケーション データ更新と共にドキュメントを生成する (パート 3 - モデルとマッピングの変更)」の手順を完了する必要があります。
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bbed62c80c14e7cfe96d38d43a5db39b0469d939
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184925"
---
# <a name="modify-formats-to-generate-documents-that-have-application-data"></a>アプリケーション データを含むドキュメントを生成するための形式の変更

[!include [task guide banner](../../includes/task-guide-banner.md)]

この手順のステップを完了するには、まず「ER アプリケーション データ更新と共にドキュメントを生成する (パート 3: モデルとマッピングの変更)」の手順を完了する必要があります。

この手順のステップでは、電子ドキュメントを生成してアプリケーション データを更新するために電子申告 (ER) コンフィギュレーションを設計する方法について説明します。 この手順では、ER コンフィギュレーションを変更し、それを使用して電子ドキュメントを生成するだけでなく、アプリケーション データの更新も行います。 この手順は、「システム管理者」または「電子レポート開発者」ロールが割り当てられているユーザー用に作成されています。 これらのステップは、DEMF データ セットを使用して完了することができます。


## <a name="modify-format-to-collect-details-of-reporting"></a>レポートの詳細を収集するために形式を変更する
1. [組織管理] > [電子申告] > [コンフィギュレーション] に移動します。
2. ツリーで、「イントラスタット (モデル)」を展開します。
3. ツリーで、「イントラスタット (モデル)\イントラスタット (形式)」を選択します。
4. [デザイナー] をクリックします。
5. ツリーで、「ファイル」を展開します。
6. ツリーで、「ファイル\申告」を展開します。
7. ツリーで、「ファイル\申告\データ」を選択します。
8. [多様性] フィールドで、「1 つ、多数」を選択します。
    * この形式要素をコンフィギュレーションして、イントラスタット レポート プロセスの詳細をアーカイブします。 この項目は、アーカイブのヘッダー レコードを表します。  
9. ツリーで、「ファイル\申告\データ」を展開します。
10. ツリーで、「ファイル\申告\データ\品目」を選択します。
11. [多様性] フィールドで、「ゼロ、多数」を選択します。
    * この形式要素をコンフィギュレーションして、イントラスタット レポート プロセスの詳細をアーカイブします。 この項目は、アーカイブされた明細行のリストを表します。  
12. ツリーで、「ファイル\申告\データ\品目」を展開します。
13. ツリーで、「ファイル\申告\データ\品目\Dim1」を選択します。
14. [除外] フィールドで [はい] を選択します。
    * このデータはアーカイブしないので、この形式要素はイントラスタット レポートの詳細のデータ ソースから除外できます。  
15. ツリーで、「ファイル\申告\データ\品目\Dim1」を展開します。
16. ツリーで、「ファイル\申告\データ\品目\Dim1\プロパティ」を選択します。
17. [除外] フィールドで [はい] を選択します。
18. ツリーで、「ファイル\申告\データ\品目\Dim1\日付」を選択します。
19. [除外] フィールドで [はい] を選択します。
20. ツリーで、「ファイル\申告\データ\品目\Dim2」を選択します。
21. [除外] フィールドで [はい] を選択します。
22. ツリーで、「ファイル\申告\データ\品目\Dim2」を展開します。
23. ツリーで、「ファイル\申告\データ\品目\Dim2\プロパティ」を選択します。
24. [除外] フィールドで [はい] を選択します。
25. ツリーで、「ファイル\申告\データ\品目\Dim2\コード」を選択します。
26. [除外] フィールドで [はい] を選択します。
27. ツリーで、「ファイル\申告\データ\品目\Dim3」を選択します。
    * 複数の形式要素に同じ名前を付けることができます。 例: Dim。イントラスタット レポートの詳細をアーカイブするためにこの形式をデータ ソースとして使用するときには明示的に認識できないため、これらの形式要素に代替名を定義する必要があります。   
28. [名前] フィールドに、「$Amount」と入力します。
    * 量  
29. [多様性] フィールドで、「1 つのみ」を選択します。
30. ツリーで、「ファイル\申告\データ\品目\Dim4」を選択します。
31. [名前] フィールドに、「Item」と入力します。
    * 項目  
32. [多様性] フィールドで、「1 つのみ」を選択します。
    * デザイン形式要素に加えて、以下のイントラスタット レポートの詳細をアーカイブする必要があります。レポートされる各商品品目の一意のレコード ID、および生成されるファイルの名前です。 このデータはイントラスタット レポートに入力されないため、これらの詳細要素に関連する形式をデータ ソース項目として追加する必要があります。  
33. ツリーで、「ファイル\申告\データ」を選択します。
34. [追加] をクリックしてドロップ ダイアログを開きます。
35. ツリーで、「データ ソース\品目」を選択します。
36. [名称] フィールドで、「ファイル名」を入力します。
    * ファイル名  
37. [データ タイプ] フィールドで、「文字列」を選択します。
38. [OK] をクリックします。
39. ツリーで、「ファイル\申告\データ\品目」を選択します。
40. [品目の追加] をクリックします。
41. [名前] フィールドに、「商品 rec id」と入力します。
    * 商品 rec id  
42. [データ タイプ] フィールドで、「Int64」を選択します。
43. [OK] をクリックします。
44. [マッピング] タブをクリックします。
45. ツリーで、「ファイル\申告\データ\ファイル名」を選択します。
46. [バインド] をクリックします。
47. ツリーで、「model」を展開します。
48. ツリーで、「モデル\トランザクション」を展開します。
49. ツリーで、「ファイル\申告\データ\Item = model.Transactions\商品 rec id」を選択します。
50. ツリーで、「モデル\トランザクション\商品 rec id」を選択します。
51. [バインド] をクリックします。
52. [保存] をクリックします。

## <a name="modify-format-to-memorize-details-of-reporting"></a>レポートの詳細を記憶するために形式を変更する
1. [形式をモデルにマップ] をクリックします。
2. [新規] をクリックします。
3. [定義] フィールドで、「アプリケーション データの更新用」ルート項目を入力または選択します。
    * アプリケーション データの更新用  
4. [名前] フィールドで、「データを更新するためのマッピング」と入力します。
    * データを更新するためのマッピング  
5. [保存] をクリックします。
    * このマッピングは、データ モデル内でイントラスタット レポートの詳細をどのように収集するかを定義します。その構造は、選択したルート項目「アプリケーション データの更新用」によって指定されます。 これらの詳細、同じルート項目「アプリケーション データ更新用」のモデル マッピング、および方向「宛先」は、アプリケーション データの更新に使用されます。 アプリケーション データの更新は、送信するイントラスタット レポートの生成後すぐに開始します。 アプリケーション データの更新は実行時にスキップできますが、データ モデルは空でなければならないことに注意してください (空のレコード リストを含みます)。   
6. [デザイナー] をクリックします。
    * 送信するイントラスタット レポート形式が、このモデル マッピングのデータ ソースとしてデフォルトで追加されていることに注意してください。  
    * 選択したモデルのルート項目に基づいてフィルタ処理されたデータ モデルの要素に、設計されたレポートの要素 (データ ソースとして提示) をバインドします。  
7. ツリーで、「アーカイブ ヘッダー」を展開します。
8. ツリーで、「アーカイブ ヘッダー\アーカイブ明細行」を展開します。
9. ツリーで、「形式」を展開します。
10. ツリーで、「形式\Declaration: XML Element(Declaration)」を展開します。
11. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)」を展開します。
12. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)」を展開します。
13. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)」を展開します。
14. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)」を展開します。
15. ツリーで、「アーカイブ ヘッダー\行数」を選択します。
16. [編集] をクリックします。
17. ツリーで、「リスト\COUNT」を選択します。
18. [機能の追加] をクリックします。
19. ツリーで、「形式」を展開します。
20. ツリーで、「形式\Declaration: XML Element(Declaration)」を展開します。
21. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)」を展開します。
22. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)」を選択します。
23. [データ ソースの追加] をクリックします。
24. [フォーミュラ] フィールドに、「COUNT(format.Declaration.Data.Item)」と入力します。
    * COUNT(format.Declaration.Data.Item)  
25. [保存] をクリックします。
26. ページを閉じます。
27. ツリーで、「アーカイブ ヘッダー\ファイル名」を選択します。
28. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\File name: Item String(File name)」を選択します。
29. [バインド] をクリックします。
30. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)\number: String(number)」を選択します。
31. ツリーで、「アーカイブ ヘッダー\アーカイブ明細行\品目番号」を選択します。
32. [バインド] をクリックします。
33. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)\value: Numeric Real(value)」を選択します。
34. ツリーで、「アーカイブ ヘッダー\アーカイブ明細行\金額」を選択します。
35. [バインド] をクリックします。
36. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Commodity rec id: Item Int64(Commodity rec id)」を選択します。
37. ツリーで、「アーカイブ ヘッダー\アーカイブ明細行\商品 rec id」を選択します。
38. [バインド] をクリックします。
39. ツリーで、「アーカイブ ヘッダー\アーカイブ明細行」を選択します。
40. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)」を選択します。
41. [バインド] をクリックします。
42. ツリーで、「アーカイブ ヘッダー」を選択します。
43. ツリーで、「形式\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)」を選択します。
44. [バインド] をクリックします。
45. [保存] をクリックします。
46. ページを閉じます。
47. ページを閉じます。
48. ページを閉じます。

