---
title: ワークフロー ビジネス イベント
description: ワークフロー ビジネス イベントは、ワークフローの処理のさまざまなポイントで生成されます。
author: ChrisGarty
manager: AnnBe
ms.date: 10/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Developer
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2019-3-31
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 08d362d9a11458443da48902a5cb07db7f20ef8e
ms.sourcegitcommit: 69eaadfb65c5d098b241dfb22f49278683c9e187
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "2631350"
---
# <a name="workflow-business-events"></a>ワークフロー ビジネス イベント
[!include[banner](../includes/banner.md)]

ワークフロー ビジネス イベントは、ワークフローの処理のさまざまなポイントで生成されます。   

## <a name="workflow-construction"></a>ワークフローの構築

ワークフローを構築するため、開発者は Visual Studio ツール内のメタデータ及びコードでワークフロー コンポーネントを定義することができます。

管理者は Web クライアントでワークフローを作成してから、ワークフロー デザイナーでそれらをデザインすることができます。 詳細については、[ワークフローの作成](../../fin-ops/organization-administration/create-workflow.md)を参照してください。

### <a name="workflow-components"></a>ワークフローのコンポーネント
ワークフロー コンポーネントはメタデータで以下のように定義されます。
- **ワークフロー タイプ** - テンプレートとしても知られるワークフロー タイプは、ワークフローで許容される要素を定義します。 管理者はワークフローのデザインを作成するときに実際に使用される要素を決定します。 
     - アプリケーション エクスプローラーで、**AOT > ビジネス プロセスおよびワークフロー > ワークフロー タイプ** の順に移動します。
- **ワークフロー要素** - ワークフロー要素はワークフローを構成する実行可能要素です。 詳細については、[ワークフロー要素](../../fin-ops/organization-administration/workflow-elements.md)を参照してください。
     - タスク (または手動タスク) - **AOT > ビジネス プロセスおよびワークフロー > ワークフロー タスク** の順に移動します。
     - 承認 - **AOT > ビジネス プロセスおよびワークフロー > ワークフローの承認** の順に移動します。
     - 自動化タスク - **AOT > ビジネス プロセスおよびワークフロー > ワークフロー自動化タスク** の順に移動します。

