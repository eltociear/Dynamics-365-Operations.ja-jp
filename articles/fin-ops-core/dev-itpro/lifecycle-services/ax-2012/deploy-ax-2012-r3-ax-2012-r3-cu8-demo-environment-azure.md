---
title: Azure に AX 2012 R3 または AX 2012 R3 CU8 デモ環境を配置する
description: このトピックでは、Microsoft Azure に AX 2012 R3 または AX 2012 R3 CU8 のデモ環境を展開する方法について説明します。
author: kfend
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: ''
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: AX 2012
ms.custom: 15561
ms.assetid: b7f2e7b9-2627-4e8f-beab-a3cea8d79dc4
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: ''
ms.dyn365.ops.version: 2012
ms.openlocfilehash: e528c7c57d88d4455fef6a0c93299294843a9933
ms.sourcegitcommit: 759325234a763e14071348a6f5399999a92f8264
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2020
ms.locfileid: "2983611"
---
# <a name="deploy-ax-2012-r3-or-ax-2012-r3-cu8-demo-environments-on-azure"></a>Azure に AX 2012 R3 または AX 2012 R3 CU8 デモ環境を配置する

[!include [banner](../../includes/banner.md)]

<a name="prerequisites"></a>必要条件
-------------

この記事の手順を実行する前に、次の条件が満たされていることを確認します。

|                |                                                                                                                                                                 |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **カテゴリ**   | **前提条件**                                                                                                                                                |
| 必要なタスク | [Azure で AX 2012 R3 の配置を計画する](plan-2012-r3-deployment-azure.md) |

