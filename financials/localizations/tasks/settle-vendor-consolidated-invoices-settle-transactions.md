--- 
title: "決済トランザクションを使用した仕入先月次締め請求書の決済 (日本)"
description: "日本では、支払は月次締め請求書に対して行われ決済されます。"
author: ShylaThompson
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Japan
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 4cd9638df09cef1f159c54a6a435661bc2b9720a
ms.contentlocale: ja-jp
ms.lasthandoff: 07/27/2017

---
# <a name="settle-vendor-consolidated-invoices-by-using-settle-transactions-japan"></a>決済トランザクションを使用した仕入先月次締め請求書の決済 (日本)

[!include[task guide banner](../../includes/task-guide-banner.md)]

日本では、支払は月次締め請求書に対して行われ決済されます。



この手順では、決済トランザクションを使用した月次締め請求書の決済について説明します。



この手順を実行する前に、月次締め請求書が作成され確定済であること、および支払いが転記されていることを確認する必要があります。 



この手順は、デモ データ会社 JPMF を使用して作成されました。


## <a name="confirm-consolidation-invoice-to-be-settled"></a>決済される月次締め請求書の確定
1. [買掛金勘定] > [定期処理タスク] > [月次締め請求書] の順に移動します。
2. 後で参照するために、[締め ID] フィールドの値をメモします。
    * 決済する月次締め請求書のステータスが「確定済」であることを確認します。    この例: 締め ID - JPMF-000004  

## <a name="settle-consolidation-invoice"></a>月次締め請求書の決済 
1. [買掛金勘定] > [仕入先] > [すべての仕入先] の順に移動します。
2. 一覧で、目的のレコードを見つけ、選択します。
    * 月次締め請求書を決済する仕入先を選択します。 この例では、JPMF-000002 を使用します。  
3. アクション ウィンドウで、[請求書] をクリックします。
4. [トランザクションの決済] をクリックします。
5. 一覧で、目的のレコードを見つけ、選択します。
    * [締め ID] が JPMF-000004 のレコードを選択します。  
6. [マーク] のチェック ボックスをオンまたはオフにします。
    * [請求書] をマークします。  
7. 一覧で、目的のレコードを見つけ、選択します。
    * 請求金額を超過して評価されている支払トランザクションを選択します。  
8. [マーク] のチェック ボックスをオンまたはオフにします。
    * 支払トランザクションをマークします。  
9. [転記] をクリックします。

## <a name="validate-consolidation-invoice-status-to-settled"></a>月次締め請求書のステータスが [決済済] であることを検証
1. [買掛金勘定] > [定期処理タスク] > [月次締め請求書] の順に移動します。
    * 月次締め請求書のステータスが「決済済」になっていることを確認します。  

