---
title: 書式設定のコンフィギュレーションを使用する、支払用の ER 生成の電子ドキュメント
description: 次の手順では、システム管理者または電子申告開発者の役割のユーザーが、支払処理の電子ドキュメントを生成する新しい電子申告 (ER) 形式のコンフィギュレーションを使用する方法を説明します。
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 179e8a20dd65847f90872ae0e56b3e4991a6b00e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184994"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a>書式設定のコンフィギュレーションを使用する、支払用の ER 生成の電子ドキュメント

[!include [task guide banner](../../includes/task-guide-banner.md)]

次の手順では、システム管理者または電子申告開発者の役割のユーザーが、支払処理の電子ドキュメントを生成する新しい電子申告 (ER) 形式のコンフィギュレーションを使用する方法を説明します。 これらのステップは GBSI サンプル会社で実行できます。

これらの手順を完了するには、先に「支払ドキュメントの形式でコンフィギュレーションの作成」の手順の各ステップを完了する必要があります。


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>電子支払方法のコンフィギュレーションの変更
1. [買掛金勘定] > [支払設定] > [支払方法] の順に移動します。
2. 必要に応じて、[ファイル形式] セクションを切り替えて展開します。
3. クイック フィルターを使用して、レコードを見つけます。 たとえば、[支払い方法] フィールドに値「電子」でフィルターを適用します。
4. [編集] をクリックします。
5. [一般的な電子申告] フィールドを [はい] に設定します。
    * 支払ファイル生成の一般的な電子申告パターンを使用するには [はい] を選択します。  
6. [名前] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
7. BACS (英国企業) 形式のコンフィギュレーションを選択します。
8. [保存] をクリックします。
9. ページを閉じます。

## <a name="test-the-format-of-generated-payment-files"></a>生成された支払ファイルの形式のテスト
1. [買掛金勘定] > [支払] > [支払仕訳帳] の順に移動します。
2. [新規] をクリックします。
3. 一覧で、選択された行をマークします。
4. [名前] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
5. 一覧で、選択された行のリンクをクリックします。
    * VendPay を選択します。  
6. [保存] をクリックします。
7. [明細行] をクリックします。
8. [会社] フィールドで、「DEMF」と入力します。
    * DEMF  
9. [口座] フィールドで、「DE-01001」という値を指定します。
    * DE-01001  
10. [説明] フィールドで「支払」と入力します。
    * 支払  
11. [借方] フィールドに数値を入力します。
    * 1000  
12. [支払] タブをクリックします。
13. [支払方法] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
14. 一覧で、目的のレコードを見つけ、選択します。
    * 電子の値を選択します。  
15. 一覧で、選択された行のリンクをクリックします。
16. [保存] をクリックします。
17. [支払の生成] をクリックします。
18. [支払方法] フィールドで、ドロップ ダウン ボタンをクリックし、ルックアップを開きます。
19. 一覧で、目的のレコードを見つけ、選択します。
    * 電子の値を選択します。  
20. 一覧で、選択された行のリンクをクリックします。
    * 電子の値を選択します。  
21. [ファイル名] フィールドに値を入力します。
    * たとえば、「支払」と入力します。  
22. [銀行口座] フィールドで、ドロップ ダウン ボタンをクリックしてルックアップを開きます。
23. 一覧で、選択された行のリンクをクリックします。
    * GBSI OPER 値を選択します。  
24. [OK] をクリックします。
25. [OK] をクリックします。
    * XML 形式で作成した支払ファイルを分析します。 設計されたドキュメント レイアウトおよび定義された支払トランザクションの属性と比較します。  

