---
title: データ エンティティ ウィザード ルール
description: このトピックでは、代理外部キー フィールドのナチュラル キー拡張と子/親関係の拡張について説明します。
author: Sunil-Garg
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 6234
ms.assetid: 551ac5d6-980c-487f-a15c-66d7ab80924a
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7502e197f0cee202227ad35b21a1b38169c0113f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183431"
---
# <a name="data-entity-wizard-rules"></a>データ エンティティ ウィザード ルール

[!include [banner](../includes/banner.md)]

このトピックでは、代理外部キー フィールドのナチュラル キー拡張と子/親関係の拡張について説明します。

## <a name="natural-key-expansion-of-surrogate-foreign-keys"></a>代理外部キーのナチュラル キー拡張

代理外部キー フィールドの拡張データ型は、**RefRecId** または派生である必要があります。 代理外部キー フィールドのナチュラル キー拡張は、次の一覧のルールを使用します。 これらのルールは、評価の順に記載されています。

1. **交換キー** – 交換キー フィールド
2. **主キー** – プライマリ インデックス キー フィールド
3. **代替キー** - 最初の固有の代替キー
4. **自動 ID キー** - 自動 ID フィールド

ナチュラル キーで入れ子になっている代理外部キー フィールドは、再帰的に展開されます。 定期的な入れ子になったサロゲートは、最初の事例に限定されます。 代理外部キーの **is mapped** プロパティを選択すると (つまり、プロパティを **true** に設定すると)、関連するデータソースがエンティティに自動的に追加され、関連するデータソースにあるナチュラル キーの各フィールドの **is mapped** プロパティが選択されます。 さらに、入れ子になった代理外部キーのデータ ソースは、再帰的にエンティティに追加されます。 代理外部キーの **is mapped** プロパティ (つまりプロパティを **false** に設定する場合) をクリアする場合、関連するデータ ソースが自動的に削除され、エンティティとネストされた代理外部データ ソースから自動的にマップ解除されます。 代理外部キー フィールドの **is mapped** プロパティを選択し、クリアした結果と **データ ソースの追加** および **Remove data source** ボタンを使用した結果は異なります。 代理外部キー データ ソースを追加すると、親データ ソースの代理外部キー フィールドの **is mapped** プロパティは自動的に **true** に設定されています。 代理外部キー データ ソースを削除すると、親データ ソースの代理外部キー フィールドの **is mapped** プロパティは自動的に **false** に設定されます。 既定では、ルート データ ソースの代理外部キーフィールドの**マップされている**プロパティは **true** に設定されています。 したがって、規定では、代理外部キー関係は 1 つのレベルに拡張されます。

## <a name="expansion-of-parentchild-relations"></a>親または子の関係の展開
親/子の関係は、子テーブルでの関係として保存されている構成/拡張子関係です。 親テーブルはリレーションを検出しません。 親/子の関係は、代理外部キー関係またはナチュラル外部キーのいずれかです。 親/子の関係は、次のルールを使用します。

- 子テーブルのコレクションは、相互参照データベースに親テーブルへの「型参照」関係を照会することによって取得できます。
- 子テーブルは、親テーブルと同じテーブル グループに属している必要があります。
- 子と親**関係タイプ** プロパティは、**アソシエーション**、**合成**、**リンク**、**集約**のいずれかである必要があります。
- 子と親 **基数**プロパティの間の関係は、**厳密に 1 つ**または **0 または 1** である必要があります。
- 子と親 **関連テーブル基数**プロパティの間の関係は、**厳密に 1 つ**または **0 または 1** である必要があります。

既定では、親/子関係は展開されません。 **データ ソースの追加** ボタンを使用して、それらを追加する必要があります。 Microsoft Visual Studio でプロジェクトの既定の動作を変更するには、**親/子の展開** オプションを **true** に設定します。

### <a name="using-label-text-as-field-names"></a>ラベル テキストをフィールド名として使用

次の規則により、オプションが選択されたときにフィールド名としてラベル テキストを使用することができます (**true**)。

- すべての空白はラベル テキストから削除されます。
- ラベル テキストは 77 文字に切り捨てられ、一意の 3 桁の数値識別子 (000 〜 999) が追加されます。
- ラベル テキストは、**NamedElement.IsValid** メソッドに渡されます。 名前が有効である場合は、フィールド名として使用できます。 そうしないと、ラベル テキストは使用されず、フィールド名前が変更されません。

### <a name="the-is-mandatory-field"></a>Is 必須項目

データ エンティティ フィールドの既定値は **自動** です。この値は明示的に変更されない限り使用されます。 関係については、関連するフィールドの**必須**プロパティは、フィールドの**必須**値の値に基づいて設定されます。

- フィールドの**必須**プロパティと関連するフィールドの**必須**プロパティが両方とも **true** である場合は、両方のフィールドが **true** に明示的に設定されます。
- フィールドの**必須**プロパティと関連するフィールドの**必須**プロパティが両方とも **false** である場合は、両方のフィールドが **false** に明示的に設定されます。

フィールドの**必須**プロパティと関連するフィールドの**必須**プロパティの値が異なる場合は、両方のフィールドは変わりません。 この場合、**自動**の既定値が使用されます。