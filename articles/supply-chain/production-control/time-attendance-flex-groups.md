---
title: "フレックス グループ"
description: "このトピックでは、時刻と出勤でのフレックス グループの使用方法について説明します。"
author: johanhoffmann
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgFlexGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: e21a2de2f46c619f27eddad4d7cced260a90bbb8
ms.openlocfilehash: 20f317ff57fac25b5b5b0d702fe64845eb849e87
ms.contentlocale: ja-jp
ms.lasthandoff: 04/09/2018

---

# <a name="flex-groups"></a>フレックス グループ

[!include[banner](../includes/banner.md)]

フレックス勤務時間では、ワークロードが低い期間中に作業者に特別休暇を提供することにより、会社の残業時間の支払を最小限に抑えることができます。 この機能は、たとえばワークロードで季節的な変更済みの区分にのみ有効です。

フレックス グループを使用して、次のルールおよび原則によって作業者のフレックス時間を設定できます。

- フレックス規制のルール
- 作業者のフレックス時間残数を計算するための原則

## <a name="set-up-flexible-working-hours-in-flex-groups"></a>フレックス グループでフレックス勤務時間の設定

- **時刻と出勤** \> **設定** \> **グループ** \> **フレックス グループ** を選択し、フレックス時間のフレックス グループを設定します。

## <a name="associate-workers-with-flex-groups"></a>フレックス グループと作業者を関連付ける

- **時刻と出勤** \> **設定** \> **時間登録作業者** を選択します。

## <a name="rules-for-flex-regulations"></a>フレックス規制のルール

フレックス規制のルールを使用して、フレックス限度または作業者のフレックス アカウントで許可されている最小時間数と最大時間数を定義します。 フレックス限度は、フレックス グループで設定します。 フレックス限度を超えた場合は、作業者のフレックス時間残数と支払を調整できます。

作業者の最小フレックスを超えた場合 (つまり、時間数がフレックス アカウントで指定された最小値を下回った場合) は、これらのメソッドを使用してフレックス規制をすることにより、作業者のフレックス時間残数を調整することができます。

- 作業者のフレックス アカウントでは、指定された最小許容値を調整することはできますが、フレックス アカウントが最小許容値を下回る時間数の作業者の支払を差し引くことはできません。
- 作業者の支払では、フレックス アカウントが最小許容値を下回る時間数に対して差し引くことができます。 この控除は、正または負の支払単位のある特定の支払タイプの支払項目を生成することによって行われます。

作業者の許可されているフレックス最大値を超えた場合、これらのメソッドを使用してフレックス規制することにより、作業者のフレックス時間残数を調整できます。

- 作業者のフレックス アカウントでは、指定された最大許容値を調整することはできますが、フレックス アカウントが最大許容値を上回る時間数の作業者の支払を補償することはできません。
- 作業者が最大許容値を超えて勤務した時間数は、支払に変換することができます。 この変換は、特定の支払タイプの支払項目を生成することによって行われます。

以下の時点で、フレックス時間残数を調整することができます。

- **支払を転送** ジョブを使用して、給与データに基づく支払ファイルをエクスポートするとき。 給与データは、**承認** ページから作業者登録を転送するときに生成されます。
- **フレックス時間残数の調整** ジョブが処理されたとき。

> [!NOTE]
> **承認** ページでの日次承認と作業者登録の転送の際には、フレックス規制は発生しません。

## <a name="principle-for-calculating-a-workers-flex-balance"></a>作業者のフレックス時間残数を計算するための原則

調整された作業者のフレックス時間残数の時間を計算するための原則は、フレックス グループで設定します。 **時間と出勤** \> **設定** \> **グループ** \> **フレックス グループ** を選択します。 

次の 2 つの原則を使用できます。

- **時間** – 作業者のフレックス時間は、その日の作業者の登録済時間からのみ計算されます。 作業者の毎日の登録が計算される場合、フレックス+ 数およびその日のフレックス- 時間は、作業者の時間プロファイルで定義されているフレックス+ とフレックス- ゾーンから計算されます。
- **支払タイプ** – 作業者のフレックス時間は、作業者の支払協定で定義されているフレックス+ およびフレックス- の所得の支払タイプに基づいて計算されます。 支払協定は、時間登録作業者に関連付けられています。 例えば、1 つまたは複数のフレックスゾーンの特定の係数で作業者のフレックス アカウントを増やしたいときに、フレックス アカウントを管理する支払タイプを使用する場合があります。

