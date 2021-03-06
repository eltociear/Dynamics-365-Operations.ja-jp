---
title: ユーザー補助機能
description: このトピックでは、Microsoft Dynamics 365 Commerce のユーザー補助機能について説明します。
author: BrianShook
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3edc6250dd5438be31d80a9d6b0f3b730438ca53
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001763"
---
# <a name="accessibility-features-and-capabilities"></a>ユーザー補助機能


[!include [banner](includes/banner.md)]

このトピックでは、Microsoft Dynamics 365 Commerce のユーザー補助機能について説明します。

## <a name="overview"></a>概要

ユーザー補助機能は、すべてのユーザーがアクセスしてアクションを実行して目標を達成できるようにする機能的手段を提供します。 この広範囲のユーザーには、聴覚、視覚、可動性、または神経多様性用の支援ツールが必要になる場合があります。

Dynamics 365 Commerce のさまざまな機能を使用して、支援機能を含むサイトを構築することができます。 サイトを設計する際、[Microsoft アクセシビリティ センター](https://www.microsoft.com/accessibility) で説明されているユーザー補助機能の領域を考慮する必要があります。 

このトピックでは、Dynamics 365 Commerce の使用時に考慮する必要があるユーザー補助機能のいくつかの追加領域について説明します。

## <a name="image-alt-text"></a>画像の代替テキスト

Dynamics 365 Commerce には、サイトで使用される画像とビデオ資産を追跡するためのデジタル資産管理システムが組み込まれています。 画像キャプション、説明、および代替テキストは、選択またはアップロードされた画像のプロパティ ウィンドウに追加できます。

## <a name="video-accessibility"></a>ビデオ アクセシビリティ

Dynamics 365 Commerce デジタル資産管理システムでは、ビデオ コンテンツに対するいくつかのユーザー補助機能がサポートされています。 次の表ではいくつかの例を一覧表示します。

| ビデオ機能               | 説明 |
|-----------------------------|-------------|
| クローズド キャプション (CC)      | 聴覚障害のあるユーザーを支援するための、ビデオのオーディオおよびオーディオ記述要素に表示できるテキスト |
| サブタイトル                   | 画面上でコンテキスト手がかりまたはダイアログのテキストを表示するキャプション ファイル |
| オーディオ トランスクリプト           | ビデオ資産のオーディオから生成された話し言葉のテキスト トランスクリプト |
| 説明オーディオ           | 画面上で発生しているコンテンツまたはコンテキストを説明する通常以外のオーディオ チャンネル |
| 最低年齢ゲート            | 閲覧者がビデオを視聴するのに必要な最低年齢を格納できる属性 (メタデータのみ) |

### <a name="configure-video-accessibility-elements"></a>ビデオ アクセシビリティー要素のコンフィギュレーション

Dynamics 365 Commerce のサイトの**資産**セクションでは、クローズド キャプション、通常のオーディオ、および記述オーディオに対する個別のファイルを含むビデオ資産をアップロードできます。 ビデオ資産をアップロードする際にはクローズド キャプションも自動的に生成されます。

#### <a name="generate-or-upload-closed-caption-files-during-video-asset-upload"></a>ビデオ資産のアップロード中におけるクローズド キャプション ファイルの生成またはアップロード

ビデオのアップロード時にクローズド キャプション ファイルが自動的に生成されるようにするには、この手順を実行します。

- **資産のアップロード** ダイアログ ボックスで、**クローズド キャプションの自動生成**を選択します。 クローズド キャプション ファイルを生成している場合、クローズド キャプション ファイルのファイル セレクターはダイアログ ボックスでは使用できません。

ビデオのアップロード時にクローズド キャプション ファイルを手動でアップロードするには、この手順を実行します。

- **資産のアップロード** ダイアログ ボックスで、**クローズド キャプションの自動生成**をオフにします。

ビデオの通常オーディオまたは記述オーディオ ファイルをアップロードするには、**資産のアップロード** ダイアログ ボックスでファイル セレクターを使用します。

> [!NOTE]
> ビデオ資産をアップロードした後に、クローズド キャプション、通常オーディオ、および記述オーディオ資産を追加することもできます。 **資産**に移動し、ビデオ資産を選択し確認してから、ビデオ資産のプロパティ ウィンドウで追加の資産をアップロードします。

#### <a name="edit-cc-and-audio-transcript-files"></a>CC およびオーディオ トランスクリプト ファイルの編集

CC およびオーディオのトランスクリプト ファイルは、オーサリング ツールで直接編集できます。 ビデオ再生は編集時に使用できます。

CC およびオーディオ トランスクリプト ファイルを編集するには、次の手順を実行します。

1. **資産**に移動し、ビデオ資産を選択してから、**CC/トランスクリプトの編集**を選択します。 クローズド キャプションとトランスクリプト コンテンツ エディターが表示されます。
1. **チェックアウト**を選択します。
1. クローズド キャプションまたはトランスクリプト テキストを編集します。
1. 完了したら、**保存**を選択し、**チェックイン**を選択します。
1. 公開する準備が整ったら、**公開**を選択します。

#### <a name="set-the-minimum-age-attribute"></a>最低年齢属性の設定

**最低年齢**メタデータ属性をビデオ資産に関連付けることができます。

ビデオ資産の**最低年齢**属性を設定するには、次の手順を実行します。

1. **資産**に移動して、ビデオ資産を選択します。
1. **チェックアウト**を選択します。
1. ビデオ資産のプロパティ ウィンドウで、**最低年齢**属性を設定します。

> [!NOTE]
> プロパティ ウィンドウは、メタデータ属性値を設定および保存する目的でのみ使用されます。 再生ゲーティングにこの属性を使用するには、カスタマイズされたモジュールを作成する必要があります。

## <a name="additional-resources"></a>追加リソース

[フォーム、製品、およびコントロールのユーザー補助機能](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/user-interface/enable-accessibility)

[Microsoft アクセシビリティ センター](https://www.microsoft.com/accessibility)

[Dynamics 365 アクセシビリティ センター](https://docs.microsoft.com/dynamics365/get-started/accessibility/index)

[コンプライアンスの概要](compliance-overview.md)

[Cookie のコンプライアンス](cookie-compliance.md)

[プライバシー ポリシー ページの追加](add-privacy-page.md)
