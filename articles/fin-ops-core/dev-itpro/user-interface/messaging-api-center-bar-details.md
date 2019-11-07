---
title: メッセージ センター、メッセージ バー、およびメッセージ詳細 API
description: このトピックでは、メッセージング システムについて説明します。
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 64153
ms.assetid: b69ec992-9bde-469e-99bb-773feb9489ff
ms.search.region: Global
ms.author: aorth
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 68daf17e5f40782a828f03cc5f9bcf7222a77b55
ms.sourcegitcommit: 574309903f15eeab7911091114885b5c7279d22a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "2658835"
---
# <a name="message-center-message-bar-and-message-details-api"></a>メッセージ センター、メッセージ バー、およびメッセージ詳細 API

[!include [banner](../includes/banner.md)]

このトピックでは、メッセージング システムについて説明します。

<a name="message-api"></a>メッセージ API
-----------

Microsoft Dynamics AX 2012 には、**info()**、**warning()**、および **error()** に対する最も多い呼び出しの一覧を表示する "1 つのサイズですべてをまかなう" 汎用的なウィンドウがあります。 このウィンドウは、適切かつ一般的には「情報ログ」または「Infolog」と略して呼ばれていました。 情報ログは場合によっては役に立つツールでしたが、「one size fits all」アプローチは重要度を区別し、ユーザーが中断すべきか否かを決定する必要性において効果がないとみなされました。 新しいメッセージング システムでは、エクスペリエンスが向上します。 このより豊かで強力なメッセージング システムには、次の機能が含まれています。

-   コンテキストのあるメッセージの関連性が強化されました (フォームとグローバル)。
-   中断のレベル (なし、軽微、および中断) を強化しました。
-   メッセージの種類間での明確さと、その用途が強化されました。
-   メッセージを表示するために使用されるコントロールは、フォーム コンテキストに基づいて deterministic です。

## <a name="legacy-api-support-info-warningcheckfailed-and-error"></a>旧 API サポート: info()、warning()/checkfailed()、および error()
従来の **info()**、**warning()**、および **error()** アプリケーション プログラミング インターフェイス (API) はまだサポートされています。 ただし、それらはフレームワークの新しいメッセージング システム上に配置されるようになり、宛先が確定的になります。 つまり、ユーザーにメッセージを表示するための最善の方法を決定するために、呼び出しのコンテキストを使用します。 一般に、API の使用がフォームから生成された場合、そのメッセージが同じフォーム上のメッセージ バーで表示されます。 (ドロップ ダイアログおよびスライダー ダイアログはどちらもフォームとみなされます) **注記:** このルールにいくつかの例外があります。 スライダーのダイアログ ボックスでは、メッセージ API が呼び出され、そのダイアログ ボックスが終了した場合は、スライダーの親フォームにメッセージが表示されます。 または、そのスライダーがクローズされたワークスペースでホストされている場合、メッセージはメッセージ センターにルーティングされます。 メッセージ API は決してメッセージを「食べる」ことはありません。 適切なホスト フォームが見つからない場合は、メッセージがメッセージ センターに送信されます。 次のスクリーン ショットは、情報、警告/ checkfailed、およびエラー バーを示しています。 

[![スクリーン ショットは、情報、警告/ checkfailed、およびエラー バーを表示](./media/1_api.jpg)](./media/1_api.jpg)

## <a name="message-api-and-batch-or-asynchronous-operations"></a>メッセージ API とバッチまたは非同期操作
**info()**、**warning()**/**checkfailed()**、または **error()** が非同期プロセス (たとえば、バッチ) から呼び出された場合、考慮するフォーム コンテキストはなく、メッセージはメッセージ センターに送信されます。 (メッセージ センターを開くには、ナビゲーション バーのフラグ アイコンをクリックします。) 

[![メッセージ センターのメッセージ](./media/2_api.png)](./media/2_api.png)

## <a name="legacy-api-support-setprefix"></a>旧 API サポート: SetPrefix()
このバージョンは **SetPrefix()** API もサポートしています。 これは、まだ下位互換性を維持しています。 ただし、**SetPrefix()** の結果は積極的にユーザーを中断しません。 代わりに、結果は収集され、(以前のバージョンのように) 保存されて、メッセージ バーまたはメッセージ センターの通知がユーザーに表示されます。 この通知は、関連するタスクが完了し、ユーザーが確認する必要のあるメッセージがある可能性があることを示します。 「結果の通知」メッセージは、実際にはタスクによる **SetPrefix()** の最初の呼び出しを使ってメッセージをフレーム化します。 この動作は、最初の呼び出しが結果の「タイトル」であった以前のバージョンの動作に類似しています。 この例では、「転記の結果」が **SetPrefix()** への最初の呼び出しのアプリケーションから取得されます。

[![SetPrefix の例](./media/3_api.png)](./media/3_api.png) 

ユーザーは、**メッセージの詳細**をクリックして、新しい**メッセージの詳細**ウィンドウを開きます。 

[![メッセージの詳細ウィンドウ](./media/4_api.png)](./media/4_api.png)

| メッセージ タイプ | 説明                                                                                                                                                                                                                                                                                                                                  |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 情報         | *通知*は、現在のユーザ活動と関連しないイベントについてユーザーに通知します。 この通知は、ユーザー アクションまたは重要なシステム イベントによって発生する可能性があります。また、製品から有用な情報を提供することもできます。 **info()** API を使用してユーザーに通知します。                                                 |
| 警告      | *警告*は、今後問題が発生する可能性のある状態についてユーザーに警告します。 ステータスが正しくないデータはエラーではありません。 ただし、そのデータを使用しようと試みるとエラーが発生する可能性があり、したがって無効なデータが警告をトリガーします。 データ検証の問題を表現するには、**warning()** または **checkfailed()** API を使用します。 |
| エラー        | *エラー*は既に発生した問題についてユーザーに警告します。 失敗したユーザー アクションは、エラーをトリガーします。 パッシブ エラー (非中断) を表現するには、**error()** API を使用します。 ユーザーへの中断エラーを表現するには、**box::** API を使用します。                                                                  |

メッセージング システムは、確定的 です。 結果は、メッセージがコードから呼び出されたかどうかによって、メッセージ バーまたはメッセージ センターのどちらかに表示されます。

-   同期のフォーム アクション (ユーザーが結果を待つ必要があるアクション) の結果であるメッセージについては、結果は現在のフォームのメッセージ バーに表示されます。 例外は、アクションの開始直後に閉じられたスライダー ダイアログのメッセージです。 これらのメッセージは親フォームに表示されます。
-   非同期 (切断された) アクションについては、ユーザーは、アクションの処理中にその他のタスクを続行でき、その結果はメッセージ センターに表示されます。

同期または他のフォーム アクションまたは評価でエラーが発生した場合は、次の 2 つのタイプのエラーがあります。

-   中断エラーは、直接アクションを完了することができないため、直ちに修正する必要があります。 このタイプのエラーはダイアログ ボックスに表示されます。
-   多くの場合にタスク/バッチ操作の失敗に終わる非中断エラー。 このタイプのエラーはメッセージ バーに表示されます。


<a name="additional-resources"></a>その他のリソース
--------

[ユーザー インターフェイス開発ホーム ページ](user-interface-development-home-page.md)


