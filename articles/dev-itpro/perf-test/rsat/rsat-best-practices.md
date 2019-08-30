---
title: Regression Suite Automation Tool ベスト プラクティス
description: このトピックでは、Regression Suite Automation Tool (RSAT)/タスクレコーダーを使用して、クライアントの機能を記録する方法について説明します。
author: robadawy
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: 21631
ms.search.region: Global
ms.author: robadawy
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 853633dff059928d89632715ddbaac84c2bb1591
ms.sourcegitcommit: f79f2249d7557e578d7d3c4d6ea83682df7362d5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2019
ms.locfileid: "1874854"
---
# <a name="regression-suite-automation-tool-best-practices"></a>Regression Suite Automation Tool ベスト プラクティス

[!include [banner](../../includes/banner.md)]

このトピックでは、Regression Suite Automation Tool (RSAT)/タスクレコーダーを使用して、クライアントの機能を記録する方法について説明します。

## <a name="authoring-test-cases-using-the-task-recorder"></a>タスクレコーダーを使用したテストケースの作成

1. すべての記録が、Finance and Operations (または Retail) のメイン ダッシュボードから開始していることを確認してください。
2. 個々の記録を短くし、販売注文の作成など、１人のユーザーが実行するビジネス タスクに集中します。 これにより、テストケースの保守性と再利用性が簡略化されます。
3. Chart コントロール はサポートされていません。 チャートに関連するタスク記録アクションは、テストケースの再生中にRSATによって無視されます。
4. 記録を作成する場合は、タブが既に開かれている場合でも、必ずタブヘッダーを選択してください。 たとえば、別のタブに切り替えてから、必要なタブを再度選択して、そのタブのコントロールを使用する前にアクティブにすることができます。 これにより、テストケースの再生中に記録の信頼性を高めることができます。
5. RSATでは、タスク レコーダーで認識されないテスト ステップを再生することはできません。 たとえば、テストケースの再生中にローカル ディスクからファイルをアップロードすることはできません。
6. RSATでは、 **ページ更新** ステップを再生できません。 テストの記録中にページを更新しないでください。

## <a name="using-the-regression-suite-automation-tool"></a>Regression Suite Automation Tool を使用する 

1. ツールを初めて開いたときに、 **設定** を選択し、必要なすべての設定が揃っていることを確認します。 
2. ツールの新しいバージョンをインストールする前に、旧バージョンを終了して、アンインストールすることをお勧めします。 
3. ツールの新しいバージョンをインストールするときに、 **すべて** のテストの実行ファイルを再生成します。
 
    ![実行ファイル メニュー項目を生成する](media/generate-execution-files.png)

    パラメータ ファイルの新しい形式で使用できる新しい機能を利用する場合を除いて、 Microsoft Excel パラメータ ファイルを再生成する必要はありません。

4. 固有値を必要とするテスト パラメーター、たとえば、 **製品受領書** フォームの製品受領書番号や **仕入先請求書** フォームの請求書番号などの場合は、 **RandBetween (a, b)** Excel 関数を使用して、テスト ケースが実行されるたびに一意の番号を生成します。
5. Excel の既定値は、タスクの記録から取得されます。 保管分析コードや追跡用分析コードなどの **参照グループ** コントロールでは、たとえば、 **SiteWH** の代わりに **2** のように、値の代わりにルックアップのキーを格納します。 Excelでこれらのフィールドを実際の値で更新して、テストの堅牢性と変更に対する耐性を高めることをお勧めします。
6. RSATを実行する前に、Finance and Operations 環境の **言語** と **日付、時刻、数字の形式** の設定で同じロケールを設定することをお勧めします。 これらの値に不整合があると、検証エラーが発生する可能性があります。   

    ![ロケール、日付、時刻、数字の形式を設定する](media/locale.png)

次に、一般的な使用順序を示します。

**順序 A: 読み込み > 新規 > 編集 > 実行 > アップロード**

1. **読み込み** を選択します。
2. テスト ケースを選択します。
3. パラメーター ファイルがないテスト ケースがある場合は、 **新規** を選択して生成します。 
4. オプション: Excel ファイルを編集して、異なるパラメーターでテストを実行します。
5. **実行**を選択します。
6. オプション: 実行が正常に終了したら、 **アップロード** を選択して、生成されたすべての自動化ファイル (Excel テスト パラメーター ファイルを含む) を Azure DevOps にアップロードします。 

**順序 B: 読み込み > 編集 > 実行 > アップロード**

1. **読み込み** を選択します。 すべてのパラメーター ファイルが既に存在する場合、 **新規** を選択して再生成する必要はありません。
2. オプション: Excel ファイルを編集して、異なるパラメーターでテストを実行します。
3. **実行**を選択します。
4. オプション: 実行が正常に終了したら、 **アップロード** を選択して、生成されたすべての自動化ファイル (Excel テスト パラメーター ファイルを含む) を Azure DevOps にアップロードします。 

**順序 C: 読み込み > 新規 (すべてのテスト ケース用) > 実行 > アップロード**

この手順は、ツールの新しいバージョンをインストールした後にお勧めします。 

1. **読み込み** を選択します。 
2. テスト計画内のすべてのテスト ケースを選択し、 **新規** を選択します。
3. Excel パラメーター ファイルを編集します。
4. **実行**を選択します。
5. 正常に実行されたら、 **アップロード** を選択して、 Azure DevOps にすべての生成されたテスト コンポーネントをにアップロードします。 

## <a name="how-to-modify-a-task-recording"></a>タスクの記録を変更する方法

既存のタスク記録を変更する場合は、これらのベストプラクティスに注意してください。 

Finance and Operations Web クライアントで、タスク レコーダー ウィンドウを開き、 **記録の編集** オプションを使用して記録の編集を開始します。

![記録の編集オプション](media/edit-recording.png)
  
編集が終了したら、記録を保存またはダウンロードし、Finance and Operations クライアントで再生して、すべての手順が正常に動作することを確認します。

![記録の再生オプション](media/playback-recording.png)
 
編集した記録を再生した後、保存します。 これで、RSATで使用できるようになります。
