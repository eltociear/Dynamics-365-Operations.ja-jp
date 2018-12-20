---
title: "外注"
description: "このトピックは、Microsoft Dynamics 365 for Finance and Operations で製造での外注のチュートリアルの構築に役立ちます。"
author: christophernread
manager: AnnBe
ms.date: 09/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: 
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: ade3f4ad9878c9e885afc5034334e41897512871
ms.openlocfilehash: 55b516f928eadea9b7ddbb1192db79f3ab7fa204
ms.contentlocale: ja-jp
ms.lasthandoff: 10/16/2018

---

# <a name="subcontracting"></a>外注

[!include [banner](../includes/banner.md)]

このトピックは、Microsoft Dynamics 365 for Finance and Operations で製造での外注のチュートリアルの構築に役立ちます。 このトピックの最初の部分では、データの設定について説明します。 2 番目の部分では、チュートリアルの手順が示されます。

## <a name="target-audience"></a>対象者

このトピックでは、製造での外注を設定する方法を説明します。 外注活動フローの基本設定を行うには、HQUS 法人で既存のデータを使用します。 HQUS 法人のデモ データには、チュートリアルで手順をサポートするために事前に設定された設定パラメータが含まれます。 チュートリアルではさまざまなロールに対する重要な問題点や課題に取り組んでいますが、システム管理者がその作業を完了できます。

## <a name="demo-scenario"></a>デモのシナリオ

HQUS 法人では、ハイエンド スピーカーが製造されています。 製造プロセス中に、スピーカーは次の 3 つの工程を経由します。

- **事前アセンブリ** – スピーカー キャビネットが組み立てられます。 工程を開始する前に、材料倉庫でキャビネットの材料がピッキングされます。
- **コーティング** – スピーカー キャビネットがアセンブリされた後に、コーティングされる必要があります。 仕入先 (下請業者) によって、この工程が完了します。 事前に組み立てられたスピーカー キャビネットは、2 つの材料と共にコーティング下請業者に出荷されます。
- **仕上げ** – 事前に組み立てられたスピーカー キャビネットが下請業者によりコーティングされた後に、スピーカーの最終的なアセンブリを完了できるよう HQUS 法人に返されます。

次の図は、3 つの工程および消費する材料を示します。

![事前アセンブリ、コーティング、仕上げの工程、および消費する材料](./media/subcontract01_operations-materials.png)

## <a name="setup"></a>段取り

このチュートリアルを開始する前に、データを設定する必要があります。

### <a name="set-up-the-finished-product"></a>完成した製品の設定

この手順では、リリースされた製品 D8100、"コーティングされたキャビネット" の設定について説明します。

1. **製品情報管理 \> 製品 \> リリース済製品**の順に選択し、**リリース済製品の詳細**ページを開きます。
2. クイック フィルター フィールドで、**D8100** を入力して既存のリリース済製品を検索します。

    ![リリース済製品の詳細ページでリリース済製品 D8100 のフィルタ処理](./media/subcontract02_filtering-released-products.png)

3. アクション ウィンドウの、**エンジニア**タブで、**工順**を選択し、**工順**ページを開きます。

    **工順**ページにリリース済製品 D8100 の 8 つの工順バージョンが表示されます。 8 つの工順バージョンは、サイト 1 とサイト 5 で 4 つの工順に分割されます。 工順 000400 は原価計算に使用され、工順 00041 はコーティング工程が内部の工程である場合に使用され、および工順 00042 はコーティング工程が外部の工程である場合に使用されます。

    ![工順ページでの 8 つの工順バージョン](./media/subcontract03_route-page.png)

4. 上部ウィンドウの、**バージョン**グリッドで、サイト **5** の工順バージョン **00042**  を選択します。
5. 下部ウィンドウの、**概要**タブで、グリッドの工順 **20** (**Cbnt CtSc**) を選択します。

    ![選択されたサイト 5 の工順バージョン 00042 の工程 20](./media/subcontract04_route-version-operation.png)

6. **一般**タブを選択します。

    フィールドの**工順タイプ**フィールドが**仕入先**に設定されていることに注意してください。 この値は、工程 20 (Cbnt CtSc) が外注作業であることを示します。

    ![一般タブで、工順タイプ フィールドを仕入先に設定](./media/subcontract05_general-tab.png)

7. **リソース要件**タブを選択します。

    生産計画立案時に適用可能なリソースを検索する機能が使用されます。 工程 20 (Cbnt CtSc) では、リソースに 2 つの機能、**コーティング**および**コーティングされたキャビネット**が必要であることに注意してください。

    ![リソース要件タブのコーティング機能およびコーティングされたキャビネット機能](./media/subcontract06_resource-requirements-tab.png)

