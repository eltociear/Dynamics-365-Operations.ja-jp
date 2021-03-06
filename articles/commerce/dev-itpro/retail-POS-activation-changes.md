---
title: カスタマイズされた Modern POS のデバイスの有効化
description: このトピックでは、カスタマイズした Modern POS アプリケーションを使用する場合に、デバイスの有効化が正常に動作するように、Microsoft Dynamics 365 Commerce Headquarters を構成する方法について説明します。
author: jashanno
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: IT Pro
ms.reviewer: rhaertle
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.author: jashanno
ms.search.validFrom: 2017-09-30
ms.dyn365.ops.version: Application update 3
ms.openlocfilehash: ca034abea3b8ef126d6fac58efa3d29c64c6fe1b
ms.sourcegitcommit: 4359e7e4eec25362df61c9a26c7218604d12da3d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "3078057"
---
# <a name="device-activation-of-a-customized-modern-pos"></a>カスタマイズされた Modern POS のデバイスの有効化

[!INCLUDE [banner](../includes/banner.md)]

このトピックでは、カスタマイズした Modern POS アプリケーションを使用する場合に、デバイスの有効化が正常に動作するように、Microsoft Dynamics 365 Commerce Headquarters を構成する方法について説明します。 カスタマイズされた返信アドレスを取得し、Headquarters でその値を入力するために必要な手順を説明します。

Modern POS は、Microsoft Dynamics 365 Commerce のクライアント側コンポーネントです。 POS を使用するには、デバイスの有効化を実行する必要があります。 デバイスの有効化は、ユーザーを認証する Azure Active Directory (Azure AD) を使用します。 この領域の拡張機能は、Web アカウント マネージャー サービスを活用するためにデバイスの有効化のフローを変更しました。 この拡張の一部として、認証承認プロセスのセキュリティが強化されました。 このセキュリティ強化では、コールバック URI に特定の一意の値が必要になるため、POS のカスタマイズ時に Headquarters で追加設定が必要です。 (コールバック URI は、返信 URI とも呼ばれます。)

既定では、Modern POS はこのコールバック URI に既に登録されています。 ただし、カスタマイズするとき、コールバック URI が変更されます。 したがって、再度動作するように正しく構成する必要があります。 このトピックでは、この構成を完了するために従う必要がある手順について説明します。 この構成が完了していない場合、カスタマイズされた POS アプリケーションでデバイスの有効化を実行しようとすると、エラー メッセージが表示されます。 このエラー メッセージは次のようになります。

> AADSTS50011: The reply address 'ms-appx-web://Microsoft.AAD.BrokerPlugin/[...]' does not match the reply addresses configured for the application

> [!NOTE]
> - Dynamics 365 Headquarters を構成する前に、カスタマイズされた Modern POS アプリケーションを 1 回使用することをお勧めします。 これにより、エラー メッセージがどのようなものかを確認し、カスタマイズされた返信アドレスをより簡単に取得できます。
> - エラーは、POS アプリケーションに対応するアプリケーション ID に使用される返信アドレスを指定します。

## <a name="setup"></a>セットアップ
次の手順は、カスタマイズされた Modern POS アプリケーションを使用する場合に、デバイスの有効化が正常に動作できるようにするために必要です。 2 つの Azure AD アプリケーションを作成します。1 つは Modern POS 用、1 つは Commerce Scale Unit 用です。 POS は Commerce Scale Unit を通じてリソースを使用するため、Commerce Scale Unit Azure AD アプリケーションが必要です。 したがって、POS が使用される場合は両方の Azure AD アプリケーションが使用されます。 このシナリオでは、Commerce Scale Unit は、POS が要求する保護されているリソースのエンドポイントとして機能します。

### <a name="create-the-commerce-scale-unit-azure-ad-application"></a>Commerce Scale Unit Azure AD アプリケーションの作成
1. Web ブラウザーで、<https://portal.azure.com/>に移動します。
2. Azure AD アプリケーションを作成するための十分なアクセス許可を持つ Azure AD 資格情報を使用してログインします。
3. **Azure Active Directory** \> **App registrations** を選択します。
4. **新しいアプリケーション登録**を選択して、次の値を入力することで、Commerce Scale Unit Azure AD アプリケーションを作成します。

    - **名前:** **カスタマイズされた Commerce Scale Unit** を入力します。 (他の固有の値を入力できますが、記録しておいてください。)
    - **アプリケーション タイプ:** **Web アプリ/API** を選択します。
    - **サインオン URL:** 実際の物理的な場所をポイントしない固有 URL を入力します。 たとえば、「`https://MyNotRealURL`」を入力します。

