---
title: AX 2012 からのアップグレード - Go live (切替)
description: このトピックでは、Dynamics AX 2012 をオフにしてから、Finance and Operations でコードとデータベースのアップグレード バージョンの実行が完了するまでの最終的な切替えプロセスについて説明します。
author: jorisdg
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jorisde
ms.search.validFrom: 2018-03-31
ms.dyn365.ops.version: Platform update 12
ms.openlocfilehash: 62f37373523c89d7b337897a0c2c0466d6baa1b3
ms.sourcegitcommit: 759325234a763e14071348a6f5399999a92f8264
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2020
ms.locfileid: "2983649"
---
# <a name="upgrade-from-ax-2012---go-live-cutover"></a>AX 2012 からのアップグレード - Go live (切替)

[!include [banner](../includes/banner.md)]

[!include [upgrade banner](../includes/upgrade-banner.md)]

標準またはプレミア承認テスト環境 (サンドボックス レベル 2 またはそれ以上) でアップグレード テストを正常に完了し、正常にテスト切替を完了した後が、実稼働環境をアップグレードして稼働させる時になります。

*切替*という用語は、新しいシステムを稼働させる最後のプロセスに使用します。 この切替プロセスは、Microsoft Dynamics AX 2012 をオフにした後かつ Finance and Operations をオンにする前に発生するタスクで構成されます。 最終的な切替を計画する前に、[切替テスト](./upgrade-cutover-testing.md)で説明されているように成功した切替モックを正常に完了する必要があります。

次の図は、実稼動環境で発生するような、切替中の全体的なプロセスを示しています。

![切替プロセス](./media/cutover_1.png)

> [!NOTE]
> このトピックでは、*サンドボックス*という用語は、SQL Azure データベースに接続されている標準またはプレミア承認テスト (レベル 2 または 3)、またはより高度な環境を示します。

## <a name="overall-process"></a>全体的なプロセス

実稼動環境のアップグレード プロセスの高レベルの手順は切替モック プロセスと同じであり、詳細な指示については [AX 2012 からのアップグレード - 切替テスト (切替モック)](./upgrade-cutover-testing.md) を参照してください。


1. AX 2012 AOS インスタンスをオフにします。
2. AX 2012 データベースのコピーを作成します。 エクスポートするコピーの一部のオブジェクトを削除する必要があるため、コピーを使用することを強くお勧めします。
3. SQLPackage.exe という名前の無料の SQL Server ツールを使用して、コピーされたデータベースを bacpac ファイルにエクスポートします。 このツールでは、SQL データベースにインポートできる特別な種類のデータベース バックアップを提供します。
4. Azure ストレージに bacpac ファイルをアップロードします。
5. サンドボックス環境で bacpac ファイルを Application Object Server (AOS) コンピューターにダウンロードし、SQLPackage.exe を使用してインポートします。 SQL データベースのユーザーをリセットするには、インポートされたデータベースに対してスクリプトを実行する必要があります。
6. インポートされたデータベースに対して適切なデータ アップグレード パッケージを実行します。

## <a name="prerequisites"></a>前提条件 
実稼動環境でアップグレードを実行する前に、次の前提条件を満たす必要があります。
-   サンドボックス環境でコードのアップグレードとデータのアップグレードを完了し、機能テスト パスを正常に完了しました
-   実稼働環境を配置します。 実稼働環境の配置を要求するオプションが点灯する前に完了しておく必要があります。
    - LCS のサブスクリプション見積もりツール。 必要なスループットの詳細を提供しているため、これを使用して実稼働環境のサイズの変更を支援します。
    - LCS での手法のテスト フェーズ。 これは、プロダクション環境でテストを開始する準備ができているプロジェクトの段階にあることを確認するためです。
    - 実稼働環境を配置するために要求が Microsoft に送信された後、配置には、約 24 時間かかるので、そのために十分な時間を確保してください。
-   すべての必要な更新プログラムおよびカスタマイズ (AOT 配置可能パッケージ) を実稼動環境に適用します。 切替モックでサイン オフした後は、コードを変更しないでください。
-   アップグレードをスケジュールするには、[AX 2012 からのアップグレード- 切替テスト (切替モック)](./upgrade-cutover-testing.md) に説明されているように、LCS から「その他」のタイプのサービスリクエストを送信して、DSE チームにタイムスロットを要求します。 これは、優先タイム スロットが使用できるようにすることです。 週末の間などスロットの需要が大幅に高くなるため注意してください。できるだけ早くこれらを要求することにより優先スケジュールを達成できます。

## <a name="related-articles"></a>関連記事
- [オンボード](../../fin-ops/imp-lifecycle/onboard.md)
- [Dynamics サービス エンジニア リング チームへのサービス要求の送信](../lifecycle-services/submit-request-dynamics-service-engineering-team.md).
- [AX 2012 からのアップグレード - 切替テスト (切替モック)](./upgrade-cutover-testing.md)
