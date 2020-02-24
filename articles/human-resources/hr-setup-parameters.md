---
title: 人事管理パラメーターのコンフィギュレーション
description: 他のパラメーター設定は会社固有ですが、人事管理のパラメーター設定は会社間で共有されます。 この記事は、会社固有の HR パラメーターを設定する方法を説明します。
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HRMParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 25ef0b515e455be7493ac816f9c5e0db08dfd483
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009703"
---
# <a name="configure-human-resources-parameters"></a>人事管理パラメーターのコンフィギュレーション

他のパラメーター設定は会社固有ですが、人事管理 (HR) のパラメーター設定は会社間で共有されます。 この記事は、会社固有の HR パラメーターを設定する方法を説明します。

2 つのページが人事管理 (HR) のパラメータの設定に使用されます。 会社間で共有されるパラメータに、**人事管理の共有パラメーター**ページを使用します。 会社固有のパラメータ (つまり、設定を単一の会社に適用する場合) に、**人事管理パラメータ**ページを使用します。 **人事管理パラメーター**ページで、設定は 6 つのタブに分割されます:

-   一般
-   採用 - これは Dynamics 365 Human Resources には含まれていません
-   報酬
-   番号順序
-   育児介護休業法 (FMLA)
-   従業員セルフサービス

各タブには単一の会社に関する情報が含まれます。 **概要**タブの設定は、休暇、傷害と疾病、新規採用に関する情報の外観を定義します。 このタブの設定は、作業中と表示される既定のエントリも定義します。 特に、このタブでは、未処理の休暇トランザクションに適用する色を選択し、レポートに使用するスタイル シートを指定したり、トレーニング コースと休暇登録の間の統合を有効にし、この統合の管理に使用する休暇コードを選択することができます。 また、けがと病気のケース インシデントの保持期間を指定することもでき、新しい作業者の雇用時に表示される既定の ID 番号を指定できます。 

**採用**タブの設定は、申請者に自動的に送信される通知のドキュメント タイプ、および未承諾の申請に対しての採用プロジェクト (特定の採用プロジェクトに対してでない申請) を定義します。 採用プロジェクトのエイジングとして定義されている期間によって、**採用管理**ワークスペースの、**エイジング プロジェクト**タイルに含まれている採用プロジェクトが決まります。 **採用**ワークスペースの、**申請の期限が近づいています**タイルで申込期限が近づいている採用プロジェクトを表示するために、申請の期限の警告に定義されている期間が使用されます。 

**報酬** タブの設定は、ユーザーが固定または変動報酬プランの情報を保存するかどうかの確認を定義します。 **保存の検証を有効にします** チェック ボックスをオンにすると、そのユーザーが報酬に関連付けられたページを閉じるといつでも、レコードを保存するかどうか確認するメッセージが表示されます。 報酬管理の一部のページでは、ユーザーが情報を削除することはできません。 したがって、ユーザーに情報を保存するかどうかを確認するよう促すことにより、後で削除できない保存される情報の量を限定できる場合があります。 **保存の検証を有効にします**チェック ボックスがオフの場合、場合によってはユーザーの準備ができる前に、レコードは常にすぐに保存されます。 パフォーマンス管理を使用している場合は、**報酬**タブでも、パフォーマンスを評価するときに報酬プランに割り当てられているモデルの代わりに使用する評価モデルを選択できます。 

### <a name="previously-released-functionality"></a>以前にリリースされた機能

**番号順序**タブの設定により、申請、休暇登録、報酬プロセス結果、ケース番号、コース、およびコースの議題などの人事管理の品目に ID を自動的に割り当てるのに使用される順序が決まります。 番号順序およびコードを管理するには、**番号順序** リスト ページを使用します。(**組織管理** &gt; **番号順序** &gt; **番号順序** の順にクリックします)。

> [!NOTE]
> 作業時間数は 1,250 を超えることはできず、雇用期間は 12 か月を超えることはできません。 これらの最大値は米国の連邦法に従います。 最後に、**従業員セルフサービス**タブの設定で、マネージャが自分たちの従業員に代わって入力できる情報を決定します。