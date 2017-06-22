---
title: "オンライン ストアのコンフィギュレーション"
description: "この記事では、Microsoft Dynamics 365 for Operations からオンライン ストアを 1 か所で設定および管理できるトピックへのリンクを示します。"
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Retail
ms.custom: 31541
ms.assetid: 7a25f9b4-a0bb-4e8c-95c0-c0799ec0620d
ms.search.region: Global
ms.author: meeram
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: 563d11fb99c8aebce78f8962dbeeac41fb469041
ms.contentlocale: ja-jp
ms.lasthandoff: 05/25/2017


---

# <a name="configure-an-online-store"></a>オンライン ストアのコンフィギュレーション

[!include[banner](../includes/banner.md)]


この記事では、Microsoft Dynamics 365 for Operations からオンライン ストアを 1 か所で設定および管理できるトピックへのリンクを示します。

次の表に記載されているトピックは、Dynamics 365 for Operations クライアントで Dynamics 365 for Operations - Retail コンポーネントおよび小売オンライン店舗の設定に役立ちます。

## <a name="configure-an-online-store"></a>オンライン ストアのコンフィギュレーション
| タスク                                                | 細目                                                                                                                                                                                                                                                                                                                                                   | トピック                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Retail コンポーネントをコンフィギュレーションします。                        | 小売操作の情報を設定および管理します。 この情報には、店舗、税、製品、ギフト カード、プロモーション、割引が含まれます。                                                                                                                                                                                                          | [小売の設定および管理](https://technet.microsoft.com/en-us/library/hh597201.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ)                                                                                                                                                                                                                                                                                          |
| 小売チャネル ナビゲーション階層をコンフィギュレーションします。    | オンライン ストアを通じて提供する製品のカテゴリ構造を設定するために、小売チャンネル ナビゲーション カテゴリ階層を作成します。 カテゴリ階層を定義し、カテゴリに製品、製品属性グループ、および属性値を割り当てます。 その後、オンライン ストアにカテゴリ階層を割り当てます。                            | [小売階層の設定](https://technet.microsoft.com/en-us/library/hh580593.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ) [属性と属性の型を設定](https://technet.microsoft.com/en-us/library/hh227548.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ) [小売属性グループの設定](https://technet.microsoft.com/en-us/library/jj728713.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ) |
| 組織階層にオンライン ストアを追加します。 | 作成したオンライン ストアで製品の品揃えを割り当てたり、注文を満たしたり、またはそのオンライン ストアの情報を含むレポートを生成したりするには、1 つ以上の組織階層に店舗を割り当てる必要があります。 少なくとも、オンライン ストアを製品の品揃えを含む組織階層に割り当てる必要があります。 | [オンライン ストアの設定](https://technet.microsoft.com/en-us/library/jj682095.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ)                                                                                                                                                                                                                                                                                                     |
| オンライン ストアに荷渡方法を追加します。          | オンライン ストアが提供する配送方法を選択します。                                                                                                                                                                                                                                                                                                 | [オンライン ストアの設定](https://technet.microsoft.com/en-us/library/jj682095.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ)                                                                                                                                                                                                                                                                                                     |
| 属性をマップし、メタデータを追加します。                   | 各カテゴリまたはチャネル製品の属性が Microsoft SharePoint サイトのオンライン ストアでどのように動作するかを示すオプションを選択します。                                                                                                                                                                                              | [オンライン ストアの設定](https://technet.microsoft.com/en-us/library/jj682095.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ)                                                                                                                                                                                                                                                                                                     |

## <a name="configure-online-store-products"></a>オンライン ストア製品のコンフィギュレーション
| タスク                                 | 細目                                                                                                                                           | トピック                                                                                                                                                                                                                                                                            |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| オンライン ストアに品揃えを追加します。 | オンライン ストアで提供する製品を含む品揃えを追加します。                                                                  | [オンライン ストアの設定](https://technet.microsoft.com/en-us/library/jj682095.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ)                                                                                                                                              |
| カタログを管理します。                     | 店舗で提供する製品を識別するために、製品カタログを使用します。                                                              | [キー タスク: 小売製品のカタログの作成](https://technet.microsoft.com/en-us/library/jj728712.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ)                                                                                                                           |
| 価格を管理します。                       | 価格と割引、チャネル、カタログ、所属、ロイヤルティ プログラムを管理するリンクとなる価格グループを設定して使用します。 | [価格グループを使用して価格を設定](https://technet.microsoft.com/en-us/library/hh597169.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ) [税の設定](https://technet.microsoft.com/en-us/library/hh580571.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ) |
| 割引を管理します。                    | 価格調整および 4 種類の割引を設定および管理します。                                                                                  | [価格調整と割引の設定](https://technet.microsoft.com/en-us/library/hh597114.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ)                                                                                                                          |
| 出荷費用を管理します。             | オンライン ストア固有の出荷費用を設定および管理します。                                                                     | [オンライン ストアの出荷費用の設定](https://technet.microsoft.com/en-us/library/jj728714.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ)                                                                                                                           |
| 荷渡方法を管理します。            | オンライン ストアが提供する荷渡方法を追加します。                                                                                        | [荷渡方法の設定](https://technet.microsoft.com/en-us/library/jj728719.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ)                                                                                                                                            |

## <a name="set-up-data-exchange-between-dynamics-365-for-operations-and-the-online-store"></a>Dynamics 365 for Operations とオンライン ストアでのデータ交換の設定
| タスク                                 | 細目                                                                                                                               | トピック                                                                                                                                                                                                                                                                                  |
|--------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| チャネル統合プロファイルを設定します。 | プロファイルは、Retail コンポーネントの相互通信を可能にします。 データ交換設定をコンフィギュレーションする前にプロファイルを設定します。 | [Real-time Service プロファイルの設定](https://technet.microsoft.com/en-us/library/hh580631.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ) [チャンネル プロファイルの設定](https://technet.microsoft.com/en-us/library/jj677402.aspx) (Microsoft Dynamics AX 2012 用 TechNet コンテンツ) |

 