8. **適用可能なリソース**を選択して、**適用可能なリソース**ダイアログ ボックスを開きます。

    工程のリソース要件に一致する 3 つのリソースが検索されます。 **仕入先**タイプがリソース 8851 および 8852 であることに注意してください。

    ![適用可能なリソースダイアログ ボックスの 3 つの適用可能なリソース](./media/subcontract07_applicable-resources-dialog.png)

9. **OK** を選択して、**適用可能なリソース**ダイアログ ボックスを閉じ、**工順**ページに戻ります。
10. **工順**ページを閉じ、**リリース済製品の詳細**ページに戻ります。

    ![リリース済製品の詳細ページ](./media/subcontract08_released-product-details-page.png)

11. アクション ウィンドウの、**エンジニア**タブで、**BOM バージョン**を選択し、**BOM バージョン**ページを開きます。

    **BOM バージョン**ページに、リリース済製品 D8100 の 4 つの部品表 (BOM) バージョンが表示されます。 BOM 000040 は原価計算および計画に使用され、BOM 000041 はコーティング工程が社内で行われた場合に使用され、および BOM 000042 と 000043 はコーティング工程を外注した場合に使用されます。

    その品目 S8050 は、**サービス**品目タイプの製品であることに注意してください。 この品目は、外注業務を表します。

    ![BOM バージョン ページの 4 つの BOM バージョン](./media/subcontract09_bom-versions-page.png)

