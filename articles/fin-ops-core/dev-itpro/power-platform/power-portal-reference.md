---
title: Power Apps ポータルと Finance and Operations
description: このトピックでは、Power Apps ポータルを Finance and Operations で使用する方法について説明します。
author: Sunil-Garg
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-05-31
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 40b13941d0f471a0aa1682d262c0c336a966716b
ms.sourcegitcommit: 4db8c30c2f26af1896938dd3ece3756577374ecb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "3416542"
---
# <a name="power-apps-portals-with-finance-and-operations"></a>Power Apps ポータルと Finance and Operations

[!include[banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> この機能を使用するには、Common Data Service のサービス更新プログラム 189 が必要です。 Common Data Service のリリース情報は、[最新バージョンの利用可能性](https://docs.microsoft.com/business-applications-release-notes/dynamics/released-versions/dynamics-365ce#all-version-availability)ページに発行されています。

Power Apps ポータルでは、Common Data Service の仮想エンティティとして使用できる Finance and Operations エンティティに対して、作成、更新、および削除 (CRUD) 操作を行うことができます。 このトピックでは、Finance and Operations アプリの Power Apps ポータルに実装されているシナリオについて説明します。

## <a name="anonymous-access-from-power-apps-portals"></a>Power Apps ポータルからの匿名アクセス

Finance and Operations の入札やオンボードなどの業務プロセスのコラボレーション シナリオは、外部ユーザーが Finance and Operations アプリのユーザーではない場合でも、Power Apps ポータルからの参加を要求します。 匿名アクセスは、Finance and Operations アプリ ユーザーではないユーザーがログインしなくてもよいので、このような状況では匿名アクセスのシンプルさが魅力的です。 ただし、業務プロセス内の意味のあるタスクを完了するために、Finance and Operations で CRUD 処理を実行することが期待されます。

必要なエンティティのみが匿名アクセスに対して有効になるようにするには、Finance and Operations のユーザーが匿名アクセスに使用するユーザーとして指定されている必要があります。 この指定は、**システム パラメーター** ページ (**システム管理 \> システム パラメーター**) の **仮想エンティティ** タブにある **匿名ポータルのアクセス ユーザー ID** フィールドで構成します。 指定されたユーザーを職務とセキュリティ ロールに割り当てて、Power Portal から匿名でやりとりするすべてのユーザーが使用できるようにする必要がある特定のデータへのアクセスを制御することができます。

このシナリオには匿名アクセスが含まれるため、セキュリティの観点から、**匿名ポータルのアクセス ユーザー ID** フィールドで指定されているユーザーにのみ、重要なユーザー コンテキストがあります。

## <a name="authenticated-access-from-power-apps-portals"></a>Power Apps ポータルからの認証済みアクセス

Power Apps ポータルから Finance and Operations へのユーザーアクセスを完全に認証することによって、Finance and Operations のユーザーが Power Apps ポータルからも操作できるようにします。 Power Apps ポータルにサインインするユーザーは、適切なセキュリティ ロールを持つ Finance and Operations のユーザーであることもわかっています。 Finance and Operations の業務プロセスにおける既存の役割は、Power Portal でこのタイプの認証されたユーザーに対するセキュリティ アクセスを制御します。

Power Apps ポータル認証は Common Data Service の連絡先エンティティにリンクされているため、Common Data Service の連絡先と Finance and Operations の対応するユーザーの間にマッピングを確立する必要があります。 このマッピングは、エントリを **msdyn\_externalportalusermapping** エンティティに追加することによって実行できます。 セキュリティの観点から、認証されたユーザーが使用できる仮想エンティティの範囲は、Power Apps ポータルで **グローバル** としてコンフィギュレーションする必要があります。

別のテナントから認証されたユーザーをユーザーとして Finance and Operations に追加する必要がある場合、Finance and Operations で[新しいユーザーの作成](../sysadmin/tasks/create-new-users.md)プロセスを使用する必要があります。 このプロセスにより、Microsoft Azure Active Directory (Azure AD) 企業間 (B2B) ゲスト ユーザーとして、テナント間のユーザーが追加されます。