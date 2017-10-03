---
title: "Operations リソース"
description: "運営リソースはプロジェクトまたは生産プロセス活動を実行します。 これらはさまざまなタイプ、さまざまな能力が指定できます。"
author: sorenva
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 30f5ef06fe20894f373e342d09a1e642ab1f0caf
ms.contentlocale: ja-jp
ms.lasthandoff: 05/25/2017

---

# <a name="operations-resources"></a>Operations リソース

[!include[banner](../includes/banner.md)]


運営リソースはプロジェクトまたは生産プロセス活動を実行します。 これらはさまざまなタイプ、さまざまな能力が指定できます。 

<a name="operations-resources"></a>Operations リソース
--------------------

運営リソースは、プロジェクトまたは生産プロセス活動を実行する機械、ツール、作業者、設備、物理的な領域、仕入先です。 これらはさまざまなタイプ、さまざまな能力が指定できます。

-   **仕入先** – プロジェクト活動または生産工程を実行する外部リソース。 たとえば、協力会社です。 仕入先リソースを仕入先勘定にリンクすると、部品表 (BOM) の明細行または生産の明細行に基づいて、協力会社の購買を生成できます。
-   **作業員** – 単独でまたは工具や機械のオペレーターとして活動する、プロジェクトまたは生産作業者。 人事管理機能を使用すると、作業者を人事管理にリンクすることができます。 スケジューリング エンジンは、対応する作業者に定義されている能力に基づいてリソースを割り当てることができます。
-   **機械** – 生産に必要な、機械や生産施設。
-   **工具** – 通常、別のリソースとともに使用してプロジェクトや生産の活動を実行する、 器具や装置。
-   **場所** – 活動を実行するために必要な特定のサイズの物理的な場所。 たとえば、組み立て場所です。
-   **設備** – 活動を実行するために必要な、建物や固定の構造。

## <a name="calendars"></a>カレンダー
カレンダーは、運営リソースに割り当てることができ、そのリソースの能力 (時間) ついて説明します。 運営リソースの作業時間は、運営リソースが所属するリソース グループに割り当てられたカレンダーによって決まります。 割り当てられたカレンダーについて、有効日と有効期限を設定できます。 運営リソースに、複数のカレンダーを割り当てることができます。 ただし、割り当てたカレンダーの日付は重複できず、運営リソースは一度に 1 つのカレンダーにのみ割り当てることができます。 **注記:** リソース グループに対して有効な作業カレンダーがない場合 (たとえば最後に割り当てられたカレンダーまたは割り当てられている唯一のカレンダーが期限切れの場合)、生産スケジューリングおよび工程スケジューリングのリソース グループに割り当てられている工順リソースにはアクセスできません。 リソース グループにカレンダーを割り当てて、リソース グループの作業時間と、リソース グループに割り当てられているすべての運営リソースの作業時間を指定することができます。 リソース グループの能力は、リソース グループに割り当てられた各運営リソースの能力の合計として計算されます。 リソース グループに割り当てられたカレンダーは、時間経過に伴い変更可能です。

## <a name="resource-capabilities"></a>リソースの能力
能力とは、運営リソースが特定の活動を実行する能力です。 運営リソースに、複数のカレンダーを割り当てることができます。 ここでスケジューリング エンジンは、運営リソースの利用可能な能力と各活動のリソース要件が一致するようにリソースを割り当てます。 機能は、運営リソースのすべてのタイプに割り当てることができます (**ツール**、**仕入先**、**機械**、**人的資源**、**場所**、**設備**)。 運営リソースに一時的に能力を割り当てるには、能力割り当ての開始日と有効期限を定義します。 詳細については、「[リソースの能力](resource-capabilities.md)」を参照してください。

