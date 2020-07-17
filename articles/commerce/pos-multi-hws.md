---
title: 専用の支払ターミナルおよびプリンターとキャッシュ ドロワーのプロンプト
description: このトピックでは、専用の支払ターミナルを持つ機能と、キャッシュ ドロワーやレシート プリンターを選択するようにユーザーに指示するプロンプトに関する情報を提供します。
author: rubendel
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: tonyafehr
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 4035817fb534477eb4146ff712a92d6e29ce2db2
ms.sourcegitcommit: 4db8c30c2f26af1896938dd3ece3756577374ecb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "3416609"
---
# <a name="dedicated-payment-terminals-and-prompts-for-a-printer-and-cash-drawer"></a>専用の支払ターミナルおよびプリンターとキャッシュ ドロワーのプロンプト

[!include [banner](includes/banner.md)]

このトピックでは、専用の支払ターミナルを持つ機能と、キャッシュ ドロワーやレシート プリンターを選択するようにユーザーに指示するプロンプトに関する情報を提供します。

## <a name="overview"></a>概要

今日の小売業者は、店舗内のチェックアウト体験を合理化するための方法を探しています。 電子支払によるペーパーレスのチェックアウトに向けた最近の傾向により、購入経験をスムーズにするだけでなく、すべての関連店舗で周辺機器を完全に補完する必要性も少なくなります。

Microsoft Dynamics 365 Commerce では、POS デバイスに専用の支払ターミナルが常に割り当てられていて、レシート プリンターやキャッシュ ドロワーがないシナリオを有効にすることでこのような傾向をサポートしています。 店員が領収書を印刷したり、現金支払を受けたりするときには、それらのデバイスを構成するハードウェア ステーションを選択するように求めるメッセージが表示されます。

## <a name="key-terms"></a>重要な用語

| 期間 | 説明 |
|---|---|
| 登録 | POS レジスターのインスタンスを構成するために使用されるエンティティ。 |
| デバイス | POS レジスタの物理的なインスタンスとそれに割り当てられた最新の POS アプリケーションの表現。 |
| 専用ハードウェア ステーション | Windows 用 Modern POS および Android アプリケーション用 Modern POS に組み込まれているプロセス間通信 (IPC) ハードウェア ステーション。 |
| ドロワーのキック (d/k) ポート | キャッシュ ドロワーをレシート プリンターに接続するための従来の方法。 |
| ネットワーク周辺機器 | ネットワーク対応型の支払ターミナル、レシート プリンター、キャッシュ ドロワーの組み込みサポート。 |

## <a name="supported-pos-clients-and-devices"></a>サポートされている POS クライアントとデバイス

このトピックで説明する機能は、Windows 用モダン POS と Android POS クライアント用のモダン POS でサポートされています。

この機能は、ネットワーク対応型の支払ターミナルとレシート プリンターをサポートしています。 キャッシュ ドロワーのサポートを提供するには、d/k ポートを介して、キャッシュ ドロワーをネットワーク対応型のレシート プリンターに接続します。

この機能に対するすぐに使える、[Adyen 向け Dynamics 365 Payment Connector](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3) によって提供されます。 ただし、その他の支払コネクタは、支払のためにコマース ソフトウェア開発キット (SDK) を介してサポートされる可能性があります。 サポートされているレシート プリンターには、Star Micronics と Epson のネットワーク対応型レシート プリンターがあります。

Star Micronics のレシート プリンターを設定するには、Star Micronics のプリンター ユーティリティを使用してデバイスを構成し、ネットワーク上で使用できるようにします。 このユーティリティは、デバイスの IP アドレスも提供します。

Epson のレシート プリンターを設定するには、Epson ePOS-Print ユーティリティを使用して、ネットワーク プロトコルを使用するデバイスを設定します。

