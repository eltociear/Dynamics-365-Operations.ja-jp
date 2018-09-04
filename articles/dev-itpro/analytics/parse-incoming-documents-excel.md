---
title: "Excel 形式の受信ドキュメントの解析"
description: "このトピックでは、受信した Microsoft Excel ファイルに含まれる内容を解析する電子申告 (ER) 形式の設計に関する情報を示します。"
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 32fd82f0e46068c7ed7bfcfddc4ff84603bd20b4
ms.contentlocale: ja-jp
ms.lasthandoff: 08/09/2018

---

# <a name="parse-incoming-documents-in-excel-format"></a>Excel 形式の受信ドキュメントの解析

[!include[banner](../includes/banner.md)]

Microsoft Excel のブック (XLSX 形式のファイル) でデータを表す、受信した Microsoft Excel ファイルを解析する電子申告 (ER) の形式を設計できます。 その後、アプリケーションのデータを更新するのに、これらのファイルからの内容を使用できます。 これは、次のような場合に便利です。

- 新しいモデルおよびフォーマットをデザインし、実行時にテストします。 この場合、Excel は実際のアプリケーション データをシミュレーションします。
- アプリケーションを超えたデータを Excel で管理し、特定のレポートを送信するのに、このデータをインポートします。

この機能の詳細については、タスク ガイド **Microsoft Excel ファイルからの ER インポート データ (第 1 部: 形式の設計)** および **Microsoft Excel ファイルからの ER インポート データ (第 2 部: データのインポート)** を実行してください (7.5.4.3 IT サービス/ソリューション コンポーネントの取得/開発 (10677) 業務プロセスの一部)。 これらのタスク ガイドは、 受信ドキュメントから情報をインポートしてアプリケーション データを更新する、ER 形式を使用した受信した Excel ファイルの解析方法を説明します。 タスク ガイドは [Microsoft ダウンロード センター](https://go.microsoft.com/fwlink/?linkid=874684)からダウンロードできます。

上記のタスク ガイドを完了するには、次のファイルをダウンロードしてください。

| コンテンツの説明                         | ファイル                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| .XLSX 形式の受信ファイル - テンプレート    | [1099import template.xlsx](https://go.microsoft.com/fwlink/?linkid=862266) |
| .XLSX 形式の受信ファイル - サンプル データ | [1099import data.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)     |

次のタスク ガイド [ER Create が外部ファイルからデータをインポートするために必要な設定](./tasks/er-required-configurations-import-data.md)を、現在の Dynamics 365 for Finance and Operation アプリケーションで実行していない場合、次のファイルをダウンロードしてください。

| コンテンツの説明    | ファイル                                                            |
|------------------------|-----------------------------------------------------------------|
| ER モデル構成 | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=862266) |
