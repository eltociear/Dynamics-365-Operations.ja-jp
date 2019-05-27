---
title: プロジェクト タイムシート モバイル アプリケーション
description: このトピックでは、Microsoft Dynamics 365 Project Timesheet モバイル アプリケーションに関する情報を提供します。 プロジェクト タイムシート モバイル アプリにより、ユーザーは自分のモバイル デバイスでプロジェクトのタイムシートを送信および承認できます。
author: abruer
manager: AnnBe
ms.date: 04/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: josaw1
ms.dyn365.ops.version: 10
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: a475085001b8fa10814c864ef35129eb6ebfdfef
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2019
ms.locfileid: "969673"
---
# <a name="microsoft-dynamics-365-project-timesheet-mobile-application"></a>Microsoft Dynamics 365 Project Timesheet モバイル アプリケーション

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>概要

Microsoft Dynamics 365 Project Timesheet モバイル アプリにより、ユーザーは自分のモバイル デバイスでプロジェクトのタイムシートを送信および承認できます (iPhone または Android)。 このモバイル アプリは、Microsoft Dynamics 365 for Finance and Operations のプロジェクト管理と会計領域に存在するタイムシート機能を表示し、ユーザーの生産性と効率を改善するだけでなく、プロジェクト タイムシートの適切なタイミングでの入力および承認を有効にします。

## <a name="download-and-install-the-mobile-app"></a>モバイル アプリのダウンロードとインストール

ユーザーのデバイスのモバイル ストアから、Android または iPhone 用 Microsoft Dynamics 365 Project Timesheet モバイル アプリをダウンロードしてインストールします。

## <a name="enable-the-app"></a>アプリを有効にする 

Dynamics 365 for Finance and Operations で、プロジェクト タイム シート モバイル アプリを有効にする必要があります。 機能を有効にするには、**プロジェクト管理および会計パラメーター \> タイムシート**の順に移動し、**Microsoft Dynamics 365 Project Timesheet を有効にする**パラメーターを選択します。

## <a name="sign-in-to-the-app"></a>アプリにサインインする

1.  モバイル デバイスでアプリを起動します。

2.  Microsoft Dynamics 365 for Finance and Operations URL を入力します。

3.  初めてサインインすると、ユーザー名とパスワードを要求されます。 資格情報を入力します。

4.  既定の会社にサインインされます。

## <a name="submit-a-project-timesheet"></a>プロジェクト タイムシートの送信

アプリで、プロジェクト タイムシートを作成および送信できます。 前のタイムシート、保存した明細行、またはプロジェクト割り当てからの情報を、新しいタイムシートの基準とすることができます。 デリゲートとして指名されている場合、別の作業者のタイム シートに入力することもできます。 デリゲートとしてタイムシートを作成するには、**メニュー**ボタンを選択し、リソース名を選択します。

タイムシート ページで、現在の日付に基づいてタイムシート期間の新しいタイムシートを作成します。 作業週が表示されます。 タイムシート期間が数週間に及ぶと、作業週タブから別の作業週を選択できます。
現在の日付のタイムシートが存在する場合は、それが表示されます。 異なるタイムシート期間で新しいタイムシートを作成する必要がある場合は、**メニュー**ボタンを選択し、**新しいタイムシート**を選択します。

**時間の追加**アクションまたは**次の時刻をコピー**アクションをクリックして、プロジェクト情報を入力できます。 **次の時刻をコピー**アクションでは、プロジェクト明細行情報をコピーしますが、時間数はコピーしません。 **次の時刻をコピー**メニューには次のオプションがあります。

- **既存のタイムシートからのコピー** - 既存のタイムシートからタイムシートの行をコピーします。

- **お気に入りからのコピー** - お気に入りとして選択したタイムシートの設定を使用して、新しいタイムシートの行を作成します。

- **割り当てからのコピー** - 割り当てられたプロジェクトから新しいタイムシートの行を作成します。

表示されるプロジェクト情報は、**プロジェクト管理および会計パラメーター**ページで定義されたモバイル パラメーターに依存します。

**法人**フィールドでは、プロジェクト作業を実行した法人を選択します。 **法人**フィールドは、法人で会社間タイムシートがサポートされている場合のみ使用できます。

タイムシートのプロジェクトに関連付けられている顧客を選択します。 Android の初期リリースでは、最初にプロジェクトを選択する必要があるため、顧客による入力はサポートされていません。 最初にプロジェクトを選択した場合、**顧客**フィールドは自動的に入力されます。

**プロジェクト**フィールドで、時間を入力するプロジェクトを選択します。 **顧客** フィールドが自動的に入力されます。

顧客およびプロジェクト ルックアップは、顧客とプロジェクトの両方にまたがった検索を有効にします。

必要に応じて**カテゴリ**、**活動**、**明細行プロパティ**、**消費税グループ**、および**品目消費税グループ**フィールドで情報を選択します。 これらのフィールドは上書きできます。

**明細行プロパティ**フィールドは、プロジェクト管理と会計パラメーターに基づく既定値に設定されます。 プロジェクト/カテゴリおよびカテゴリ/リソース パラメーターを有効にすると、**明細行プロパティ**値は、この検証に対して定義した既定値に設定されます。 プロジェクト/カテゴリおよびカテゴリ/リソース パラメーターが有効でない場合、**プロジェクト管理および会計パラメータ**ページの**既定の明細行プロパティの有効化**フィールドに従って、**明細行プロパティ**値は既定値となります。 **明細行プロパティ**値は上書きできます。

時間を追加する日付を選択します。 毎日働いた時間数を入力します。

入力する時間に関するコメントを追加するには、**コメントの追加**をクリックし、内部対象ユーザー、顧客ユーザー、またはその両方に対するコメントを入力します。
内部コメントはプロジェクト マネージャーが確認できます。 顧客コメントは請求書に含まれます。

お気に入りとして行を保存するには、チェック ボックスをオンにし、**お気に入りとして保存**をクリックします。

モバイル アプリケーションでは、財務分析コードおよび添付ファイルのサポートは提供されません。

必要なプロジェクト明細行の追加を続行して、タイムシートを完了します。

**送信**をクリックして、承認ワークフローにタイムシートを送信します。

## <a name="review-timesheets"></a>タイムシートの確認

確認する必要があるタイムシートのリストは、メニューで利用可能です。 このオプションは、ユーザーがワークフローの承認者として指定された場合のみ利用可能です。 ヘッダーおよび明細行の承認の両方がサポートされます。 明細行レベルの承認には、承認に対して複数の明細行をマークする機能があります。 タイムシート情報を確認した後、**承認**、**委任**、または**返品**をクリックしてワークフローを続行します。