---
title: 仕入先への支払留保条件の作成と適用
description: このトピックでは、仕入先への支払の保留条件の設定と管理に関する情報を提供します。
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410241"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a>仕入先への支払留保条件の作成と適用

[!include [banner](../includes/banner.md)] 

プロジェクトの仕入先に対する支払留保条件の設定は、組織で仕入先への支払いの一部を保持したい場合に役立ちます。 たとえば、仕入先への支払を、商品が予定どおりに配送されるまで保留するとします。 仕入先との契約の交渉時に、仕入先への支払い留保の条件を指定することができます。

## <a name="create-vendor-payment-retention-terms"></a>仕入先への支払留保条件を作成する

留保する仕入先支払の割合と、リリースされる留保した金額の割合を入力できます。 仕入先請求書の金額は、契約が指定した完了状態に到達するまで、自動的に留保されます。 仕入先に対する留保条件の設定後は、当該仕入先が関連するすべてのプロジェクトにその条件を適用できます。

以下の手順を使用して、仕入先への支払の留保条件を設定および管理します。 

1. **プロジェクト管理と会計** > **留保** > **仕入先支払留保条件**に移動します。
2. **新規** を選択して、新たな仕入先への留保条件を追加します。 新しい条件の **ルール ID** が自動的に入力されます。 
3. **説明**フィールドに簡単な説明を入力し、**条件**クイックタブの**明細行の追加**を選択して 、以下の条件値を入力します :

   - **配送単位の割合** : 条件の完了率を入力します。 金額は、プロジェクトの完了段階が指定された割合になるまで、仕入先の請求書に自動的に保持されます。 たとえば、50 を入力すると、プロジェクトが 50% 完了するまで金額が留保されます。
   - **留保する割合** : 仕入先の請求金額のうち、保持する割合を入力します。 たとえば、「10.00」 と入力した場合、仕入先の請求書に記載されている金額の 10% は、**納品単位の割合フィールド**で設定されている完了率に達するまで保持されます。
   - **リリースする割合** : **明細行の追加**を選択して、選択したプロジェクトの完了レベルに応じてリリースされる、留保済み金額の割合を入力します。

> [!NOTE]
> プロジェクト完了のさまざまなレベルに対して複数のマイルストーンが存在する場合は、留保ルールごとに別の仕入先の留保条件を入力します。 各明細行には、指定されたプロジェクト完了レベルごとに、異なる留保率と異なるリリース率を指定できます。

仕入先の留保条件の設定後は、プロジェクトにこの条件を適用することができます。

## <a name="apply-vendor-retention-terms-to-a-project"></a>仕入先の留保条件をプロジェクトに適用する

1. **プロジェクト管理と会計** > **プロジェクト** > **すべてのプロジェクト** を開き、プロジェクトのリストページからプロジェクトを開きます。
2. **仕入先契約** クイック タブで、**行の追加** をクリックします。
3. **口座コード フィールド**で、次のいずれかのオプションを選択します : 

   - **テーブル** : 仕入先の留保条件が、単一の仕入先に適用されます。
   - **グループ** : 仕入先の留保条件が、仕入先グループ内のすべての仕入先に適用されます。
   - **すべて** : 仕入先の留保条件が、すべての仕入先に適用されます。

4. **仕入先 / 仕入先グループ フィールド**で、仕入先の留保条件を適用する仕入先、または仕入先グループを選択します。 前のステップで **すべて** を選択した場合、このフィールドは使用できません。
5. **仕入先の留保条件**フィールドで、前述の手順で作成した留保条件を選択します。
6. プロジェクトで仕入先に対して Pay-when-paid (PWP) 条件が設定されている場合は、**PWP しきい値の割合**フィールドににプロジェクトのしきい値の割合を入力します。

仕入先留保条件は、仕入先用に作成した発注書にも表示されます。