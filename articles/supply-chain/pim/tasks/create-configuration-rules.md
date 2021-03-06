---
title: コンフィギュレーション ルールの作成
description: この手順は、分析コード ベースのコンフィギュレーションを使用して BOM 明細行の特定の組み合わせを使用または禁止できるコンフィギュレーション ルールを作成します。
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMTable, BOMConfigRule, ConfigItemIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f15c0328e391d81c4c977f974553ae9135b207c
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844900"
---
# <a name="create-configuration-rules"></a>コンフィギュレーション ルールの作成

[!include [task guide banner](../../includes/task-guide-banner.md)]

この手順は、分析コード ベースのコンフィギュレーションを使用して BOM 明細行の特定の組み合わせを使用または禁止できるコンフィギュレーション ルールを作成します。 この手順の作成に使用するデモ データの会社は USMF です。 これは、分析コード ベースのコンフィギュレーションでの組み合わせの作成方法を説明する 8 つの手順の 7 番目です。

1. [製品情報管理] > [部品表およびフォーミュラ] > [部品表] の順に移動します。
2. 一覧で、目的のレコードを見つけ、選択します。
    * [分析コードベースのコンフィギュレーションの BOM] を検索して選択します。  
3. [アクション] ウィンドウで、[オプション] をクリックします。
4. [ビューの変更] をクリックします。
5. [ヘッダーの表示] をクリックします。
    * [コンフィギュレーション ルート] クイック タブにアクセスするヘッダー表示を開きます。  
6. [コンフィギュレーション ルート] セクションを展開または折りたたみます。
    * [コンフィギュレーション ルート] クイック タブを展開モードにする必要があります。  
7. [コンフィギュレーション ルール] をクリックします。
8. [新規] をクリックします。
9. 一覧で、選択された行をマークします。
10. [品目番号] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
    * 現在のコンフィギュレーション グループの品目が表示されます。 ルールの条件を表す 1 つを選択します。  
11. 一覧で、選択された行のリンクをクリックします。
12. [方法] フィールドで、オプションを選択します。
    * 別のコンフィギュレーション グループの品目の選択または選択解除を使用することができます。  
13. [派生グループ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
14. 一覧で、目的のレコードを見つけ、選択します。
15. 一覧で、選択された行のリンクをクリックします。
    * 目的のコンフィギュレーション グループを選択します。  
16. [派生品目番号] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
17. 一覧で、選択された行のリンクをクリックします。
    * 選択された方法によって選択または選択解除となる品目番号を選択します。  
18. ページを閉じます。

