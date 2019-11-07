---
title: 1 つの Azure AD テナントにおける複数の LCS プロジェクトおよび実稼働環境
description: このトピックでは、複数の LCS プロジェクトと実稼動環境を同じ Azure Active Directory テナント上に実装する方法について説明します。
author: ClaudiaBetz-Haubold
manager: AnnBe
ms.date: 06/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: chaubold
ms.search.validFrom: 2018-05-30
ms.dyn365.ops.version: AX 7.0
ms.openlocfilehash: a13e9186aae821e128c6ca14e25faace6637bd2a
ms.sourcegitcommit: d554faca895609b8124bf2ea5aca5a55c407534a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "2537821"
---
# <a name="multiple-lcs-projects-and-production-environments-on-one-azure-ad-tenant"></a>1 つの Azure AD テナントにおける複数の LCS プロジェクトおよび実稼働環境

[!include [banner](../includes/banner.md)]

すべての新しいクラウド プロジェクトにおいて、1 つの Microsoft Dynamics Lifecycle Services (LCS) の実装プロジェクトは、1 つの実稼働インスタンスへのアクセスを可能にする Microsoft Azure Active Directory (Azure AD) のテナントでインスタント化されます。 まれに、特定の実装の要件を処理するため、並列実行している複数の生産インスタンスが必要になります。 同じ Azure AD テナントに対して複数の LCS プロジェクトを作成することで、複数の実稼動インスタンスを持つことができます。 複数の生産インスタンスが必要になる場合の最も一般的なシナリオを次に示します。

- 移住地や待機時間のデータまたはデータ量のグローバル実装の要件は、1 つのインスタンスでは満たされません。
- 組織内の異なる部署は、製品を独立したアプリケーションとして個別に実行しています。

Microsoft Dynamics サービス エンジニアリング (DSE) チームによる手動操作は、共有 Azure AD テナントで追加の LCS プロジェクトを作成するために必要になります。 このアプローチは、単一インスタンスの戦略が本当に実現可能でない場合にのみ使用する必要があります。 追加の LCS プロジェクトを作成する前に、業務の妥当性を指定し、アプローチのすべての影響を理解していることを確認する必要があります。 このプロセスは、可能な限り実装ライフサイクルの早い段階で開始する必要があります。 続行する場合は、追加の LCS プロジェクトを必要としているプロジェクトに誰が割り当てられているかを、FastTrack ソリューション アーキテクトに通知する必要があります。 ソリューション アーキテクトがプロジェクトに割り当てられていない場合、顧客は、サポート チケットを開く必要があります。

## <a name="licensing-requirements"></a>ライセンス要件

同じ Azure AD テナント上で実行されるすべての LCS 実装プロジェクトでは、ライセンス契約の最小要件を満たす必要があります。 たとえば、同じ Azure AD テナントに 3 つの LCS 実装プロジェクトがある場合、顧客は最低限のサブスクリプション ライセンス数の 3 倍以上を購入する必要があります。 現在、ライセンスの最少要件は 20 のユーザー フルライセンスです。 したがって、同じ Azure AD テナントで 3 つの LCS 実装プロジェクトを実行するには、少なくとも 60 ライセンスを購入する必要があります。

ライセンスは Azure AD テナントに関連付けられているため、付与された LCS プロジェクトは割り当てられた数量のライセンスしか使えませんが、すべての LCS プロジェクトの**利用可能なサブスクリプション**ページでは、ライセンスの総数が表示されます。 この LCS プロジェクトへのライセンス配分は、システム外で文書化する必要があります。

同時に複数の環境にアクセスするユーザーは、環境ごとに個別にライセンスが必要です。 ライセンスの詳細については、[ライセンス ガイド](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409)をダウンロードしてください。

## <a name="disadvantages-of-multiple-lcs-projects"></a>複数の LCS プロジェクトの欠点

