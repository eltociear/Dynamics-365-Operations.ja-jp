---
title: 仕訳帳の転記の取消
description: このトピックでは、伝票トランザクション リストまたは財務仕訳帳から伝票を取り消けせるようにする能力について説明します。
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248588"
---
# <a name="reverse-journal-posting"></a>仕訳帳の転記の取消

[!include [banner](../includes/banner.md)]

このトピックでは、仕訳帳全体、またはその発生元に関係なく伝票トランザクション リストから 1 つ以上の伝票を取り消すことができるようにする Microsoft Dynamics 365 Finance 能力について説明します。 

## <a name="reversing-journals"></a>仕訳帳の取り消し

仕訳帳明細行は個別に取り消すことができます。 仕訳帳転記の取消により、財務仕訳帳全体を取り消すこともできます。 仕訳帳を取り消すには: 
- 財務仕訳帳を開き、転記された仕訳帳のフィルター処理を行います
- ページ上部の取消メニューをクリックします
- 伝票および伝票明細行の合計数が、取り消される明細行の合計金額と共に表示されます
- 既存のトランザクションの日付を使用する場合ははいを選択し、新しく入力する場合はいいえを選択します。 場合によっては、元のトランザクションの期間が終了していることがあり、取消のために新しいトランザクション日付を入力する必要があります。
- いいえを選択した場合、取消のためにトランザクションの日付を入力します。 
- 取消トランザクションに追加するコメントを入力します。
- 取消ボタンをクリックします

トランザクションは取り消されます。 

伝票明細行の数が 100 行を超える場合、バッチ処理を使用して取消プロセスが実行されます。 実行されたバッチ ジョブのコメントを表示することにより、取消の結果を確認することができます。 失敗はすべてバッチ ジョブ履歴に記録されます。

伝票明細行の数が 100 行以下である場合、取消プロセスがすぐに実行されます。 結果は、取消ができなかったすべての伝票および取消ができなかった理由を表示するダイアログ内に表示されます。 OK をクリックしてダイアログを閉じます。

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>伝票トランザクション リストから伝票を取り消します。 

また、すべての補助元帳間で**伝票のトランザクション リスト**から伝票を取り消すこともできます。 さらに、一度に複数の伝票を取り消すこともできます。 

複数の伝票を取り消すには: 
- ページ上部の取消メニューをクリックします
- 伝票および伝票明細行の合計数が、取り消される明細行の合計金額と共に表示されます
- 既存のトランザクションの日付を使用する場合ははいを選択し、新しく入力する場合はいいえを選択します。 場合によっては、元のトランザクションの期間が終了していることがあり、取消のために新しいトランザクション日付を入力する必要があります。
- いいえを選択した場合、取消のためにトランザクションの日付を入力します。 
- 取消トランザクションに追加するコメントを入力します。
- 取消ボタンをクリックします

トランザクションは取り消されます。 

伝票明細行の数が 100 行を超える場合、バッチ処理を使用して取消プロセスが実行されます。 実行されたバッチ ジョブのコメントを表示することにより、取消の結果を確認することができます。 失敗はすべてバッチ ジョブ履歴に記録されます。

伝票明細行の数が 100 行以下である場合、取消プロセスがすぐに実行されます。 結果は、取消ができなかったすべての伝票および取消ができなかった理由を表示するダイアログ内に表示されます。 OK をクリックしてダイアログを閉じます。
