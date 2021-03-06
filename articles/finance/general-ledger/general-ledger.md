---
title: 一般会計と財務諸表の概要
description: 法人の財務レコードを定義および管理するには、一般会計を使用します。
author: ShylaThompson
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: GeneralJournalEntryWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 65431
ms.assetid: d2c604df-daae-42cd-82d9-c80e3dee4a60
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4cad11bcd1b1674055a07b5093093e33d3ac556
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771802"
---
# <a name="general-ledger-and-financial-reporting-overview"></a>一般会計と財務諸表の概要

[!include [banner](../includes/banner.md)]

法人の財務レコードを定義および管理するには、一般会計を使用します。 一般会計では借方と貸方のエントリ登録です。 これらのエントリは、勘定科目表に表示される勘定を使用して分類されます。 

 - [勘定科目表の計画](plan-chart-of-accounts.md)
 - [主勘定タイプ](main-account-types.md)

配賦ルールに基づいて、金額を、1 つ以上の勘定または勘定と分析コードの組み合わせに配賦または配分できます。 配賦には、固定と変動の 2 つのタイプがあります。 また、勘定科目間のトランザクションを決済し、通貨金額を再評価することもできます。 会計年度末には、決算トランザクションを生成し、次の会計年度に使用する勘定を用意します。 連結機能を使用すれば、複数の関連する法人の財務結果を 1 つの連結した組織の結果にまとめることができます。 関連会社は、同じデータベースに格納することも、別のデータベースに格納することもできます。

- [連結と削除の概要](../budgeting/consolidation-elimination-overview.md)
- [総勘定元帳残高](general-ledger-account-balances.md)
- [財務分析コード](financial-dimensions.md)

[![業務プロセス](./media/GL-process.PNG)](./media/GL-process.PNG)

## <a name="sales-tax"></a>消費税
すべての会社は税金を徴収し、さまざまな税務当局に支払います。 ルールと税率は国/地域、都道府県、市区郡、および市町村によって異なります。
また、ルールは、税務当局が要件を変更した際に、定期的に更新する必要があります。 売上税コードには、徴収額と当局への支払額に関する基本的な情報が含まれています。 売上税コードの設定時には、徴収する必要のある金額または割合を定義します。 また、トランザクション金額に金額や割合を適用する各種方法も定義します。 このセクションのトピックでは、税務当局が定める徴収方法と税率に対して売上税コードを設定する方法について説明します。

 - [消費税の概要](indirect-taxes-overview.md)
 - [基準金額および計算方法に基づいた、売上税の税率](marginal-base-field.md)
 - [消費税支払と丸めルール](round-sales-tax-payments.md)


## <a name="additional-resources"></a>追加リソース

#### <a name="whats-new-and-in-development"></a>新機能および開発中の機能

予定されている新機能を確認するには、[Microsoft Dynamics 365 リリース プラン](https://go.microsoft.com/fwlink/?linkid=2010158) を参照してください。 

#### <a name="blogs"></a>ブログ

Retail およびその他のソリューションに関する意見、ニュース、その他の情報については、[Microsoft Dynamics 365 ブログ](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) と [Microsoft Dynamics 365 Finance and Operations - Financials のブログ](https://community.dynamics.com/365/financeandoperations/b/financials)を参照してください。

[Microsoft Dynamics Operations Partner Community Blog (Microsoft Dynamics Operations パートナー コミュニティのブログ)](https://community.dynamics.com/partner/b/operationspartnercommunityblog) では、MBS Operations に関する最新情報とトレンドを知るための単一のリソースが Microsoft Dynamics パートナー向けに提供されています。

### <a name="videos"></a>ビデオ

[Microsoft Dynamics 365 YouTube チャンネル](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ) のハウツー ビデオをご覧ください。

#### <a name="community-blogs"></a>コミュニティのブログ

- [Dynamics 365 for Finance and Operations の元帳に関する確認事項](https://financefunction.tech/2018/04/29/what-you-should-know-about-ledger-in-dynamics-365-for-finance-and-operations)

