---
title: "開発と継続的な配信のよく寄せられる質問"
description: "このトピックでは、ISV やパートナーによってよく寄せられる質問、特に、開発、テスト、デリバリー、およびライフサイクル管理に関するガイドラインについて、その回答をまとめています。"
author: RobinARH
manager: AnnBe
ms.date: 02/13/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: Operations
ms.custom: 202614
ms.assetid: bc80fee3-8f54-43c4-9162-f058056c956c
ms.search.region: Global
ms.author: robadawy
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 2c535b8b8140304ae11ff133ae77818c32064687
ms.contentlocale: ja-jp
ms.lasthandoff: 08/09/2018

---

# <a name="development-and-continuous-delivery-faq"></a>開発と継続的な配信のよく寄せられる質問

[!include [banner](../includes/banner.md)]

このトピックでは、ISV やパートナーによってよく寄せられる質問、特に Microsoft Dynamics 365 for Finance and Operations の開発、テスト、デリバリー、およびライフサイクル管理に関するガイドラインについて、その回答をまとめています。

<a name="customization"></a>カスタマイズ
-------------

### <a name="do-i-customize-overlayer-or-use-extensions"></a>カスタマイズ (オーバーレイ) するか、または拡張子を使用するか。

アプリケーションのカスタマイズは*拡張機能*と呼ばれる新しいフレームワークを使用して有効になります。 開発者は、個別のアセンブリと配布可能なパッケージにコンパイルする拡張モデルを作成できます。 拡張モデル内では、開発者は新しい要素を作成して、他のモデルに属する要素を拡張し、イベント ハンドラとプラグインを使用してビジネス ロジックをカスタマイズすることができます。 拡張子により、ビルドの高速化、アプリケーション ライフサイクル管理およびコード移動の効率化、設計時のパフォーマンスの向上、アプリケーションのアップグレードにかかるコストの最小化が可能になります。 Microsoft Dynamics AX 2012 で利用可能なフレームワークと似ている、メタデータおよびコードの *オーバーレイヤ* を使用して、カスタマイズを作成することができます。 コードをオーバーレイすると、X++ コードとメタデータを自由に変更できますが、カスタマイズするコードの同じパッケージ (同じアセンブリ) にコンパイルします。 次にいくつかガイドラインを挙げます。

-   拡張機能を既定の開発モードとして使用し、最後の手段としてのみオーバーレイに戻します。
-   コードをオーバーレイする必要があるとき、機能またはビジネス ロジックをオーバーレイ コードに含めないでください。 代わりに、デリゲート メソッドを定義して呼び出し、イベント ハンドラーを使用している拡張モデルにロジックを実装します。 コード移行のコンテキストで詳細な例については、[委任](../migration-upgrade/delegates-migration.md) を参照してください。
-   よく使用されるオーバーレイヤー パターンを Microsoft に報告し、拡張サポートを要求します。

詳細については、[拡張機能のホーム ページ](../extensibility/extensibility-home-page.md) および [開発者ホーム ページ](developer-home-page.md) を参照してください。

### <a name="how-do-i-prevent-my-models-from-being-customized-by-customers-or-other-partners"></a>モデルが、顧客や他のパートナーによってカスタマイズされないようにするにはどうすればよいですか。

[モデルのカスタマイズを無効にして機能を廃止する方法](lock-models.md) に説明されているようにモデルのカスタマイズをブロックするか、モデル ファイルを配布せずに展開可能パッケージを顧客に配布することができます。 このトピックの後方の「アプリケーションを顧客に配布する方法」を参照してください。

### <a name="how-can-i-define-the-scope-of-my-models-how-many-models-or-packages-should-i-create"></a>モデルのスコープをどのように定義できますか。 モデルまたはパッケージをいくつ作成する必要がありますか。
モデルとモデル要素を設計することは、他のタイプのソフトウェア ライブラリを設計することと変わりありません。 [SOLID (オブジェクト指向設計)](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)) の設計原則を適用する必要があります。 さらに、Dynamics 365 Unified Operations プラットフォーム特有の次のヒントをお勧めします。
-   ソリューションに出荷するコンポーネントと残りのコンポーネントよりも頻繁にサービスするコンポーネントがある場合は、別々のモデルとパッケージに配置することをお勧めします。
-   一般的には、実装の初期段階では (それぞれ 1 つのモデルを持つ) 2 つのパッケージ、Microsoft プラットフォーム パッケージに対する拡張機能を含む 1 つの基盤パッケージ、Microsoft アプリケーション パッケージに対する拡張機能を含む 1 つのアプリケーション パッケージから始めます。 必要な場合、さらにモデルを導入できます。
-   既存のパッケージは、必要に応じてより小さなパッケージに分割することができます。 パッケージのいずれかを使用して実装が既に行われている場合、ライフサイクル管理を容易にするためにパッケージの名前の変更を避けます。

