---
title: 転記された仕訳帳の仕訳入力
description: この手順では、転記された仕訳入力の仕訳を行う方法について説明します。
author: aprilolson
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e20229ca910aa0d7d820434c22edf5a27030bba5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175511"
---
# <a name="journalize-posted-journal-entries"></a>転記された仕訳帳の仕訳入力

[!include [task guide banner](../../includes/task-guide-banner.md)]

この手順では、転記された仕訳入力の仕訳を行う方法について説明します。 この手順では、デモ データの会社 USMF を使用します。

1. **ナビゲーション ウィンドウ**で、**モジュール > 一般会計 > 元帳の設定 > 一般会計パラメーター**の順に移動します。
2. **拡張仕訳元帳**フィールドは、はいまたはいいえに設定します。 [はい] の場合は、レポートの出力が異なります。
3. 仕訳プロセスが実行されなかった場合に、期間を終了するかどうかを選択します。 このオプションが [はい] に設定されている場合、期間は仕訳プロセスがその期間に対して完了するまで、閉じることはできません。  
4. ページを閉じます。
5. **ナビゲーション ウィンドウ**で、**モジュール > 一般会計 > 定期処理タスク > 仕訳**の順に移動します。
6. **フィルター**をクリックします。
7. 定義するフィルター基準の行を強調表示します。
8. **基準**フィールドで、フィルター基準を入力または選択します。
9. **OK** をクリックして、フィルター ページを閉じます。
10. **OK** をクリックして仕訳入力プロセスを開始します。 レポートは、プロセスが完了した後生成されます。  

