---
title: 経費精算書の再設計
description: このトピックでは、Microsoft Dynamics 365 Finance の経費精算書エントリのために再設計され再考された経験に関する情報を提供します。 この新しいエクスペリエンスにより、経費精算書を完成させるプロセスが簡略化され、必要な時間が短縮されます。
author: ryansandness
manager: AnnBe
ms.date: 06/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2019-6-30
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 8a8ad1ad84b8acaa54d8b03327157a930e562f59
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187662"
---
# <a name="expense-reports-reimagined"></a>経費精算書の再設計

[!include[banner](../includes/banner.md)]

経費精算書エントリは、経費精算書の完成単純化および必要な時間を節約するために再設計されています。 新しい経費のエクスペリエンスに関する主なコンポーネントは次のとおりです。

- 委任経費にアクセスできる新しい経費管理ワークスペースが表示されます。
- 新しいレシート照合エクスペリエンスにより、ヘッダーレベルの入庫をより良く表示し、経費明細行にレシートを添付するプロセスを簡略化することができます。
- 新しい読み取り専用グリッドで、多数の経費明細行と追加のデータ列を表示できます。 明細行と分割行をすべて表示して、親経費と共に表示できます。
- 経費を編集するための簡略化されたウィンドウ。
- 問題の内容および解決方法を理解するための正しいコンテキストがあることを保証するための再設計されたエラー、警告およびポリシー メッセージ。 Microsoft は、ユーザーが作業を完了する前、および箇条書きメッセージのような不完全な問題に取り組む前に現れた数々のメッセージを解決しました。
- 組織で必要なフィールド、オプションのフィールド、およびキャプチャしないフィールドを指定するための新しいページ。 このページでは、ユーザーが設定する必要があるフィールドの数を減らします。
- 経費精算書の新しい概観により、もはや精算書が会計担当者向けに設計されたようには見えません。

新しいエクスペリエンスを有効にするには、**機能管理**ワークスペースを使用して、**経費精算書の再設計**機能をオンにします。 この機能をオンにすると、次のアクションが実行されます。

- 既存の経費ワークスペースは、新しいワークスペースに置き換えられます。
- 経費フィールド表示の新しいメニュー項目が追加されます。
- 経費精算書 (既存のページ) の既存のメニュー項目または経費精算書のフィールドは削除されません。
- ワークフローと承認を行っても、既存の経費精算書ページに移動します。

## <a name="getting-started-video-for-new-users"></a>新しいユーザー向けビデオの使用にあたり

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Y7gO]

[Dynamics 365 for Finance and Operations の経費エクスペリエンス](https://youtu.be/Ocy-MsTvEE0) ビデオ (上記参照) は、YouTube で入手可能な [Finance and Operations プレイリスト](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) に含まれています。

## <a name="new-features"></a>新機能

| 新機能 | 説明 |
|---|----|
| 経費フィールドの表示 | 新しい設定ページでは、組織に対して無効となるフィールド、どのフィールドを必須とするか、および推奨されるフィールドを指定できます。 |
| 必須フィールド | 新しい単純なコンフィギュレーションを使用すると、ポリシー フレームワークを使用しなくてもいくつかのフィールドを必要に応じて作成できます。 |
| オプション フィールド | 省略可能なフィールドの 2 番目のページが追加されます。 これにより、従業員はフィールドを設定する必要はありませんが、フィールドは簡単にアクセスできます。 |
| 未添付の領収書を追加 | 経費精算書に未添付の精算書を追加する機能は、ワークスペースおよび経費精算書にさらに表示されます。 |
| メッセージングの強化 | 警告またはエラーのある経費明細行の方が見やすいです。 |
| メッセージ バーのメッセージの減少| 情報ログ メッセージの数が減少し、重複メッセージが表示されないようにするための作業が行われました。 |
| グループ化された共通のアクション | このインターフェイスは、一般的な明細行レベル アクションのほとんどに新しいアクション ボタンが追加され、ヘッダーには省略記号ボタン (...) および比較的頻繁でないアクションが追加されています。 |
| 可視性を高める新しいワークスペース | 新しいワークスペースは、ユーザーが別のエリアに移動するための機能およびリンクを統一します。 |
| 経費作成時の既存の経費およびレシートの追加 | 経費精算書を作成するときに、すべてまたは選択した経費およびレシートを追加できます。 |
| 為替レート計算機能 | 為替レート計算機能が追加されており、この機能を使用すると、立て替えた複数通貨換算の為替レートを計算できます。 |
| 新しい経費明細行の保存および追加 | 新しい経費が入力されると、**保存**と**新しい**ボタンの使用が可能となり、経費明細行をすばやく入力するために役立ちます。 |
| 分割行と明細行のより良い可視性 | 明細行と分割行は経費の一覧に直接追加され、表示を強化し、ポリシー エラーまたはその他のエラーがあるかどうかを容易に判断できるようにします。 |
| 明細表示時にレシートを表示 | 明細表示時にレシートが表示されます。 |

最初のリリースは、経費エントリのシナリオに重点を置いています。 経費精算書のレビューまたは承認シナリオでは、既存の経費エントリ ページが引き続き使用されます。

次の機能は既存のページに表示されますが、新しいページにはまだ存在しません。 これらの機能は、次の数リリースにわたって再紹介されます。

- 承認
- 買掛金勘定承および会計を編集する機能
- 複数のエントリ ポイント
- 出張費要求の統合
- 経費フィールド表示のデータ エンティティ
- 日当経費のエントリ
- 明細行レベルのワークフロー
- 中間承認者のサポート
- 高度な明細表示