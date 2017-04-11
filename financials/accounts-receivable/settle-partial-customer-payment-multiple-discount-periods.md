---
title: "複数の割引期間を持つ部分的な顧客支払を決済します。"
description: "この記事は、複数の割引期間がある場合に一部顧客支払が決済される方法を示します。"
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14471
ms.assetid: b633a7c4-c18d-42e7-91cc-adcdc8a3ba98
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 9da48c7861f48ec2a154ac12616149d1208346cf
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-customer-payment-that-has-multiple-discount-periods"></a>複数の割引期間を持つ部分的な顧客支払を決済します。

この記事は、複数の割引期間がある場合に一部顧客支払が決済される方法を示します。

Fabrikam は、顧客 4031 に 2 つの現金割引期間を提示します。 顧客は、請求書の支払が 5 日以内に行われた場合には 2% の現金割引を、14 日以内に行われた場合には 1% の現金割引を受けます。 Fabrikam は、一部支払に対する現金割引も提供します。 決済パラメータは**売掛金勘定パラメータ**ページにあります。

## <a name="invoice"></a>請求書
6年7月25日に、Arnieは顧客4031について1,000.00の請求書の入力および転記します。 従業員がこの請求書に対する現金割引を確認すると、Arnieは請求書が6年1月30日に支払う場合4031顧客が20.00割引を受けることが表示されます。 請求書が7年3月9日に支払う場合は、顧客10.00割引が表示されます。

| 現金割引日 | 現金割引金額 | トランザクション通貨の金額 |
|--------------------|----------------------|--------------------------------|
| 6/30/2015          | 20.00                | 980.00                         |
| 7/9/2015           | 10.00                | 990.00                         |
| 7/25/2015          | 0.00                 | 1,000.00                       |

アーニーはこのトランザクションを [**顧客トランザクション**] ページで表示できます。

| 伝票番号   | トランザクション タイプ | 日      | 請求書 | トランザクション通貨での借方金額 | トランザクション通貨での貸方金額 | 残高  | 通貨 |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10030 | 請求書          | 6/25/2015 | 10030   | 1,000.00                             |                                       | 1,000.00 | USD)       |

## <a name="partial-payment-before-the-cash-discount-date"></a>現金割引の日付前の一部支払
顧客 4031 は 6 月 28 日に、294.00 の一部支払を行います。 6 月 28 日が最初の現金割引期間内であるため、顧客が 6.00 ドルの割引を受けます。 [**トランザクションの決済**] ページでは、[**現金割引金額**] の値が 20.00、[**適用する現金割引金額**] の値が 6.00 です。

| マーク     | 現金割引の使用 | 伝票番号   | 口座 | 日      | 期日  | 請求書 | トランザクション通貨の金額 | 通貨 | 決済金額 |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| 選択済 | 標準            | FTI-10030 | 4031    | 6/25/2015 | 7/25/2015 | 10030   | 1,000.00                       | USD)       | 294.00           |

割引の情報は [**未処理トランザクションの決済**] ページの下部に表示されます。 [**決済金額**] の値を **294.00** に変更しないと、表示される [**現金割引金額**] の値が異なります。 ただし、決済が [**決済金額**] の値を自動的に調整するため 6.00 ドルは現金割引として支払の転記時に取得されます。

|                              |           |
|------------------------------|-----------|
| 現金割引日           | 6/30/2015 |
| 現金割引金額         | 20.00     |
| 現金割引の使用            | 標準    |
| 適用される現金割引          | 0.00      |
| 適用する現金割引金額 | 6.00      |

アーニーが支払を転記すると、請求書の残高は 700.00 ドルになります。

## <a name="partial-payment-before-the-second-cash-discount-date"></a>現金割引の 2 番目の日付前の一部支払
7 月 8 日に、顧客が請求金額の残りを支払います。 この支払は 2 番目の現金割引期間内に行われるため、7.00 ドル (つまり 1% の割引) が適用されます。

| マーク     | 現金割引の使用 | 伝票番号   | 口座 | 日      | 期日  | 請求書 | トランザクション通貨での借方金額 | トランザクション通貨での貸方金額 | 通貨 | 決済金額 |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| 選択済 | 標準            | FTI-10030 | 4031    | 6/25/2015 | 7/25/2015 | 10030   | 700.00                               |                                       | USD)       | 693.00           |

割引の情報は [**未処理トランザクションの決済**] ページの下部に表示されます。

|                              |           |
|------------------------------|-----------|
| 現金割引日           | 2015/7/9 |
| 現金割引金額         | 30.00     |
| 現金割引の使用            | 標準    |
| 適用される現金割引          | 6.00      |
| 適用する現金割引金額 | 7.00      |

請求書の残高は 0.00 ドルになります。 アーニーはこの情報を [**顧客トランザクション**] ページで表示できます。

| 伝票番号    | トランザクション タイプ | 日      | 請求書 | トランザクション通貨での借方金額 | トランザクション通貨での貸方金額 | 残高 | 通貨 |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10030  | 請求書          | 6/25/2015 | 10030   | 1,000.00                             |                                       | 0.00    | USD)       |
| ARP-10030  |  支払         | 6/28/2015 |         |                                      | 294.00                                | 0.00    | USD)       |
| DISC-10030 |  現金割引   | 6/28/2015 |         |                                      | 6.00                                  | 0.00    | USD)       |
| ARP-10031  |  支払         | 2015/7/8  |         |                                      | 693.00                                | 0.00    | USD)       |
| DISC-1031  |  現金割引   | 2015/7/8  |         |                                      | 7.00                                  | 0.00    | USD)       |