### <a name="scenario-1-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-minimum-is-exceeded"></a>シナリオ 1: 最小許容フレックス時間を超えているため、作業者の支払いやフレックス アカウントを調整

フレックス勤務をする作業者は、マイナスのフレックス アカウントを持っています。

- **フレックスアカウント:** -4

作業者は、次の構成を持つフレックス グループに関連付けられています。

- **最小フレックス時間:** -0.5
- **最小支払タイプ:** 1302
- **支払タイプ因数:** -1.00

作業者のフレックス アカウントと最小許容フレックス時間との差が示すように、作業者は最小許容フレックス時間を 3.5 時間超過しています。

給与管理者が **支払へ振替** または **フレックス調整** ジョブを実行して作業者の支払データを転送すると、次の調整が行われます。

- 作業者のフレックス アカウントは、3.5 時間で調整されます。 したがって -4.0 時間のフレックス時間残数は、作業者の -0.5 時間の最小許容フレックス時間に調整されます。
- 支払タイプ 1302 の支払項目が作成されます。 この支払項目には、作業者の支払から差し引かれると -3.5 時間の支払単位があります。 この場合、支払単位は、3.5 時間のプラス調整の値が、フレックス グループで定義されている -1.0 のマイナスの支払タイプ因数によって乗算されるため、マイナスの数値になります。 この支払項目は、**支払へ振替** ジョブよって生成される支払ファイルの一部とされます。

### <a name="scenario-2-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-maximum-is-exceeded"></a>シナリオ 2: 最大許容フレックス時間を超えているため、作業者の支払いやフレックス アカウントを調整

フレックス勤務をする作業者は、プラスのフレックス アカウントを持っています。

- **フレックスアカウント:** 6

作業者は、次の構成を持つフレックス グループに関連付けられています。

- **最大フレックス時間:** 2.0
- **最小支払タイプ:** 1302
- **支払タイプ因数:** -1.0

作業者のフレックス アカウントと最大許容フレックス時間との差が示すように、作業者は最大許容フレックス時間を 4.0 時間超過しています。

給与管理者が **支払へ振替** または **フレックス調整** ジョブを実行して作業者の支払データを転送すると、次の調整が行われます。

- 作業者のフレックス アカウントは、-4.0 時間で調整されます。 したがって 6.0 時間のフレックス時間残数は、作業者の 2.0 時間の最大許容フレックス時間に調整されます。
- 支払タイプ 1302 の支払項目が作成されます。 この支払項目には、作業者の支払に追加される 4.0 時間の支払単位があります。 この場合、4.0 時間のマイナス調整が、フレックス グループで定義されている -1.0 のマイナス支払タイプ因数によって乗算されるため、支払単位は正の数になります。 この支払項目は、**支払へ振替** ジョブよって生成される支払ファイルの一部とされます。

### <a name="scenario-3-managing-a-workers-flex-balance-based-on-pay-types"></a>シナリオ 3: 支払タイプに基づく作業者のフレックス時間残数の管理

先に説明したように、フレックス アカウントはフレックス+ に登録されている時間と作業者の時間プロファイルが定義されているフレックス- ゾーン、または作業者の支払協定で定義されている支払タイプに基づいて管理できます。 支払タイプを使用すると、作業者のフレックス アカウントは、**承認** ページから作業者登録を転送する際に生成される支払項目によって調整されます。 例えば、1 つまたは複数のフレックスゾーンの特定の係数で作業者のフレックス アカウントを増やしたいときに、フレックス アカウントを管理する支払タイプを使用する場合があります。

このシナリオでは、作業日を表す次のフレックス プロファイルを使用します。

| プロファイル タイプ  | 開始    | 終了      |
|---------------|----------|----------|
| フレックス+         | 午前 12 時 00 分 | 午前 08 時 00 分 |
| 出勤      | 午前 08 時 00 分 | 午前 08 時 00 分 |
| フレックス-         | 午前 08 時 00 分 | 午前 09 時 00 分 |
| 標準勤務時間 | 午前 09 時 00 分 | 午前 11 時 30 分 |
| 有給休暇    | 午前 11 時 30 分 | 午後 12 時 00 分 |
| フレックス-         | 午後 12 時 00 分 | 午後 04 時 00 分 |
| 退勤     | 午後 04 時 00 分 | 午後 04 時 00 分 |
| フレックス+         | 午後 04 時 00 分 | 午前 12 時 00 分 |

