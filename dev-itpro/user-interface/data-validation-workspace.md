---
title: "データ検証ワークスペース"
description: "データ検証チェックリスト ワークスペースを使用して、会社、エリア、人員に対してデータ検証プロセスの追跡ができます。 チェックリストは新規実装中、更新後、または移行後に使用できます。"
author: bking
manager: AnnBe
ms.date: 05/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: 
ms.assetid: 
ms.search.region: Global
ms.author: bking
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: e105c4b171979a03c20718c1fa9d558c921cd704
ms.contentlocale: ja-jp
ms.lasthandoff: 06/20/2017


---

# <a name="data-validation-workspace"></a>データ検証ワークスペース

[!include[banner](../includes/banner.md)]


このトピックでは、**データ検証チェックリスト ワークスペース** と関連するコンフィギュレーションの概要を示します。

## <a name="data-validation-checklist-workspace"></a>データ検証チェックリスト ワークスペース

**データ検証チェックリスト** ワークスペースを使用して、会社、エリア、人員に対してデータ検証プロセスの追跡ができます。 チェックリストは新規実装中、更新後、または移行後に使用できます。 **データ検証チェックリスト** ワークスペースのビューに応じて、データ検証プロジェクトに対するすべてのタスクおよび状態、または自分に割り当てられたタスクのみを表示することができます。

最初にワークスペースの先頭でデータ検証プロジェクトを選択する必要があります。 ワークスペースに表示されるすべてのデータは選択したデータ検証プロジェクトにより、フィルター処理されて表示されます。

### <a name="summary-tiles"></a>概要タイル

[**概要**] タイルはプロセスの概要を示し、インジケーターがデータ検証プロセスを順調に進めるのに役立ちます。 そのプロセスについて、すべての残余タスク、完了タスク、進行中のタスク、および開始されていないタスクを表示できます。 この情報は、選択されたデータ検証プロジェクトに含まれるすべての会社で使用されます。

### <a name="tasks-and-status-section"></a>タスクと状態のセクション

[**タスクと状態**] セクションで、全体のデータ検証プロジェクトの状態が、法人ごと、領域ごと、またタスク リストごとの状態といったさまざまな方法で表示されます。 特定の会社の状態を表示するフィルターを選択できます。 各ステータスのタブは、完成した割合および残っているタスク数の両方で内訳を表示します。

最後のタブは、詳細なタスクのリストのためにあります。 この一覧は、すべてのタスク リストを表示します。
複数の方法でタスク リストをフィルター処理できます。 [**タスクの編集**] をクリックしてタスクの状態を変更するかタスクを割り当てます。 [**添付ファイル**] をクリックしてタスクの添付ファイルを表示します。

タスク名はユーザーが作業を完了するために閲覧する必要がある Microsoft Dynamics 365 for Finance and Operations, Enterprise edition ページへのハイパーリンクです。 [**データ検証プロジェクトのコンフィギュレーション**] フォームからタスクを編集または作成する際に [**メニュー項目名**] フィールド を使用してこのハイパーリンクを設定できます。

[**添付ファイル**] アクションを使用して、ファイル、注記、画像、URL を関連付けることができます。 たとえば、タスクに対して印刷されたレポート ファイルを添付することができます。 添付ファイルが存在する場合には、[**添付ファイル**] 列にアイコンが表示されます。

[**完了処理実施者**] オプションには、作業が完了した後にタスクを完了した作業者の名前が自動的に入力されます。 タスクが完了としてマークされると、[**完了日**] フィールドが、現在の日時に自動的に更新されます。

### <a name="configure-data-validation-project-page"></a>データ検証プロジェクト ページのコンフィギュレーション

**データ検証チェックリスト** ワークスペースを使用する前に [**データ検証プロジェクトのコンフィギュレーション**] ページを使用してプロセスをコンフィギュレーションする必要があります。 ([**ワークスペース**] \> [**データ検証チェックリスト**] \> [**データ検証プロジェクトのコンフィギュレーション**] をクリックします。)

### <a name="task-areas"></a>タスク領域

タスク領域を使用して、データ検証タスクを組織内の所有権の論理領域にグループ化します。 たとえば、買掛金勘定、売掛金勘定、または総勘定元帳がタスク領域として使用される場合があります。

[**メニュー項目名**] はタスク作業工数に関連付けられており、ワークスペースのタスク リンクから関連するページに直接移動するために使用できます。 たとえば、買掛金勘定の **買掛金勘定エイジング** レポートを実行するデータ検証タスクは、[**買掛金勘定エイジング レポート**] ページにリンクできます。
