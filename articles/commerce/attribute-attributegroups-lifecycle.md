---
title: 属性および属性グループの管理
description: このトピックでは、ユーザー定義フィールドを通して製品およびその特性を説明する方法を提供する、属性の使用方法について説明します。
author: ashishmsft
manager: AnnBe
ms.date: 04/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application pdate 5, AX 8.0
ms.openlocfilehash: 11f385514cc12733987a4855b626c067ff355b54
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023123"
---
# <a name="manage-attributes-and-attribute-groups"></a>属性および属性グループの管理

[!include [banner](includes/banner.md)]

*属性*は、製品とユーザー定義フィールドによる特性をさらに記述する方法を提供 (たとえば、**メモリ サイズ**、**ハード ディスク能力**、**エネルギー スター対応**など)。 属性は、製品カテゴリ、チャネルなどのさまざまな Commerce エンティティに関連付けられており、それらに対して既定値を設定できます。 製品は、製品カテゴリまたはチャネルに関連付けられる場合、その属性と既定値を継承します。 既定値は、個々の製品レベルやチャネル レベル、またはカタログで上書きできます。


例えば、典型的なテレビ番組は、以下の属性を有することがあります。

| カテゴリ   | 属性                | 許容値          | 既定値 |
|------------|--------------------------|-----------------------------|---------------|
| テレビ & ビデオ | ブランド                    | 有効なブランド値       | None          |
| テレビ         | スクリーン サイズ              | 20–80 インチ                | None          |
|            | [垂直解像度]      | 480i、720p、1080i、または 1080p | 1080p         |
|            | 画面の更新頻度      | 60hz、120hz、または 240hz       | 60hz          |
|            | [HDMI 入力]              | 0–10                        | 3             |
|            | [DVI 入力]               | 0–10                        | 1             |
|            | [複合の入力]         | 0–10                        | 2             |
|            | [コンポーネントの入力]         | 0–10                        | 1             |
| LCD        | [3D 準備完了]                 | [はい] または [いいえ]                   | 有           |
|            | [3D 有効]               | [はい] または [いいえ]                   | 無            |
| プラズマ     | [作業開始の温度]      | 32–110 度              | 32            |
|            | [作業終了の温度]        | 32–110 度              | 100           |
| プロジェクション | プロジェクションの管の保証 | 6、12、または 18 か月         | 12            |
|            | プロジェクションの管の \#   | 1–5                         | 3             |

## <a name="attributes-and-attribute-types"></a>属性と属性タイプ

属性は *属性タイプ* をベースにしています。 属性タイプは、特定の属性に入力できるデータのタイプを示します。 次の属性タイプがサポートされます。

- **通貨** – このタイプは、通過の値をサポートします。 これはバインドできますし (値の範囲をサポートできる) 開いたままにもできます。
- **日時** – このタイプは、日付と時刻の値をサポートします。 それはバインドできますし、開いたままにすることもできます。
- **小数点** – このタイプは、小数点以下を含む数値をサポートします。 また、測定単位もサポートします。 それはバインドできますし、開いたままにすることもできます。
- **整数** – このタイプは、数値をサポートします。 また、測定単位もサポートします。 それはバインドできますし、開いたままにすることもできます。
- **テキスト** – このタイプは、テキストの値をサポートします。 また、事前定義された一連の使用可能な値 (*列挙型* である) がサポートされます。
- **ブール値** – このタイプは、バイナリ値をサポートします (**true** または **false**)。
- **参照** – このタイプは、他の属性を参照します。

### <a name="set-up-attribute-types"></a>属性タイプを設定します

1. 販売促進マネージャーとして、バック オフィス クライアントにログインします。
2. **製品情報管理** &gt; **設定** &gt; **カテゴリと属性** &gt; **属性タイプ**の順に移動します。
3. **テキスト**タイプの 2 つの属性タイプを作成し、**固定リスト**オプションを**はい**に設定し、値の一覧を追加します。

    - 1 つの属性タイプを**レンズ図形**と名付け、**楕円** と **四角**、そして **長方形** の値を追加します。
    - その他の属性の型の名前を**サングラス ブランド**とし、**Ray ban** と **Aviator**、そして **Oakley** の値を追加します。

