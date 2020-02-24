---
title: コール センターのカタログ
description: このトピックでは、Dynamics 365 Commerce でのカタログのコール センター固有の機能について説明します。
author: josaw1
manager: AnnBe
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e4d2b1f4b7fb9394f54674f9622c8a8edd435311
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023137"
---
# <a name="call-center-catalogs"></a>コール センターのカタログ

[!include [banner](includes/banner.md)]

このトピックでは、Dynamics 365 Commerce でのカタログ能力にリンクされたコール センター固有の機能について説明します。

Commerce にあるカタログ機能は、複数の目的で使用できます。 最初に、カタログ機能はサード パーティの電子商取引統合をサポートするために作成されました。 カタログの設定には、製品およびサード パーティの電子商取引ソリューションによって消費の外部で発行した属性のグループを作成する会社が許容されます。

コール センター チャネル サポートが追加された際、カタログのコンセプトが拡大され、従来型の直接消費者マーケティング カタログに関連する機能のサポートおよび管理のための追加機能が追加されました。 直接消費者の会社により多くの場合、印刷されたカタログを生成し、そして顧客の 1 つまたは複数のセグメントに郵送されます。 これらのカタログは、顧客が注文作成時のカタログ ID コードを提供する場合にのみ授与される特別なプロモーションまたはオファーを持っています。

直接消費者のマーケティング企業は、これらのカタログへの対応を追跡することに重点を置いて、それらを生産して郵送するコストが正当化されることに焦点を当てています。 応答を追跡するため、コードは従来カタログの裏面に印刷され、次にカタログ受取人が電話で注文するために呼び出したときに要求され適用されます (または従来より、顧客が注文オンラインを配置するときに、コードが入力される場合があります)。 このカタログの追跡コードを識別するために使用されているさまざまな業界条件がありますが (キー コード、プロモーション コード、カタログ コード、ソース コードを含む)、**ソース コード ID** として Commerce のコードを参考にします。

## <a name="basic-catalog-setup"></a>基本カタログ設定

**Retail と Commerce** \> **カタログと品揃え** \> **すべてのカタログ**の順に移動して、カタログをコンフィギュレーションします。

