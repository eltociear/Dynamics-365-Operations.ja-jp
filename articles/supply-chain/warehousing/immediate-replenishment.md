---
title: "即時補充"
description: "このトピックでは、場所のディレクティブが在庫の配賦に失敗したときに、在庫を補充するため、即時補充を使用する方法について説明します。"
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a11a26df85647aa36cd30c42f81be4ec2af4409b
ms.contentlocale: ja-jp
ms.lasthandoff: 04/13/2018

---

# <a name="immediate-replenishment"></a>即時補充

[!include [banner](../includes/banner.md)]

場所ディレクティブの明細行が在庫の配賦に失敗した直後に、在庫を補充するため、即時補充ができるようになります。 補充は、場所ディレクティブの設定における単一明細行に基づいています。 その明細行で指定されている測定単位の在庫の手持がない場合、その測定単位の補充がすぐに発生します。

即時補充は、在庫の配賦が場所ディレクティブの複数の明細行に基づいており、要求が配賦の終わりに合計され、および場所ディレクティブの最後の明細行により指定される測定単位で補充される方法への代替を提供します。

即時補充を使用する利点は、特定の場所に送信される特定の単位および数量により補充が制限できることです。

## <a name="business-scenario"></a>ビジネス シナリオ

たとえば、「ボックス」および「各」測定単位に対して個別のピッキング エリアを持つ倉庫があるとします。 できるだけ多くのボックスをピッキングしてから、「各」領域から 1 つのボックスより少ない残りの数量をピッキングすることにより、ピッキング プロセスを最適化するようにします。

この場合、即時補充を使用することができます。 場所ディレクティブで、要求補充を使用して需要数量のボックスの不足分をすぐにピッキングできるよう、即時補充を設定できます。 これにより、できるだけ多くのボックスのピッキングが含まれるように、ピッキング プロセスを最適化します。 即時補充はボックスの補充を生成し、「各」測定単位でその数量がピッキングされるよう、要求は渡されません。 つまり、「各」測定単位(1 つのボックスより少ない数量) でピッキングするはずの数量のみが、「各」領域からピッキングされます。 「ボックス」領域に不足が発生した場合、合計要求からできるだけ多くのボックスをピッキングできます。 残りの数量は、その後「各」領域からピッキングされます。

## <a name="where-it-applies"></a>該当する場所

補充テンプレートが設定されている場所ディレクティブの明細行の配賦に失敗した場合、即時補充がウェーブ実行中に使用されます。

## <a name="set-up-immediate-replenishment"></a>即時補充の設定

- [**倉庫管理**] \> [**設定**] \> [**場所ディレクティブ**] の順に移動し、次に、[**即時補充テンプレート**] リストの [**明細行**] タブで、 ウェーブ需要に対する補充テンプレートを選択します。

場所ディレクティブの明細行が専用測定単位の配賦に失敗した場合は、補充テンプレートが適用されます。

## <a name="troubleshooting"></a>トラブルシューティング

即時補充が場所ディレクティブの明細行に対して選択されているが、場所ディレクティブの明細行に対して要求補充テンプレートを使用する際に補充作業が生成されない場合、2 つの主要な原因を調査する必要があります。

- 適用される要求補充テンプレートが、正しい場所テンプレートを使用し、[**補充**] タイプの作業テンプレートに設定されているかどうかを確認します。
- 要求補充テンプレートが補充の手持在庫を検索する場所で、十分な手持在庫があることを確認します。