![属性タイプ](media/AttributeType.png)

### <a name="set-up-an-attribute"></a>属性を設定します

1. 販売促進マネージャーとして、バック オフィス クライアントにログインします。
2. **製品情報管理** &gt; **設定** &gt; **カテゴリと属性** &gt; **属性**の順に移動します。
3. **レンズ**と名付けられた属性を作成します。
4. **属性タイプ**フィールドを**レンズ図形**に設定します。

![属性](media/Attribute.png)

## <a name="attribute-metadata"></a>属性メタデータ

*属性のメタデータ* では、各製品の属性がどのように動作するかを指定するオプションを選択できます。 たとえば、属性が必要か、検索で属性を使用できるか、フィルターとして属性を使用できるか特定することができます。

製品では、属性メタデータの設定はチャネル レベルで上書きできます。 この機能は、このトピックの後半で説明されます。

ご存知のように、**属性**ページには、属性メタデータに関連するオプションが含まれています。 **POS の属性メタデータ**のもと、**絞り込み可能**と名付けられたオプションは、販売時点管理 (POS) での属性値の動作、またはシステムがこれらの属性値を処理する方法に影響します。 **絞り込み可能**オプションから**はい**に設定できる属性のみ、POS での製品の洗練またはフィルター処理のために表示されます。

ここでは、**属性**ページで、残りの属性メタデータ オプションをお見せします。

- 検索可能
- 取得可能
- 照会可能
- 並べ替え可能
- 複数の値を許可
- 大文字と小文字および形式を無視
- 完全一致

これらのオプションは、もともとオンライン店舗の検索機能を向上させることを意図していました。 Commerce には、すぐに使えるオンライン店舗が含まれていませんが、電子商取引発行ソフトウェア開発キット (SDK) は含まれています。 顧客は、この SDK を使用して任意の検索インデックスに製品を配置することが可能です。 製品データはインポートされますが、顧客は引き続き検索可能なデータ、クエリ可能なデータなどを区別することができるはずです。 この方法により、最適なインデックスを作成して、*これらの意見で* がインデックスされる属性のみをインデックス化できるようにすることができます。

