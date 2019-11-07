---
title: 埋め込みビューアを使用してPDFドキュメントのプレビューをする
description: このトピックでは、ビジネスドキュメントを表示するにあたり、埋め込みPDFプレビューオプションを使用する方法について説明します。
author: tjvass
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: Platform update 28
ms.openlocfilehash: 75d1eeba976ffae690bc1fd6fcdcee4d816c609a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191557"
---
# <a name="preview-pdf-documents-with-an-embedded-viewer"></a>埋め込みビューアを使用してPDFドキュメントのプレビューをする

[!include[banner](../includes/banner.md)]

埋め込みPDFプレビューオプションを利用することにより、ビジネスドキュメントの作成にまつわるアプリケーションエクスペリエンスび効率を上げることができます。 Finance and Operations アプリケーションは、本サービスによって作成されたビジネスドキュメントをプレビューするにあたって最新のエクスペリエンスをお届けします。 組み込みのツールバーを使用することで、ドキュメントの閲覧やダウンロード、またはローカルに接続されている機器での印刷ができます。

埋め込みのビューアーを使うと、画面条の表示内容と印刷された内容に整合性を持たせることができます。 加えて、従来の操作と比較してレポートの表示時間が大幅に短縮されます。 Preview オプションは対応するすべての機器での使用が可能であり、サードパーティ製のソフトウェアを追加する必要はありません。 組み込みのビューア ツールバー オプションを使用すると、ドキュメントのダウンロードおよび閲覧が簡単になります。

次の図は、最新のビジネスドキュメントをプレビューした例です。
![PDFプレビュー フォーム](./media/pdf-document-preview.png)

従来のHTMLベースのプレビューは、実物のドキュメントに即したプレビューへと取って代わります。 最新のPDFプレビュー機能には、いくつかの重要な特徴があります。 以下のような特徴を持っています:

- 画面上に表示された内容を忠実に印刷処理します。
- オンプレミス配置を含む、さまざまなデバイスおよびプラットフォーム上であっても、常に整合したドキュメントレポートプレビューを提供します。
- サーバーサイド レンダリングにより、ドキュメントを作成する際の効率が向上します。
- 組み込みツールによって、ビジネスドキュメントの内容をすばやく閲覧することができます。

## <a name="accessing-the-pdf-preview-experience"></a>PDFプレビュー機能にアクセスする
利用可能となるPDFドキュメント ビューアー コントロールは、ほとんどの配置タイプで使用できるようになっています。 ただし、ワンボックス配置の場合は、 **レポートオプション**  ページにてPDFプレビュー機能を有効にする必要があります。 PDFのプレビューを有効にするには、以下の手順を実行します。 

1) ブラウザウィンドウのURL末尾に "& Mi = sysreportadministration" を追加して **レポートオプション** に移動します。
2) **埋め込みビューアを使用してドキュメントをプレビューする** フィールドを **はい** と設定します。
3) **保存**をクリックします。

## <a name="additional-feature-information"></a>追加の機能

- 既定では、展開/折りたたみが可能なセクションが用意されています。 これらのインタラクティブな操作は、PDFドキュメントが作成された後には機能しなくなります。
- プリンターのドロップダウンメニューから、ローカル接続されている機器を選択することができます。 ここで表示されるリストには、サービスを通じて接続されるネットワークプリンターは含まれません。
- ドキュメントは組み込みツールバーのアクションを使用してローカルデバイスにダウンロードされます。
- アプリケーション拡張機能を使用して、PDFドキュメント内の埋め込みドリルスルー リンクを有効にすることができます。
- PDF以外の形式のドキュメントを作成するには、 **印刷先** オプションを使用します。
