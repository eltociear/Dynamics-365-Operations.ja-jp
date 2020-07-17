---
title: Finance and Operations と Microsoft Power Platform の統合
description: このトピックでは、Common Data Service における Finance and Operations の仮想エンティティについて説明します。
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
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: f6b61284ce52af563fabc3e86086f7bf9c43cabf
ms.sourcegitcommit: a9dffa475d243e42bd0b64943418c81540d88ba1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "3414067"
---
# <a name="microsoft-power-platform-integration-with-finance-and-operations"></a>Finance and Operations と Microsoft Power Platform の統合

[!include[banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> この機能を使用するには、Common Data Service のサービス更新プログラム 189 が必要です。 Common Data Service のリリース情報は、[最新バージョンの利用可能性](https://docs.microsoft.com/business-applications-release-notes/dynamics/released-versions/dynamics-365ce#all-version-availability)ページに発行されています。

Finance and Operations は、Common Data Service の仮想データ ソースであり、Common Data Service および Microsoft Power Platform からの完全な作成、読み取り、更新、削除 (CRUD) 操作を可能にし ます。 定義上、仮想エンティティのデータは、Common Data Service には存在しません。 その代わりに、属しているアプリケーションで引き続き存在します。 Common Data Service から Finance and Operations エンティティに対して CRUD 操作を有効にするには 、エンティティを Common Data Service の仮想エンティティとして使用できるようにする必要があります。 これにより、Finance and Operations アプリに存在するデータに対して、Common Data Service と Microsoft Power Platform から CRUD 処理を実行できるようになります。

## <a name="prerequisite-reading"></a>前提条件の参照先

Finance and Operations アプリの仮想エンティティのアーキテクチャを理解するには 、Common Data Service と仮想エンティティのしくみを理解しておく必要があります。 したがって、次のドキュメントが前提条件になります。

- [Common Data Service とは](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- [エンティティ概要](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)
- [エンティティの関連付けの概要](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)
- [外部データ ソースのデータを含む仮想エンティティの作成と編集](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)
- [Power Apps ポータルについて](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [Power Apps でのアプリの作成の概要](https://docs.microsoft.com/powerapps/maker/)

## <a name="virtual-entities-for-finance-and-operations-apps"></a>Finance and Operations アプリの仮想エンティティ

Finance and Operations 内のすべての Open Data Protocol (OData) エンティティは、Common Data Service の仮想エンティティとして使用できます。したがって Power Platform でも使用できます。 作成者は、Finance and Operations から直接データを使用して Customer Engagement アプリのエクスペリエンスを構築できるようになりました。このとき、完全な CRUD 機能を使用でき、Common Data Service にコピーする必要はありません。 Power Apps ポータルは、Finance and Operations の業務プロセスのコラボレーション シナリオを可能にする外部向けの Web サイトを構築するために使用できます。

## <a name="architecture"></a>アーキテクチャ

仮想エンティティは、Finance and Operations 以外にも有用な Common Data Service の概念です。 次の図は、仮想エンティティの Finance and Operations プロバイダーを実装する方法を示しています。 6 つの主要メソッドがプロバイダーによって実装されます。 最初の 5 つのメソッドは、**Create**、**Update**、**Delete**、**Retrieve**、**RetrieveMultiple** という標準的な CRUD 操作です。 最後のメソッドである **PerformAction** は、このトピックで後述するように OData アクションを呼び出すために使用されます。 Finance and Operations 仮想エンティティ データ プロバイダー (図では "VE プラグイン" と表示) を呼び出すと、Finance and Operations の CDSVirtualEntityService Web API エンドポイントに対して Secure Sockets Layer (SSL)/トランスポート層セキュリティ (TLS) 1.2 セキュア Web 呼び出しが行われます。 その後、この Web サービスは、Finance and Operations 内の関連する物理エンティティへの呼び出しにクエリを変換し、それらのエンティティで CRUD 操作または OData 操作を呼び出します。 Finance and Operations エンティティはすべての操作で直接呼び出されるため、エンティティまたはバッキング テーブルのビジネス ロジックも呼び出されます。

[![Finance and Operations アプリの仮想エンティティのアーキテクチャ](../media/fovearchitecture.png)](../media/fovearchitecture.png)

呼び出し時、Common Data Service から Finance and Operations アプリまで 2 つの変換点があります。 変換の最初のポイントは、エンティティの物理名などの概念を Finance and Operations エンティティ名に変換する VE プラグインにあります。 また、会社の参照などの既知の概念も変換されます。 Web サービス呼び出しでは、引き続き EntityCollection、Entity、および QueryExpression オブジェクトを使用して、実行される操作が表されます。このとき、VE プラグインから変換されたエンティティ名と概念が使用されます。 最後に、Finance and Operations の CDSVirtualEntityAdapterService Web API によって、QueryExpression から QueryBuildDataSource およびその他の内部 Finance and Operations 言語構成要素への変換が完了します。

仮想エンティティの一部としての Common Data Service および Finance and Operations 間での呼び出しはすべて、コンフィギュレーションで指定されている Azure Active Directory (Azure AD) アプリケーションを使用して、サービス間 (S2S) 呼び出しとして実行されます。 このアプリケーションのユーザーは、CDSVirtualEntityAdapterService Web API とカタログ エンティティ CDSVirtualEntityListEntity に*のみ*アクセスできるようにする必要があります。 これらの特権は、CDSVirtualEntityApplication という名前の、標準のセキュリティ ロールに含まれています。 S2S 呼び出し中に、アクションを呼び出す Common Data Service のユーザーの ID が Common Data Service により提供されます。 CDSVirtualEntityAdapterService Web API は、Finance and Operations の関連付けられているユーザーを検索し、そのユーザーのコンテキストでクエリを実行します。 したがって、S2S 呼び出しでは、すべての Finance and Operations エンティティに明示的にアクセスする必要はありません。 代わりに、データ アクセスを決定するには、アクションを呼び出すユーザーの特権が必要な場合があります。

Power Apps ポータルでは、仮想エンティティにもアクセスできます。 Power Apps ポータル認証は連絡先レコードに基づいているため、連絡先レコードと Finance and Operations ユーザーの間のマッピングは Common Data Service の msdyn\_externalportalusermapping テーブルで管理されます。 このテーブルは、Common Data Service の高度な特権を持つユーザーのみが編集できます。このユーザーは、ポータル ユーザーのセキュリティア クセスを Finance and Operations 仮想エンティティに対して制御する権限を持っています。 Power Apps ポータル アクセス用に設定されたすべての Finance and Operations ユーザーには、CDSVirtualEntityAuthorizedPortalUser セキュリティ ロールが割り当てられている必要があります。また、システム管理者またはセキュリティ管理者ロールを割り当てることはできません。 仮想エンティティに適用される Power Apps ポータル セキュリティ設定に関係なく、Finance and Operations アプリへの結果のクエリは常に関連付けられた Finance and Operations ユーザーとして実行され、そのユーザーのエンティティと行のセキュリティ設定に従います。 匿名ポータルのアクセスもサポートされます。 このタイプのアクセスとその実行方法については、[Power Apps ポータル参照](power-portal-reference.md)を参照してください。