ネットワーク周辺機器の設定方法の詳細については、[ネットワーク周辺機器サポートの概要](https://go.microsoft.com/fwlink/?linkid=2129965) を参照してください。

## <a name="set-up-a-dedicated-payment-terminal-and-a-prompt-for-a-printer-and-cash-drawer"></a>専用の支払ターミナル、およびプリンターとキャッシュ ドロワーのプロンプトの設定

### <a name="set-up-hardware-profiles"></a>ハードウェア プロファイルの設定

2 つのタイプのハードウェア プロファイルを持っている必要があります。 最初のものはレジスターに割り当てられます。 2 番目のものは、店舗レベルのハードウェア ステーションに割り当てられ、ネットワーク レシート プリンターとキャッシュ ドロワーを論理的にグループ化するために使用されます。

#### <a name="set-up-a-hardware-profile-for-the-register"></a>レジスターにハードウェア プロファイルを設定する

レジスターに割り当てられているハードウェア プロファイルを設定するには、次の手順に従います。

1. Dynamics 365 Commerce で、**ハードウェア プロファイル** を検索します。
2. **新規** を選択します。
3. ハードウェア プロファイル番号を割り当て、説明を入力します。 このハードウェア プロファイルは、レジスター自体に割り当てられます。 したがって、**フォールバック専用** などの説明で十分です。
4. さまざまなデバイス タイプのクイック タブで、次のデバイス タイプを設定します。

    | デバイス | 種類 | デバイス名 | 追加の詳細 |
    |---|---|---|---|
    | プリンター | 予備 | **Epson** または **Star** | デバイス名は大文字と小文字が区別されます。 **レシート プロファイル ID** は、ハードウェアステーションにチャンネルレベルで割り当てられている **ハードウェア プロファイル ID** で設定されているネットワーク プリンターにマップされているレシートプロファイル ID と同じである必要があります。 |
    | キャッシュ ドロワー | 予備 | **Epson** または **Star** | デバイス名は大文字と小文字が区別されます。 **共有シフトを使用** オプションを **はい** に設定します。 |
    | EFT サービス | Adyen | 該当なし | 最初から用意されている Adyen コネクタを設定する方法については、[Adyen 用の Dynamics 365 Payment Connector ](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3) を参照してください。 その他の支払コネクタは、支払のために [支払用コマース ソフトウェア開発キット (SDK)](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/end-to-end-payment-extension) を介してサポートされる可能性があります。 |
    | PIN パッド | ネットワーク | **MicrosoftAdyenDeviceV001** | なし。 |

5. Dynamics 365 Commerce で、**レジスター** を検索します。
6. レジスター番号を選択してレジスターを選択し、**編集** を選択します。
7. 作成したハードウェア プロファイルをレジスターに割り当てて、専用の支払ターミナルを使用するようにします。 このレジスターにマップされているデバイスには、Windows アプリケーション用のモダン POS か Android アプリケーション用のモダン POS のいずれかを使用する必要があります。
8. **保存** を選択します。
9. アクション ウィンドウの **レジスター** タブで、**IP アドレスの構成** を選択します。
10. **PIN パッド** のクイックタブで、支払ターミナルの IP アドレスを入力します。 Adyen コネクタを使用して支払ターミナルの IP アドレスを取得する方法については、[Adyen 用 Dynamics 365 Payment Connector](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3) を参照してください。
11. **保存** を選択します。

#### <a name="set-up-a-hardware-profile-for-the-receipt-printer-and-cash-drawer"></a>レシート プリンターとキャッシュ ドロワーのハードウェア プロファイルの設定

ネットワーク レシート プリンターとキャッシュ ドロワーをグループ化するために使用するハードウェア プロファイルを設定するには、次の手順を実行します。

1. Dynamics 365 Commerce で、**ハードウェア プロファイル** を検索します。
2. **新規** を選択します。
3. ハードウェア プロファイル番号を割り当て、説明を入力します。 このハードウェア プロファイルは、レシート プリンターとキャッシュ ドロワーをグループ化するために使用されます。 したがって、**ネットワーク プリンターとキャッシュ ドロワー** などの説明は十分です。
4. さまざまなデバイス タイプのクイック タブで、次のデバイス タイプを設定します。

    | デバイス | 種類 | 説明 | 追加の詳細 |
    |---|---|---|---|
    | プリンター | ネットワーク | **Epson** または **Star** | デバイス名は大文字と小文字が区別されます。 **レシート プロファイル ID** は、レジスターに割り当てあてられているハードウェア プロファイルで設定されているプリンターにマップされている **ハードウェア プロファイル ID** と同じである必要があります。 |
    | キャッシュ ドロワー | 予備 | **Epson** または **Star** | デバイス名は大文字と小文字が区別されます。 **共有シフトを使用** オプションを **はい** に設定します。 |

5. **保存** を選択します。

### <a name="set-up-hardware-stations"></a>ハードウェア ステーションの設定

2 つのハードウェア ステーションを用意する必要があります。 最初のものがレジスターにマップされます。 必要に応じて、レシートを印刷するか、キャッシュ ドロワーを開く必要がある場合は、この 2 番目の設定を選択します。

#### <a name="register-a-hardware-station"></a>ハードウェア ステーションの登録

1. Dynamics 365 Commerce で、**すべての店舗** を検索します。
2. **小売チャンネル ID** 値を選択して店舗を選択し、**編集** を選択し ます。
3. **ハードウエア ステーション** クイック タブで、**追加**を選択します。
4. **ハードウェア ステーション タイプ** フィールドを **専用** に設定します。
5. 説明を入力しますが、このハードウェア ステーションにはその他の値は設定しないでください。 このハードウェア ステーションは、常にレジスターに対して使用されます。 

#### <a name="set-up-a-hardware-station-for-the-receipt-printer-and-cash-drawer"></a>レシート プリンターとキャッシュ ドロワーのハードウェア ステーションの設定

1. Dynamics 365 Commerce で、**すべての店舗** を検索します。
2. **小売チャンネル ID** 値を選択して店舗を選択し、**編集** を選択し ます。
3. **ハードウエア ステーション** クイック タブで、**追加**を選択します。
4. **ハードウェア ステーション タイプ** フィールドを **専用** に設定します。
5. 説明を入力します。 このハードウェア ステーションは、レシート プリンターとキャッシュ ドロワーに使用されます。
6. **ハードウェア プロファイル** フィールドで、レシート プリンターとキャッシュ ドロワーに対して以前に作成したハードウェア プロファイルを選択します。
7. **保存** を選択します。
8. レシート プリンターとキャッシュ ドロワーのハードウェア ステーションが選択されている状態で、**IP アドレスの構成** を選択します。
9. プリンターの IP アドレスを取得し、レシート プリンターとキャッシュ ドロワーの両方の IP アドレスとして入力します。
10. **保存** を選択します
11. **配布スケジュール** を検索します。
12. 配分スケジュール **1090** を選択して、**今すぐ実行** を選択します。
13. 配分スケジュール **1070** を選択して、**今すぐ実行** を選択します。

### <a name="set-up-the-system-to-prompt-for-receipt-printer-and-cash-drawer-selection-as-its-required"></a>レシート プリンタとキャッシュ ドロワーの選択を要求するようにシステムを設定する

1. サポートされている POS クライアントで、シフトが開いている場合は現在のシフトを閉じます。
2. サインインして、**非ドロワーのドロワー操作** を選択します。
3. **ハードウェア ステーションの管理** 操作を使用して、ハードウェア ステーションの電源をオンにします。
4. レジスターで作成したハードウェア ステーションを選択して、有効にします。
5. POS からサインアウトし、再度サインインしてシフトを開きます。

これで、ハードウェア プロファイルに割り当てられている支払ターミナルが常に有効になり、レシート プリンターやキャッシュ ドロワーが必要な場合は、そのことを確認するメッセージが表示されます。

この機能を要求した加盟店の多くは、電子メールで領収書を提供して、電子支払を奨励することで無駄を削減することに興味を持っています。 POS の構成によっては、店舗の店員に顧客が紙の領収書や現金での支払を希望している場合のみレシート プリンターやキャッシュ ドロワーを選択するように求めています。

領収書を印刷する必要があり、かつ現金が支払に使用されている場合を除いて、店員は各トランザクションでハードウェア ステーションを 1 回だけ選択するように求めるメッセージが表示されますが、最初に選択されたハードウェア プロファイルには両方のデバイスは含まれていません。 この場合は、店員は、トランザクションを完了するために使用できるハードウェアステーションを選択するように求められます。

## <a name="related-articles"></a>関連記事

- [Android と iOS での POS ハイブリッドアプリの設定](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/hybridApp)
- [Adyen 向け Dynamics 365 Payment Connector](https://docs.microsoft.com/dynamics365/commerce/dev-itpro/adyen-connector?tabs=8-1-3)
- [ネットワーク周辺機器サポートの概要](https://go.microsoft.com/fwlink/?linkid=2129965)