## <a name="resource-groups"></a>リソース グループ
リソース グループは、工程のスケジューリング方法を使用するときにリソースをスケジュールする粒度を表す一連の運営リソースです。 したがって、リソース グループは、通常、作業現場フロアで黄色のラインで示される作業セルの物理的な構成に対応します。 リソース グループとは、グループに割り当てられる運営リソースのサイト、生産単位、および倉庫の環境です。 運営リソースをリソース グループに割り当てている場合、そのリソース グループが置かれているサイトでのみリソースをスケジューリングできます。 作成する運営リソースを、リソース グループに割り当てる必要はありません。 ただし、運営リソースは、作業実行のスケジュールの前にリソース グループに割り当てる必要があります。 運営リソースは、限られた期間、リソース グループに割り当てることができます。 また、サイト全体のリソースを共有できるように、複数のリソース グループに同じ運営リソースを割り当てることができます。 ただし、有効日と有効期限を重複させることはできません。 つまり、運営リソースを 2 つの異なるリソース グループに同時に割り当てることはできません。 リソース グループの割り当ての変更は、新しいリソース割り当てに対してのみ有効です。 スケジュール済のジョブ、工程、プロジェクトの時間予測についての確保済能力には影響しません。 **注記:** **仕入先**タイプの運営リソースをリソース グループに割り当てると、そのリソース グループに割り当てられているすべての運営リソースを**仕入先**タイプにし、同じ仕入先勘定にリンクする必要があります。

## <a name="production-units"></a>生産単位
生産単位はリソース グループのコレクションの管理単位です。 生産単位には複数のリソース グループを含めることができますが、リソース グループは 1 つの生産単位のみに割り当てることができます。 生産単位は、生産リソースの物理的な配置を反映し、トランザクションやトランザクションの処理方法には影響しません。 生産単位をサイトに関連付ける必要があります。 生産単位に対してピッキング倉庫と保管倉庫を割り当てることもできます。 生産単位を使用して、生産関連データの統合のフィルタ処理を実行できます。 たとえば、作業現場のマネージャーは、特定の生産単位の未処理のワークロードと使用可能な能力の概要を表示できます。 リソース グループに割り当てられる生産単位を変更できます。 生産単位を削除することもできます。 ただし、生産単位に対するこれらの変更は、マスタ スケジューリングの実行後に作成された新しいオーダーに対してのみ有効です。 生産単位の変更を既存のオーダーに適用する場合は、手動でこの変更を適用する必要があります。

## <a name="resource-scheduling"></a>リソース スケジューリング
運営リソースは、プロジェクトや生産のスケジューリング時に、活動に割り当てられます。 次の 2 つのスケジューリング方法を使用できます: 工程スケジューリングおよびジョブ スケジューリング。 工程スケジューリングを使用すると、各工程や各プロジェクト活動は、工程で指定されたリソース要件に一致する運営リソースを含むリソース グループでスケジューリングされます。 特定の運営リソースが運営に必要な場合は、グループの特定の運営リソースのみの能力がスケジューリングで確保されます。 ジョブのスケジューリングは、工程のスケジューリングよりも詳細なフォームのスケジューリングです。 各工程を個々の作業 (ジョブ) に分割します。 次に、これらのジョブは、ジョブを実行する運営リソースに割り当てられます。 スケジューリングでは、生産工順またはプロジェクト活動で定義された工程時間に基づいて、リソース グループの能力が確保されます。 有限能力で作業している場合、スケジュールは、活動を完了するのに必要な運営リソースの利用可能性によって異なります。 工程のスケジューリングにおいて、リソース グループの能力は、そのグループに所属する運営リソースの利用可能な能力の合計です。 運営リソースに対して既に存在する確保済能力は使用できない能力と見なされます。 利用可能な能力が生産に不十分である場合、製造オーダーが遅延したり、さらに停止したりする可能性があります。 **リソース** ページで、確保済能力の選定方法を制御する複数のプロパティを定義できます。

