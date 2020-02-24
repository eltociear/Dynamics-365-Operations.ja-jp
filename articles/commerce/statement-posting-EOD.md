---
title: 明細書転記機能の改良
description: このトピックでは、明細書転記の機能に加えられた機能強化事項について説明します。
author: josaw1
manager: AnnBe
ms.date: 05/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: anpurush
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 1e3fc0e8cb5c9a6cc7729dfbddd5d918a1d6bdb5
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023189"
---
# <a name="improvements-to-statement-posting-functionality"></a>明細書転記機能の改良

[!include [banner](includes/banner.md)]

このトピックでは、明細書転記の機能に加えられた最初の一連の機能強化事項について説明します。 これらの機能強化事項は、Microsoft Dynamics 365 for Finance and Operations 7.3.2 で利用可能です。

## <a name="activation"></a>アクティブ化

既定では、Finance and Operations 7.3.2 の展開中に、プログラムは明細書転記のレガシ機能を使用するために設定されます。 改良された明細書転記機能を有効にするには、そのためのコンフィギュレーション キーをオンにする必要があります。

- **システム管理** \> **設定** \> **ライセンス コンフィギュレーション**の順に移動し、その後、**小売**ノードで、**小売明細書 (従来)** チェック ボックスを消去し、**小売明細書**チェック ボックスをオンにします。

新しい**小売明細書**コンフィギュレーション キーが有効になると、**小売明細書**という新しいメニュー項目が使用できます。 このメニュー項目は手動で作成、計算、および明細書の転記をすることができます。 バッチの転記プロセスを使用する際にエラーが生じるステートメントは、このメニュー項目を通して使用可能にもなります。 (新しい**小売明細書 (従来)** コンフィギュレーション キーが有効になると、メニュー項目は**未処理の明細書**と呼ばれます。)

Retail には、これらのコンフィギュレーション キーに関連付けられている以下の検証が含まれています。

- 両方のコンフィギュレーション キーを、同時に有効にすることはできません。
- ライフサイクル (作成、計算、消去、転記など) の間に指定された明細書上で実行されるすべての工程に対して、同じコンフィギュレーション キーを使用する必要があります 。 たとえば、**小売明細書 (従来)** コンフィギュレーション キーが有効である間は、明細書の計算やを作成することはできません。さらに**小売明細書**コンフィギュレーション キーが有効である間は、同じ明細書を転記しようとします。

> [!NOTE]
> **小売明細書 (従来)** コンフィギュレーション キーを代わりに使用するやむを得ない理由がない限り、改良された明細書転記機能の**小売明細書**コンフィギュレーション キーを使用することをお勧めします。 Microsoft は新しい改良された明細書転記機能に投資し続けるため、ユーザーが益を得るには早期にそれに切り替えることが重要です。 従来の明細書転記機能は、8.0 リリースから廃止される予定です。

## <a name="setup"></a>セットアップ

明細書転記機能の改良の一環として、**小売パラメーター**ページの**転記**タブの**明細書**クイック タブで、3 つの新しいパラメータが導入されました。

- **明細書のクリアを無効にする**– このオプションは、従来の明細書転記機能に対してのみ適用されます。 このオプションを**いいえ**に設定して、ユーザーが半転記の状態になっている明細書を削除するのを防ぎます。 半転記の状態になっている明細書が削除されると、データが破損します。 特別な事情でのみ、このオプションを**はい**に設定する必要があります。
- **計算時に在庫を引き当てる**– 在庫引当の**在庫の転記**バッチ ジョブを使用し、このオプションを**いいえ**に設定することをお勧めします。 このオプションを**いいえ**に設定すると、改良された明細書転記機能は、計算時に在庫引当のエントリを作成しようとしません (エントリが**在庫の転記**バッチ ジョブを通してまだ作成されていない場合)。 代わりに、機能は転記時にのみ、在庫引当のエントリを作成します。 この実装は設計上の選択であり、計算プロセスおよび転記プロセス間の時間枠が典型的に小さいという事実に基づいていました。 ただし、計算時に在庫引当を行う場合は、このオプションを**はい**に設定できます。

    このオプションの設定に関係なく、従来の明細書転記機能によって、明細書の計算プロセス中に常に在庫が引当られます (引当が**在庫の転記**バッチ ジョブを通してまだ行われていない場合)。

- **棚卸を無効化する必要がある**– このオプションを**はい**に設定すると、計算済金額とトランザクション金額の差額が、小売店舗の**明細書**クイック タブで定義されるしきい値以外であっても、明細書の転記プロセスが続行されます。

また、**小売パラメーター**ページの**転記**タブの**バッチ処理**クイック タブに次のパラメーターが導入されました。 