複数の LCS プロジェクトを持つことにはいくらかの欠点があります。 次にそのいくつかを挙げます。

- マスター データは共有されません。
- 会社間トランザクションがサポートされていません。
- 統合は各 LCS プロジェクトで構成される必要があります。
- 各 LCS プロジェクトには、個別の自分のデータベースの持ち込み (BYOD) インスタンスが必要です。
- コードが同じ場合でも、各インスタンスでユーザー受け入れテスト (UAT) を行う必要があります。 コード ベースを共有している場合でも、LCS のプロジェクト間で誤差が発生する可能性があるため、各インスタンスに UAT が必要です。 差異の 1 つのソースは LCS プロジェクトごとに個別に実行する必要がある統合設定および BYOD コンフィギュレーションであるため、各 LCS プロジェクトでテストする必要があります。 さらに、地域ごとに違うアプリケーション構成が機能に影響する可能性があったり、別のデータ センターが別の Azure サービスのセットをサポートしたりなど、様々なデータ バリエーションがあります。
- Microsoft Azure DevOps は各 LCS プロジェクトで構成される必要があります。 カスタマイズとコードを共有する場合、同じ Azure DevOps プロジェクトを使用することが理にかなっています。

## <a name="advantages-of-multiple-lcs-projects"></a>複数の LCS プロジェクトの利点

複数の LCS プロジェクトを持つことにも利点があります。 次にそのいくつかを挙げます。

- 待機時間低減のため、LCS プロジェクトごとにデータ センターを選択することができます。
- データ所在地の法的要件を満たすため、LCS プロジェクトごとにデータ センターを選択することができます。
- コードの導入やアップグレードなど、サービス運用のスケジュールを立てることがより柔軟になります。

## <a name="requesting-multiple-lcs-projects-on-the-same-azure-ad-tenant"></a>同じ Azure AD テナントで複数の LCS プロジェクトを要求します。

ソリューションに同じ Azure AD テナントで複数の LCS プロジェクトが必要になる場合、元のプロジェクトを除くすべての LCS プロジェクトは DSE チームにより必要に応じたプロビジョニングをする必要があります。 プロジェクトがオンボーディングされた時点など、できるだけ早く、この要件について DSE チームに知らせる必要があります。 詳細については、[Onboard の製品](../imp-lifecycle/onboard.md) を参照してください。 追加の LCS 実装プロジェクトを要求するには、顧客は、LCS でサポート ポータルを使用してサポート リクエストを作成する必要があります。 この要求では、顧客は次の情報を指定する必要があります。

- 業務の妥当性。
- エンタープライズおよびプロジェクト構造。 この情報には、次の詳細が含まれています。

    - 実装プロジェクトの名前
    - LCS プロジェクトごとのライセンスの詳細

- 同じ Azure AD テナントにおける、複数の LCS プロジェクトの影響を、顧客が理解していることを確認します。

## <a name="online-deployments-in-china-sovereign-cloud"></a>中国の主権クラウドにおけるオンラインの展開
中国の導入 / ロールアウトが実装に含まれる場合、Dynamics 365 Finance オンライン導入が 2019 年 4 月より中国本土で利用可能になったと伝えています。 詳細については、[Microsoft Dynamics 365 for Finance and Operations 21Vianet にて運用](../../dev-itpro/deployment/china-local-deployment.md) を参照してください。 この配置は、中国における規制要件に準拠するように設計されており、サービスには 21Vianet が運営およびトランザクション処理する別のテナント (Azure Active Directory) を持つクラウド サービスのインスタンスが、物理的に分離されています。 

これは、別のテナント (Azure Active Directory) を持つ複数のクラウドの単一組織です。 上記のように、マルチ Lifecycle Services プロジェクトまたは運用環境におけるメリットとデメリットは引き続き適用されますが、ライセンス要件と要求の手順は異なります。 あらゆるプロセス支援において、Microsoft Account Executive または実装パートナーと協力します。