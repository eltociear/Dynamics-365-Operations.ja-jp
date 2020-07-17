---
title: POS に割引を表示
description: このトピックでは、Microsoft Dynamics 365 Commerce が販売担当者に対してどのようにプロモーションについて知り、クロスセルとアップセルに使用できるかについて説明します。
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 05/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail, Commerce
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-02-28
ms.dyn365.ops.version: Application update 10.0.10
ms.openlocfilehash: 0ffa7ca6294c7b523ec743f1cb9bc4aef8ef46a8
ms.sourcegitcommit: 4d5bcda288341572076364559125c86e2ec05273
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "3334711"
---
# <a name="show-discounts-in-pos"></a>POS に割引を表示

[!include [banner](includes/banner.md)]

プロモーションは、購買決定を行う動機付けの顧客にとって重要な役割を果たします。 たとえば、魅力的なプロモーションと割引によって小売市場全体があふれているので、休日は小売業者の最大販売数を生産できます。 店舗では、利用可能なプロモーションを把握して理解している場合、それらのプロモーションを簡単に活用して、品目のクロスセルおよびアップセルを行うことができます。 このトピックでは、Microsoft Dynamics 365 Commerce が販売担当者に対してどのようにプロモーションについて知り、クロスセルとアップセルに使用できるかについて説明します。

## <a name="learn-about-store-discounts"></a>店舗割引について

コマースには、「すべての割引の表示」という名前の操作が含まれます。 この操作では、店舗で現在実行中のすべての割引が表示されます。 「すべての割引の表示」操作は、販売時点管理 (POS) にマップできます。このボタンは、**ようこそ**ページまたは**トランザクション** ページに追加できます。 次の図は、開かれた**すべての割引**ページを示しています。

![すべての割引ページ](./media/View_all_discounts.png "すべての割引ページ")

割引を表示するために、システムは次のいずれかの条件に一致するすべての割引を検索します。

- 割引の価格グループが店舗の価格グループと一致します。
- 割引の価格グループは、所属またはロイヤルティ プログラムにマップされます。
- 割引の価格グループは、店舗に関連付けられているカタログにマップされます。

小売業者は通常、多くのクーポンとそれに対応する固有の顧客のための割引を作成しているので、**すべての割引**ページでは、クーポンに基づく割引の一部が表示されます。このページは、顧客固有の割引は意図されていません。 クーポンに基づく割引は、クーポン ヘッダーごとに**クーポンコードなしで適用**がオンになっている場合にのみ表示されます。 この場合、レジ担当者は、クーポン コードまたはバー コードを入力またはスキャンすることなく、クーポンを適用することができます。

**クーポン コードなしで適用**がオンになっている場合は、さまざまなシナリオが可能になります。 たとえば、レジ担当者は顧客に対して顧客緩和の目的または製品の欠陥のために、追加割引を提供することができます。 印刷されたクーポン コードまたはバーコードは、レジ担当者に渡す必要はありません。 代わりに、レジ担当者は**クーポン適用**ボタンを選択します。 その後、このクーポンが自動的にトランザクションに適用されます。 クーポン ヘッダーに対して複数のクーポンが存在する場合は、システムによってトランザクションの最初の有効なクーポンが自動的に選択されます。

**すべての割引**ページでは、販売担当者はキーワードで割引を検索することもできます。 キーワード検索では、割引名と割引の説明を含むフィールドが検索されます。 販売担当者は、割引にクーポンコードが必要かどうかに基づいて割引をフィルタ処理することもできます。

## <a name="cross-sell-and-upsell-by-using-discounts"></a>割引を使用したクロスセルとアップセル

数量割引、組み合わせ割引、しきい値割引などの複数行割引は、より多くの割引を受けるために顧客がより多くの製品を購入するためのよい手段です。 したがって、これらは、顧客のカートおよび小売業者の収益のサイズを増加するのにも役立ちます。 これらの割引は、E コマース ウェブサイト、ソーシャルメディア、および店舗のバナーで公開できます。

ただし、これらの宣伝方法をすべて使用している場合でも、顧客はプロモーションを利用する機会を逃してしまう可能性があります。 販売担当者が、選択した明細行やカート全体に適用されるプロモーションを簡単に知ることができるようにするために、小売業者は、**取引ページ** のボタングリッドに「利用可能な割引を表示する」操作を実行するボタンを追加することができます。 この方法では、販売担当者が取引の明細行を選択し、選択した明細行に使用できるすべての割引を表示するボタンを選択することができます。 また、販売担当者がトランザクション全体に適用される割引を表示するために、別のタブを選択することもできます。

**すべての割引** ページには、適用された割引と競合しない割引のみが表示されます。 この動作を使用すると、販売担当者が顧客に割引について通知した場合、または顧客が必要なアクションを実行した場合 (たとえば、10% 割引を受けるため、品目をさらに 1 つ購入した場合)、その割引はトランザクションに適用されます。 クーポンに基づく割引は、**クーポンコードなしで適用** がオンになっている場合にのみ表示されます。

すべての割引の優先順位が同じである単純なシナリオでは、割引同時実行モードが**組み入れられて**、割引実行モードは**優先順位内のみの最良価格と組み入れ、優先順位間で組み入れない**に設定されており、**すべての割引**ページでは優先順位が高い場合、すべての割引が組み入れられ、相互に競合することはないので、利用可能な割引のみ表示します。

次の図は、割引同時実行モードが **最も高い価格**または**排他的**であるシナリオなど、高度なシナリオで表示される割引を決定するロジックを示しています。 このようなシナリオでは、表示される割引が、割引同時実行管理が**優先順位内のみの最良価格と組み入れ、優先順位間で組み入れない**または**優先順位内のみの最良価格、常に優先順位間で組み入れる**かどうかによって、影響されます。

次の図は、割引同時実行管理時に使用するロジックが**優先順位内のみの最良価格と組み入れ、優先順位間で組み入れない**に設定を表示しています。

![優先順位内のみの最良価格と組み入れ、優先順位間で組み入れないロジック](./media/Model_1.png "優先順位内のみの最良価格と組み入れ、優先順位間で組み入れないロジック")。

次の図は、割引同時実行管理時に使用するロジックが**優先順位内のみの最良価格、常に優先順位間で組み入れ**に設定を表示しています。

![優先順位内のみの最良価格、常に優先順位間で組み入れロジック](./media/Model_2.png "優先順位内のみの最良価格、常に優先順位間で組み入れロジック")。