## <a name="continuous-delivery"></a>継続的な配信
### <a name="do-i-need-build-environments"></a>環境を構築する必要があるか。

はい、ビルド環境で提供されているビルドおよびテストの自動化ツールを活用する必要があります。 Lifecycle Services (LCS) プロジェクトからビルド環境を展開することができます。 毎日のビルドおよび毎日の回帰テストの作成は、継続的デリバリーを可能にし、アプリケーションの品質を維持するための重要なツールです。 詳しくは、「[継続的ビルドとテストの自動化を使用した開発者トポロジの展開](../perf-test/continuous-build-test-automation.md)」をご覧ください。

開発活動にはビルド環境を使用せず、これらのビルド VM にテスト データベースのバックアップを保持します。 ビルド VM は、毎回のビルドおよび Microsoft バイナリまたは LCS からのプラットフォーム更新で更新されるたびに、既知の状態へリセットされるように設計されています。 たとえば、バイナリの修正プログラムやプラットフォームの更新をビルド VM に適用する場合、VM は更新の一部として次のビルドのために準備します。 これによって、カスタマイズは削除され、データベースの同期もトリガーされます。

### <a name="what-strategy-do-i-use-for-test-automation"></a>テストの自動化にどのような戦略を使用しますか ?

テストの自動化については、独立したデータまたは独自のデータを作成する単体テスト (SysTest フレームワークを使用) に焦点を合わせます。 実行するテスト データに依存する少数の機能的なシナリオ テスト (タスク レコーダーに基づく) を使用します。 シナリオ テストは、維持にコストがかかります。 単体テストは任意の開発環境で簡単かつ迅速に実行できます。 [テストの自動化ピラミッド](https://blogs.msdn.microsoft.com/dave_froslie/2016/03/09/test-automation-pyramid/)に関するブログ記事を確認し、[自動化されたテスト ガイダンス](https://blogs.msdn.microsoft.com/axdevalm/2016/08/12/automated-testing-guidance-for-ax-7/)を参照してください。 

![media/testautomationpyramid1.png](media/testautomationpyramid1.png) いくつかの重要な概念に留意してください。

-   独立して実行されて順番を想定しないテストを記述します。
-   タスク レコーダー テストは、機能シナリオのテストに限定する必要があります。
-   シナリオが完了した後のシナリオ テストおよび単体テスト完了後のシナリオ テストを記述します。
-   可能であれば、テスト ヘルパー クラスを作成して、チームの他の人も同様に活用することができます。
-   SysTest フレームワークは役割に基づくテストをサポートし、この機能を活用します。

### <a name="how-can-i-be-more-agile-in-my-development"></a>開発に関してどのようにより機敏になれますか。

スプリント (2週間、優先) またはサイクル (1ヶ月) ごとに増分機能を提供します。 各スプリントの終わりでアプリケーションの出荷可能な品質を管理します。 作業項目の進捗管理には Visual Studio Team Services (VSTS) を使用し、常に新しい機能よりもバグに優先度を高くします。 大規模なバックログのバグは、アプリケーションの新しい機能と品質の効率的な配信にとって直ちに負担となります。

### <a name="how-do-i-manage-test-data"></a>テスト データをどのように管理しますか。

次のようにテスト データベースを作成および管理します。

-   クリーンな環境で開始します。
-   必要に応じてすべての基本データを作成します。 基本データはすべてのテストの開始点として使用されます。
-   AxDB データベースのバックアップ (.bak) を取得します。
-   このバックアップを開発者と共有します。

ビルド環境では、このバックアップを I:\\DynamicsBackupDatabases にコピーします (環境によっては i: とは異なるドライブになる可能性があります)。 このデータベースは、すべてのビルドの開始時にリストアされます。 このステップは、**ビルドの準備**と呼ばれるビルド定義の最初のステップの一部として実行されます。 

![media/prepareforbuild.png](media/prepareforbuild.png)

### <a name="how-do-i-distribute-my-application-to-customers"></a>顧客にアプリケーションをどのように配布しますか。

アプリケーションを顧客またはパートナーに配布するために使用できる成果物には、モデル ファイルまたは展開可能なパッケージの 2 つがあります。 モデル ファイルは、ソース コードが含まれるデザイン タイム コンポーネントです。 顧客がアプリケーションを他のサード パーティのモデルと統合する場合、またはモデルのカスタマイズを許可する場合は、モデル ファイルを使用します。 詳細については、「[モデルの配分: モデルのエクスポートおよびインポート](models-export-import.md)」を参照してください。 モデル ファイルは、ISV にとってソリューションを配布するための最も一般的な方法です。 配置可能パッケージは最後のアプリケーションです。 アプリケーションをカスタマイズしたり、他のサードパーティ製のモデルと統合したりしない顧客では、展開可能なパッケージを使用します。 配置可能なパッケージを使用する場合、顧客はアプリケーションの使用または拡張のみが可能です。 ソース コードを見たりアクセスしたりしません。 展開可能なパッケージを作成するには、Visual Studio ツール (**Dynamics 365**&gt;**展開**&gt;**展開可能パッケージを作成**) またはビルド環境を使用します。 ビルド環境は、すべての成功したビルドで配置可能パッケージを生成します。

## <a name="development-topologies"></a>開発トポロジ
### <a name="should-i-develop-on-premises-or-in-the-cloud"></a>社内で、またはクラウドで開発すべきか。

開発には 2 つのモードがあります。ダウンロード可能な VHD 経由で利用できるクラウド VM とオンプレミス VM です。 開発には、社内 VM とクラウド VM を組み合わせて使用します。

-   オンプレミス開発者 VM は、それをサポートするハードウェア、IT インフラストラクチャと Windows サーバー ライセンスが既にある場合、費用効果が高くなります。
-   限られた期間、追加のリソースが必要な場合は、クラウド VM を使用してスケール アウトします。 オンプレミスでの最悪の場合のキャパシティを計画するよりコスト効率がよくなります。
-   バージョン管理のために、すべての VM (オンプレミスおよびクラウド VM) を VSTS に接続します。

ビルド、機能テスト、デモには、クラウド VM を使用します。 Microsoft Azure サブスクリプションで実行している場合は、使用中でない場合は停止します。

### <a name="should-i-use-a-customers-dev-environment"></a>顧客の開発環境を使用する必要がありますか。

パートナーである場合、独自の知的財産 (IP) を開発するため独自の VM を使用します。これが、別の顧客の実装間で再利用可能がコードとコンフィギュレーションのデータ パッケージになります。 顧客固有の実装については、顧客の開発 VM を使用することができます。 すべての顧客サブスクリプションは少なくとも 1 つの開発 VM に添付されます。 顧客は、アドオン開発用 VM の支払いや、ローカル開発用 VM の実行が可能です。

### <a name="what-are-the-benefits-of-msdn-subscriptions-with-respect-to-development"></a>開発に関して MSDN サブスクリプションの利点とは

次は、MSDN サブスクリプションの利点を持つ Visual Studio (VS) の概要です。

-   Visual Studio Professional with MSDN の場合は月間 $50 で、VS Enterprise with MSDN の場合は $150 で Microsoft Azure サブスクリプションが含まれます。
-   サブスクリプションは開発/テスト レートが低く、Windows レートではなく Linux レートを支払います。
-   詳細については、<https://azure.microsoft.com/en-us/pricing/member-offers/msdn-benefits-details/> にアクセスしてください。

マイクロソフト パートナーは、Microsoft コア コンピテンシーを取得して MSDN サブスクリプションで無料の VS Enterprise を獲得できます。 たとえば、ゴールド パートナー用のアプリケーション開発コンピテンシーは、コア給付金に付属している 10 のライセンスに加えて 25 の無料 MSDN エンタープライズ ライセンスを獲得します。 詳細については、[Visual Studio サブスクライバの月間 Azure クレジット](https://azure.microsoft.com/en-us/pricing/member-offers/msdn-benefits-details/) にアクセスしてください。 これらの利点により、クラウド開発は非常に経済的です。例:

-   D12v2 VM 表示価格は = $470/月 (4コア、28ギガ)
-   D12v2 MSDN Azure またはその他の dev/test サブスクリプションで実行している場合の VM 価格 = $276/月
-   1 日あたり 12 時間停止: 276/2 =&gt; $138/月
-   月額 (VS Professional with MSDN) =&gt; 138 - 50 = **$88/月**
-   月額 (VS Enterprise with MSDN) =&gt; 138 – 150 = **無料**

次に別の例を示します。

-   D13v2 マシン 表示価格は = $843/月 (8コア、56ギガ)
-   MSDN Azure のサブスクリプションで稼働している場合、D13v2 マシン価格 = $551/月
-   1 日あたり 12 時間停止: 551/2 = $275.5/月
-   月額 (VS Professional with MSDN): 275.5 - 50 = **$225.5/月**
-   月額 (VS Enterprise with MSDN) =&gt; 275.5 – 150 = **$125.5/月**

VM ごとに毎月平均 15 USD のストレージ (非プレミアム) を追加します。

### <a name="can-more-than-one-developer-develop-concurrently-on-the-same-vm"></a>複数の開発者が同じ VM 上で同時に開発できますか。

これはサポートされていません。 ただし、同じ VM の 1 つ以上の開発者アカウントをプロビジョニングできますが、同時に開発することはできません。 詳細については、[開発マシンで新しい開発者を有効化する](enable-development-machine.md) を参照してください。

Microsoft パートナーが 1 つ以上の顧客のコードを作成する場合は、顧客ごとに少なくとも 1 つの開発 VM を持つことをお勧めします。 顧客プロジェクトに従事している追加の開発者ごとに、1 つの追加の VM が必要です。 開発 VM は、ソース コードがバージョン コントロール (Visual Studio Team Services) にチェックインされ、テスト データベースのバックアップを保持している限り、使い捨て資産と考えることができます。 

## <a name="customer-implementation-lcs-projects"></a>顧客実装 LCS プロジェクト
### <a name="how-many-sandbox-environments-do-i-need-within-an-lcs-customer-implementation-project"></a>LCS 顧客実装プロジェクト内でいくつのサンド ボックス環境が必要ですか。

顧客サブスクリプションは、既定では、次の 3 つの環境があります: 開発またはビルド環境、2 層サンド ボックス環境、および本番環境です。 アプリケーションが生産の稼働に移行する前に、構成と UAT 環境として 2 層のサンド ボックス環境を使用できます。 Go-Live にする必要のあるコードとデータをサンドボックスに構成した後 (*ゴールド構成*とも呼ばれる)、同じ環境で検証を実行することができます。 検証に合格したとき、サンド ボックス データベースをそのゴールド構成の時点まで復元します。 コードを生産に展開して、サンドボックス データベースを生産環境にコピーすることができます。 また、特にアプリケーションが稼働後に、階層 2 またはそれ以上にある複数のサンドボックス環境を持つように選択することができます。 1 つのサンド ボックスは、生産開始前の UAT 環境として使用することができ、他のサンド ボックスはコンフィギュレーション、アップグレード、またはその他のシナリオに使用されます。 階層 2 またはそれより高階層のサンドボックスをさらに購入することができます。 次のサービス要求とツールは LCS でサポートされています。これにより、実装に十分な 1 つの階層 2 サンドボックスがあるかどうかを判断するのに役立ちます。

1.  サンドボックス データベースを特定の時点に復元します。
2.  実稼動環境にサンドボックス データベースをコピーします (アプリケーションが本番稼働に公開される前にのみ許可されます)。
3.  サンドボックス環境にコンフィギュレーション データ パッケージを適用します。
4.  実稼動環境にコンフィギュレーション データ パッケージを適用します。
5. 実稼動環境からサンドボックス データベースを更新します。 実稼動環境のデータベースを階層 2 のサンドボックス環境にコピーします。 これは、アプリケーションが稼働していて、問題をデバッグしたり、今後の更新を検証したりするのが一般的です。
6.  実稼働環境に適用する前に検証用のサンドボックス環境に更新プログラム (修正プログラム、カスタマイズ) を適用します。  