- **同時に転記する明細書の最大数** – このフィールドは、複数の明細書の転記に使用されるバッチ タスクの数を定義します。 
- **明細書ごとの注文処理の最大スレッド** – このフィールドは、1 つの明細書の販売注文を作成および請求するために、明細書の転記バッチ ジョブで使用されるスレッドの最大数を表します。 明細書の転記プロセスで使用されるスレッドの総数は、このパラメーターの値に**同時に転記する明細書の最大数**パラメーターを掛けた値に基づいて計算されます。 このパラメーターの値を高く設定しすぎると、明細書転記プロセスのパフォーマンスに悪影響を及ぼす可能性があります。
- **集計に含まれる最大トランザクション明細行** – このフィールドは、新しいトランザクションが作成される前に、1 つの集計トランザクションに含まれるトランザクション明細行の番号を定義します。 集計トランザクションは、顧客、営業日、財務分析コードなどのさまざまな集計基準に基づいて作成されます。 1 つの小売トランザクションからの行が異なる集計トランザクションに分割されないことに注意することが重要です。 これは、集計トランザクションの行数が、特徴的製品の数などの要因に基づいて若干増減する可能性があることを意味します。
- **店舗トランザクションを検証するスレッドの最大数** – このフィールドは、小売トランザクションの検証に使用されるスレッド数を定義します。 小売トランザクションの検証は、トランザクションが明細書に取り込まれる前に行われる必要がある必須ステップです。 また、**小売パラメーター**ページの**転記**タブ上にある**ギフト カード**クイック タブの**ギフト カード製品**を定義する必要もあります。 ギフト カードが組織によって使用されていない場合でも、これを定義する必要があります。

> [!NOTE]
> 明細書転記に関連する、さらに小売店舗および**小売パラメーター**ページで定義されるすべての設定およびパラメーターが、改良された明細書転記機能に適用されます。

## <a name="processing"></a>処理中

明細書は、**明細書をバッチ計算する**および**明細書をバッチ転記する**のメニュー項目を使用して、バッチで計算および転記されます。 また、明細書は、改良された明細書転記機能が提供する**小売明細書**メニュー項目を使用して、手動で計算および転記されます。

バッチで明細書を計算および転記するプロセスと手順は、従来の明細書転記機能でのものと同じです。 ただし、大幅な改良が、明細書のコア バックエンド処理に加えられています。 これらの改良は、プロセスをより強くし、状態およびエラー情報への可視性を高めます。 したがって、ユーザーはエラーの根本原因に対処でき、必要になるデータ破損およびデータ修正の発生なしで、転記プロセスを続行できます。

次のセクションでは、小売明細書および転記済明細書のユーザー インターフェイスに表示される、明細書転記機能の主要な改良点のいくつかについて説明します。

### <a name="status-details"></a>状態の詳細

計算および転記プロセス間の明細書転記ルーティンに、新しい状態モデルが導入されました。

次の表では、計算プロセス中のさまざまな状態およびその順序について説明します。

| 注文の状態 | 行政単位 (区画)      | 説明 |
|-------------|------------|-------------|
| 1           | 開始済    | 明細書が作成され、計算の準備ができています。 |
| 2           | マーク済     | 明細書の範囲にあるトランザクションは、明細書パラメーターに基づいて識別され、明細書 ID でマークされています。 |
| 3           | 計算済 | 明細行が計算され、表示されます。 |

次の表では、転記プロセス中のさまざまな状態およびその順序について説明します。

| 注文の状態 | 行政単位 (区画)                   | 説明 |
|-------------|-------------------------|-------------|
| 1           | 確認済                 | 複数の検証は、パラメーター (たとえば、廃棄請求金額)、および明細書と明細行 (たとえば、計算済金額とトランザクション金額の差額) に関連して行われます。 |
| 2           | 集計              | 名前付きおよび名前のない顧客の販売トランザクションは、コンフィギュレーションに基づいて集計されます。 すべての集計トランザクションが最終的に、販売注文に変換されます。 |
| 3           | 顧客注文が作成されました  | 集計されたトランザクションに基づき、販売注文がシステムで作成されます。 |
| 4           | 販売注文が請求されました | 販売注文が請求されます。 |
| 5           | 割引が転記されました        | 期間割引仕訳帳がコンフィギュレーションに基づいて転記されます。 |
| 6           | 収入/経費が転記されました   | 収入/経費トランザクションは、伝票として転記されます。 |
| 7           | 伝票がリンクされました         | 支払仕訳帳が作成され、対応する請求書にリンクされています。 |
| 8           | 支払が転記されました         | 支払仕訳帳が転記されます。 |
| 9           | ギフト カードが転記されました       | ギフト カード トランザクションは、伝票として転記されます。 |
| 10          | 投稿済                  | 転記済として明細書がマークされます。 |