## <a name="workflow-runtime"></a>ワークフロー ランタイム
ユーザーがワークフローを送信すると、ワークフローはキューに追加され、**ワークフロー メッセージ処理** バッチ ジョブを使用して実行されます。 ワークフローの実行時、終了に達するまですべての [接続されたワークフロー要素](../../fin-ops/organization-administration/create-workflow.md#connect-the-elements)を経て進行します。 ワークフロー ランタイムが[手動タスク要素](../../fin-ops/organization-administration/workflow-elements.md#manual-task)に遭遇すると、[タスクに割り当てわれたユーザー](../../fin-ops/organization-administration/configure-manual-task-workflow.md#assign-the-task)に対して作業項目が作成されます。 ワークフロー ランタイムが[承認要素](../../fin-ops/organization-administration/workflow-elements.md#approval-processes)に遭遇すると、[各承認ステップに割り当てわれたユーザー](../../fin-ops/organization-administration/configure-approval-step-workflow.md#assign-the-approval-step)ごとに作業項目が作成されます。

## <a name="workflow-business-event-categories"></a>ワークフロー ビジネス イベントのカテゴリ

ワークフロー ビジネス イベントには 5 つの異なるカテゴリがあります。 カテゴリが Microsoft Flow に表示され、イベントを選択できます。

![Microsoft Flow でのビジネス イベント カテゴリ](media/Business-event-category.png  "Microsoft Flow でのビジネス イベント カテゴリ")
- **カテゴリ: ワークフロー タイプ** 
     - これらのイベントは、開始および完了などのワークフロー イベントで発生します。 すべてのワークフロー インスタンスはこのカテゴリに相当します。
     - **ID の形式** - "Workflow_" + ワークフロー名 + ワークフロー インスタンス ID、たとえば、"Workflow_BudgetPlanReview_000002"
     - **名前の形式** - ワークフロー ラベル + " (" + ワークフロー インスタンス ID ")"、たとえば、"Prepare department budget (000002)"
- **カテゴリ: 開始されたワークフロー要素**
     - これらのイベントはワークフロー要素が開始されたときに発生します。 ワークフロー インスタンス内のすべての有効なワークフロー要素はこのカテゴリに相当します。 
     - **ID の形式** - "Workflow_" + ワークフロー名 + ワークフロー インスタンス ID + "_" + ワークフロー要素名 + "_Started"、たとえば、"Workflow_BudgetPlanReview_000002_BudgetActivateBudgetPlanChild_Started"
     - **名前の形式** - ワークフロー ラベル + " (" + ワークフロー インスタンス ID ") - " + ワークフロー要素ラベル、たとえば、"Prepare department budget (000002) - Activate associated budget plan"
- **カテゴリ: ワークフロー要素**
     - これらのイベントは、完了などの、開始以外のワークフロー要素イベントで発生します。 ワークフロー インスタンス内のすべての有効なワークフロー要素はこのカテゴリに相当します。 
     - **ID の形式** - "Workflow_" + ワークフロー名 + ワークフロー インスタンス ID + "_" + ワークフロー要素名、たとえば、"Workflow_BudgetPlanReview_000002_BudgetActivateBudgetPlanChild"
     - **名前の形式** - ワークフロー ラベル + " (" + ワークフロー インスタンス ID ") - " + ワークフロー要素ラベル、たとえば、"Prepare department budget (000002) - Activate associated budget plan"
- **カテゴリ: ワークフローの外部タスク** 
     - これらのイベントはワークフロー自動化タスク要素が開始されたときに発生します。 ワークフロー インスタンス内のすべての有効なワークフロー自動化タスク要素はこのカテゴリに相当します。 
     - **ID の形式** - "Workflow_" + ワークフロー名 + ワークフロー インスタンス ID + "_" + ワークフロー要素名 + "_ExternalTask"、たとえば、"Workflow_BudgetPlanReview_000002_BudgetActivateBudgetPlanChild_ExternalTask"
     - **名前の形式** - ワークフロー ラベル + " (" + ワークフロー インスタンス ID ") - " + ワークフロー要素ラベル、たとえば、"Prepare department budget (000002) - Activate associated budget plan"
- **カテゴリ: ワークフロー作業項目**
     - これらのイベントはユーザーに対してワークフロー作業項目が作成されるときに発生します。 ワークフロー インスタンス内のすべての有効なワークフロータスクおよびワークフロー承認はこのカテゴリに相当します。 
     - **ID の形式** - "Workflow_" + ワークフロー名 + ワークフロー インスタンス ID + "_" + ワークフロー要素名 + "_WorkItem"、たとえば、"Workflow_BudgetPlanReview_000002_BudgetActivateBudgetPlanChild_WorkItem"
     - **名前の形式** - ワークフロー ラベル + " (" + ワークフロー インスタンス ID ") - " + ワークフロー要素ラベル、たとえば、"Prepare department budget (000002) - Activate associated budget plan"

## <a name="completion-of-a-work-item-in-flow"></a>フローでの作業項目の完了
ワークフロー ビジネス イベント は承認フローのトリガーに優れたターゲットです。 **ワークフロー作業項目** イベントは、フローの作業項目の完了を容易にするために、validate および OData 完了アクションと組み合わせて使用できます。

承認やタスク作業項目は、次の手順を使用してフローで完了できます:
- 適切な **ワークフロー作業項目** イベントをターゲットにした **ビジネス イベントが発生した場合** トリガーを使用して、フローをトリガーします。
- **WorkflowWorkItems** エンティティで **検証** メソッドを呼び出すことで、**ワークフロー作業項目** に有効な一連の情報が含まれ、完了の準備が出来ていることを検証します。 
- 作業項目に完了する準備ができていない場合は、割り当てられたユーザーに通知を送信して、注意が必要な作業項目があることを知らせます。
- 作業項目に完了す準備ができている場合は、使用可能な回答オプションをユーザーに送信して、割り当てられたユーザーに回答を要求します。
- 回答が提供された後で **WorkflowWorkItems** エンティティの **完了** メソッドを呼び出して、その回答で作業項目を完了します。 

Microsoft Flow で作業項目完了を設定する詳細なガイドは [ワークフロー承認ビジネス イベントを消費する](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/how-to/how-to-flow) を参照してください。

## <a name="templates-for-work-item-completion-in-microsoft-flow"></a>Microsoft Flow での作業項目完了のテンプレート

Microsoft Flow での作業項目完了に関する次のテンプレートが使用できます。
- [Dynamics 365 for Finance and Operations ワークフロー作業項目 (PU26) を完了](https://flow.microsoft.com/en-us/galleries/public/templates/efb564143834442283c41e19cdc2a6bb/complete-dynamics-365-for-finance-and-operations-workflow-work-items-pu26/)
- [Dynamics 365 for Finance and Operations ワークフロー作業項目 (PU29) を完了](https://flow.microsoft.com/en-us/galleries/public/templates/ebeccaa6f7aa40899828d8d01151d268/complete-dynamics-365-for-finance-and-operations-workflow-work-items-pu29/)

プラットフォーム更新プログラム 29 バージョンは、ビジネス イベント ペイロードから完了オプションを取得します。 これらのオプションはプラットフォーム更新プログラム 29 で追加され、承認アクションによりユーザーに表示されます。 

## <a name="troubleshooting-workflow-business-events"></a>ワークフロー ビジネスイベントのトラブルシューティング

ワークフロー ビジネスイベントにてエラーを発生させずに完了するには、正確な作業が必要になる多くの重要な要素があります:

- **ワークフロー** - ワークフローが正常に動作することと、各項目が正しく作成されていることを確認します。 ワークフローがアプリケーション内で動作せず、状態の変化が発生した場合、イベントは発生しません。 必要に応じてワークフローの設定を調整します。 この調整を行うには、 **ワークフローの履歴** フォームの詳細を確認してください。

- **フロー** - **有効なイベント** タブの **システム管理 > 設定 > ビジネスイベント > ビジネス イベント カタログ** でフローのサブスクリプションが利用可能となっていることを確認します。フローのサブスクリプションが見当たらない場合、フローを確認し、必要に応じて再作成してください。

- **ビジネス イベント** - 別のビジネス イベントをトリガーするフローを作成することで、他のビジネス イベントが発生することを確認します。 たとえば、フリー テキストのインボイス転記済イベントは、単一行のフリー テキスト インボイスを作成して転記することでトリガーできます。 詳細については [ビジネス イベントのトラブルシューティング](troubleshooting.md) を参照してください。