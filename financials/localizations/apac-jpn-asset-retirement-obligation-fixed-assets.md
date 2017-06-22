---
title: "固定資産の資産償却責務の設定"
description: "日本では、資産除去債務 (ARO) は法的な除去責務のある固定資産に対して認識されます。 この記事は、ARO の負債がどのように認識、償却、および未払となるか、および固定資産と ARO の負債が除去される方法について説明します。"
author: RichardLuan
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetRetirementObligation_JP, AssetRetirementObligationDocument_JP, AssetRetirementObligationExplorer_JP, AssetRetirementObligationLine_JP, AssetTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 10174
ms.assetid: f14ac15f-b99b-4853-9648-de31f3cb36cf
ms.search.region: Japan
ms.author: RichardLuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: cba53384e80a7c7459d3df73af6b7cd752f4094e
ms.contentlocale: ja-jp
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-asset-retirement-obligation"></a>資産償却責務の設定

[!include[banner](../includes/banner.md)]


日本では、資産除去債務 (ARO) は法的な除去責務のある固定資産に対して認識されます。 この記事は、ARO の負債がどのように認識、償却、および未払となるか、および固定資産と ARO の負債が除去される方法について説明します。

資産償却責務 (ARO) は、資産償却の原価を耐用年数で配分するために使用されます。 ARO は、固定資産の取得または構築する際に最初に負債として認識されます。 ARO 負債は、耐用年数の初めに見積もられた資産に対する償却原価の現在の値を表します。 ARO 負債を固定資産の取得原価に追加すると、ARO の負債原価は固定資産の耐用年数で償却されます。 ARO 負債の利息費用は、最終的な ARO 負債が当初の見積除去原価に到達するように、特定の割引率での未払費用になります。 固定資産が除去されると、ARO 負債の勘定に支払額が転記されます。 元の見積からの違いがない限り、これ以外の経費は転記されません。 次の表に、ライフ サイクルの実例を示します。

| 品目        | コンテンツ                                                                                                                                                                                   |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 前提 | 取得原価: **10,000** (残存価額 0) 耐用期間: **5** 減価償却方法: **定額** 見積除去原価: **1,000** 割引率: **3%**                  |
| ステップ１      | 借方: 設備 **10,863** 貸方: 他の支払 **10,000** 貸方: ARO の負債 **863**                                                                                                |
| ステップ２\*    | 借方: 減価償却費用 **2,173** 貸方: 減価償却累計額 (FA) **2,000** 貸方: 減価償却累計額 (ARO) **173**                                                     |
| ステップ 3\*    | 借方: 支払利息 **27** 貸方: ARO の負債 **27**                                                                                                                              |
| ステップ 4      | 借方: 減価償却累計額 (FA) **10,000** 借方: 減価償却累計額 (ARO) **863** 貸方: 設備 **10,863** 借方: ARO 負債 **1,000** 貸方: 他の支払 **1,000** |

> [!NOTE]
>\** 手順 2 と 3 が、固定資産の耐用年数全体に複数回繰り返されます。

![ARO トランザクションの T 字勘定での表示](./media/aro-t-account.png) 

## <a name="setup-information"></a>設定情報
ARO を使用するには、次の設定手順を完了する必要があります。

-   既定の帳簿、理由コード、および番号順序などの、基本的な固定資産パラメーターを**固定資産パラメーター** ページで設定します
-   固定資産グループを**固定資産グループ**ページで定義します
-   減価償却の会計カレンダーを設定します
-   現在の市場の割引率を使用する割引率スケジュールを設定して、ARO 金額を計算します
-   資産に使用する ARO タイプと、ARO 金額の変更を転記する頻度を指定します
-   ARO の見積償却原価計画を設定し、資産の耐用年数の会計期間ごとに ARO 金額をシミュレーションします
-   **資本化資産償却責務**と**資産償却債務 - 増加****経費**のドキュメント タイプで使用する転記プロファイルを設定します
-   **処分する ARO** のトランザクション タイプである固定資産を転記する際に、トランザクション金額の取得元の勘定を設定します

## <a name="technical-information-for-system-administrators"></a>システム管理者向け技術情報
このタスクを完了するために使用するページに対するアクセス権限がない場合は、システム管理者に連絡し、次の表に示される情報を提供します。

| カテゴリ                  | 前提条件                                                                                                                                                         |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| コンフィギュレーション キー        | アプリケーション オブジェクト ツリー (AOT) の**データ ディクショナリ** &gt; **コンフィギュレーション キー** ノードで、固定**資産**のコンフィギュレーション キーが使用できることを確認します。 |
| セキュリティ ロールおよび職務 | このタスクを実行するには、**固定資産の管理**のセキュリティ ロールのメンバーである必要があります。|