5. Azure が **サインオン URL** フィールドの値を検証するように、Tab キーを押します。 次に、**作成** を選択し、処理が正常に完了するまで待機します。 (エラーが発生する場合は、解決してもう一度やり直します。)

    タイルに、新しい Azure AD アプリケーションの詳細が表示されます。

6. タイルの上部の **設定** を選択し、アプリケーションの **設定** タイルを開きます。 次に、**プロパティ** を選択します。
7. **プロパティ** タイルで、**アプリケーション ID URI** フィールドの値をコピーします。 この値は、次のセクションで POS の DLLHost.exe.config ファイルに貼り付けます。

> [!NOTE]
> このトピックの後半で再び使用するため、Web ブラウザー ウィンドウを閉じないでください。

### <a name="update-the-modern-pos-configuration"></a>Modern POS 構成の更新
1. ファイル エクスプローラーで、**C:\\Program Files (x86)\\Microsoft Dynamics 365\\70\\Retail Modern POS\\ClientBroker** に移動します。 (このパスは、コンピューターの Microsoft Windows オペレーティング システムが、x64 アーキテクチャ ベースであることを前提としています)。
2. エクスプローラーで、**ファイル** \> **Windows PowerShell を開く** \> **管理者として Windows PowerShell を開く** を選択します。
3. 表示された Microsoft Windows PowerShell ウィンドウで、**notepad DLLHost.exe.config** と入力して Enter キーを押します。 (Windows PowerShell ウィンドウは、現在のファイル ディレクトリを既にポイントしています。)
4. 表示されたメモ帳ウィンドウで、**AADRetailServerResourceId** キーに対応する値を見つけます。 (この値は、既定では `https://commerce.dynamics.com` です)。次に、前のセクションの手順 7 でコピーしたアプリケーション ID URI 値を貼り付けます。
5. **ファイル** \> **保存** を選択します。

> [!NOTE]
> 次にセクションで再び使用するため、メモ帳ウィンドウを閉じないでください。

### <a name="create-the-customized-modern-pos-azure-ad-application"></a>カスタマイズされた Modern POS Azure AD アプリケーションを作成する
1. <https://portal.azure.com/> が開いている Web ブラウザー ウィンドウに戻り、「Commerce Scale Unit Azure AD アプリケーションを作成する」セクションの手順 3 と 4 を繰り返して、Retail Modern POS Azure AD アプリケーションを作成します。 ただし、今回は次の値を入力します。

    - **名前:** **カスタマイズされた Retail Modern POS** を入力します。 (他の固有の値を入力できますが、記録しておいてください。)
    - **アプリケーション タイプ:** **ネイティブ**を選択します。
    - **リダイレクト URI:** このトピックの先頭でお勧めしたように、Dynamics 365 バックオフィスを構成することなく、カスタマイズされた Modern POS アプリケーションを使用するしようとすると、エラー メッセージが表示されます。 そのエラー メッセージに対応する返信アドレス (リダイレクト URI) を入力します。 値の先頭は **ms-appx-web://Microsoft.AAD.BrokerPlugin/[...]** です。

        > [!NOTE]
        > - Windows のイベント ビューアーの **Microsoft-Dynamics-Commerce-ModernPos/Operational** で返信アドレス (リダイレクト URI) を表示することもできます。 イベント ID は 40619 です。 エラー メッセージの先頭は "This UWP application was assigned the following callback URI to be used while interacting with Azure AD: ms-appx-web://Microsoft.AAD.BrokerPlugIn/S-1-15-2-[...]" です。
        > - Azure AD アプリケーションが作成されたら、必要に応じて追加リダイレクト URI を指定できます。 異なるコールバック URI のある複数のパッケージが何らかの理由で生成された場合、この 1 つの Azure AD アプリケーションを保持し、その中にすべてのリダイレクト URI を保持してください。

2. Azure が **リダイレクト URI** フィールドの値を検証するように、Tab キーを押します。 次に、**作成** を選択し、処理が正常に完了するまで待機します。 (エラーが発生する場合は、解決してもう一度やり直します。)

    タイルに、新しいカスタマイズされた Retail Modern POS Azure AD アプリケーションの詳細が表示されます。

3. **アプリケーション ID** フィールドを見つけ、値をコピーします。 (この値は、**AADClientId** キーに対応する値として DLLHost.exe.config ファイルに貼り付けます。)
4. タイルの上部の **設定** を選択し、アプリケーションの **設定** タイルを開きます。 次に、**必要なアクセス許可** を選択します。
5. **必要なアクセス許可** タイルで **+ 追加** を選択します。
6. **API アクセスの追加** タイルで、**1 API を選択する** を選択します。
7. **API を選択**タイルの検索フィールドで、「Commerce Scale Unit Azure AD アプリケーションを作成する」のセクションで作成した Commerce Scale Unit Azure AD アプリケーションの名前を入力します。 (このトピックでは、アプリケーションの名前は**カスタマイズされた Commerce サーバー**です。) そのアプリケーションに対応する品目を選択し、**選択** を選択します。

    **API アクセスを追加する** タイルで、**2 アクセス許可を選択** が自動的に選択され、**アクセスを有効にする** という名前の新しいタイルが表示されます。

