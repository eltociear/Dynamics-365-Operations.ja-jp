---
title: 診断とトラブルシューティングの Retail コンポーネント イベント
description: 診断とトラブルシューティングを有効にするため、Retail Modern POS などのクライアントを含むすべてのコマース コンポーネントと Commerce Scale Unit などのサーバー コンポーネントは、イベントをイベント ビューアー (または Retail Cloud POS の場合はブラウザー開発ツール コンソール) にローカルで記録します。 この記事では、コマース固有のコンポーネントからイベントを検索する場所について説明します。
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: IT Pro
ms.reviewer: rhaertle
ms.search.scope: Operations, Retail
ms.custom: 85493
ms.assetid: a22c9493-c000-4514-bb0d-b3cc674439d9
ms.search.region: Global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9424cba2170f1af619fe0197f710ef40a001059d
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004645"
---
# <a name="retail-component-events-for-diagnostics-and-troubleshooting"></a>診断とトラブルシューティングの Retail コンポーネント イベント

[!include [banner](../includes/banner.md)]

診断とトラブルシューティングを有効にするため、Retail Modern POS などのクライアントを含むすべてのコマース コンポーネントと Commerce Scale Unit などのサーバー コンポーネントは、イベントをイベント ビューアー (または Retail Cloud POS の場合はブラウザー開発ツール コンソール) にローカルで記録します。 この記事では、コマース固有のコンポーネントからイベントを検索する場所について説明します。

<a name="viewing-events-in-event-viewer"></a>イベント ビューアーでのイベントの表示
------------------------------

