---
title: "支払方法"
description: "小売業者が受け入れる各支払タイプは、システムの設定時に Microsoft Dynamics 365 for Operations の [小売りとコマース] でコンフィギュレーションする必要があります。 この記事では、設定可能な支払タイプおよびその設定方法について説明します。"
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: MargoC
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: e41a952889a7329c3d3f1d82ba875f5964ee5b7f
ms.contentlocale: ja-jp
ms.lasthandoff: 05/25/2017


---

# <a name="payment-methods"></a>支払方法

[!include[banner](includes/banner.md)]


小売業者が受け入れる各支払タイプは、システムの設定時に Microsoft Dynamics 365 for Operations の [小売りとコマース] でコンフィギュレーションする必要があります。 この記事では、設定可能な支払タイプおよびその設定方法について説明します。

小売業者は、販売する製品およびサービスと引き換えにさまざまなタイプの支払方法を受け入れることができます。 最も一般的な支払形式は現金ですが、小売業者は小切手、カード、伝票などの形式で支払を受け取ることもできます。 小売業者が受け入れる各支払タイプは、システムの設定時に Microsoft Dynamics 365 for Operations - Retail でコンフィギュレーションする必要があります。 次の一覧は、Dynamics 365 for Operations - Retail で設定できる各支払タイプを示しています。

-   [**現金**]: 紙幣や硬貨など、通貨の物理的な形式。 この通貨は、法人基本通貨または店舗の国内通貨のいずれかにすることができます。
-   [**小切手**]: 特定の銀行に特定の通貨で特定の金額の支払を振り出すことを指示する流通証券。 小切手の有効期限は、特に指定のない限り、一般に、無期限にまたは発行日から 6 か月です。 この期間は、小切手が振り出された銀行によって異なります。 指図式小切手、払戻小切手、持参人払式小切手、受取人指定小切手など、さまざまな種類の小切手があります。 各店舗の支払方法として小切手を設定できます。 小切手は、法人レベルまたは店舗レベルで定義された通貨で受け入れることができます。 店舗で支払として小切手を受け入れる前に、支払方法として小切手を設定する必要があります。
-   [**通貨**]: 法人の既定の通貨以外の主要な支払形式。 硬貨と紙幣はどちらも通貨の形式です。 通貨の支払方法は、[小売りとコマース] で使用されるすべての通貨を表します。 この支払方法を使用する前に、通貨を設定し、通貨の小売取引情報を指定する必要があります。
-   [**カード**] – デビット カード、クレジット カードなど、[小売りとコマース] で使用されるあらゆる種類のカード。 あらゆる種類のカードを表す 1 つのカード支払方法を組織レベルで設定することは良い考えです。 その後、同じ設定を使用して処理されるカードまたはカード セットごとに、支払方法を店舗レベルで設定します。 店舗での支払としてカードを受け入れる前に、デビット カード、クレジット カードなど、市場で一般に使用できるメーカーのカードを設定する必要があります。
-   [**クレジット メモ**] – POS で発行または引き換えが行われるクレジット メモ。 クレジット メモには、クレジット メモと、返品販売に対して発行される返品クレジット メモがあります。 クレジット メモの一部だけが引き換えられた場合、新しい残高に対する新しいクレジット メモが発行されます。 新しいクレジット メモには、新しい番号が割り当てられます。 クレジット メモは 1 回だけ使用可能であり、使用された番号はすべてシステムで記録されます。 レコードは [**クレジット メモ テーブル**] ページに表示できます。 顧客は、クレジット メモの金額を超えて引き換えることはできません。
-   [**ギフト カード**]: POS で発行および引き換えが行われるギフト カード。 ギフト カードの金額を超えて支払うことはできません。
-   [**顧客 ID**]: 販売時にレジスターで顧客 ID に請求できる支払。 この支払方法は、顧客が別の支払方法を使用して支払を行うときに、販売情報や顧客固有の割引を収集する場合にも使用できます。 この場合は、顧客固有の情報を設定する必要があります。
-   [**ロイヤルティ ポイント**] – ロイヤルティ プログラムを通して顧客が収集するポイント。 ロイヤルティ プログラムを作成すると、顧客はポイントを獲得してさまざまな方法で交換することができます。 たとえば、あるロイヤルティ プログラムで、顧客が割引の形式でロイヤルティ ポイントを買い戻し、さらに支払形式として使用できます。

[小売りとコマース] で支払方法を設定するには、次の作業を行う必要があります。

1.  組織の支払方法の設定します。 組織全体で受け入れる支払方法を作成します。
2.  組織全体のカード タイプとカード番号の作成。 クレジット カードまたはデビット カードを受け入れる場合、カードの支払方法を 1 つ作成し、組織全体のカード タイプとカード番号を作成する必要があります。
3.  店舗の支払方法を設定。 支払方法を各店舗に関連付けて、各支払方法の店舗固有の設定を入力します。
4.  店舗のカード支払方法の設定。 店舗で受け入れるカード支払方法について、カードの設定を行います。