前の表でのそれぞれの状態は本質的に依存せず、階層構造の依存関係は状態間で構築されます。 この依存関係は、上から下へ流れます。 状態を処理している間に、システムに任意のエラーが発生すると、明細書の状態は、前の状態に戻されます。 プロセスに続く再試行は、失敗した状態から再開し、移行し続けます。 このアプローチには、次の利点があります。

- ユーザーには、エラーが発生した状態への完全な可視性があります。
- データの破損が回避されます。 たとえば、従来の明細書転記機能では、いくつかの販売注文が請求されても、他のユーザーが開いているというインスタンスがありました。 請求書の転記にエラーがあったために、一部の支払仕訳帳には決済するための対応する請求書がないというインスタンスもありました。
- ユーザーは、明細書の**実行の詳細**グループで**状態の詳細**ボタンを使用して、明細書の現在の状態を表示できます。 ステータスの詳細ページには、3 つのセクションがあります。

    - 最初のセクションでは、エラーが発生したかどうか、エラー コードおよび詳細なエラー メッセージと共に、明細書の現在の状態を表示します。
    - 2 番目のセクションでは、計算プロセスのさまざまな状態を表示します。 視覚キューは、正常に実行されてき状態、エラーが原因で実行できなかった状態、およびまだ実行されていない状態を示します。
    - 3 番目のセクションでは、転記プロセスのさまざまな状態を表示します。 視覚キューは、正常に実行されてき状態、エラーが原因で実行できなかった状態、およびまだ実行されていない状態を示します。

また、2 番目と 3 番目のセクションのヘッダーは、関連するプロセスの全般的な状態を表示します。

### <a name="event-logs"></a>イベント ログ

さまざまな操作 (たとえば、作成、計算、削除、および転記)、および同じ操作の複数のインスタンスを経た明細書は、明細書のライフサイクル中に呼び出される可能性があります。 たとえば、明細書が作成および計算された後、ユーザーは明細書を削除してもう一度計算することができます。 明細書の**実行の詳細**グループの**イベント ログ**ボタンは、それらの操作が呼び出されたときに関する情報と共に、明細書で呼び出されたさまざまな操作の完全な監査証跡を提供します。

### <a name="aggregated-transactions"></a>集計トランザクション

転記プロセス中に、コンフィギュレーションに基づいて販売トランザクションが集計されます。 これらの集計トランザクションはシステムに格納され、販売注文を作成するのに使用されます。 各集計トランザクションは、システムで対応する 1 つの販売注文を作成します。 ユーザーは、明細書の**実行の詳細**グループで**集計トランザクション**ボタンを使用して、集計トランザクションを表示できます。

集計トランザクションの**販売注文の詳細**タブは、次の情報を表示します。

- **レコード ID**– 集計トランザクションの ID。
- **明細書番号**– 集計トランザクションが属する明細書。
- **日付**– 集計トランザクションが作成された日付。
- **販売 ID**– 販売注文が集計トランザクションから作成される場合、販売注文 ID。 このフィールドが空白の場合、対応する販売注文が作成されていません。
- **集計行の数**– 集計トランザクションおよび販売注文の明細行の合計数。
- **状態**– 集計トランザクションの最後の状態。
- **請求書 ID**– 集計トランザクションの販売注文が請求される場合、売上請求書 ID。 このフィールドが空白の場合、販売注文の請求書が転記されていません。

集計トランザクションの**トランザクションの詳細**タブは、集計されたトランザクションで引き出されたすべての小売トランザクションを表示します。 集計されたトランザクションの集計行は、小売トランザクションから集計されたすべてのレコードを表示します。 集計行は、品目、バリアント、数量、価格、正味金額、単位、および倉庫などの詳細も表示します。 基本的に、各集計行は、1 つの販売注文明細行に対応します。

**集計トランザクション**ページから、**販売注文を XML 形式でエクスポートする**ボタンを使用して、特定の集計トランザクションの XML をダウンロードできます。 XML を使用して、販売注文の作成および転記を含む問題をデバッグすることができます。 XML をダウンロードし、テスト環境にアップロードして、テスト環境での問題をデバッグします。 集計トランザクションの XML をダウンロードするための機能は、転記された明細書では使用できません。

集計トランザクション ビューには、次の利点があります。

- ユーザーには、販売注文の作成中に失敗した集計トランザクションや、請求時に失敗した販売注文の可視性があります。
- ユーザーには、トランザクションの集計方法への可視性があります。
- ユーザーには、小売トランザクションからの、販売注文への、売上請求書への完全な監査証跡があります。 この監査証跡は、従来の明細書転記機能では使用できませんでした。
- 集計された XML ファイルは、販売注文の作成および請求時に問題を識別しやすくします。

### <a name="journal-vouchers"></a>仕訳伝票