これらの残りのオプションの目的については、[SharePoint Server 2013 の検索スキーマの概要](https://technet.microsoft.com/library/jj219669.aspx)を参照してください。

## <a name="filter-settings-for-attributes"></a>属性のためのフィルター設定

属性のフィルター設定を使用して、属性のフィルターを POS に表示する方法を定義できます。 属性のフィルター設定へアクセスするには、**属性**ページで、属性を選択し、アクション ペインで**フィルター設定**を選択します。

**フィルターの表示設定**ページでは、次のフィールドが含まれています。

- **名前** – 既定では、このフィールドは属性の名前を設定します。 ただし、その値は変更できます。
- **オプションを表示** – 次のオプションを選択できます。

    - **単一の値** – このオプションでは、次の属性タイプを選択できます。**ブール値**、**通貨**、**10 進数**、**整数**、そして**テキスト**。 このオプションは、調整のクライアントで、これらの属性の単一の値の選択が可能です。
    - **複数の値** – このオプションでは、次の属性タイプを選択できます。**通貨**、**10 進数**、**整数**、**テキスト**。 このオプションは、調整のクライアントで、この属性の多値の選択が可能です。

- **表示制御** – 次のオプションを選択できます。

    - **リスト** – このオプションは、全ての属性タイプで使用できます。
    - **範囲** – このオプションでは、次の属性タイプを選択できます。**通貨**、**10 進数**、そして**整数**。
    - **スライダー** – このオプションでは、次の属性タイプを選択できます。**通貨**、**10 進数**、そして**整数**。
    - **バー付きスライダー** – このオプションでは、次の属性タイプを選択できます。**通貨**、**10 進数**、そして**整数**。

- **しきい値** – 表示制御タイプで**範囲**を選択した場合、この設定が必要です。 セミコロン (;) を区切り記号として使用し、値を定義することができます。

    例えば**バッグ数量**のようなフィルターに、しきい値を **10、20、50、100、200、500、1000、5000** とすることができます。 この場合、その POS では次の範囲が表示されます。 結果セット内に商品を持たない範囲はすべてグレー表示になります。

    - 10 未満
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - 500 回以上

![属性のフィルター設定](media/AttributeFilterSettings.PNG)

## <a name="attribute-groups"></a>属性グループ

属性を定義した後は、属性グループに割り当てることができます。 *属性グループ* は、製品コンフィギュレーション モデルのコンポーネントまたはサブコンポーネントの個々の属性をグループ化するために使用されます。 属性は、複数の属性グループに含めることができます。 属性グループは、各種の選択が特定のコンテキストで並べられるため、ユーザーが製品を構成する際に役立ちます。 属性グループをカテゴリまたはチャネルに割り当てることができます。

属性グループに含まれている属性の既定値を設定することもできます。 例えば、属性グループに色の属性を追加し、既定の属性値として**青色**を選択します。 この場合、その属性グループの 1 つを含む製品に属性グループが追加されると、各製品の既定の色として**青色**が表示されます。

![属性グループ](media/AttributeGroup.png)

### <a name="create-an-attribute-group"></a>属性グループの作成

1. 販売促進マネージャーとして、バック オフィス クライアントにログインします。
2. **製品情報管理** &gt; **設定** &gt; **カテゴリと属性** &gt; **属性グループ**の順に移動します。
3. **ファッション サングラス**という名の属性グループを作成します。
4. 次の属性を追加します。**レンズ図形**と**サングラス ブランド**。

### <a name="assign-attribute-groups-to-categories"></a>属性グループをカテゴリに割り当てる

1 つまたは複数の属性グループは、次のタイプのカテゴリ階層内のカテゴリ ノードを関連付けることができます。Commerce 製品階層、チャネル ナビゲーション カテゴリ階層、および補助製品カテゴリ階層。 そして、製品を分類されると、属性グループに含まれる属性を継承します。

![製品階層 – 製品属性グループ](media/AGRetailProdHierarchy.PNG)

この手順では、属性グループを Commerce 製品階層内のカテゴリに割り当てます。

1. 販売促進マネージャーとして、バック オフィス クライアントにログインします。
2. **Retail と Commerce** &gt; **カテゴリと製品の管理** &gt; **Commerce 製品階層**の順に移動します。
3. **ファッション ナビゲーション階層**を選択します。
4. **紳士服**で、**パンツ**カテゴリを選び、**製品属性グループ**クイック タブ上で**男性用ベルト**という名の属性グループを追加します。
5. **ファッション サングラス**カテゴリを選択し、**属性の表示**を選び**ファッション サングラス**属性グループで新しい属性を確認します。

    属性グループに新しい**レンズ図形**と**サングラス ブランド**属性が表示されます。

6. **紳士服**で、**パンツ**カテゴリを選択し、**属性の表示**を選び**男性用ベルト**の属性グループを確認します。

    属性グループに、**男性用ベルト ブランド**と**ベルト ファブリック**、**ベルト サイズ**の属性が表示されます。

> [!NOTE]
> この手順を使用して、チャンネル ナビゲーション カテゴリ階層と補助製品カテゴリ階層内のカテゴリに属性グループを割り当てることもできます。 手順 2 では、次のナビゲーション パスを使用します。
>
> - Retail と Commerce &gt; カテゴリと製品の管理 &gt; チャネル ナビゲーション カテゴリ
> - Retail と Commerce &gt; カテゴリと製品の管理 &gt; 補助製品カテゴリ

### <a name="assign-attribute-groups-to-stores"></a>属性グループを店舗に割り当てる

1 つ以上の属性グループを店舗階層の 1 つ以上の店舗に関連付けることができます。 そして、製品が特定の店舗に対して強化されると、属性グループに含まれる属性を継承します。

1. 販売促進マネージャーとして、バック オフィス クライアントにログインします。
2. **Retail と Commerce** &gt; **チャネル設定** &gt; **チャネル カテゴリと製品属性**の順に移動します。
3. ヒューストン チャネルに属性グループを割り当てます。

    1. **ヒューストン**チャネルを選択します。
    2. **属性グループ**クイック タブで、**追加**を選び、**名前**フィールドで **SharePointProvisionedProductAttributeGroup** を選択します。
    3. もう一度**追加**を選び、**名前**フィールドで**男性用ベルト**を選択します。
    4. もう一度**追加**を選び、**名前**フィールドで**ファッション サングラス**を選択します。

        > [!NOTE]
        > オプションを使用すると、このチャネルが階層内で、親チャネルから属性グループを継承するよう指定できます。 **継承**オプションを**はい**に設定すると、子チャネル ノードは、すべての属性グループとそれらの属性グループ内のすべての属性を継承します。

4. これらはヒューストン チャネルで使用できるように属性を有効にします。

    1. アクション ペインで、**属性メタデータの設定**を選択します。
    2. **ファッション**カテゴリ ノードを選び、**チャネル製品属性**クイック タブ で各属性の**属性を含む**を選択します。
    3. **ファッション アクセサリー**カテゴリ ノードを選び、**ファッション サングラス**カテゴリを選択し、**チャンネル製品属性**クイック タブで各属性の**属性を含む**を選択します。
    4. **紳士服**カテゴリ ノードを選び、**パンツ**カテゴリを選択し、**チャネル製品属性**クイック タブで各属性の**属性を含む**を選択します。

![チャネル カテゴリと製品属性 – 属性グループ](media/CCPAttrGrp.png)

## <a name="overriding-attribute-values"></a>属性値の上書き

属性の既定値は、製品レベルで各製品に対して上書きすることができます。 特定のチャネルを対象とする特定のカタログの個々の製品について、既定値を上書きすることもできます。

### <a name="override-the-attribute-values-of-an-individual-product"></a>個々の製品の属性値を上書き

1. 販売促進マネージャーとして、バック オフィス クライアントにログインします。
2. **Retail と Commerce** &gt; **カテゴリと製品の管理** &gt; **カテゴリ別リリース済製品**の順に移動します。
3. **ファッション** &gt; **ファッション アクセサリ** &gt; **ファッション サングラス**カテゴリ ノードを選択します。
4. グリッドで必要な製品を選択します。 そして、アクション ペイン、**製品**タブの、**設定**グループで、**製品属性**を選択します。
5. 左側のペインで属性を選択し、右側のペインでその値を更新します。

![製品詳細ページ – 製品属性グループ](media/ProdDetailsProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-catalog"></a>カタログ内の製品属性値を上書き

1. 販売促進マネージャーとして、バック オフィス クライアントにログインします。
2. **Retail と Commerce** &gt; **カタログ管理** &gt; **すべてのカタログ**の順に移動します。
3. **Fabrikam 基本カタログ**カタログを選択します。
4. **ファッション** &gt; **ファッション アクセサリ** &gt; **ファッション サングラス**カテゴリ ノードを選択します。
5. **製品**クイック タブで、必要な製品を選び、製品グリッドの上部で**属性**を選択します。
6. 次のクイック タブで、必要な属性の値を更新します。

    - 共有製品メディア
    - 共有の製品属性
    - チャネル メディア
    - チャネル製品属性

    > [!NOTE]
    > 共有製品メディアと共有製品属性が作成される場合、それらはすべての製品に適用されます。

![カタログ製品属性グループ](media/CatalogProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-channel"></a>チャネル内の製品属性値を上書き

1. 販売促進マネージャーとして、バック オフィス クライアントにログインします。
2. **Retail と Commerce** &gt; **チャネル設定** &gt; **チャネル カテゴリと製品属性**の順に移動します。
3. **ヒューストン**チャネルを選択します。
4. **製品**クイック タブで、必要な製品を選び、製品グリッドの上部で**属性**を選択します。

    > [!NOTE]
    > 製品がない場合は、**製品**クイック タブで**追加**を選択して製品を追加し、**製品を追加**ダイアログ ボックスで必要な製品を選択します。

5. 次のクイック タブで、必要な属性の値を更新します。

    - 共有製品メディア
    - 共有の製品属性
    - チャネル メディア
    - チャネル製品属性

    > [!NOTE]
    > 共有製品メディアと共有製品属性が作成される場合、それらはすべての製品に適用されます。
