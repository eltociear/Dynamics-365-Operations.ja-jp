---
title: 分析ワークスペースでの埋め込みレポートのカスタマイズ
description: このトピックでは、分析ワークスペースに埋め込まれているアプリケーション レポートをパワー ユーザーがカスタマイズできるようにする方法について説明します。
author: TJVass
manager: AnnBe
ms.date: 7/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: PowerBIConfiguration
audience: IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 27661
ms.assetid: 861cfa94-c6f3-4c84-89ac-22c78bf6b7a4
ms.search.region: Global
ms.author: milindav
ms.search.validFrom: 2019-07-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3722c7e46f77779005b82968aa6cdd1175d5a438
ms.sourcegitcommit: 9f762fa89c5b432667aa156c22d679a7f601952d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2019
ms.locfileid: "1731110"
---
# <a name="customize-embedded-reports-in-analytical-workspaces"></a>分析ワークスペースでの埋め込みレポートのカスタマイズ

[!include [banner](../includes/banner.md)]


## <a name="analytical-workspaces"></a>分析ワークスペース

アプリケーション スイートには、分析ワークスペースがバンドルされています。 レポートを使用すると、標準の業務オペレーションに基づくデータへのユーザー インサイトを提供できます。 このレポートは、ビジネス専門家によって定義される包括的なレポートです。 これには、あらゆる業種の幅広いユーザーの興味を引くメトリクスが含まれます。

ただし、場合によっては、標準レポートに、すべての顧客に関連しないデータが含まれていることがあります。 多くの場合、顧客は、標準レポートから除外されたデータポイントまたは計算にアクセスすることができます。

パワー ユーザーは、ウェブ フレンドリー設計ツールを使用して、アプリケーションに埋め込まれている分析レポートをカスタマイズできます。 自由形式のキャンバス デザイナーを使用すると、必要な関連業務インサイトに習熟しているユーザーは組織の成功を支援できます。

> [!IMPORTANT]
> 埋め込み分析レポートに対して行われたカスタマイズは、サービスによって自動的に配置され、システムの他のユーザーが使用できるようになります。

### <a name="important-points-about-embedded-analytical-reports"></a>埋め込み分析レポートに関する重要なポイント

標準レポートからは、特定のビジネス ペルソナに合わせてカスタマイズされたインサイトが提供されますが、カスタマイズによって、しばしば、これらの標準レポートの価値を最大化することができます。

このサービス機能に関する重要な注意事項を次に示します。

- カスタマイズはレポート デザイン キャンバスに限定されます。 ユーザーは、レポートのデータ セットの定義を変更できません。
- 分析ワークスペースに対して行われるレポートのカスタマイズは、環境内のすべてのユーザーに適用されます。
- このサービスでは、製品のアップグレード時にレポートのカスタマイズが自動的に維持されます。
- Microsoft Dynamics 365 for Finance and Operationsサービスは、分析ワークスペースに対して行われたカスタマイズのエクスポートをサポートしていません。

### <a name="customize-an-analytical-workspace"></a>分析ワークスペースをカスタマイズします。

埋め込みアプリケーション ソリューションをカスタマイズするには、ユーザーはシステム レポート エディター セキュリティ グループのメンバーである必要があります。 このセキュリティ グループのメンバーは、アプリケーション ワークスペースのアクション ウィンドウの**オプション** タブにあるボタンを使用してカスタマイズを行うことができます。 この例では、アプリケーション スイートにバンドルされている標準分析ワークスペースのいずれかをカスタマイズする方法を示します。

1. [Finance and Operations] をクリックし、カスタマイズするアプリケーション ワークスペースを開きます。 この例では、 **報酬管理** ワークスペースに埋め込まれている標準分析レポートを置換します。

    ![報酬管理ワークスペース](media/compensation-management-workspace.png)

2. **分析** タブを選択すると、ワークスペースの埋め込み分析レポートにアクセスできます。

    ![報酬管理分析ワークスペースの [分析] タブ](media/compensation-management-analytics.png)

    デフォルトでは、Finance and Operations と共にパッケージ化された標準分析ワークスペース ソリューションが表示されます。 このソリューションのレポートは、プロビジョニング プロセス中に環境に合わせて自動的に配置および設定されます。

    > [!NOTE]
    > 分析ワークスペースには、Power BI専用の環境に対してのみ使用できるホストされたMicrosoftサービスが必要です。 詳細については、「[1 Box 環境での分析ワークスペースおよびレポートへのアクセス](https://blogs.msdn.microsoft.com/dynamicsaxbi/2017/07/29/accessing-analytical-workspaces-on-1box-environment/)」を参照してください。

3. アクション ペインの**オプション** タブの**Power BI**グループで **Edit Analytics** を選択してください。

    ![Analytics Analytics ボタンを編集します](media/analytical-workspace-edit-entry.png)

    編集モードで分析ワークスペースが開き、Power BI web デザイナー ツールに直接アクセスできます。

    ![分析ワークスペース レポート エディター](media/analytical-workspace-edit-view.png)

4. レポート キャンバスPower BIをカスタマイズするには、web デザイナー ツールを使用します。 直感的な web コントロールを使用すると、ビジュアルの追加および削除、ビジュアル型の変更、コンテンツの書式設定などの一般的なアクションを実行できます。 視覚エフェクト レポートのソースを調査して、システムで利用可能な最も関連性のあるデータに基づいて意思決定を行うこともできます。 詳細については、「[Power BIレポートへの視覚エフェクトの追加](https://docs.microsoft.com/power-bi/visuals/power-bi-report-add-visualizations-i)」を参照してください。
5. レポートのカスタマイズが完了したら、 **保存** ボタンを選択してレポート編集のレベルを上げます。 レポートへのカスタマイズは、サービスにすぐに反映されます。 したがって、組織のユーザーは最新のイノベーションにアクセスできます。

## <a name="restore-the-standard-application-solution"></a>標準のアプリケーション ソリューションの復元

アプリケーション ソリューションにバンドルされている分析ワークスペースを復元するには、次の手順に従います。

1. 分析ワークスペースの、アクション ペインの、**オプション** タブの、**Power BI**グループで、**Restore Analytics** を選択してください。
2. ワークスペースの更新を表示するには、ページを再度読み込みます。 ワークスペースから移動して戻ってくるか、ブラウザーを更新します。
3. **報酬管理**ワークスペースで、**Analytics** タブを選択すると、アプリケーションと共にパッケージ化された元の分析ワークスペースにアクセスできます。