## <a name="1-log-on-to-lifecycle-services"></a>1. ライフサイクル サービスにログオンする
Microsoft Dynamics Lifecycle Services は、顧客およびパートナーが Microsoft Dynamics AX の管理に使用できるクラウドベースの共同ワークスペースです。 Azure に AX 2012 R3 を配置するには、この Web サイトを使用します。 Lifecycle Services は顧客やパートナーがサポート計画の一部として使用できます。 CustomerSource または PartnerSource の資格情報でアクセスすることができます。 [Lifecycle Services にログオン](https://lcs.dynamics.com/en/)

## <a name="2-create-a-project"></a>2. プロジェクトの作成
Lifecycle Services にログインした後、既存のプロジェクトを開くか、または新しいプロジェクトを作成します。 プロジェクトは、Lifecycle Services でのエクスペリエンスの主な開催者です。 プロジェクトに関連する手法は、既定でプロジェクトに含まれるフェーズとタスクを決定します。

## <a name="3-connect-the-project-to-your-azure-subscription"></a>3. Azure サブスクリプションにプロジェクトを接続する
Azure サブスクリプションに Lifecycle Services プロジェクトを接続します。 これにより、Lifecycle Services は AX 2012 R3 環境をサブスクリプションに展開できます。 Azure サブスクリプションにプロジェクトを接続するには、次の手順を実行します。 プロジェクトは 1 つの Azure サブスクリプションにだけ接続できることに留意してください。 複数の Azure サブスクリプションがある場合、この手順を実行する前にどのサブスクリプションを使用するかを必ず識別します。

1.  **クラウド ホスト環境**をクリックします。 **クラウド ホスト環境** ページが表示されます。
2.  **Microsoft Azure 設定**パネルが画面の横に表示されます。 表示されない場合は、**Microsoft Azure 設定**をクリックします。
3.  Azure サブスクリプション ID を入力します。 サブスクリプション ID を検索する必要がある場合は、次の手順を実行します。
    1.  ブラウザの別のインスタンスを開きます。
    2.  **Azure 管理ポータル**にログオンします。
    3.  左のナビゲーション ウィンドウで、**設定**をクリックします。 (設定リンクを表示するには、ナビゲーションペインの一番下までスクロールしなければならない場合があります。) **Settings** ページが表示されます。
    4.  サブスクリプション ID をコピーして、Lifecycle Services の **Azure サブスクリプション ID** フィールドに貼り付けます (現在別のブラウザー インスタンスに表示されています)。

4.  **次へ** をクリックします。
5.  **ダウンロード**をクリックして管理証明書をダウンロードします。 この管理証明書により、Lifecycle Services はお客様の代わりに Azure と通信できます。 既定では、管理証明書はコンピューターのダウンロード フォルダーに保存され、LifecycleServicesDeployment.cer という名前が付きます。
6.  管理証明書を Azure にアップロードします。 そのためには、次の手順を実行します。
    1.  ブラウザの別のインスタンスを開きます。 (または、手順 3 で開いた可能性のあるブラウザインスタンスに移動します。)
    2.  **Azure 管理ポータル**にログオンします。
    3.  左のナビゲーション ウィンドウで、**設定**をクリックします。 **設定** ページが表示されます。
    4.  **管理証明書**をクリックします。
    5.  ページの下部にある**アップロード**をクリックします。
    6.  **管理証明書をアップロード** ウィンドウで、手順 5 でダウンロードした管理証明書を参照します。 その後、チェック マークをクリックします。

7.  Lifecycle Services で **Microsoft Azure 設定**パネルを表示するブラウザーに戻ります。 **次へ** をクリックします。
8.  最も近い地域を選択します。 AX 2012 R3 環境は、この領域のデータ センターに配置されます。
9.  **接続** をクリックします。

これで、プロジェクトが指定された Azure サブスクリプションに接続できるようになりました。 プロジェクトを間違った Azure サブスクリプション (複数の Azure サブスクリプションがあると仮定した場合) に接続していることが分かった場合、プロジェクトを削除し、新しいプロジェクトを作成し、新しいプロジェクトを適切な Azure サブスクリプションに接続させるためのこの手順を繰り返す必要があります。

## <a name="4-deploy-an-ax-2012-r3-or-ax-2012-r3-cu8-demo-environment-on-azure"></a>4. Azure に AX 2012 R3 または AX 2012 R3 CU8 デモ環境を配置する
Azure に AX 2012 R3 または AX 2012 R3 CU8 デモ環境を配置するには、以下の手順に従ってください。

1.  **クラウド ホスト環境**ページで、追加 (+) アイコンをクリックします。
2.  **環境のトポロジの選択**パネルで、**デモ**を選択します。
3.  **AX 2012 R3 のデモンストレーション**または **AX 2012 R3 CU8 のデモンストレーション**をクリックします。
4.  **環境名**フィールドに、配置される環境の名前を入力します。
5.  **詳細設定**をクリックします。
6.  仮想マシン名をカスタマイズするには、**仮想マシン名をカスタマイズ** をクリックします。 一般的な IT 名前付けガイドラインをサポートするために、仮想マシンに名前を付ける機能がほとんどの配置トポロジの**詳細設定**に用意されています。 名前を定義することに加えて、各仮想マシン タイプに開始インデックスを選択できます。 インデックスは、配置される仮想マシン タイプのインスタンスごとに増加します。 仮想マシン名は 13 文字またはそれ以下にする必要があります。 インデックスはマシン名とハイフン (-) で区切られ、その後に最大 2 桁のインデックスが続きます。 例: ACustomVMName-99。仮想マシン インスタンスが最初の展開後に環境へ追加されると、展開サービスは中断した仮想マシン名のインクリメントを開始します。 たとえば、2 で始まるインデックスを持つ 4 つの AOS 仮想マシンを展開する場合、最後の AOS インスタンス名は AOS-6 になります。 もう 2 つ AOS インスタンスを追加する場合は、AOS-7 と AOS 8 になります。 展開内の仮想マシン タイプの 1 つがカスタマイズされている場合は、すべての仮想マシン名をカスタマイズする必要があります。 これは、仮想マシン名が誤って紛失してしまったため、長期的な展開が発生しないようにするためです。
7.  1 つの仮想マシンが Azure 上に配置されます。 この仮想マシンの既定のサイズは D3 (4 コア、14 GB メモリ) です。 サイズを変更する場合、**サイズ** リストからさまざまなサイズを選択します。
    -   仮想マシンに関するサイズおよび価格決定の詳細については、[仮想マシンの価格決定の詳細](https://azure.microsoft.com/pricing/details/virtual-machines/) を参照してください。
    -   仮想マシンにインストールされているソフトウェアの詳細については、 [Azure で AX 2012 R3 の配置を計画する](plan-2012-r3-deployment-azure.md) を参照してください。

8.  ライセンスの条項を確認するには、**ソフトウェア ライセンス条項**をクリックします。 次に、チェック ボックスを選択して、条件に同意することを示します。
9.  **次へ** をクリックします。
10. **展開**をクリックして、環境を展開する準備が整ったことを確認します。 配置には数時間かかる場合があります。 配置が完了すると、**クラウド ホスト環境** ページの **配置ステータス** 列に **配置済み** が表示されます。 (これを表示するにはブラウザーを更新する必要があります。) 配置が失敗すると、すぐエラー メッセージが表示される場合があります。 配置プロセスでエラーが後に発生する場合に、エラーの詳細がページの右側の**詳細**ペインに表示されます。

## <a name="5-open-the-ax-2012-r3-client"></a>5. AX 2012 R3 クライアントを開きます。
AX 2012 R3 クライアントがインストールされている仮想マシンに接続するには、以下の手順を完了してください。

1.  **クラウド ホスト環境**ページで、設置したデモ環境を選択します。
2.  環境に関する詳細を表示するためにページの右側にスクロールします。
3.  **DEMO-&lt;GUID&gt;** リンクをクリックします。
4.  ページの下部にある**開く**をクリックして、.rdp ファイルを開きます。
5.  資格情報を求めるメッセージが表示されたら、 この環境の **クラウドによってホストされた環境** ページにある、適切なユーザー名とパスワードを入力します。
6.  仮想マシンのデスクトップが表示されたとき、Microsoft Dynamics AX アイコンをクリックして、AX 2012 R3 クライアントを開きます。