イベントがログされるコンピューターに対して物理的にアクセスできる場合、イベント ビューアーを使用して、Microsoft Windows を実行するコンピューター上にインストールされたコンポーネント用イベントを表示することができます。 イベント ビューアーの詳細については、TechNet の [イベント ビューアー](https://technet.microsoft.com/library/4229f239-16a6-4ecd-b3cf-aec03dc08cd5) を参照してください。 また、イベント ビューアーを使用して、ユーザーがアクセス権を持つコンピューターからリモートでイベントを表示することができます。 イベント ビューアーを使用して、リモートでイベントを表示する方法の詳細については、TechNet の [リモート コンピューターでイベント ログを使用](https://technet.microsoft.com/library/cc766438.aspx) を参照してください。 イベント ビューアは通常、次の使用例でのトラブルシューティングに使用されます。

-   開発者トポロジまたはイベント ビューアーへのアクセスを提供するダウンロード可能な仮想ハードディスク (VHD) での開発
-   会議室パイロットを実行していて、そのコンピューティングのイベント ビューアにアクセスできるときのクライアント コンポーネント

ただし、ほとんどの場合、特にコンピューターのイベント ビューアーへのアクセスがない場合、Microsoft Dynamics Lifecycle Services (LCS) でログ検索を使用できます。 ログ検索については、この記事の後半で説明します。 このセクションは、次のコンポーネントに適用されます。

-   コマース スケール ユニット
-   Retail Modern POS
-   Retail ハードウェア ステーション

### <a name="find-commerce-specific-events-in-event-viewer"></a>イベント ビューアーで、コマース固有のイベントを検索する

コンピューターでイベント ビューアを起動するには、**開始** ボタンをクリックし、**イベント ビューア** をクリックします。 

[![スタート ボタンのショートカット メニューのイベント ビューアー コマンド](./media/launch-event-viewer.png)](./media/launch-event-viewer.png) 

すべてのコマース固有イベント ログにはイベント ビューアーで次のパスを確認できます。アプリケーションおよびサービス ログ \\Microsoft\\Dynamics 以下のコマース固有のイベント ログを提供します。

-   **Commerce-RetailServer** – このログには、Commerce Scale Unit コンポーネントによって記録されるイベントが含まれます。
-   **Commerce-ModernPos** - このログには、Retail Modern POS によって記録されるイベントが含まれます。 これらのイベントには、TypeScript および C\# (CRT) レイヤーからのイベントが含まれます。
-   **Commerce-LoggingProvider** – このログには、この記事の前半で一覧に含まれていない他のすべてのコマース コンポーネントによって記録されるイベントが含まれています。

### <a name="enable-debug-event-logs"></a>デバッグ イベント ログの有効化

現在、さまざまなコンポーネントによって記録されたイベントの一部がデバッグ イベント ログに送信されます。 これらのイベントは非常に高いレートで記録され、詳細なデバッグ シナリオでのみ有用な詳細イベントです。 イベント ビューアーでのデバッグ イベント ログを有効にするには、この手順を実行します。

-   デバッグ ログを右クリックし、**ログの有効化** をクリックします。

[![デバッグ ログのショートカットメニューでログ コマンドを有効化](./media/enable-debugging-log.png)](./media/enable-debugging-log.png)

## <a name="viewing-events-by-using-the-f12-browser-developer-tools-console"></a>(F12) ブラウザー開発者ツール コンソールを使用してイベントを表示
Retail Cloud POS はブラウザー ベースのコンポーネントなので、ブラウザー開発者ツール コンソールを使用してそのイベントを表示できます。 Microsoft ブラウザ開発者ツール コンソールの詳細については、MSDN の [コンソールを使用してエラーとデバッグを表示する](https://msdn.microsoft.com/library/dn255006(v=vs.85).aspx) を参照してください。 Retail Cloud POS のブラウザー開発者ツールを使用するには、サポートされているバージョンのブラウザを使用する必要があります。

### <a name="view-events-in-the-browser-developer-tools-console"></a>ブラウザー開発者ツール コンソールでのイベントの表示

1.  Internet Explorer または Microsoft Edge を開始し、Retail クラウド POS に移動します。
2.  F12 キーを押し、**コンソール** タブをクリックします。
3.  Retail Cloud POS の操作を実行する際に、イベントはコンソールに記録されます。 イベント重要度でフィルター処理して、異なる重要度レベルのイベントを表示することができます。

[![ブラウザー開発者ツールのコンソール タブ](./media/browser-console-1024x522.png)](./media/browser-console.png)

## <a name="correlating-events"></a>関連のイベント
このセクションでは、さまざまなコマース コンポーネントからイベントを関連付ける方法について説明します。

### <a name="data-flow-between-a-pos-client-and-commerce-scale-unit"></a>POS クライアントと Commerce Scale Unit 間のデータ フロー

以下の図は、販売時点管理 (POS) クライアントと Commerce Scale Unit 間のデータ フローを示しています。

#### <a name="pos-client-startup"></a>POS クライアントの起動

ユーザーが POS クライアントを起動すると、新しい AppSessionID が生成されます。 AppSessionID は、POS クライアントで計測されるすべてのイベントのログを作成するために使用されます。 イベント ビューアおよびアプリ インサイトに記録したすべてのイベントはこの ID を持っています。

#### <a name="user-sign-in"></a>ユーザー サインイン

ユーザーが POS クライアントにサインインすると、新しい UserSessionID が生成されます。 UserSessionID は、POS クライアントで計測されるすべてのイベントのログを作成するために使用されます。 イベント ビューアーに記録されたすべてのユーザー イベントはこの ID を持ちます。 この ID は、ユーザーがログインしている間維持されます。 現在のユーザーがサインアウトして、新しいユーザーがログインすると、新しい UserSessionID が生成されます。

#### <a name="pos-client-calls-to-commerce-scale-unit"></a>POS クライアントによる Commerce Scale Unit への呼び出し

POS クライアントが Commerce Scale Unit を呼び出すときはいつでも、AppSessionID と UserSessionID がヘッダーとして送信されます。 次に、Commerce Scale Unit は、受信要求 (イベント ID 5000) のイベントを記録します。 このイベントには、2 つの ID と ActivityID が含まれます。 その後、ActivityID はすべての関連するイベントにも使用されます。 AppSessionID、UserSessionID、ActivityID は、Commerce Scale Unit がホストされているイベント ログで使用可能です。 LCS ログ検索でも利用できます。

#### <a name="request-activity-on-commerce-scale-unit"></a>Commerce Scale Unit での要求の活動

Commerce Scale Unit 要求の一部として記録されるすべてのイベントは、最初の受信要求イベント用に記録された初期イベントと同じ ActivityID を持ちます (イベント ID 5000)。 これらのイベントは、イベント ビューアーと LCS ログ検索の両方で利用できます。 

[![POS クライアントと Commerce Scale Unit 間のデータ フロー](./media/event-log-data-flow1-1018x1024.png)](./media/event-log-data-flow1.png)

### <a name="finding-retail-modern-pos-events-in-event-viewer"></a>イベント ビューアーでの Retail Modern POS イベントの検索

Retail Modern POS によってが記録されたすべてのイベントには、次のデータ点が含まれています。

-   **AppSessionID** - アプリケーションが最初に起動されたときに生成される一意の ID。 これは記録されるすべてのイベントに含まれています。
-   **UserSessionID** – ユーザーが Retail Modern POS にサインインするときに生成される固有の ID。 これはユーザーがサインインしている限り、記録されるすべてのイベントに含まれています。 新しいユーザーがサインインするとき、新しい UserSessionID が作成されます。

AppSessionID 値および UserSessionID 値は、Retail Modern POS がインストールされているマシン上のイベント ビューアーの**詳細**タブで見つけることができます。 

[![イベント ビューアーの詳細タブ](./media/correlation-1024x672.png)](./media/correlation.png)

### <a name="finding-incoming-commerce-scale-unit-request-events-in-event-viewer"></a>イベント ビューアーで、受信する Commerce Scale Unit 要求のイベントを検索

イベント ビューアで受信する Commerce Scale Unit 要求のデータを関連付けるには、最初に **Analytic** チャネルを有効にする必要があります。 分析チャネルを有効にするには、次の手順を実行します。

1.  イベント ビューアーの左ウィンドウで、**Commerce RetailServer** を選択します。
2.  **表示** &gt; **分析とデバッグ ログを有効にします**をクリックします。 分析チャネルの新しいノードは、**Commerce-RetailServer** ログ プロバイダーの下に表示されます。
3.  **分析** ノードを右クリックし、**ログの有効化** をクリックします。

イベント ビューアーでは、受信しているすべての Commerce Scale Unit の要求がイベント 5000 として Commerce-RetailServer ソースの分析チャネルに記録されます。 これらのイベントには、前述した AppSessionID と UserSessionID もあります。 すべてのイベントには、同じ要求のログに記録されたイベントごとに、固有の ActivityID も用意されています。

## <a name="using-lcs-log-search"></a>LCS ログ検索の使用
LCS ログ検索で、1 つのポータルからすべてのコンポーネントのデータを表示できます。 イベントは、(Commerce Scale Unit などの) クラウドでホストされたコンポーネントと (Retail Modern POS および Retail Hardware Station などの) 店舗内コンポーネントの両方からアクセスすることができます。 すべてのクラウドホストおよびストア内コンポーネントからのイベント データは、索引付けされ検索可能になる LCS ログ検索に流れます。 データは通常、記録されてから 5 分以内に利用可能です。 POS クライアントおよび Retail Hardware Station では、すべてのイベントが永続ストレージにローカルでキュー格納され、キューがいっぱいになった後にバッチでアップロードされます。 この動作により、ネットワーク トラフィックを最適化できます。  また、インターネット接続がない場合でもイベントを保存することができます。 接続が回復した後、すべての保留中のイベントがアップロードされます。 

LCS ログ検索は、HA 運用トポロジに使用できます。 次のコマースのコンポーネントに使用することができます。

-   Retail Modern POS
-   Retail Cloud POS
-   Commerce Scale Unit (Retail Cloud Scale Unit で実行中)

LCS ログ検索に、次のコマース コンポーネントからのログは**含まれません**。

-   コマース レイアウト デザイナー
-   コマース受領書デザイナー
-   Retail Modern POS のセルフ サービス インストーラー
-   小売ハードウェア ステーション用のセルフ サービス インストーラー
-   Commerce Scale Unit (Retail Store Scale Unit で実行中)
-   Retail ハードウェア ステーション

### <a name="access-lcs-log-search"></a>LCS ログ検索にアクセス

LCS ログ検索にアクセスするには、次の手順を実行します。

1.  [Lifecycle Services](https://lcs.dynamics.com/) に移動します。
2.  プロジェクトに関連付けられている資格情報を使用してログインします。
3.  プロジェクト ページで、正しいプロジェクトを選択します。
4.  **プロジェクトの詳細**ページで、正しい環境を選択します。
5.  **環境の詳細**ページで、**環境の監視**をクリックします。
6.  **環境の監視**ページで、**未加工ログの表示**をクリックします。
7.  **ログ検索**ページで、次のいずれかのクエリを選択します。
    -   **コマース クライアント イベント** クエリには、Retail Modern POS、Retail Cloud POS、および Commerce Scale Unit (Retail Cloud Scale Unit で実行中) からのイベントが含まれます
    -   **すべてのログ** クエリには、Commerce Scale Unit、Commerce Data Exchange、および Commerce Data Exchange: リアルタイム サービスからのデータが含まれます

以下の条件でフィルター処理してクエリを調整することができます。

-   開始および終了日時 (協定世界時 \[UTC\])
-   デバイス ID
-   POS ユーザー
-   POS アプリケーション セッション ID
-   POS ユーザー セッション ID
-   重大度

[![環境監視ページの検索結果](./media/log-search-results.png)](./media/log-search-results.png)



