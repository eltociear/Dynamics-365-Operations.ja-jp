---
title: RCS で ER コンフィギュレーションを作成し、グローバル リポジトリにアップロードする
description: このトピックでは、Microsoft Regulatory Configuration Service (RCS) の電子レポート (ER) の構成を作成する方法と、グローバル レポジトリにアップロードする方法ついて説明します。
author: JaneA07
manager: AnnBe
ms.date: 05/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 0e194a8b777f984412d81e315f92ab4bb8a3b0c9
ms.sourcegitcommit: 204cec8ca2a6c4474d21dbcd408e369131a47856
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "3371255"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a>Regulatory Configuration Services (RCS) で ER の構成を作成し、グローバル リポジトリにアップロードする

[!include [banner](../includes/banner.md)]

Microsoft Regulatory Configuration Service (RCS) を使用して電子レポート (ER) の構成を設計し、組織内で使えるように公開することができます。

以下の手順では、システム管理者 または電子レポートの開発者ロールを持つユーザーが、RCS インスタンスで構成された ER 構成の派生バージョンを作成し、派生する構成をグローバル リポジトリにアップロードする方法を説明します。 

この手順を完了する前に、まず以下の手順を完了する必要があります:

- RCS インスタンスへのアクセス権。
- 有効な構成プロバイダーを作成する。 詳細については、[構成プロバイダーを作成して、有効としてマークする](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) を参照してください。

また、RCS 環境がプロビジョニングされていることを確認しておく必要があります。

1. Finance and Operations アプリで、**組織管理** \> **ワークスペース** \> **電子レポート** に移動します。
2. RCS 環境がご利用の会社にプロビジョニングされていない場合は、**Regulatory services – 外部の構成** を選択し、続いてプロビジョニングの指示に従います。

RCS 環境が既にプロビジョニングされている場合は、[サインイン] オプションを選択して、ページの URL を使用してこの機能にアクセスします。

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a>RCS で構成の派生バージョンを作成する

1. **電子レポート**ワークスペースで、ご利用の組織に対して有効な構成プロバイダーがあることを確認します。 
2. **コンフィギュレーションをレポートする**を選択します。
3. 新しいバージョンを派生させる構成を選択します。 ツリーの上にあるフィルターフィールドを使用して検索を絞り込むことができます。
4. **構成の作成** \> **名前から派生する**を選択します。
5. 名前と説明を入力し、**構成の作成** を選択して、新たな派生バージョンを作成します。
6. 新たに派生した構成を選択し、バージョンの説明を追加して、**OK** を選択します。 構成先のステータスが**完了**に変更されます。

![RCS における新たな構成のバージョン](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_CompleteConfig.JPG)

> [!NOTE]
> 構成のステータスが変更されると、接続されているアプリケーションに関連した検証のエラーメッセージが表示される場合があります。 検証を無効にするには、**構成** タブのアクション ウィンドウで、**ユーザーパラメーター** を選択し、**設定のステータス変更時に検証をスキップしてリベースする** オプションを **はい**に設定します 

## <a name="upload-a-configuration-to-the-global-repository"></a>グローバル リポジトリに構成をアップロードする

新たな構成や派生した構成を組織と共有するには、グローバル リポジトリにアップロードします。

1. 構成の完成バージョンを選択し、**リポジトリにアップロード** を選択します。
2. **グローバル (Microsoft)** オプションを選択し、**アップロード** を選択します。

    ![リポジトリ オプションへのアップロード](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_Upload_to_GlobalRepo_options.JPG)

3. 確認のメッセージ ボックスで、**はい** を選択します。 
4. 必要に応じてバージョンの説明を更新し、**OK** を選択します。 

構成のステータスが**共有**に更新され、構成がグローバル リポジトリにアップロードされます。 そこからは、次の方法で作業することができます:

- Dynamics 365 のインスタンスにインポートします。 詳細については、[(ER) RCS から構成をインポートする](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md) を参照してください。
- サード パーティや外部の組織と共有する場合は、[RCS 電子レポート (ER) の構成を外部組織と共有する](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/rcs-global-share-configuration.md)を参照してください

![グローバル リポジトリの イントラスタット Contoso の構成バージョンが派生されました](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/Janeaug_RCSdocs/articles/finance/localizations/media/RCS_Config_upload_GlobalRepo.JPG)