明細書の**実行の詳細**グループの**仕訳伝票**ボタンは、明細書用に作成され、割引、収入/経費勘定、ギフト カードなどに関連するすべてのさまざまな伝票トランザクションを表示します。

現時点では、プログラムは、転記済明細書のみに対するこのデータを表示します。

### <a name="payment-journals"></a>支払仕訳帳

明細書の**実行の詳細**グループの**支払仕訳帳**ボタンは、明細書用に作成されるすべてのさまざまな支払仕訳帳を表示します。

現時点では、プログラムは、転記済明細書のみに対するこのデータを表示します。

## <a name="other-improvements"></a>その他の改良

その他、明細書転記の機能に加えられた、ユーザーが表示できるバックエンド改良点です。 次にいくつか例を挙げます。

- 集計はスタッフ、端末、シフト エンティティを考慮しません。 より少ない集計パラメーターがあるため、少ない販売注文明細行を処理する必要があります。
- 小売トランザクション テーブルで発生したデッドロックは、拡張機能テーブルの追加を導入することによって、および小売トランザクション テーブルでの更新操作ではなく挿入操作によって減らされます。
- 実行中のバッチ タスクの数が、パラメーター化され制限されています。 したがって、この番号は、具体的に顧客の環境に対して微調整されます。 従来の明細書転記機能では、バッチ タスクは同時に無制限に作成されました。 結果として、管理不能な負荷、間接費、およびバッチ サーバー上のボトルネックが生じました。
- 明細書は、トランザクションの最大数を持つ明細書の優先順位付けによって、効率的に処理のキューに格納されます。
- **明細書をバッチ計算する**および**明細書をバッチ転記する**などのバッチ プロセスは、バッチ モードでのみ実行されます。 従来の明細書転記機能では、ユーザーは、マルチ スレッドであるバッチ処理とは異なり、単一スレッド操作である対話モードでこれらのバッチ プロセスを実行するよう選択できました。
- 従来の明細書転記機能では、バッチ タスクの任意の失敗は、エラー状態のバッチ ジョブ全体に据え置かれていました。 改良された機能では、バッチ タスクの失敗は、その他のバッチ タスクが正常に完了した場合に、バッチ ジョブをエラー状態に据え置きません。 エラーが原因で転記されなかった任意の明細書を確認できる、**小売明細書**ページを使用して、バッチの実行の転記状態を評価する必要があります。
- 従来の明細書転記機能では、最初に発生した明細書の失敗が、バッチ全体の失敗の原因となります。 残りの明細書は処理されません。 改良された機能では、一部の明細書が失敗した場合でも、バッチ処理はすべての明細書の処理を続行します。 1 つの利点は、エラーを含む明細書の正確な数への可視性を、ユーザーが取得することです。 したがって、ユーザーはすべての明細書が転記されるまで、エラー修正および明細書転記プロセスを実行する継続的なループで行き詰る必要はありません。

## <a name="general-guidance-about-the-statement-posting-process"></a>明細書転記プロセスに関する一般的なガイダンス

- バッチ実行がマルチスレッドに関するバッチ フレームワークの能力を最大限に活かすために、バッチで明細書転記プロセスを実行することをお勧めします。 マルチスレッドは、通常明細書転記に表示される大量のトランザクションを処理するために必要とされます。
- 品目モデル グループでマイナスの現物在庫を有効にし、シームレスな転記エクスペリエンスができるようにすることをお勧めします。 一部のシナリオでは、マイナスの現物在庫がない限り、マイナスの明細書は転記できない可能性があります。 たとえば、理論上、在庫に 1 単位の品目のみがあり、および品目の販売トランザクションと返品トランザクションがあった場合、マイナスの現物在庫が有効になっていない場合でもトランザクションは転記されます。 ただし、明細書転記プロセスは、単一の顧客注文で販売トランザクションと返品トランザクションの両方を取り込むため、販売明細行が最初に転記され、返品明細行がそれに続くという保証はありません。 したがって、エラーが発生します。 このシナリオでマイナスの現物在庫を有効にすると、トランザクション転記は悪影響を受けませんし、システムは在庫を正しく反映します。
- 明細書を計算および転記する間に、集計を使用することをお勧めします。 したがって、いくつかの集計パラメーターに対する以下の設定をお勧めします。

    - **小売** \> **本社の設定** \> **パラメーター** \> **小売パラメーター**の順にを移動します。 その後、**明細レベル**フィールドの、**在庫更新**クイック タブの、**転記**タブで、**集計**を選択します。
    - **小売** \> **本社の設定** \> **パラメーター** \> **小売パラメーター**の順にを移動します。 それから、**集計**クイック タブの、**転記**タブで、**伝票トランザクション**オプションを**はい**に設定します。