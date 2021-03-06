---
title: 既定のカテゴリ ランディング ページと検索結果ページの概要
description: このトピックでは、Dynamics 365 Commerce での既定のカテゴリ ランディング ページと検索結果ページの概要を提供します。
author: v-chgri
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 17746d2923ab84311253c47647c0020807bdb75c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002499"
---
# <a name="overview-of-default-category-landing-page-and-search-results-page"></a>既定のカテゴリ ランディング ページと検索結果ページの概要


[!include [banner](includes/banner.md)]

このトピックでは、Microsoft Dynamics 365 Commerce E コマースでの既定のカテゴリ ランディング ページと検索結果ページの概要を提供します。

## <a name="default-category-landing-page"></a>既定のカテゴリ ランディング ページ

既定のカテゴリ ランディング ページは、Web サイトのユーザーがナビゲーション階層でカテゴリを選択したときに、通常表示されるページです。 カテゴリ ページを使用すると、参照したり、分類された製品を並べ替えたり、絞り込んだりすることができます。

![既定のカテゴリ ランディング ページ](./media/SimpleCategoryLandingDressCategory.png)

ページの上部には、販売促進マネージャーがカテゴリ化したすべての製品カテゴリおよび他のページを表示するヘッダーがあります。 コンフィギュレーションはチャネル ナビゲーション階層のコンフィギュレーションの一部として実行されます。 ページの下部には、買い物客が興味を持つ可能性のあるさまざまなトピックへのクイック リンクを含むフッターがあります。

カテゴリには、次のコンポーネントが不可欠です。

- **製品配置タイル**は、ナビゲーション階層のコンフィギュレーションの一部として、販売促進マネージャーによってカテゴリで定義された製品を示します。
- **絞り込み条件と選択肢の概要**は、カウントを提供し、品目の絞り込みに使用できるフィルターです。 販売促進マネージャーは、チャネル カテゴリおよび製品属性に関連するメタデータのコンフィギュレーションの一部として、これらをコンフィギュレーションします。
- **並べ替えのオプション**は、Web サイトの訪問者が製品を並べ替えるために使用します。 既定では、次の並べ替えのオプションを利用できます。

    - 価格 – 低から高
    - 価格 – 高から低
    - 製品名 – \[A-Z\]
    - 製品名 – \[Z-A\]
    - 評価 – 低から高
    - 評価 – 高から低

- **ページネーション**を使用すると、Web サイトの訪問者は、カテゴリ化された製品結果のあるページから別のページに移動できます。
- **合計数**には、カテゴリで定義されている製品の合計数が表示されます。

## <a name="enrich-a-category-landing-page"></a>カテゴリ ランディング ページの拡充

カテゴリ ランディング ページに、特定のカテゴリに合わせたよりカスタマイズされた経験が必要な場合は、そのカテゴリのカテゴリ ランディング ページを「拡充」できます。 たとえば、マーケティング ビデオおよびいくつかのカテゴリのストーリーテリングを追加して、買い物客の注意を引くことができます。 詳細については、[カテゴリ ランディング ページの拡充](enrich-category-page.md) を参照してください。

![拡充されたカテゴリ ランディング ページ](./media/CategoryLandingPages.png)

## <a name="auto-suggest-and-search-results-pages"></a>自動提案および検索結果ページ

Web サイトのユーザーは、ナビゲーション階層からカテゴリに移動するか、検索フィールドに検索用語を入力することによってサイトを探索できます。

ユーザーが検索フィールドに入力し始めるとすぐに、検索語を提案する没入型の自動提案機能が使用できます。

次に、表示される可能性のある提案のタイプをいくつか示します。

- **キーワード**は、チャンネルに類別されたすべての製品の中から品目を検索するために使用されます。
- **製品**は、製品の詳細ページへの直接リンクを提供します。
- **スコープ カテゴリ検索候補**は、さまざまなカテゴリを一覧表示し、ユーザーが特定のカテゴリのキーワードを検索できるようにします。

![没入型の自動提案](./media/ImmersiveAutoSuggestUX.png)

ユーザーがキーワードまたはスコープ カテゴリ検索候補のいずれかを選択した場合、または、入力した検索語句に対する提案がない場合は、検索結果ページにリダイレクトされます。 ユーザーは、検索結果の一覧を参照、並べ替え、および絞り込んで、目的の品目を見つけることができます。

![検索のランディング](./media/SearchLanding.png)

検索結果ページには、次のコンポーネントが不可欠です。

- **製品配置タイル**は、ユーザーの検索用の製品を示します。 既定では、これらのタイルは、ユーザー検索のクラウドベースの検索関連性スコアで並べ替えられます。
- **絞り込み条件と選択肢の概要**は、カウントを提供し、品目の絞り込みに使用できるフィルターです。 販売促進マネージャーは、「チャネル カテゴリおよび製品属性」メタデータのコンフィギュレーションの一部として、これらをコンフィギュレーションします。
- **並べ替えのオプション**は、Web サイトの訪問者が製品を並べ替えるために使用します。 既定では、次の並べ替えのオプションを利用できます。

    - 価格 – 低から高
    - 価格 – 高から低
    - 製品名 – \[A-Z\]
    - 製品名 – \[Z-A\]
    - 評価 – 低から高
    - 評価 – 高から低
    - 既定

- **ページネーション**を使用すると、Web サイトの訪問者は、カテゴリ化された製品結果のあるページから別のページに移動できます。
- **合計数**には、カテゴリで定義され、検索基準に合致する製品の合計数が表示されます。

## <a name="additional-resources"></a>追加リソース

[ホーム ページの概要](quick-tour-home-page.md)

[製品詳細ページの概要](quick-tour-pdp.md)

[買い物カゴとチェック アウト ページの概要](quick-tour-cart-checkout.md)

[アカウント管理ページの概要](quick-tour-account-management.md)