8. **アクセスを有効にする**タイルで、**カスタマイズされた Commerce Scale Unit にアクセスする**行の上にマウス ポインターを置き、左側に表示されるチェック ボックスを選択します。 (Commerce Scale Unit Azure AD アプリケーションに別の名前を入力し、**カスタマイズされた Commerce Scale Unit** の代わりに、その名前が行で使用される場合)。タイルの下部にある **選択** ボタンが使用できるようになります。
9. **選択** を選択して **API アクセスを追加する** タイルに戻ります。
10. **完了** を選択し、**必要なアクセス許可** タイルに戻ります。
11. **アクセス許可の付与** を選択します。 アクセス許可を付与することを確認するメッセージが表示されたら、**はい** を選択します。
12. DLLHost.exe.config ファイルの内容が表示されているメモ帳ウィンドウに切り替えます。 (前のセクションの手順を完了した後にこのウィンドウから離れます。)
13. **AADClientId** キーに対応する値を見つけます。 (既定では、この値はバックオフィス環境に対応するグローバル一意識別子 [GUID] です)。手順 3 でコピーした値を貼り付けます。
14. **ファイル** \> **保存** を選択します。

### <a name="configure-dynamics-365-headquarters"></a>Dynamics 365 Headquarters の構成
前の手順は、Modern POS アプリケーションを認証できるようにするために必要でした。 ここでは、要求を承認できるように、次の手順を実行し、新しい Azure AD アプリケーションを Headquarters の安全なプログラムの一覧に追加する必要があります。 (安全なプログラムの一覧はホワイトリストと呼ばれることもあります)。

1. Web ブラウザーで、Headquarters URL に移動し、Azure AD 資格情報を使用してログインします。
2. **Retail と Commerce** &gt; **Headquarters の設定** &gt; **パラメーター** &gt; **Commerce 共有パラメーター**の順に移動します。
3. **ID プロバイダー** タブの **ID プロバイダー** セクションで、`HTTPS://sts.windows.net/` から始まるプロバイダーを選択します。 選択したプロバイダーに基づいて、**依存する関係者** セクションの値が更新されます。
5. **依存する関係者** セクションで、**+ 追加**を選択し、次の値を入力します。

    - **ClientId:** 前のセクションの手順 3 でコピーし、手順 13 で DLLHost.exe.config に貼り付けた値を入力します。
    - **タイプ:** **パブリック** を選択します。
    - **UserType:** **作業者** を選択します。
    - **名前:** このエントリが参照する、ユーザーがわかりやすい説明を入力します。

6. アクション ウィンドウで、**保存**を選択します。 作成した依存する関係者は選択したままにしてください。
7. **サーバー リソース ID** セクションで、**+ 追加**を選択し、次の値を入力します。

    - **サーバー リソース ID:** 「Modern POS 構成の更新」セクションの手順 4 でコピーした URL を入力します。 (最初は、「Commerce Scale Unit Azure AD アプリケーションを作成する」セクションの手順 4 でこの値を作成しました。)
    - **名前:** このエントリが参照する、ユーザーがわかりやすい説明を入力します。

8. アクション ウィンドウで、**保存**を選択します。
9. **Retail と Commerce** &gt; **Retail と CommerceIT** \> **配送スケジュール**の順に移動します。
10. ジョブ **1110** (**グローバル構成**) を選択し、アクション ペインで **今すぐ実行** を選択します。 このジョブは、新しいデータを同期させます。 ただし、Commerce Scale Unit にはキャッシュがあり、数分は更新されません。 したがって、迅速な更新が必要な場合、Commerce Scale Unit アプリケーション プールを再利用する必要があります。

    > [!NOTE]
    > 最適な結果を得るため、Modern POS が終了していることと、DLLHost.exe のインスタンスがタスク マネージャーに存在しないことを確認します。

### <a name="perform-modern-pos-device-activation"></a>Modern POS のデバイスの有効化の実行
Modern POS デバイスを有効化してください。 依然として問題が発生する場合は、Windowsでイベント ビューアーを開き、Modern POS に対応するログを表示します。 前のセクションで見逃したステップを判断する際に役立つを警告やエラーを探します。
