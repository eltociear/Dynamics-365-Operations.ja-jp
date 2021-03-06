---
title: ピッキング行のグループ化
description: このトピックでは、ピッキング行のグループ化の概要を示します。
author: Mirzaab
manager: AnnBe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1b1d0135d450bc9be7b1303240a9ca70f95ae38e
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906271"
---
# <a name="pick-line-grouping"></a>ピッキング行のグループ化

[!include [banner](../includes/banner.md)]

ピッキング行のグループ化では、品目と場所が同じ複数の作業明細行を結合して、モバイル デバイスでユーザーに提示される 1 つのピッキングを作成できます。 したがって、倉庫の作業者は、可能な限り効率的な指示を受け取ることができますが、システムに必要な作業明細行の分割 (たとえば、異なるコンテナや注文など) も維持されます。

## <a name="set-up-pick-line-grouping"></a>ピッキング行のグループ化の設定

### <a name="create-a-mobile-device-menu-item"></a>品目のモバイル デバイス メニューの作成

1. **倉庫管理 \> 設定 \> モバイル デバイス \> モバイル デバイス メニュー項目**に移動して、**"販売グループ ライン ピッキング - ユーザー主導**という名前の新しいメニュー項目を作成します。
2. **モバイル デバイス メニュー項目**で、次の値を設定します。

    - **メニュー項目名**フィールドに、**販売ピッキング - グループ明細行**と入力します。
    - **タイトル** フィールドに、**販売ピッキング - グループ明細行**と入力します。
    - **モード** フィールドで、**作業**を選択します。
    - **既存の作業を使用** オプションを **はい** に設定します。

3. **一般**クイック タブで、次の値を設定します。

    - **指示者**フィールドで、**ユーザー主導**を選択します。
    - **ライセンス プレートの生成**オプションを**はい**に設定します。
    - **グループ ピック** オプションを**はい**に設定します。

4. **作業クラス** クイック タブで、次の手順に従って、モバイル デバイスのメニュー項目に対して有効な作業クラスを構成します。

    1. **新規** を選択します。
    2. **作業クラス ID** フィールドで、使用する倉庫に応じて**販売**または **SO ピッキング**を選択します。
    3. **ワーク オーダー タイプ** フィールドで、**販売注文**を選択します。

### <a name="set-up-a-mobile-device-menu"></a>モバイル デバイス メニューを設定する

1. **倉庫管理 \> 設定 \> モバイル デバイス \> モバイル デバイス メニュー**の順に移動します。 
1. 作成したメニュー項目を目的のメニューに追加します。

### <a name="set-up-a-work-template"></a>作業テンプレートを設定する

1. **倉庫管理 \> 設定 \> 作業 \> 作業テンプレート**の順に移動します。
1. この機能で使用する必要がある作業テンプレートを検索します。 この例では、標準の **51 ステージにピック** Contoso 作業テンプレートを選択します。
1. メニューで**クエリの編集**を選択します。
1. **並べ替え**タブで**追加**を選択し、次の値を設定します。

    - **テーブル** フィールドで、**一時的な作業トランザクション**を選択します。
    - **派生テーブル** フィールドで、**一時的な作業トランザクション**を選択します。
    - **フィールド** フィールドで、**品目番号**を選択します。
    - **検索の方向**フィールドで、**昇順**を選択します。

> [!NOTE]
> ピッキング行のグループ化機能を機能させるには、作業明細行を品目 ID で並べ替える必要があります。 同じ品目を含む行が順序付けされない場合は、グループ化されません。

## <a name="example"></a>例

### <a name="create-picking-work"></a>ピッキング作業の作成

ピッキング行のグループ化を設定する前に、適格な出荷作業をいくつか作成する必要があります。

1. **販売とマーケティング \> 販売注文 \> すべての販売注文**の順に移動します。
2. **新規**を選択して新しい販売注文を作成します。 
3. **顧客口座**フィールドで、顧客を選択します。 
4. **一般** クイック タブの**倉庫**フィールドで、**51** を選択します。 その後、**OK** を選択します。
5. **販売注文明細行**で、次の 6 行を追加します。

    - **明細行 1:** **品目番号**フィールドで、**M9200** を選択します。 **数量**フィールドに **3** と入力します。
    - **明細行 2:** **品目番号**フィールドで、**M9201** を選択します。 **数量**フィールドに **3** と入力します。 
    - **明細行 3:** **品目番号**フィールドで、**M9202** を選択します。 **数量**フィールドに **2** と入力します。 
    - **明細行 4:** **品目番号**フィールドで、**M9200** を選択します。 **数量**フィールドに **1** と入力します。 
    - **明細行 5:** **品目番号**フィールドで、**M9200** を選択します。 **数量**フィールドに **3** と入力します。
    - **明細行 6:** **品目番号**フィールドで、**M9202** を選択します。 **数量**フィールドに **7** と入力します。 

    各品目の合計数量の概要を次に示します。

    - **品目 M9200:** 各 7
    - **品目 M9201:** 各 3
    - **品目 M9202:** 各 9

6. 注文を倉庫にリリースする前に、ピッキング場所にすべての注文のすべての品目に十分な在庫があることを確認する必要があります。 **場所のディレクティブ**の設定を確認して、販売注文のピッキングに使用されるピッキング場所を決定します。
7. 在庫を引当し、倉庫にリリースします。 6 行の作業 ID が作成されます。 行は品目番号順に並べ替えられます。

### <a name="run-the-mobile-device-flow"></a>モバイル デバイス フローを実行する

1. モバイル デバイスで、モバイル デバイス メニュー品目を含むメニューを選択します。
1. **販売ピッキング - グループ明細行**メニュー品目を選択し、ピッキングを開始します。

    メニューを選択して作業 ID を入力すると、品目 M9200 のすべてのピッキング明細行がグループ化されるピッキング ステップが表示されます。 品目 M9200を 7 つずつピッキングするように指示されます。

1. ピッキング ステップを確定します。 
1. 仕掛品のクライアント画面で、品目 M9200 の 3 つのピッキング明細行がすべて同時に閉じられていることを確認します。

    作業明細行 4 が表示されます。

1. ピッキング ステップを確定します。

    モバイル デバイスの最後のピッキング ステップでは、ワーク オーダーから最後の 2 つのピッキング明細行を集計します。

1. 品目 M9202 の各 9 個のピッキング ステップを完了します。
1. 作業を完了するには、プット ステップと、追加のピック / プットのペアを確認します。

> [!NOTE]
> - 作業明細行は、順序が正しい場合にのみグループ化できます。
> - 次の機能はサポートされていません。
>
>    - CW 品目。 作業に CW 品目がある場合は、ピッキングを開始する前にエラー メッセージが表示されます。
>    - ピース ピッキング。
>    - 未完了の補充作業がある作業明細行。
>    - 超過ピッキング。
