---
title: "原価バージョン"
description: "この記事は、原価バージョン、その管理方法、そこに含めることができるデータのタイプについての情報を提供します。 原価バージョンの主な目的は、品目、原価カテゴリ、間接原価の計算式に関する原価レコードを保持することです。"
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 54532
ms.assetid: cd239da5-f434-4d1b-8196-5414c888d76d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ce1f0c2107b701f12c18646ff4369e543bec7c97
ms.contentlocale: ja-jp
ms.lasthandoff: 05/25/2017


---

# <a name="costing-versions"></a>原価バージョン

[!include[banner](../includes/banner.md)]


この記事は、原価バージョン、その管理方法、そこに含めることができるデータのタイプについての情報を提供します。 原価バージョンの主な目的は、品目、原価カテゴリ、間接原価の計算式に関する原価レコードを保持することです。

原価バージョンは、内部に保持しているデータに応じて 1 つ以上の目的に使用できます。 原価バージョンの主な目的は、品目、原価カテゴリ、間接原価の計算式に関する原価レコードを保持することです。 原価バージョンには、割り当てられた原価タイプに基づいて、一連の標準原価レコードまたは予定原価レコードを格納することができます。

## <a name="costing-versions-for-standard-or-planned-costs"></a>標準または予定原価用の原価バージョン
### <a name="standard-costs"></a>標準原価

標準原価 − 原価バージョンは、品目に対する標準原価在庫モデルをサポートできます。この場合、原価バージョンには品目および製造プロセスに関する一連の標準原価レコードが格納されます。 製造プロセスに関する原価データは、工順の原価カテゴリおよび製造間接費の計算式で表されます。

### <a name="planned-costs"></a>予定原価

予定原価 − 原価バージョンに、品目および製造プロセスに関する一連の予定原価レコードを格納できます。 予定原価の原価バージョンは、多くの場合、原価計算シミュレーション (購入材料や製造プロセスの原価変更が、製造された品目の原価計算に及ぼす影響のシミュレーションなど) に使われます。 品目の予定原価の原価レコードを使用して、品目原価の初期値に指定することにより、実績原価在庫モデルをサポートすることもできます。 これらの値には、製造品目の予定原価の計算が含まれます。

## <a name="entering-costs"></a>コスト入力
原価バージョンにおける原価レコードのデータを管理するには、購入した品目およびサイト間で移動した品目の原価を入力します。 その他に製造環境のデータ管理では、工順に関連付けられた原価カテゴリの原価の入力、製造間接費を反映する間接原価の計算式の入力、および製造品目の原価計算を行います。 

原価バージョンにおける品目原価データは、各品目の 1 つまたは複数の原価レコードで構成されます。 品目の原価レコードを初期入力すると、ステータスは [**保留中**] であり、発効日が設定されています。 品目の原価レコードを有効にすると、ステータスは [**有効**] に更新され、発効日は有効化した日に更新されます。 各品目原価レコードで、反映されるサイト、発効日、またはステータスが異なっている場合があります。 未来の日付の製造完了品目の原価を計算する場合は、ステータスが [**保留中**] または [**有効**] であるかに関係なく、BOM の計算には、該当する発効日の原価レコードを使用します。 品目の現在の有効な原価レコードを使用して、製造オーダー原価を見積もり、標準原価在庫モデルで在庫トランザクションを評価します。 原価カテゴリの原価レコードおよび間接原価の計算式の管理は、品目原価レコードの管理と類似しています。 

原価バージョンに対する 2 つのブロック ポリシーで、保留原価を保持するかどうか、および保留原価を有効にするかどうかが決定されます。 原価バージョンにおける原価レコードのデータ管理を許可または禁止するには、ブロック ポリシーを使用します。 

原価バージョンには、BOM の計算に使用する品目の販売価格や購買価格に関するデータも格納できます。

## <a name="item-sales-prices-for-bom-calculations"></a>BOM 計算の品目の販売価格
販売価格に関するデータを含める主な理由は、製造品目の計算済販売価格を保有することです。 計算済販売価格を分析し、コンポーネント、工順工程、および間接費がコストと販売価格に寄与する方法を決定します。 

販売価格に関するデータを含める 2 番目の理由は、コンポーネント品目の販売価格レコードを定義することです。 これらのレコードは、製造された品目の販売価格を計算するために使用できます。 最初に BOM 計算グループに埋め込まれている販売価格モデルを定義し、BOM 計算グループを購入品目に割り当てます。 次に、予定原価を使用する BOM 計算を実行するとき、BOM 計算グループの原価価格モデルを選択します。 

そうしない場合、レコードが手動で入力されたか計算されたかにかかわらず、品目の販売価格レコードは照会情報としてのみ使用されます。 品目の販売価格レコードを有効化すると、品目の基準販売価格を更新できます。 ただし、基準販売価格はサイト固有ではなく、手動で上書きできます。 品目の基準販売価格は、販売注文および販売見積に対する既定の販売価格として使用されます。

## <a name="item-purchase-prices-for-bom-calculations"></a>BOM 計算の品目の購買価格
購買価格のデータを有効にする主な理由は、コンポーネント品目の購買価格レコードを定義するためです。これらのレコードを使用して製造品目のコストを計算できるようになります。 品目購買価格レコードは手動で入力する必要があります。 

購買価格の内容を有効にするには、最初に、品目の購買価格のコスト価格モデルを含む BOM 計算グループを定義し、購入品目に BOM 計算グループを割り当てます。 計画コストを使用した BOM 計算を実行して製造品目の販売価格を計算するとき、BOM 計算グループにコスト価格モデルを使用します。 

品目の購買価格レコードは、参照情報としても使用されます。 品目の購買価格レコードの状態を [**保留中**] から [**有効**] に変更すると、品目の基準購買価格を更新できます。 ただし、基準購買価格はサイト固有ではなく、手動で上書きできます。 品目の基準購買価格は、発注書の既定の購買価格として使用されます。



