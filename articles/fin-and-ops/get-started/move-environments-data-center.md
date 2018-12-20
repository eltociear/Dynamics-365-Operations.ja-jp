---
title: "データ センター間で環境を移動する"
description: "このトピックでは、Microsoft によって管理されている Microsoft Dynamics 365 for Finance and Operations 環境を異なる Microsoft Azure データ センターに移動する方法について説明します。"
author: ClaudiaBetz-Haubold
manager: AnnBe
ms.date: 06/04/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: chaubold
ms.search.validFrom: 2018-05-30
ms.dyn365.ops.version: AX 7.0
ms.translationtype: HT
ms.sourcegitcommit: dcbe39a5d9ca4a9fc109468772b6dd89b0dd971e
ms.openlocfilehash: d4e606fb9caf37472597c0ed2fe15214d30087cb
ms.contentlocale: ja-jp
ms.lasthandoff: 08/09/2018

---

# <a name="move-environments-between-data-centers"></a>データ センター間で環境を移動する

[!include [banner](../includes/banner.md)]

場合によっては、Microsoft によって管理されている Microsoft Dynamics 365 for Finance and Operations 環境を異なる Microsoft Azure データ センターに移動する必要があります。 この移動が必要になる場合のいくつかのシナリオを次に示します。

- 使用するデータ センターは、環境が当初配置されていたときには使用できませんでした。
- プロジェクト作成者は、環境が本来配置された以前に、最適なデータ センターを決定するための十分な調査を行っていません。
- 顧客はその操作の物理的な場所を移動し、ワイド エリア ネットワーク (WAN) 接続がより短い待機時間を提供するデータ センターにより近くなります。

Microsoft により同じデータ センターですべての環境を維持するよう求められます。 環境を別のデータ センターに移行する場合、最終的にはすべての環境を同じデータ センターに展開することを計画する必要があります。

環境が展開されているデータ センターを Microsoft Dynamics Lifecycle Services (LCS) の**環境の管理**ページ上で確認できます

データ センターを変更するには、すべての環境を再配置する必要があります。 サンド ボックス環境 (サンド ボックスのスタンダード承認テスト環境、およびサンド ボックスの開発およびテスト環境) のプロセスは実稼動環境のプロセスとは異なります。

## <a name="move-sandbox-environments"></a>サンドボックス環境の移動

この移動はセルフサービスのアクションなので、パートナーや顧客は Microsoft の関与なしで既存のサンドボックス環境を移動する必要があります。 このアクションには、パートナーまたは顧客のリソースの側でわずかな作業量が必要ですが、エンド ツー エンド プロセスの完了には数日かかることがあります。 環境間でデータの移動を効率化するには、移動を開始する前に、最適な順序を決定するために計画を作成する必要があります。

### <a name="save-data"></a>データの保存

移動を開始する前に、データを保存する必要があります。

- **Microsoft SQL Server に基づくレベル 1 環境データベース:** データベースのバックアップを作成します。
- **Azure SQL データベースに基づくレベル 2 およびそれ以上の環境:** 次のオプションのいずれかを選択します。

    - **オプション 1:** [Azure SQL データベースから SQL Server 環境に Finance and Operations データベースをコピー](../../dev-itpro/database/copy-database-from-azure-sql-to-sql-server.md)に記載されている手順に従います。
    - **オプション 2:** Azure サブスクリプションを持っている場合、サブスクリプションの下に Azure SQL データベースのコピーを保存してください。
    - **オプション 3:** Azure SQL データベース環境を複数持ってる場合、1 つの環境を再配置し、古い環境をデータ センターに残してから、環境間でデータベース更新の要求をします。
    - **オプション 4:** データ パッケージとしてデータを保存し、再配置が完了した後にパッケージをインポートします。

### <a name="move-the-environments"></a>環境の移動

データ保存後、これらの手順に従ってください。

1. コードのすべてのパッケージが LCS でアセット ライブラリにアップロードされていることを確認します。
2. 各環境について、次の手順を実行します。

    1. LCS で**完全な詳細**を選択します。
    2. 環境を停止してから、環境が停止した時に、**割り当て解除**を選択します。
    3. 割り当て解除が完了した後、**削除**を選択します。
    4. この環境が削除された後、**構成**を選択し、環境を再配置します。
    5. **地理/場所**フィールドで、使用するデータ センターを選択します。
    6. 環境が再配置された後は、コード パッケージを適用します。
    7. 再配置された環境がビルド環境として使用されている場合は、[継続的ビルドとテストの自動化を使用した配置](../../dev-itpro/perf-test/continuous-build-test-automation.md)に記載されている必要なコンフィギュレーションを完了します。
    8. データを復元します。

> [!NOTE]
> - サンド ボックス環境では、Azure BLOB ストレージに格納されているファイルの移動はサポートされていません。
> - 小売顧客は、移動後に小売コンポーネントが正常に機能するため追加の手順が必要であることに注意する必要があります。 詳細については、[データ管理](../../dev-itpro/data-entities/data-entities-data-packages.md)を参照してください。

## <a name="move-production-environments"></a>実稼働環境の移動

実稼働環境を既に配置している場合は、すべてのサンドボックス環境の移動が完了した後に、実稼働環境を別のデータセンターに移動するためのサポート要求を開く必要があります。 このシナリオはまれであり、移動を完了するための自動/セルフサービス アクションはありません。 このシナリオでは、Azure BLOB ストレージに格納されているファイルも移動されます。 実稼働環境を別のデータ センターに移動するために必要な保守ウィンドウとダウンタイムの詳細については、次を参照してください。[サービスの説明](https://go.microsoft.com/fwlink/?LinkId=867755&clcid=0x409)と関連するサービス レベル契約 (SLA) のドキュメント。
