---
title: Project Service Automation の統合パラメーター
description: このトピックでは、Microsoft Dynamics 365 for Project Service Automation を Microsoft Dynamics 365 Finance に統合するときに既定のデータを入力しコンフィギュレーションする方法について説明します。
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: f7cef5384812e0dcb7d5e084ddd7668a7687a259
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174933"
---
# <a name="project-service-automation-integration-parameters"></a>Project Service Automation 統合パラメーター

[!include[banner](../includes/banner.md)]

**Project Service Automation 統合パラメーター** ページで、Dynamics 365 Project Service Automation を Dynamics 365 Finance に統合するときに既定のデータを入力する方法をコンフィギュレーションできます。 プロジェクトが Project Service Automation から Finance に正常に同期されるには、次のフィールドが設定されるている必要があります。

> [!NOTE]
> - プロジェクト タスクの統合、経費トランザクションのカテゴリ、時間見積、経費見積、および機能ロックは、バージョン 8.0 で利用できます。
> - 実績の統合は、バージョン 8.0.1 以降で使用可能です。


| タブ                    | フィールド                | 説明 |
|------------------------|----------------------|-------------|
| 一般                | 既定のプロジェクト タイプ | 既定のプロジェクト タイプを選択します。 Project Service Automation からプロジェクトが同期されるときに、統合テンプレートの既定値を指定しなかった場合、この値が使用されます。 同期中に、新しいプロジェクトの**プロジェクト タイプ**フィールドがこの値に設定されます。 ただし、プロジェクト契約明細行が Project Service Automation から同期されるときに、値が更新される場合があります。 |
|                        | 時間カテゴリ        | 既定の時間カテゴリを選択します。 時間見積が Project Service Automation から同期されるときに、この値が使用されます。 時間見積および時間の実績が Project Service Automation から同期されている場合、Finance の新しいプロジェクト時間予測の**カテゴリ**フィールドはこの値に設定されます。 |
|                        | 手数料カテゴリ         | 既定の手数料カテゴリを選択します。 手数料の実績が Project Service Automation から同期されるときに、この値が使用されます。 同期時に、手数料の実績が Project Service Automation から同期されている場合、Finance の新しい手数料トランザクションの**カテゴリ**フィールドはこの値に設定されます。 |
| プロジェクト グループの既定値 | プロジェクト タイプ         | 既定のプロジェクト グループを設定するプロジェクト タイプを選択できる行を追加するには、**新規**をクリックします。 特定のプロジェクト タイプは、コンフィギュレーションで 1 回のみ選択できます。 |
|                        | プロジェクト グループ        | 選択されたプロジェクト タイプの既定のプロジェクト グループを選択します。 新しいプロジェクトが Project Service Automation から同期されるときに、統合テンプレートの既定値を指定しなかった場合、プロジェクト タイプの**プロジェクト グループ**フィールドは既定値に設定されます。 |
| 請求タイプの既定値  | 請求タイプ         | **新規**をクリックして行を追加し、既定の明細行プロパティを設定する請求タイプを選択できます。 特定の請求タイプは、コンフィギュレーションで 1 回のみ選択できます。 |
|                        | 明細行プロパティ        | 指定された請求タイプの既定の明細行プロパティを選択します。 新しい時間見積、新しい経費見積、または新しい実績が Project Service Automation から同期されるときに、**明細行プロパティ**フィールドは請求タイプの既定値に設定されます。 |
| 機能ロック  | 適用できません       | Project Service Automation から作成されたプロジェクトおよび契約の Finance で無効にする機能を選択します。 たとえば、契約およびプロジェクトを編集し、作業分解構造を作成し、Finance でタイムシートを入力する機能を無効にできます。 パラメーター設定によって利用できない場合でも、会計関連のフィールドは継続して有効になります。 既定では、すべての機能が有効になります。 |
