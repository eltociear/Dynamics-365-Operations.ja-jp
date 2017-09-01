--- 
title: "フォーミュラのコピー"
description: "多少の違いはあっても、既存のフォーミュラと同じ構成要素を含んでいるフォーミュラを作成することに焦点を当てています。"
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: eafa45ef371c6b327a31e2c591a723e72d0e8479
ms.contentlocale: ja-jp
ms.lasthandoff: 07/27/2017

---
# <a name="copy-a-formula"></a>フォーミュラのコピー

[!include[task guide banner](../../includes/task-guide-banner.md)]

多少の違いはあっても、既存のフォーミュラと同じ構成要素を含んでいるフォーミュラを作成することに焦点を当てています。 式明細行を作成するため、[コピー] 機能を使用して必要な構成要素のほとんどを持つ既存の式をコピーできます。 次に、新しいバージョンの個々の行に必要な変更を加えることができます。 [コピー] 機能を使用すると、ほぼ同一である複数の式を作成する必要はありません。 このタスクの作成に使用するデモ データの会社は USP2 です。


## <a name="create-a-formula"></a>フォーミュラの作成
1. [製品情報管理] > [部品表およびフォーミュラ] > [フォーミュラ] の順に移動します。
2. [新規] をクリックします。
3. [フォーミュラ] フィールドに値を入力します。
4. [名前] フィールドに値を入力します。
    * 意味のあるフォーミュラ名を入力します。  
5. [サイト] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
6. 一覧で、選択された行のリンクをクリックします。
7. [品目グループ] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
8. 一覧で、目的のレコードを見つけ、選択します。
9. 一覧で、選択された行のリンクをクリックします。
10. [保存] をクリックします。

## <a name="copy-formula-lines"></a>フォーミュラ明細行のコピー
1. アクション ウィンドウで、[フォーミュラ] をクリックします。
2. [コピー] をクリックします。
3. [品目番号] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
4. 一覧で、選択された行のリンクをクリックします。
5. [フォーミュラバージョン] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
6. 一覧で、選択された行のリンクをクリックします。
7. [OK] をクリックします。

## <a name="adjust-copied-formula-lines"></a>コピーしたフォーミュラ明細行の調整
1. 一覧で、選択された行をマークします。
2. [削除] をクリックします。
3. [はい] をクリックします。

## <a name="approve-formula"></a>フォーミュラを承認
1. アクション ウィンドウで、[フォーミュラ] をクリックします。
2. [フォーミュラを承認] をクリックします。
3. [承認者] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
4. 一覧で、選択された行のリンクをクリックします。
5. [選択] をクリックします。
6. [OK] をクリックします。

