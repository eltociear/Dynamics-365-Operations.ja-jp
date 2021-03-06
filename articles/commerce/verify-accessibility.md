---
title: ページ コンテンツのアクセシビリティの検証
description: このトピックでは、Microsoft Dynamics 365 Commerce のページ コンテンツのアクセシビリティを検証する方法について説明します。
author: arotkin
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: arotkin
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8e35b0f71ff41bade266fb177e4500c7d124ed1f
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002662"
---
# <a name="verify-page-content-accessibility"></a>ページ コンテンツのアクセシビリティの検証


[!include [banner](includes/banner.md)]

このトピックでは、Microsoft Dynamics 365 Commerce のページ コンテンツのアクセシビリティを検証する方法について説明します。

## <a name="overview"></a>概要

ページの変更が完了したら、Web 上の全ユーザーがコンテンツにアクセスできることを確認する必要があります。 Commerce 作成ツールにおいて、統合された [Microsoft アクセシビリティ インサイト](https://accessibilityinsights.io/) サービスを使用することで、ページ コンテンツのアクセシビリティを簡単に確認できます。 このサービスは、ページと最新の [World Wide Web コンソーシアム (W3C) アクセシビリティ](https://www.w3.org/standards/webdesign/accessibility) ガイドラインを検証します。

[Microsoft アクセシビリティ インサイト](https://accessibilityinsights.io/) の統合は、使用する前に、テナントまたはサイト レベルで有効にする必要があります。

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a>テナント内のすべてのサイトに対する Microsoft アクセシビリティ インサイトの有効化

テナント内のすべての Commerce サイトに対する [Microsoft アクセシビリティ インサイト 統合](https://accessibilityinsights.io/) を有効にするには、次の手順を実行します。

> [!NOTE]
> テナントの設定にアクセスするには、システム管理者として Commerce にサインインする必要があります。

1. システム管理者として Commerce にサインインします。
1. 左のナビゲーション ウィンドウで、**テナントの設定** (ギア記号の横) を選択して展開します。
1. **テナントの設定**で、**機能**を選択します。
1. **アクセシビリティ チェック** オプションを**オン**にします。

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a>1 つのサイトに対する Microsoft アクセシビリティ インサイトの有効化

1 つの Commerce サイトに対する [Microsoft アクセシビリティ インサイト 統合](https://accessibilityinsights.io/) を有効にするには、次の手順を実行します。

1. **サイト**で、**Fabrikam** (またはサイトの名前) を選択します。
1. 左のナビゲーション ウィンドウで、**サイト設定**を選択して展開します。
1. **サイト設定**で、**機能**を選択します。
1. **アクセシビリティ チェック** オプションを**オン**にします。

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a>ホーム ページのコンテンツのアクセシビリティを確認する

統合された [Microsoft アクセシビリティ インサイト](https://accessibilityinsights.io/) サービスを使用して、Commerce のホーム ページのコンテンツのスキャンおよび確認をするには、次の手順を実行します。

1. **サイト**で、**Fabrikam** (またはサイトの名前) を選択します。
1. 左のナビゲーション ウィンドウで、**ページ**を選択します。
1. ホーム ページを検索、選択して、ページ エディターで開きます。
1. コマンド バーで、**アクセシビリティのチェック**を選択します。 **アクセシビリティのチェック**のページが表示されます。
1. スキャンが完了した後、レポートの内容を確認します。
1. チェックが失敗した場合、失敗したチェック項目をそれぞれ選択して展開し、詳細を表示します。
1. 確認した後、レポートを閉じるには、**アクセシビリティのチェック** ページの下部までスクロールし、**OK** を選択します。

## <a name="additional-resources"></a>追加リソース

[既存のサイト ページの変更](modify-existing-page.md)

[新しいサイト ページの追加](add-new-page.md)

[ページ レイアウトの選択](select-page-layouts.md)

[SEO メタデータの管理](manage-seo-metadata.md)

[ページの保存、プレビュー、および公開](save-preview-publish-page.md)

[製品ページの拡充](enrich-product-page.md)

[カテゴリ ランディング ページの拡充](enrich-category-page.md)
