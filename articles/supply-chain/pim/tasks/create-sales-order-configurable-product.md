---
title: コンフィギュレーション可能な製品の販売注文の作成
description: この手順では、販売注文で製品にコンフィギュレーション テンプレートを適用する方法を示します。
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39ccb68ba76cd710412df6a46fc624608d02902b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844540"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>コンフィギュレーション可能な製品の販売注文の作成

[!include [task guide banner](../../includes/task-guide-banner.md)]

この手順では、販売注文で製品にコンフィギュレーション テンプレートを適用する方法を示します。 この例では、デモ データの会社 USMF の D0006 スピーカー モデルが使用されています。 通常、販売注文担当者がこの手順を使用します。


## <a name="create-a-sales-order"></a>販売注文の作成
1. [販売注文の処理と照会] をクリックします。
2. [新規] をクリックします。
3. [販売注文] をクリックします。
4. [顧客口座] フィールドで [US-001] を選択します。 
5. [OK] をクリックします。
6. [品目番号] フィールドで D0006 を選択します。
    * このタスクでは、コンフィギュレーション可能な製品を選択する必要があります。  
7. [製品と供給] をクリックします。
8. [コンフィギュレーション明細] をクリックします。
    * 選択されたコンフィギュレーションに基づいて価格が変更され、[ケーブルを含める] フィールドが True に設定されることに注意してください。  
    * ケーブルに対して選択された既定の価格および設定に注意してください。  
9. [テンプレートの読み込み] をクリックします。
    * この例では、事前定義済のコンフィギュレーションを選択するためにどのようにテンプレートを追加できるかを示します。 この手順をタスク ガイドとして使用して、使用できる他の属性値を確認したい場合、[ロック解除] ボタンをクリックする必要があります。  
10. [OK] をクリックします。
11. [OK] をクリックします。
12. [明細行の詳細] セクションを展開します。
13. [製品] タブをクリックします。
    * 品目のコンフィギュレーションは、製品分析コードの下に一覧表示されます。  
14. ページを閉じます。

## <a name="select-the-product-configuration"></a>製品コンフィギュレーションの選択