新しいカタログを作成する際は、まず 1 つまたは複数のチャネルにカタログをリンクする必要があります。 これは、**カタログ設定**フォームの**Commerce チャネル** クイック タブで行われます。 **追加**をクリックし、1 つまたは複数のチャネルを選択します。 選択されたチャンネルにリンクした品目のみが[品揃え](https://docs.microsoft.com/dynamics365/unified-operations/retail/assortments)カタログを作成するときに使用することができます。

カタログに製品を追加するには、ナビゲーション階層を選択する必要があります。 ナビゲーション階層は、カタログのカテゴリ構造をサポートします。 **カタログ** ページの **Commerce チャネル** クイック タブで、選択されたチャネルにリンクされているナビゲーション階層のいずれかから選択する必要があります。 ナビゲーション チャネルが以前のチャネルにリンクされなかった場合は、**Retail と Commerce** \> **チャネル設定** \> **チャネル カテゴリおよび製品属性**の順に移動し、ナビゲーション階層既定を各チャネルにリンクします。

**カタログ設定**ページの**カタログ**メニュー タブで、**製品を追加**をクリックし製品をカタログに追加するか、ナビゲーション階層内のノードを選択します (ノードを選択することで画面プレゼンテーションを変更し、カタログ内のカテゴリへ製品を直接追加することができます)。

メイン カタログ ヘッダー ビューへ戻るには、カタログ階層のトップ ノードをクリックします。 必要に応じて、**一般**クイック タブで実質的な有効期限を構成します。

カタログが使用可能になる前に、発行される必要があります。 **カタログ**メニューで**検証カタログ**をクリックし、検証を処理します。 これは必要なアクションはであり、必要な設定が正しいことを検証します。 検証詳細を表示するには、**結果を表示**をクリックします。 エラーが見つかった場合は、データを修正し、検証が合格するまでもう一度実行する必要があります。

検証確認後、メニューの**ワークフロー**をクリックし、承認ワークフローを開始します。 **ワークフロー**メニューの**送信**をクリックし、プロセスを実行します。 **Retail と Commerce** \> **本社の設定** \> **Commerce ワークフロー**から、ワークフローの手順と承認済みユーザーをコンフィギュレーションします。 ワークフローは、カタログを**承認済**ステータスに入れるために必要な手順を定義します。 カタログが**承認済**ステータスにある際、**カタログ**メニューで**発行**オプションをクリックし、プロセスを完了します。 カタログが**発行済**ステータスで実行後、コール センター注文エントリで使用でき、タログ プロセスを送信します。

## <a name="use-catalogs-to-drive-sales-order-pricing-and-promotions"></a>販売注文の価格およびプロモーションを増やすためカタログを使用

コール センターで使用するカタログを定義するためのコア理由は、特定の価格およびそのカタログのプロモーションを構成できるようにすることです。 このカタログから注文する顧客は、カタログの**ソース コード ID** が適用された場合、コール センター注文エントリの価格およびプロモーションを受け取ります。

カタログ特定の価格を構成するには、**カタログ**から**グループ価格**オプションを選択し、カタログに 1 つまたは複数の価格グループをリンクします。 同じ価格グループにリンクされていたすべての取引契約、価格調整仕訳帳、および詳細割引 (しきい値、数量、組み合わせ) は、顧客がカタログから注文する際に適用されます。

**ソース コード**クイック タブで**追加**をクリックし、1 つまたは複数の**ソース コード ID** 識別子をカタログに追加します。 これは、販売注文ヘッダー (および明細行) にコール センター注文入力中に適用されるコードです。 このコードは、カタログに販売注文をリンクさせ、最終的に価格グループおよび設定された特別価格とプロモーションに使用されます。

## <a name="use-the-source-id-to-track-costs-and-response-rates"></a>ソース ID を使用し、原価と反応率を追跡

**ソース コード ID** を定義する際、必要に応じて ID を**ターゲット マーケット ID** にリンクします。 **ターゲット マーケット ID** は、**Retail と Commerce** \> **顧客** \> **ターゲット マーケット**で定義することができます。 ターゲット マーケットは、ユーザー定義のセグメントに属している顧客または見込顧客の一覧です。 ソース コード ID に顧客または見込顧客をリンクすることは、カタログの受信者に可視性を高めます。 顧客がターゲット マーケットにリンクし、そのターゲット マーケットが有効なソース コード ID/カタログにリンクしている場合、コール センターでは、顧客が**顧客サービス**ページの**顧客**メニュー タブによる**ソース コード**メニュー オプションを選択して受け取ったカタログを確認することが可能です。 注文の入力時に、コール センターのユーザーはまた顧客が販売注文ヘッダー上の**ソース**ドロップダウン リストで送られた特定のカタログを見ることもできます。 フィルターを**すべて**から**対象**に変更することで、ユーザーが顧客に送信された特定の有効カタログを参照できます。 これは、顧客がカタログを忘れたり、販売注文を作成を呼び出す際にカタログ コードを見つけたり読んだりすることができない場合に役立ちます。

カタログに複数のソース コード ID をリンクすることは可能です。 これは、異なるセグメントによって会社が回収率を追跡する際、頻繁に必要です。 会社は固有のカタログ コードを違う顧客セグメントに与え、特定のカタログ イベントの中で、セグメント レベルまで下げて、応答レートを追跡できます。

特定の**ソース コード ID** レコードを選択し、**ソース コード**クイック タブで**詳細**オプションをクリックすると、営業プロジェクション、メーリング コストおよび日付がキャプチャできる追加の場所を提供します。 このデータは、カタログの有効性についての詳細な分析を行うのに便利です。 ユーザーは時間の経過と共にこのページに戻り、**ソース コード分析**および**プロモーションを比較**ボタンを使用して、現在の販売データに基づく分析のレポートをトリガーし、コストと予算を実績と比較します。

## <a name="configure-catalog-specific-order-and-item-scripts"></a>カタログに固有の注文および品目のスクリプトを設定

コール センターのユーザーが販売注文を作成する際、スクリーン スクリプトを使用できます。 これらのテキスト ベースのスクリプトは、ユーザーが顧客に伝えるべき追加情報を提供するか、またはコール センターのユーザーが販売注文を作成している時にレビューおよび反応する必要がある内部メモまたはアラームかもしれません。

異なるカタログ用の異なるスクリプト セットを持つことは便利です。 **スクリプト**クイック タブで、定義済みのスクリプトはカタログにリンクすることができます。 スクリプトが注文の開始時 (ソース コード ID が注文ヘッダー上で入力され次第) または注文の終了時 (販売注文の概要フォームで) に表示されるかどうかを特定するには、**タイミング**フィールドを使用します。

カタログ階層のノードを選択および**製品**クイック タブでデータを扱う際、ユーザーが**スクリプト**アクションを使用して、カタログまたは品目に固有のスクリプトをリンクすることも可能です。

## <a name="configure-catalog-specific-up-sell-and-cross-sell-items"></a>カタログ固有のアップセルおよびクロスセル品目を構成

アップセル/クロスセルの提案を品目にリンクすることで、製品設定から実行できますが、場合によっては、会社が固有のカタログから固有の製品を注文する顧客に特別なアップセル/クロスセル品目を促進させたいかもしれません。 **製品**クイック タブで品目を選択し、**アップセル/クロスセル品目**をクリックして、製品をカタログから選択した品目を購入する顧客にアップまたはクロス販売に設定します。 コール センターの注文入力時に、カタログ固有のアップセル/クロスセル品目は、通常の製品構成によってその品目に対して設定されている可能性のある標準アップセル/クロスセル製品の代わりに、画面に表示されます。

アップセル/クロスセル品目は、両品目が注文入力中に表示される際、ユーザーに表示される固有メッセージを表示するスクリプト機能も利用できます。 カタログ製品用に構成されているアップセル/クロスセル製品に関連付けられてスクリプトは、コール センターの注文入力にカタログのソース コードが適用される場合にのみ表示されます。

## <a name="catalog-page-analysis"></a>カタログ ページ分析

**カタログ**タブで、オプションは**カタログ ページ**を構成するために利用可能です。 この機能を使用すると、印刷されたカタログと関連された原価の特定ページおよびページ タイプを定義できます。

カタログに製品を構成する際、**製品のページ レイアウト**アクションを使用し、固有ページ、ページの割合および品目のページ詳細位置を定義します。 このデータを構成すると、ユーザーは**カタログ領域分析レポート**を利用できます。 このレポートは、**Retail と Commerce** \> **コール センター レポート** \> **カタログ領域分析**レポートに移動することで検出されます。 このレポートは、カタログ (カタログのソース ID が注文ヘッダーまたは明細行に関連付けされた販売注文) および従来型の直接マーケティング**平方インチ分析**レポートに与えるページと原価の関連付けされた割合に対して販売を分析するものです。

## <a name="catalog-requests"></a>カタログ要求

カタログが設定および Commerce で公開され、**送信カタログ**機能を利用することができます。 この機能は、**顧客検索**および**顧客サービス**ページで利用できます。 **顧客検索**または**顧客サービス**から選択された顧客アカウントを表示しながら顧客レコードを選択すると、ユーザーは公開済みで有効なカタログの一覧から選択できるようダイアログ ボックスをオープンする**送信カタログ**オプションを選択できます。 ユーザーは、カタログ、数量、および送信する特定のソース コード ID を選択できます。 **送信**ボタンをクリックする際、要求は保存され、**カタログ要求**レポートを印刷して管理することができます。 このレポートは、**Retail と Commerce** \> **コール センター レポート** \> **カタログ要求レポート**に移動することで検出されます。 カタログを要求した顧客の名前および住所を含むすべてのカタログ要求が、一覧表示します。 レポートは内部的に使用することができ、データはカタログを顧客に物理的に送るための外部プロセスをサポートするサード パーティへ送信することができます。

## <a name="additional-features"></a>追加機能

**カタログ**タブでは、**支払スケジュール**および**無料製品**を構成するオプションも利用可能です。 カタログにリンクされたソース コード ID がコール センターの注文入力時に適用される場合、顧客は無料製品または既定の固有カタログ支払スケジュールの使用に適しています。 システム内のすべての有効な支払スケジュールではなく、カタログにリンクされた支払スケジュールからのみ選択できるように顧客を制限する必要がある場合、**カタログ計画のみ可能**チェック ボックスは、その制限を強制するよう定義されているソース コード ID の 1 つ以上を選択することができます。

## <a name="additional-notes"></a>追加注記

現時点では、ソース コード ID がコール センターの販売注文に適用される際、価格、プロモーション、スクリプトおよびアップセル/クロスセルの特定カタログを推進するために使われます。 システムでは、販売注文の注文からカタログに含まれていない製品を禁止または防止しません。 カタログの一部でない品目が注文される場合、システムでは品目価格またはプロモーションのコール センター チャネル (**Retail と Commerce** \> **チャネル** \> **コール センター** \> **すべてのコール センター**) で定義された**価格グループ**を最初に使用します。 特定のチャンネルの価格が見つからない場合は、品目の基準販売価格が使用されます。