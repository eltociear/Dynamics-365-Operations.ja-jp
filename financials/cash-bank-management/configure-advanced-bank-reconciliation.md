---
title: "詳細な口座調整の概要"
description: "高度な口座調整は、電子口座取引明細書のインポートと、自動的に、Microsoft Dynamics 365の銀行トランザクションで調整することができます。  この資料では、調整のプロセスの設定について説明します。"
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: c2fc9e858f61d7d0122393bbf306ba64ac3659b8
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>詳細な口座調整の概要

高度な口座調整は、電子口座取引明細書のインポートと、自動的に、Microsoft Dynamics 365の銀行トランザクションで調整することができます。  この資料では、調整のプロセスの設定について説明します。  

高度な口座調整機能を使用する前に設定する必要があるいくつか個があります。 設定の口座取引明細書のインポートに関する詳細については、" [口座取引明細書のインポート処理] (設定、高度な銀行調整インポートprocess.mdを設定する場合)。  調整プロセスの設定の必要条件を次に示します。

## <a name="transaction-codes"></a>トランザクション コード
トランザクション コードは、口座調整の照合ルールの一部として使用できます。  トランザクション コードは工程と口座取引明細書365 for Operationsの間で同じタイプのトランザクションのみが一致ができます。  一致のタイプを行うには、最初に365 for Operationsの銀行トランザクションに使用するトランザクション タイプを定義する必要があります。および銀行で使用する明細書のトランザクション コードにそれらのタイプをマップします。  工程の銀行トランザクション365 for Operationsのトランザクション タイプは**銀行トランザクション タイプ**ページで定義されます。  これはまたそのトランザクション タイプに関連付けられる転記に使用する主要な勘定を定義するかです。 

工程の銀行トランザクション コード365 for Operationsが定義されている場合は、電子口座取引明細書に使用されるトランザクション コードにそのをマップします。  このマッピング プロセスは**トランザクション コードのマッピング**ページを使用して実行されます。  トランザクション コードのマッピングは、銀行口座ごとに入力されます。

## <a name="matching-rules-and-matching-rule-sets"></a>照合ルールおよび照合ルール セット
一致通常、工程の銀行トランザクションと口座取引明細書のトランザクションのDynamics 365の間の自動調整の基準を定義することができます。  一致ルールの設定はされた**調整の照合規則**ページです。  詳細については、表示、[口座調整の照合ルールを設定する] (銀行設定と調整しますrules.md)。 

一致ルール セットが口座調整プロセス中に順に実行すると、ルールのグループを定義するのに使用されます。  一致ルール セットは**調整のルール セットと**ページで設定します。

## <a name="cash-and-bank-management-parameters"></a>現金および銀行管理パラメーター
**現金と銀行管理パラメータ**ページの詳細な口座調整プロセスに特定の複数のパラメータがあります。  **借方/貸方の[明細金額**変更**口座取引明細書**ページでのビュー。  このオプションを選択した場合、口座取引明細書のトランザクション金額は別の借方と貸方列に表示されます。  選ばれなくて、口座取引明細書のトランザクション金額は、適切な符号がある一つの金額列に表示されます。 

パラメータ ページでコンフィギュレーション オプションは、対応する検証ルールで設定された選択を上書きします。  たとえば、手動または自動でパラメータ ページの日付の差設定を越えたドキュメントをできません。  また、オプションがに**トランザクション タイプのマッピングを検証します。**オンの場合、トランザクション タイプは手動または自動で一致するトランザクションに工程銀行トランザクションと口座取引明細書のトランザクションの365 for Operationsの間でマップする必要があります。 

**、現金と銀行管理パラメータ**ページで必要な番号順序を設定する必要があります。  **番号順序**タブで、ダウンロード** ID、ステートメントID、ID、口座調整を調整します**のセット番号順序コードの参照。

## <a name="bank-account-reconciliation-options"></a>銀行口座調整のオプション
最初に銀行口座の詳細な口座調整を有効にする必要があります。  複数の追加オプションは、高度な口座調整の機能が有効な**銀行口座**ページで使用できます。 

**電子支払の検証として口座取引明細書を使用して、**機能は、電子支払のステータスの口座調整の機能が統合されます。  これが有効になると、銀行関係のドキュメントは電子支払の条件に自動的に設定されますが作成されます**送信**。  また、電子支払のステータスが更新されてから**送信**に最も**入庫**支払が一致したら、調整が転記されます。 

**明細書の銀行口座の名前**フィールドは、電子口座取引明細書の銀行口座に使用する名前です。  この名前は、複数の銀行口座の情報を含めることができるステートメントに基づいて銀行口座にインポートする場合、トランザクションを決定するときに使用されます。 

オプションは、にインポート**と調整させました**自動的に口座取引明細書を検証し、新しい口座調整、ワークシートを作成し、既定の照合ルール セットを実行します。  この機能は手動で一致する必要があるトランザクションの時点までプロセスが自動化されます。  銀行口座の設定はインポートするときに決定されます。