12. **部品表明細行**クイック タブで、**編集**を選択して **BOM 明細行の編集**ダイアログ ボックスを開きます。

    リリース済製品 D8100 の製造オーダーが作成および見積をする場合、発注書は品目 S8050 に対して自動的に生成されます。 この発注書は、製造オーダーにリンクされます。 発注書を自動的に生成するには、**行タイプ**フィールドを**仕入先**に設定し、下請業者の仕入先勘定を選択する必要があります。 この場合、仕入先勘定は US-801です。

    BOM 明細行が、工程番号 (この場合、20) を通じてコーティング工程に関連付けられていることに注意してください。

    ![BOM 明細行のダイアログ ボックスの編集](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a>倉庫作業者のパスワードの作成

携帯デバイスを使用する倉庫作業者のパスワードを定義する必要があります。

1. **倉庫管理 \> 設定 \> 作業者**の順に選択して、**作業ユーザー**ページを開きます。
2. **ユーザー**クイック タブで、ユーザー **51** の行を選択します。

    ![作業ユーザー ページ](./media/subcontract11_work-users-page.png)

3. **パスワードのリセット**を選択します。
4. **パスワード**および**パスワードの確認**フィールドに、**1** を入力します。
5. **パスワードの設定**を選択します。

## <a name="step-by-step-walkthrough"></a>ステップ バイ ステップ チュートリアル

**シナリオおよび背景**

製品 D8100、"コーティングされたキャビネット"に対して 10 個の製造オーダーが作成されます。 キャビネットのコーティングは、仕入先 US-801、完全なコーティング ソリューションで行われる外注された工程です。 製造オーダーは、3 つの工程で構成されます。 最初の工程は、社内工程としてキャビネットが事前に組み立てられます。 原材料倉庫で、事前組み立ての材料がピッキング用にリリースされます。 事前アセンブリを完了した後に、事前に組み立てられたキャビネットがコーティング工程に必要な 2 つの材料と共に、完全なコーティング ソリューションに送られます。 仕入先からコーティングされたキャビネットを受け取ると、完了済と報告される前に、最終的な社内アセンブリ工程が実行されます。

1. **生産管理 \> 製造オーダー \> すべての製造オーダー**の順に選択し、**すべての製造オーダー**ページを開きます。
2. アクション ウィンドウで、**新しい製造オーダー**を選択して**製造オーダーの作成**ダイアログ ボックスを開きます。

    ![製造オーダー ダイアログ ボックスの作成](./media/subcontract12_create-production-order-dialog.png)

3. **品目番号**フィールドで、**D8100** を選択します。
4. 品目番号を選択した後に、在庫分析コードのフィールドが表示されます。 **色**フィールドで、**クロム**を選択します。

    BOM および工順の有効なバージョンを挿入するかどうかを尋ねるメッセージ ボックスが表示されます。

    ![メッセージ ボックス](./media/subcontract13_message-box.png)

5. **はい**を選択します。 

    **製造オーダーの作成**ダイアログ ボックスでは、**BOM 番号**および**工順番号**フィールドで、製品 D8100 の BOM および工順の有効なバージョンがそれぞれ自動で選択されます。 この場合、BOM **000040** および工順 **000040** が選択されます。
    
    > [!NOTE]
    > BOM および工順の両方については、原価計算と計画にバージョン 000040 が使用されます。

6. **サイト**フィールドで、**5** を選択します。
7. **倉庫**フィールドで、**51** を選択します。
8. **BOM 番号**および**工順番号**フィールドで、自動的に選択された値を **000042** に変更します。

    > [!NOTE]
    > BOM および工順の両方については、バージョン 000042 を使用してキャビネットのコーティングを仕入先 US-801 に外注します。

    ![製造オーダーの作成ダイアログ ボックスで設定された値](./media/subcontract14_create-production-order-dialog-set.png)

9. **作成**を選択して製造オーダーを作成し、**すべての製造オーダー**ページに戻ります。

    ![すべての製造オーダー ページの新規製造オーダー](./media/subcontract15_new-production-order.png)

10. アクション ウィンドウの、**新しい製造オーダー**タブで、**見積**を選択して**見積**ダイアログ ボックスを開きます。

    ![見積ダイアログ ボックス](./media/subcontract16_estimate-dialog.png)

11. **OK** を選択して見積を確認し、**すべての製造オーダー**ページに戻ります。

    > [!NOTE]
    > 製造オーダーの見積時に、仕入先 US-801 に対してサービス品目 S8050 の発注書が生成されます。

12. アクション ウィンドウの、**製造オーダー**タブで、**BOM** を選択して **BOM** ページを開き、製造オーダーの BOM 明細行を表示できます。

    サービス品目 S8050 については、製造オーダーの見積が行われたときに生成された発注書への参照があることに注意してください。

    ![BOM ページの製造オーダー BOM 明細行](./media/subcontract17_production-order-bom-lines.png)

13. **BOM** ページを閉じて、**すべての製造オーダー**ページに戻ります。
14. アクション ウィンドウの、**スケジュール**タブで、**ジョブのスケジュール**を選択して**ジョブのスケジューリング**ダイアログ ボックスを開きます。
15. 次の値を指定します。

    - **スケジューリング指示**フィールドで、**今日からフォワード**を選択します。
    - **有限能力**オプションを**はい**に設定します。

    ![ジョブのスケジューリング ダイアログ ボックス](./media/subcontract18_job-scheduling-dialog.png)

16. **OK** を選択して、**ジョブのスケジューリング**ダイアログ ボックスを閉じ、**すべての製造オーダー**ページに戻ります。
17. アクション ウィンドウの、**スケジュール**タブで、**ガント**を選択して**ガント チャート - リソース ビュー**ページを開きます。

    ガント チャートでは、リソースで生産ジョブをスケジュールする方法の視覚概要を提供します。 外部のコーティング工程が 3 つのジョブから成ることに注意してください: プロセス ジョブ、配送ジョブ、および待ち時間ジョブ。

    ![ガント チャートのガント チャート - リソース ビュー ページ](./media/subcontract19_gantt-chart.png)

18. **ガント チャート - リソース ビュー**ページを閉じて、**すべての製造オーダー**ページに戻ります。
19. アクション ウィンドウの、**新しい製造オーダー**タブで、**リリース**を選択して**リリース**ダイアログ ボックスを開きます。

    ![ダイアログ ボックスをリリース](./media/subcontract20_release-dialog.png)

20. **OK** を選択して**リリース**ダイアログ ボックスを閉じます。
21. **生産管理 \> 定期処理のタスク \> 倉庫にリリース \> BOM およびフォーミュラ明細行の自動リリース**の順に選択して、**BOM およびフォーミュラ明細行の自動リリース**ダイアログ ボックスを開きます。

    ![BOM およびフォーミュラ明細行ダイアログ ボックスの自動リリース](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. **OK** を選択して BOM およびフォーミュラ明細行の自動リリース ジョブを実行します。

    このジョブでは、原材料の倉庫へのピッキング作業をリリースします。

23. **生産管理 \> 製造オーダー \> すべての製造オーダー**の順に選択し、**すべての製造オーダー**ページを開きます。
24. クイック フィルター フィールドを使用して、処理中の製造オーダーを選択します。
25. アクション ウィンドウの、**倉庫**タブで、**作業の詳細**を選択し、**作業**ページを開きます。

    ページに原材料ピッキングに対する 2 つの作業セットが表示されることに注意してください。 最初の作業は材料 M8100 および M8101 対象です。 これらの材料は工程 10 で消費されます。 2 つ目の作業は材料 M8202 および M8250 対象です。 これらの材料は、外注作業である工程 20 で消費されます。

    ![作業ページの原材料ピッキングに対する 2 つの作業セット](./media/subcontract22_work-page.png)

26. 工程 10 の倉庫作業を処理する倉庫アプリを開始します。

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. **生産管理 \> 製造オーダー \> すべての製造オーダー**の順に選択し、**すべての製造オーダー**ページを開きます。
28. クイック フィルター フィールドを使用して、処理中の製造オーダーを選択します。
29. アクション ウィンドウの、**新しい製造オーダー**タブで、**開始**を選択して**開始**ダイアログ ボックスを開きます。
30. **一般**タブで、次の値を指定します。

    - **開始工程番号** フィールドで、**10** を選択します。
    - **終了工程番号** フィールドで、**10** を選択します。

    ![一般タブで設定されている値](./media/subcontract23_start-dialog.png)

31. **OK** を選択して、**開始**ダイアログ ボックスを閉じ、**すべての製造オーダー**ページに戻ります。

    製造オーダーのステータスが**開始済**であることに注意してください。 工程 10 の材料は、ピッキング リスト仕訳帳の自動転記で消費されます。 工程 10 の時間消費量は、工順カード仕訳帳の自動転記で扱われます。

32. 工程 20 の倉庫作業を処理する倉庫アプリを開始します。

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. アクション ウィンドウの、**新しい製造オーダー**タブで、**開始**を選択して**開始**ダイアログ ボックスを開きます。
34. **一般**タブで、次の値を指定します。

    - **開始工程番号** フィールドで、**20** を選択します。
    - **終了工程番号** フィールドで、**20** を選択します。
    - **数量**フィールドに **10** と入力します。
    - **ピッキング リスト転記**オプションを**いいえ**に設定します。

    ![一般タブで設定されている値](./media/subcontract24_general-tab.png)

35. **OK** を選択して、**開始**ダイアログ ボックスを閉じ、**すべての製造オーダー**ページに戻ります。

    コーティング工程、およびサービス品目に使用される材料のピッキング リストが作成されます。 サービス品目は外注作業の原価を表します。

36. アクション ウィンドウの、**表示**タブで、**ピッキング リスト**を選択して**ピッキング リスト**ページを開きます。
37. 転記されていないピッキング リストを選択し、仕訳帳明細行を表示する仕訳帳番号を選択します。

    ![ピッキング リスト ページの仕訳帳明細行](./media/subcontract25_picking-list.png)

38. アクション ウィンドウで、**印刷** \> **ピッキング リスト レポート**を選択し、**ピッキング リスト レポート**ダイアログ ボックスを開きます。
39. **納品書レイアウトの使用**オプションを**はい**に設定します。

    ![ピッキング リスト レポート ダイアログ ボックス](./media/subcontract26_picking-list-report-dialog.png)

40. **OK** を選択して**ピッキング リスト**レポートを生成します。

    この場合、仕入先納品書は生産ピッキング リスト仕訳帳から印刷されます。 納品書では、コーティング工程を行う仕入先に出荷される材料を指定します。

    ![ピッキング リスト レポート](./media/subcontract27_picking-list-report.png)

41. **ピッキング リスト**レポートを閉じ、**ピッキング リスト**ページに戻ります。
42. アクション ウィンドウで、**転記**を選択して**仕訳帳の転記**ダイアログ ボックスを開きます。

    ![転記仕訳帳ダイアログ ボックス](./media/subcontract28_post-journal-dialog.png)

43. **OK** を選択して**転記仕訳帳**ダイアログ ボックスを閉じます。
44. 発注書を開きます。

    ![発注書ページ](./media/subcontract29_purchase-order-page.png)

45. アクション ウィンドウの、**購買**タブで**確認**をクリックします。
46. **転記**を選択して**転記仕訳帳**ダイアログ ボックスを開きます。
47. **OK** を選択して、**転記仕訳帳**ダイアログ ボックスを閉じ、**発注書**ページに戻ります。
48. 単価を **33** から **40** に変更します。

    ![発注書ページで変更された単価](./media/subcontract30_unit-price.png)

49. 発注書を再度確認します。
50. 製品受領書。

    ![製品受領書ダイアログ ボックスの転記](./media/subcontract31_posting-product-receipt-dialog.png)

51. 仕入請求書。
52. 照合状態を更新します。

    ![仕入先請求ページ](./media/subcontract32_vendor-invoice-page.png)

53. 完了レポート。

    ![完了レポート ダイアログ ボックス](./media/subcontract33_report-as-finished-dialog.png)

54. 終了。

    ![終了ダイアログ ボックス](./media/subcontract34_end-dialog.png)

55. 原価の比較。

    ![原価の比較チャート](./media/subcontract35_cost-comparison-charts.png)

データの設定がありません。