この場合、支払タイプに基づく作業者のフレックス時間残数を管理できるようにします。 したがって、作業者のフレックスグループで **支払タイプに基づく** オプションを **はい** に設定する必要があります。

フレックス勤務を説明するため、新しい支払タイプも定義する必要があります。 このシナリオでは、支払タイプが **FlexCnt** という名前にします。

| 支払タイプ | 説明  |
|----------|--------------|
| FlexCnt  | フレックス カウンター |

次に、支払タイプを設定し支払プロファイルに新しいタイプの明細行を追加するには、次の手順に従います。

1. **時刻と出勤** \> **設定** \> **グループ** \> **フレックス グループ** を選択し、**新規** を選択します。
2. **フレックス+** フィールドと **フレックス-** フィールドの両方で、新しい支払タイプ **FlexCnt** を指定します。
3. **時刻と出勤** \> **設定** \> **支払協定** を選択し、**契約明細行** を選択します。
4. **月曜日** に対して、**フレックス+** プロファイル タイプは、次の 3 つの明細行を追加します。

    | 支払タイプ | 説明  | 開始時刻 | 終了時刻  | 最小 | 最大 | 係数 |
    |----------|--------------|-----------|----------|---------|---------|--------|
    | FlexCnt  | フレックス カウンター | 午前 12 時 00 分  | 午後 06 時 00 分 | 00.00   | 00.00   | 1.00   |
    | FlexCnt  | フレックス カウンター | 午後 06 時 00 分  | 午前 12 時 00 分 | 00.00   | 02.00   | 1.50   |
    | FlexCnt  | フレックス カウンター | 午後 06 時 00 分  | 午前 12 時 00 分 | 02.00   | 06.00   | 2.00   |

    > [!NOTE]
    > 個々の明細行は、異なる時間間隔に対して使用され異なる係数を有します。 作業者が時間間隔で働くフレックス時間は、その明細行の係数によって乗算されます。 たとえば、午後 6 時から午後 8 時までの作業時間には 1.50 が掛けられます。 係数は、[**支払協定行**] ぺージの [**一般**] タブの [**係数**] フィールドで指定します。

作業者は、その日の次の登録を入力します。

| 仕訳帳の登録タイプ | 開始    | 終了      |
|---------------------------|----------|----------|
| 出勤                  | 午前 7 時 00 分 | 午前 7 時 00 分 |
| 生産ジョブ            | 午前 7 時 00 分 | 午後 09 時 00 分 |
| 退勤                 | 午後 09 時 00 分 | 午後 09 時 00 分 |

支払う必要のある金額は、[**承認**] ページで、作業者の登録に基づいて計算されます。 登録が計算された後、[**時間**] タブで結果を表示できます。このシナリオでは、次のフィールドに関心があります。

| フレックス + | フレックス - | 時刻  | 有給時間内勤務 |
|--------|--------|-------|----------|
| 6.00   | 0.00   | 13.50 | 08.00    |

フレックス+ 時間は 6 時間、および時間プロファイル内のフレックス ゾーンに基づいて計算します。 この金額は、午前 7 時から午前 8 時までの 1 時間のフレックス+ 時間と、午後 4 時から午後 9 時までの 5 時間のフレックス+ 時間で構成されます。

登録を転送するときに、フレックス+ 時間数が 6.0 時間から 8.0 時間に変更されたことが表示されます。

| フレックス + | フレックス - | 時刻  | 有給時間内勤務 |
|--------|--------|-------|----------|
| 8.00   | 0.00   | 13.50 | 08.00    |

この変更は、フレックス時間が時間の代わりに支払タイプに基づいて計算されているので、転送後に発生します。 次の表に、8 時間の計算方法を示します。

| 移動元     | 終了       | 時刻 | 係数    | フレックス アカウント |
|----------|----------|------|-----------|--------------|
| 午前 7 時 00 分 | 午前 08 時 00 分 | 1    | 1         | 1            |
| 午後 04 時 00 分 | 午後 06 時 00 分 | 2    | 1         | 2            |
| 午後 06 時 00 分 | 午後 08 時 00 分 | 2    | 1.5       | 3            |
| 午後 08 時 00 分 | 午後 09 時 00 分 | 1    | 2         | 2            |
|          |          |      | **合計** | **8**        |
