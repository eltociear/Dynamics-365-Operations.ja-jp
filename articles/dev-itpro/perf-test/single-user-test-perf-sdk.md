<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="single-user-test-perf-sdk.md" target-language="ja-JP">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>single-user-test-perf-sdk.6f689c.c9fae9d6b7abeb5cae5ff07e808ca84d0f3325f7.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>c9fae9d6b7abeb5cae5ff07e808ca84d0f3325f7</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>6a975e23130a77aa625d4213000fc0ffbc32dadf</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/05/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\dev-itpro\perf-test\single-user-test-perf-sdk.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Single-user testing with Task recorder and the Performance SDK</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">タスクレコーダーおよびパフォーマンスSDKを使用したシングルユーザーテスト</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic explains how to do single-user testing by using Microsoft Visual Studio and the Performance SDK together with a performance test script that is generated by using Task recorder.</source><target logoport:matchpercent="87" state="translated" state-qualifier="fuzzy-match">このトピックでは、タスク レコーダーにて生成されたパフォーマンス テスト スクリプトと共に Microsoft Visual Studio とパフォーマンス SDK を使用してシングルユーザー テストを行う方法を説明します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Single-user testing with Task recorder and the Performance SDK</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">タスクレコーダーおよびパフォーマンスSDKを使用したシングルユーザーテスト</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>Use the information in this topic to do single-user testing by using Visual Studio and the Performance software development kit (SDK) together with a performance test script that is generated by using Task recorder.</source><target logoport:matchpercent="78" state="translated" state-qualifier="fuzzy-match">Visual Studio および パフォーマンス ソフトウェア デベロップメント キット (SDK) を使用し、タスク レコーダーにて生成されたパフォーマンス テスト スクリプトとともシングルユーザーテストを行うには、このトピックに記載の内容を参考にしてください。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>Visual Studio 2019 will be the last version of Visual Studio with web performance and load test features.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">Visual Studio 2019は Visual Studio の最新バージョンです。webパフォーマンスと負荷機能テストを実装しています。</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>In the future, we will be publish recommendations for alternative solutions.</source><target logoport:matchpercent="91" state="translated" state-qualifier="fuzzy-match">将来的に、推奨される代替ソリューションを公開する予定です。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>If you are using the Visual Studio and Test Controller/Test Agent for on-premises load testing, Visual Studio 2019 will be the last version.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">Visual Studio および、オンプレミスでの負荷テストに向けたテストコント ローラー/テストエージェントをご利用の場合、 Visual Studio 2019が最新のバージョンになります。</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>You can continue using it until the end of the support cycle.</source>
        <target logoport:matchpercent="91" state="translated" state-qualifier="leveraged-inherited">そのサポート サイクルが終了するまで継続して使用することができます。</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>If you are using the cloud-based load testing service, it will continue to run through March 31, 2020.</source>
        <target logoport:matchpercent="74" state="translated" state-qualifier="leveraged-inherited">クラウド ベースの負荷テストサービスをご利用の場合、同サービスは 2020 年 3 月 31 日まで継続してご利用いただけます。</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Until then, you can continue to use all of the experiences powered by this service without interruption.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">それまでの間は、同サービスの全機能を継続してご利用いただけます。</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Alternatively, you can switch to on-premises load testing.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">また、オンプレミス負荷テストに切り替えることがも可能です。</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>For more information, see <bpt id="p1">[</bpt>Cloud-based load testing service end of life<ept id="p1">](https://devblogs.microsoft.com/devops/cloud-based-load-testing-service-eol/)</ept>.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-inherited">詳細については、 <bpt id="p1">[</bpt>クラウド ベース 負荷テストサービスの終了について<ept id="p1">](https://devblogs.microsoft.com/devops/cloud-based-load-testing-service-eol/)</ept> をご参照ください。</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Prerequisites</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">必要条件</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>To complete the steps in this topic, you must have a Microsoft Dynamics 365 for Finance and Operations development environment that has platform update 21 or later.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">このトピックで扱う手順を完了するには、ププラットフォーム更新プログラム21、またはそれ以降が設定された Microsoft Dynamics 365 for Finance and Operations 開発環境を用意する必要があります。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Use Task recorder to define and record an end-to-end business scenario</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">タスクレコーダーを使用してエンドツーエンドの業務シナリオを定義し、記録します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Before you run a single-user test, you must work with your business team to define your end-to-end scenarios and then use Task recorder to create a recording of the steps in each scenario.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">シングルユーザーテストを実行する前に、業務チームと協力してエンドツーエンドのシナリオを定義した上で、タスクレコーダーを使用して各シナリオのステップを記録することを強く推奨します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>For more information about how to create a task recording, see <bpt id="p1">[</bpt>Task recorder<ept id="p1">](../user-interface/task-recorder.md)</ept>.</source><target logoport:matchpercent="71" state="translated" state-qualifier="fuzzy-match">タスク の記録方法についての詳細は、 <bpt id="p1">[</bpt>タスク レコーダー<ept id="p1">](../user-interface/task-recorder.md)</ept>を参照してください。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>The scenarios that you should test depend on your customer's business requirements.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">テストを行うべきシナリオは、顧客の業務要件によって異なります。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>In this topic, you will use the "Create and confirm a sales order" sample scenario.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">このトピックでは、「販売注文の作成および確認」を行うサンプルシナリオを使用します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>Sign in to Finance and Operations as a Sales persona.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">財務担当者として Finance and Operations にログインします。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Turn on Task recorder, and create and confirm a sales order that includes the following information:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">タスクレコーダー を有効にして、次の情報を含む販売注文の作成と確認を行います。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Customer account</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">顧客口座</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Item number</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">品目番号</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Sales quantity</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">販売数量</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Site</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">サイト</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>Warehouse</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">倉庫</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>Sales price</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">販売価格</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>When you've finished, select <bpt id="p1">**</bpt>Save as developer recording<ept id="p1">**</ept> to download the XML file.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">完了後、 <bpt id="p1">**</bpt>開発者記録として保存<ept id="p1">**</ept> を選択してXMLファイルをダウンロードします。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Configure a Finance and Operations development environment</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Finance and Operations 開発環境の設定</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>Download the <bpt id="p1">[</bpt>selenium-dotnet-strongnamed-3.13.1.zip<ept id="p1">](https://selenium-release.storage.googleapis.com/index.html?path=3.13/0)</ept> and <bpt id="p2">[</bpt>IEDriverServer<ph id="ph1">\_</ph>Win32<ph id="ph2">\_</ph>3.13.0.zip<ept id="p2">](https://selenium-release.storage.googleapis.com/index.html?path=3.13/)</ept> files.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">[</bpt>selenium-dotnet-strongnamed-3.13.1.zip<ept id="p1">](https://selenium-release.storage.googleapis.com/index.html?path=3.13/0)</ept> と <bpt id="p2">[</bpt>IEDriverServer<ph id="ph1">\_</ph>Win32<ph id="ph2">\_</ph>3.13.0.zip<ept id="p2">](https://selenium-release.storage.googleapis.com/index.html?path=3.13/)</ept> をダウンロードします。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Unblock and unzip the files.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">ファイルのブロックを解除し、解凍します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>In the <bpt id="p1">**</bpt>dist<ept id="p1">**</ept> folder, rename the .nupkg files as .zip files, and then unzip them.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">**</bpt>解凍先<ept id="p1">**</ept> のフォルダーで、. nupkgファイルを .zipファイルとして名前を変更し、解凍します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Original file name</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">元のファイル名</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>New file name</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">新しいファイル名</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>Selenium.Support.StrongNamed.3.13.1.nupkg</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Selenium.Support.StrongNamed.3.13.1.nupkg</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>Selenium.Support.StrongNamed.3.13.1.zip</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Selenium.Support.StrongNamed.3.13.1.zip</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>Selenium.WebDriver.StrongNamed.3.13.1.nupkg</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Selenium.WebDriver.StrongNamed.3.13.1.nupkg</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Selenium.WebDriver.StrongNamed.3.13.1.zip</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Selenium.WebDriver.StrongNamed.3.13.1.zip</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>Under your <bpt id="p1">**</bpt>PerfSDK<ept id="p1">**</ept> folder, create a folder that is named <bpt id="p2">**</bpt>Common<ph id="ph1">\\</ph>External<ph id="ph2">\\</ph>Selenium<ept id="p2">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">**</bpt>PerfSDK<ept id="p1">**</ept> フォルダ配下に、 <bpt id="p2">**</bpt>Common<ph id="ph1">\\</ph>External<ph id="ph2">\\</ph>Selenium<ept id="p2">**</ept>というフォルダを作成します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>New PerfSDK folder<ept id="p1">](./media/single-user-test-03.png)](./media/single-user-test-03.png)</ept></source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">[</bpt><ph id="ph1">![</ph>新規PerfSDKフォルダ<ept id="p1">](./media/single-user-test-03.png)](./media/single-user-test-03.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>Copy the following files, and save them to the folder that you created in the previous step:</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">次のファイルをコピーして、上記の手順で作成したフォルダに保存します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>IEDriverServer.exe from the unzipped IEDriverServer<ph id="ph1">\_</ph>Win32<ph id="ph2">\_</ph>3.13.0.zip file</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">IEDriverServer<ph id="ph1">\_</ph>Win32<ph id="ph2">\_</ph>3.13.0.zip ファイルを解凍後に取得できる、IEDriverServer.exe</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>WebDriver.dll and WebDriver.xml from the lib<ph id="ph1">\\</ph>net45 folder in the unzipped Selenium.WebDriver.StrongNamed.3.13.1.zip file</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Selenium.WebDriver.StrongNamed.3.13.1.zip ファイルを解凍後に生成される、lib<ph id="ph1">\\</ph>net45 フォルダ内の、WebDriver.dll と WebDriver.xml</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>WebDriver.Support.dll and WebDriver.Support.xml from the lib<ph id="ph1">\\</ph>net45 folder in the unzipped Selenium.Support.StrongNamed.3.13.1.zip file</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Selenium.Support.StrongNamed.3.13.1.zip ファイルを解凍後に生成される、lib<ph id="ph1">\\</ph>net45 フォルダ内の WebDriver.Support.dll と WebDriver.Support.xml</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>Generate a C<ph id="ph1">\#</ph> performance test from Task recorder</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">タスクレコーダーから C<ph id="ph1">\#</ph> パフォーマンステストを生成する</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>When you've finished recording the end-to-end scenario, you must generate a C<ph id="ph1">\#</ph> performance test script that is based the task recording.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">エンドツーエンドのシナリオの記録が完了後、タスクレコーディングをもとに C<ph id="ph1">\#</ph> パフォーマンス テスト スクリプトを生成する必要があります。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>In a development environment, open Microsoft Visual Studio as an admin.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">開発環境では、Microsoft Visual Studio を管理者権限で開きます。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>From your <bpt id="p1">**</bpt>PerfSDK<ept id="p1">**</ept> folder, open the <bpt id="p2">**</bpt>PerfSDKSample<ept id="p2">**</ept> solution.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">**</bpt>PerfSDK<ept id="p1">**</ept> フォルダから、 <bpt id="p2">**</bpt>PerfSDKSample<ept id="p2">**</ept> ソリューションを開きます。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>In a tier-1 sandbox or a cloud-hosted-environment, the PerfSDK folder is typically in K:<ph id="ph1">\\</ph>PerfSDK<ph id="ph2">\\</ph>PerfSDKLocalDirectory.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Tier1サンドボックス、またはクラウドホスト環境では、PerfSDKフォルダは一般的に K:<ph id="ph1">\\</ph>PerfSDK<ph id="ph2">\\</ph>PerfSDKLocalDirectory にあります。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>PerfSDK directory<ept id="p1">](./media/single-user-test-05.png)](./media/single-user-test-05.png)</ept></source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">[</bpt><ph id="ph1">![</ph>PerfSDKディレクトリ<ept id="p1">](./media/single-user-test-05.png)](./media/single-user-test-05.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Add a reference to the WebDriver.dll file in the Common<ph id="ph1">\\</ph>External<ph id="ph2">\\</ph>Selenium folder.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">Common<ph id="ph1">\\</ph>External<ph id="ph2">\\</ph>Selenium フォルダー内の WebDriver.dll への参照を追加します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>PerfSDKSample references<ept id="p1">](./media/single-user-test-06.png)](./media/single-user-test-06.png)</ept></source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">[</bpt><ph id="ph1">![</ph>PerfSDKSample 参照<ept id="p1">](./media/single-user-test-06.png)](./media/single-user-test-06.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>On the <bpt id="p1">**</bpt>Dynamics 365<ept id="p1">**</ept> menu, point to <bpt id="p2">**</bpt>Addins<ept id="p2">**</ept>, and then select <bpt id="p3">**</bpt>Create C<ph id="ph1">\#</ph> perf test from recording<ept id="p3">**</ept>.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">**</bpt>Dynamics 365<ept id="p1">**</ept> メニューにて <bpt id="p2">**</bpt>アドイン<ept id="p2">**</ept> を指定し、 <bpt id="p3">**</bpt>記録から C<ph id="ph1">\#</ph> パフォーマンステストを作成<ept id="p3">**</ept> を選択します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>In the <bpt id="p1">**</bpt>Import Task Recording<ept id="p1">**</ept> dialog box, enter the following required details:</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">**</bpt>タスクの記録をインポートする<ept id="p1">**</ept> ダイアログ ボックスで、以下の必要な詳細を入力します:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source><bpt id="p1">**</bpt>Recording path<ept id="p1">**</ept> – The file location of the developer recording of your end-to-end scenario.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">**</bpt>レコーディングパス<ept id="p1">**</ept> エンドツーエンドシナリオにおける開発者記録ファイルの場所。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source><bpt id="p1">**</bpt>Project path<ept id="p1">**</ept> – The location of the PerfSDKSample project.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match"><bpt id="p1">**</bpt>プロジェクト<ept id="p1">**</ept> のパス: PerfSDKSampleプロジェクトの場所。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>Typically, the path is <ph id="ph1">\&lt;</ph>Your<ph id="ph2">\_</ph>PerfSDK<ph id="ph3">\_</ph>Folder<ph id="ph4">\&gt;</ph><ph id="ph5">\\</ph>SampleProject<ph id="ph6">\\</ph>PerfSDKSample<ph id="ph7">\\</ph>PerfSDKSample.csproj.</source><target logoport:matchpercent="101" state="translated" state-qualifier="id-match">通常は次のパスに指定されています <ph id="ph1">\&lt;</ph>ご利用の<ph id="ph2">\_</ph>PerfSDK<ph id="ph3">\_</ph>フォルダ<ph id="ph4">\&gt;</ph><ph id="ph5">\\</ph>SampleProject<ph id="ph6">\\</ph>PerfSDKSample<ph id="ph7">\\</ph>PerfSDKSample.csproj.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source><bpt id="p1">**</bpt>PerfSDK path<ept id="p1">**</ept> – The location of PerfSDK.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>PerfSDKのパス<ept id="p1">**</ept> – PerfSDK の場所。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Typically, the path is <ph id="ph1">\&lt;</ph>ServiceVolumeDrive<ph id="ph2">\&gt;</ph><ph id="ph3">\\</ph>PerfSDK<ph id="ph4">\\</ph>PerfSDKLocalDirectory.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">通常は次のパスに指定されています <ph id="ph1">\&lt;</ph>ServiceVolumeDrive<ph id="ph2">\&gt;</ph><ph id="ph3">\\</ph>perfsdk<ph id="ph4">\\</ph>PerfSDKLocalDirectory</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source>When you've finished, select <bpt id="p1">**</bpt>Import<ept id="p1">**</ept>.</source><target logoport:matchpercent="85" state="translated" state-qualifier="fuzzy-match">完了後、 <bpt id="p1">**</bpt>インポート<ept id="p1">**</ept>を選択します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>A new C<ph id="ph1">\#</ph> class is created under the <bpt id="p1">**</bpt>Generated<ept id="p1">**</ept> folder of your PerfSDKSample project.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">PerfSDKSample プロジェクトの <bpt id="p1">**</bpt>生成された<ept id="p1">**</ept> フォルダ配下に新しいC<ph id="ph1">\#</ph> クラスが作成されます。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>New C# class in the Generated folder<ept id="p1">](./media/single-user-test-09.png)](./media/single-user-test-09.png)</ept></source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">[</bpt><ph id="ph1">![</ph>生成されたフォルダ内の新しいC#クラス<ept id="p1">](./media/single-user-test-09.png)](./media/single-user-test-09.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>Build the solution.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">ソリューションをビルドします。</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>Run single-user testing by using Test Explorer in Visual Studio</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Visual Studioの テストエクスプローラー を使用したシングル ユーザー テストの実行</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>Update the <bpt id="p1">**</bpt>CloudEnvironment.config<ept id="p1">**</ept> file of the PerfSDKSample project in the following ways, so that it reflects the configuration of your environment:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">以下に示す方法で PerfSDKSample プロジェクトの <bpt id="p1">**</bpt>CloudEnvironment.config<ept id="p1">**</ept> ファイルを更新します。これにより、ご利用の環境の設定が反映されます。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>In each <bpt id="p1">**</bpt>AuthenticatorConfiguration<ept id="p1">**</ept> element under the <bpt id="p2">**</bpt>AuthenticatorConfigurationCollection<ept id="p2">**</ept> element, replace <bpt id="p3">**</bpt>AadAuthenticator<ept id="p3">**</ept> with <bpt id="p4">**</bpt>SelfMintedTokenAuthenticator<ept id="p4">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p2">**</bpt>AuthenticatorConfigurationCollection<ept id="p2">**</ept> 要素の配下にある <bpt id="p1">**</bpt>AuthenticatorConfiguration<ept id="p1">**</ept> の各要素を <bpt id="p3">**</bpt>AadAuthenticator<ept id="p3">**</ept> を <bpt id="p4">**</bpt>selfmintedtokenauthenticator<ept id="p4">**</ept> に置き換えます。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>Comment out the <bpt id="p1">**</bpt>AzureActiveDirectoryConfiguration<ept id="p1">**</ept> and <bpt id="p2">**</bpt>KeyVaultConfigurations<ept id="p2">**</ept> elements.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">**</bpt>AzureActiveDirectoryConfiguration<ept id="p1">**</ept> 要素と <bpt id="p2">**</bpt>KeyVaultConfigurations<ept id="p2">**</ept> 要素をコメント行にします。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source><bpt id="p1">[</bpt><ph id="ph1">![</ph>Updated and commented code sample<ept id="p1">](./media/single-user-test-10.png)](./media/single-user-test-10.png)</ept></source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt"><bpt id="p1">[</bpt><ph id="ph1">![</ph>更新およびコメント化されたコードのサンプル<ept id="p1">](./media/single-user-test-10.png)](./media/single-user-test-10.png)</ept></target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>In Visual Studio, on the <bpt id="p1">**</bpt>Test<ept id="p1">**</ept> menu, point to <bpt id="p2">**</bpt>Windows<ept id="p2">**</ept>, and then select <bpt id="p3">**</bpt>Test Explorer<ept id="p3">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Visual Studioの <bpt id="p1">**</bpt>テスト<ept id="p1">**</ept> メニューにて、 <bpt id="p2">**</bpt>Windows<ept id="p2">**</ept> を指定し、 <bpt id="p3">**</bpt>テストエクスプローラー<ept id="p3">**</ept>を選択します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>Right-click your test case, and then select <bpt id="p1">**</bpt>Run selected tests<ept id="p1">**</ept>.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">実施したテストケースを右クリックし、 <bpt id="p1">**</bpt>選択したテストの実行<ept id="p1">**</ept> を選択します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>Tips and tricks</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">ヒントや秘訣</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>Use the following tips and tricks for single-user testing that uses Task recorder and the Performance SDK:</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">タスクレコーダーとパフォーマンスSDKを使用したシングルユーザーテストには、以下のヒントと秘訣を参照してください。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>Run your business end-to-end scenario first, before you capture it by using Task recorder.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">タスクレコーダーを使用して業務を取り込む前に、エンドツーエンドの業務シナリオを最初に実行します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>When you record your scenario by using Task recorder, enter values manually instead of selecting them in drop-down lists.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">タスクレコーダーを使用してシナリオを記録する場合は、ドロップダウンリストから値を選択するのではなく、手動で値を入力します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>Replay your task recording to make sure that everything works as you expect.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">記録したタスクを再生し、すべてが期待どおりに動作することを確認してください。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>Restart Visual Studio if you don't see your test case after the solution is built.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">ソリューションをビルド後にテストケースが表示されない場合は、 Visual Studio を再起動します。</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>Troubleshooting</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">トラブルシューティング</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>For information about single-user or multi-user testing that uses the Performance SDK, see <bpt id="p1">[</bpt>Troubleshooting guide<ept id="p1">](troubleshoot-perf-sdk-user-testing.md)</ept>.</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">パフォーマンス SDK を使用したシングルユーザーまたはマルチユーザー テストの詳細は <bpt id="p1">[</bpt>トラブルシューティング ガイド<ept id="p1">](troubleshoot-perf-sdk-user-testing.md)</ept> を参照してください。</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>