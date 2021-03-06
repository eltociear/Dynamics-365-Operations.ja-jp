---
title: Power Apps ホスト コントロール
description: Power Apps ホスト コントロールを使用すると、アプリを Power Apps から Finance and Operations アプリの 1 つに埋め込むことができます。
author: TLeforMicrosoft
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 16061
ms.assetid: 80c93e91-1952-44ce-af93-a17965ee476a
ms.search.region: Global
ms.author: tlefor
ms.search.validFrom: 2017-04-26
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2fd603139d2798d5f8f2e1fcb18a0ca2713c6566
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017717"
---
# <a name="power-apps-host-control"></a>Power Apps ホスト コントロール

[!include [banner](../includes/banner.md)]

Microsoft Power Apps では、作成したアプリ、または別の人が作成してユーザーと共有したアプリを使用して組織データを管理できます。 [電話などのモバイル デバイス](https://powerapps.microsoft.com/tutorials/run-app-client/) または [ブラウザー](https://powerapps.microsoft.com/tutorials/run-app-browser/) で実行するアプリ。 Microsoft Visual Studio 開発者エクスペリエンスを使用する開発者は、アプリを Finance and Operations アプリに組み込むこともできます。 Power Apps の詳細については、[https://powerapps.microsoft.com](https://powerapps.microsoft.com/) を参照してください。

## <a name="host-an-app-from-power-apps-on-a-page"></a>ページの Power Apps からアプリをホストする

1.  Power Apps で、ホストする Web ベースのアプリを検索し、**アプリ ID** 値を記録またはコピーします。
  
    ![アプリ ID](media/powerapps-appid.png)
  
2.  Visual Studio でプロジェクトを開き、フォーム デザイナーで、Power Apps ホスト コントロールのインスタンスをページに追加します。
3.  **プロパティ** ウィンドウに**アプリ ID** の値を入力します。
4.  ページでアプリが現在のデータ ソースを共有、またはそこにリンクされている場合、アプリで表示するデータのプライマリまたはリンクされたキー フィールドの ID を渡すことができます。 この場合、ID を**エンティティ ID**、**エンティティ ID データ ソース/フィールド**、または **DataMethod** プロパティの値で指定します。 この値は、アプリにパラメーター値として渡され、アプリはその値を使用して、リンクされているデータを取得する必要があります。 
    
    ![Power Apps ホスト コントロールのプロパティ ウィンドウ](media/powerapps-properties.png)
    
5.  場合によっては、Microsoft によって提供される開発またはサンドボックス Power Apps 環境でアプリをホストする場合があります。 この場合、**Power Apps 環境のオーバーライド** プロパティの値としてそのオーバーライド URL を指定する必要があります。

サイズは、コントロールを配置したコンテナーによって決定されます。 使用可能なスペースが限られているフォーム パターンでコントロールを配置し、アプリが使用可能領域よりも大きく設計されている場合、埋め込みアプリにスクロール バーが表示されるようになります。