-   **能力** – 1 時間あたりの運営リソースの能力を、能力単位で指定します。
-   **バッチ能力** – 運営リソースが実行ごとに処理できる区分の最大数を指定します。
-   **効率** – その運営リソースから期待される効率を指定します。 効率はリソースのスループットを調整します。これにより、運営リソースに対して予約される時間に影響を与えます。 運営リソースを使用する工程のリード タイムも、それに応じて調整されます。 次の式が計算に使用されます。スケジューリング時間 = 時間 × 100 ÷ このフォーミュラの効率、*時間*には実行時間と段取り時間の両方が含まれます。
-   **工程のスケジューリング率** – 工程のスケジューリングで使用する運営リソース能力の最大割合を指定します。 ジョブのスケジューリング時に流動性を考慮するには、この率を 100% 未満にする必要があります。
-   **有限能力** – 利用可能な実際の能力に基づいてスケジュールを立てる場合、かつ既存の確保済能力を考慮する場合は、このオプションを**はい**にします。 このオプションが**いいえ**に設定されている場合、運営リソースには無限の能力があるとされ、それによりリソースが予約超過になることがあります。
-   **作業タイプ指定** – 必要な作業時間のスケジューリングのプロパティーについて使用可能な実際の能力に基づいて運営リソースのスケジュールを設定する場合は、このオプションを**はい**に設定します。
-   **排他** – 現在の生産が完了するまで別のジョブや工程のために運営リソースを有効にしない場合は、このオプションに**はい**を設定します。 この場合、リソースの実行時間に間隔がある場合でも、運営リソースが使用できなくなります。
-   **ボトルネック リソース** – 運営リソースをボトルネック リソースとして定義します。 ボトルネック リソースは、**マスター プラン** ページで**有限能力**と**ボトルネック スケジューリング** オプションを選択している場合に、有限能力を使用してスケジュールされます。

生産中の工程など、複数の運営リソースを同時に実行するようにスケジュールするには、基本工程と二次工程を使用して、さまざまなリソースの要件を指定する必要があります。 また、異なる能力を持つ複数の運営リソースを確保できます。 基本工程に対してスケジュールされている運営リソースが、活動の期間を決定します。

## <a name="lean-work-cells"></a>リーン作業セル
リソース グループがリーン作業セルであることを指定できます。 そうすることで、リソース グループは、生産フローの一部になることができます。 リソース グループをリーン作業セルとして指定すると、リソース グループおよび割り当てられた運営リソースが、製造オーダーまたはプロジェクトの時間予測の工程に割り当てられることも防ぎます。 リーン作業セルとして機能する各リソース グループには、次の情報を指定する必要があります。

-   **カレンダー** – 標準的な作業日のプロパティーを持つ、作業セルの作業カレンダー。
-   **入庫倉庫と入庫場所** – 活動の材料のピッキングで使用される既定の場所。
-   **出力倉庫と出力場所** – 作業セルのすべての出荷が設定される既定の場所。
-   **ランタイムの原価カテゴリ** – 直接労務が原価計算で追跡される場合、このカテゴリが作業セルに対して定義される必要があります。

リソース グループがリーン作業セルとして使用される場合、作業セルの能力は、リソース グループで直接指定されます。 したがって、運営リソースをリソース グループに割り当てる必要はありません。 作業セルが協力会社によって管理されている場合にのみ、**仕入先**タイプの運営リソースを作業セルに割り当てる必要があります。 作業セルとしてマークされているリソース グループに運営リソースを割り当てる場合、作業セルの能力には影響しません。

## <a name="costing-resources"></a>原価計算リソース
工順工程またはプロジェクトの時間予測などの活動を定義すると、特定の運営リソースまたはリソース グループの要件を指定できます。 ただし、特定のタイプの運営リソースの条件、または特定の機能またはコンピテンシーがある運営リソースの条件も指定できます。 したがって、実際のリソース割り当ては、活動がスケジューリングされ、能力を引当するまで行われません。 したがって、工程では、特定の運営リソースに基づいた見積と BOM 計算を行う必要があることを指定できます。 この運営リソースは、原価計算のリソースと呼ばれます。 また、原価計算のリソースから原価カテゴリと工程時間を、活動に転送できます。 工程をスケジューリングすると、見積と BOM 計算には、実際にスケジュールするリソースを使用します。



