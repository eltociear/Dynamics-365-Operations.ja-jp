---
title: "ソフトウェアのライフサイクル ポリシーおよびオンプレミス リリース"
description: "このトピックでは、Microsoft Dynamics 365 for Finance and Operations (オンプレミス) リリースにおける ライフサイクルおよびサポート ポリシーの概要を説明します。"
author: meeramahabala
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SysAbout
audience: Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.custom: 69914
ms.search.region: Global
ms.author: meeram
ms.search.validFrom: 2017-07-15
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: 53c0da5e9697deaf946ccd4fbcd2102faa62b195
ms.openlocfilehash: b5342eb766fe945c301c77b1048cf974e5808461
ms.contentlocale: ja-jp
ms.lasthandoff: 11/02/2018

---

# <a name="software-lifecycle-policy-and-on-premises-releases"></a>ソフトウェアのライフサイクル ポリシーおよびオンプレミス リリース

[!include [banner](../includes/banner.md)]

このトピックでは、Microsoft Dynamics 365 for Finance and Operations (オンプレミス) リリースにおける ライフサイクルおよびサポート ポリシーの概要を説明します。

## <a name="modern-lifecycle-policy"></a>Modern Lifecycle ポリシー 
Microsoft Dynamics 365 for Finance and Operations (オンプレミス) ソフトウェアは、Modern Lifecycle ポリシーの対象となるソフトウェア。 Modern Lifecycle Policy は、継続的に保守およびサポートされる製品およびサービスをカバーします。 このポリシーの詳細については、[Modern Lifecycle ポリシー](https://support.microsoft.com/en-us/help/30881/modern-lifecycle-policy) を参照してください。  

ライセンス認証された顧客は、次のサービスとシステムの要件に従って、Dynamics 365 for Finance and Operations オンプレミス ソフトウェアに対する更新で最新の状態にする必要があります。 このポリシーでは、SA (Software Assurance) または拡張計画を維持し、このトピックの後半で説明する更新プログラムを展開する必要があります。 修正サポート ライフサイクル ポリシー (5 + 5) を使用するお客様は、Microsoft Dynamics AX 2012 R3 にダウングレードする必要があります。 顧客が SA または Enhancement Plan を失うと、Microsoft Dynamics AX 2012 R3 への永久ライセンスの権利のみが適用され、Microsoft Dynamics 365 for Finance and Operations (オンプレミス) ソフトウェアをアンインストールする必要があります。 

## <a name="on-premises-software-update-policies"></a>オンプレミス ソフトウェアの更新ポリシー 
顧客はオンプレミスの展開を完全に制御しており、このポリシーに従わなければなりません。 顧客はオンプレミス環境に更新プログラムをインストールすることを制御しています。 Microsoft は最低限、2027 年 12 月 31 日を通じて Dynamics 365 for Finance and Operations (オンプレミス) ソフトウェアをサポートしますが、顧客がこのポリシーに従って配置されたソフトウェアを最新の状態に保っている場合のみに限ります。

重要な修正および重要でない更新は、次のように処理されます。 
  - **重要な修正** - 重要な修正には、セキュリティの修正および、信頼性と可用性をサポートするために必要な修正が含まれます。 重要な修正は、最新のプラットフォーム更新版で利用可能になります。  
  - **重要ではない更新** – 重要ではない更新を導入するには、最新の Finance and Operations プラットフォームと財務レポートのバージョンに更新する必要があります。   

## <a name="dynamics-365-for-finance-and-operations-on-premises-release-dates"></a>Dynamics 365 for Finance and Operations オンプレミス リリースの日付
アプリケーションおよびプラットフォーム リリースは、ソフトウェアのライフサイクルの月末に期限が切れます。

### <a name="application-releases"></a>アプリケーション リリース

| リリース          |バージョン         | ビルド番号          | 適用の対象 | 有効期限  | 製品の有効期間 | 
|------------------|----------------------|------------------|--------------|---------------|-----------------|
|  Dynamics 365 for Finance and Operations (オンプレミス) | 8.1 | 8.1.136 | 2018 年 11 月 | 2019 年 4 月     | 2027 年 12 月  |
|  Dynamics 365 for Finance and Operations, Enterprise edition (オンプレミス) | 7.3 | 7.3.11971  | 2018 年 3 月 | 2020 年 4 月*     | 2027 年 12 月  |
|  Dynamics 365 for Finance and Operations, Enterprise edition (オンプレミス) | 2017 年 7 月 | 7.2.11792 | 2017 年 6 月 | 2019 年 4 月     | 2027 年 12 月  |


\*すべてのユーザーは、2019 年 4 月 30 日までに Finance and Operations の最新バージョンにする必要があります。 ただし、Microsoft に提出された[拡張要求](../extensibility/extensibility-home-page.md)を実行しなかったユーザーには例外を設けます。 それらのユーザーは、2020 年 4 月までバージョン 7.3 を使用することができます。 詳細については、[1 つのバージョン サービスに関してよく寄せられる質問](../../fin-and-ops/get-started/one-version.md)を参照してください。

### <a name="platform-releases"></a>プラットフォームのリリース

| リリース          |ビルド番号         | 適用の対象          | 有効期限 | 有効期間  |
|------------------|----------------------|------------------|--------------|---------------|
|  プラットフォーム update 20 | 7.0.5030.XXXX  | 2018 年 11 月  | 2019 年 2 月 | 2027 年 12 月     |
|  プラットフォーム update 15 | 7.0.4841.XXXX  | 2018 年 6 月  | 2018 年 9 月 | 2027 年 12 月     |
|  プラットフォーム アップデート 12 | 7.0.4709.41182  | 2018 年 3 月  | 2018 年 6 月 | 2027 年 12 月     |
|  プラットフォーム アップデート 11 | 7.0.4679.35176 | 2017 年 10 月 | 2018 年 4 月 | 2027 年 12 月     |
|  プラットフォーム アップデート 10 | 7.0.4641.16233 | 2017 年 8 月 | 2018 年 4 月 | 2027 年 12 月     |
|  プラットフォーム アップデート 9 | 7.0.4612.35162 | 2017 年 8 月 | 2018 年 4 月 | 2027 年 12 月     |
|  プラットフォーム アップデート 8 | 7.0.4565.1612 | 2017 年 7 月 | 2018 年 4 月 | 2027 年 12 月     |

  > [!NOTE]
  > プラットフォームのリリースは、本質的に累積的です。 重要な、または重要ではない修正プログラムでは、最新バージョンのプラットフォームを使用する必要があります。 

### <a name="downloadable-virtual-hard-drive-vhd-releases"></a>ダウンロード可能な仮想ハード ドライブ (VHD) をリリース
VHD の使用の際には、[ソフトウェア ライセンス条件](https://go.microsoft.com/fwlink/?linkid=851163)が適用されます。 


|                   リリース                    |           VHD 名           | VHD 有効期限 |
|----------------------------------------------|------------------------------|---------------------|
| プラットフォーム アップデート 12 / アプリケーション リリース 7.2 | FinandOps7.2PlatUpdate12.vhd |    2018 年 5 月 24 日     |
| プラットフォーム アップデート 12 / アプリケーション リリース 7.3 | FinandOps7.3PlatUpdate12.vhd |    2018 年 6 月 5 日    |
| プラットフォーム アップデート 15 / アプリケーション リリース 7.3 | FinandOps7.3withPlatUpdate15 |    2018 年 12 月    |

