---
title: テスト ケースのチェーンへの変数のコピー
description: このトピックでは、 Regression Suite Automation Tool を使用してテスト ケースを連鎖させる方法 (テストが他のテストに値を渡す機能) について説明します。
author: robadawy
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: 21631
ms.search.region: Global
ms.author: robadawy
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c625bc4f9ce57489c20a9f4f0e490d4df8d5f6f2
ms.sourcegitcommit: c5ef9a1d1853095ab537389b9a8e2d2adb39ed8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "3033079"
---
# <a name="copy-variables-to-chain-test-cases"></a>テスト ケースのチェーンへの変数のコピー

[!include [banner](../../includes/banner.md)]

Regression Suite Automation Tool の主要な機能の１つとして、テスト ケースの連鎖、つまり、テストが他のテストに値を渡す機能、があります。 テスト ケースは、 Azure DevOps テスト計画内で定義されている順序に従って実行され、テスト ツール自体で更新することもできます。 １つのテスト ケースから別のテスト ケースに変数を渡す場合は、テストを正しく順序付けることが重要です。

タスク レコーダーでテストを記録しながら変数の値を保存するには、次に示すように、フィールドを右クリックして **タスク レコーダー > コピー** を選択します。 これにより、変数が記録ファイルに保存されます。 この変数は、後続のテストで使用できます。 
 
![タスク レコーダーのメニュー項目のコピー](media/task-recorder-copy.png)

RSAT が Excel パラメーター ファイルを生成すると、これらの保存された値が、**一般**タブの**保存された変数**テーブルに表示されます。
 
![Excel に保存された変数](media/saved-variables.png)
 
テスト再生時にこれらの変数を再利用するには、次に示すように、変数名をコピーして、別のテスト (または同じテスト) のデータ ファイルでパラメーター値の代わりに使用します。 
 
![Excel での変数の再利用](media/reuse-variables.png)
 
変数は、定義されている同じテストケースで使用できます。また、同じテストの実行中にテスト間で渡すこともできます。

## <a name="support-for-formulas-of-saved-variables"></a>保存された変数の式のサポート

保存された (コピーされた) 変数を含むフォーミュラを作成できます。 Regression Suite Automation Tool の古いバージョンのを使用している場合、この機能を利用するためには新しいExcel パラメーター ファイルを再生成する必要があります。 サポートされ演算子は、 **+**、 **-**、 **/** および **\*** です。 Regression Suite Automation Tool 式で使用できるのは、数値変数のみです。 文字列または日付はサポートされていません。 変数名は常に二重の中かっこ **{{varname}}** で指定します。 たとえば、 **{{var1}} + {{var2}}**。

次の図では、2つの異なる変数が式で使用されています。
 
![Excelでの式の作成](media/formulas.png)

## <a name="use-variables-in-message-validation"></a>メッセージ検証での変数の使用

保存された変数を、メッセージ検証タブの文字列の一部として使用することもできます。以下は、`Customer account {{variable name}} already exists.` というメッセージを検証する例です。これは、テストの実行中に情報ログに表示されます。 `{{variable name}}` は、記録中にコピーされる変数です。

保存済 (コピー済) 変数は、同じテスト ケース内で、または同じテスト スイート内の複数のテスト ケース間で使用できます。

![変数を含むメッセージ](media/rsat-message-with-variable.png)

