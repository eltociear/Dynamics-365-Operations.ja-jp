---
title: "データ統合方法 (インポート/エクスポート) の選択"
description: "このトピックは、設計者と開発者が Microsoft Dynamics 365 for Finance and Operations の統合シナリオを実装する際に意思決定を適切に行えるようにすることを目的としています。"
author: Sunil-Garg
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 821d8927211d7ac3e479848c7e7bef9f650d4340
ms.openlocfilehash: f9421b7ecb06b63281274ac30acf30cd1369f300
ms.contentlocale: ja-jp
ms.lasthandoff: 08/13/2018

---

# <a name="choose-a-data-integration-importexport-strategy"></a>データ統合方法 (インポート/エクスポート) の選択

[!include [banner](../includes/banner.md)]

このトピックは、設計者と開発者が Microsoft Dynamics 365 for Finance and Operations の統合シナリオを実装する際に意思決定を適切に行えるようにすることを目的としています。

このトピックでは、統合パターン、統合シナリオ、統合ソリューション、Finance and Operations のベストプラクティスについて説明します。 ただし、すべての統合パターンを使用または設定する方法に関する技術詳細は含まれません。 また、サンプル統合コードも含まれていません。

次のテーブルに、Finance and Operations で使用可能な受信統合パターンを示します。

| パターン                       | ドキュメント |
|-------------------------------|---------------|
| OData                         | [OData](odata.md) |
| バッチ データ API                | [定期統合](recurring-integrations.md)<br>[データ パッケージ API](data-management-api.md) |
| 顧客サービス                | [顧客サービス](custom-services.md) |
| 外部 Web サービスの消費 | [外部 Web サービスの使用](consume-external-web-service.md) |
| Excel 統合             | [Office 統合](../office-integration/office-integration.md) |

> [!NOTE]
> オンプレミス配置の場合、唯一サポートされる API は[データ パッケージ API](data-management-api.md) です。 これは、7.2、platform update 12 ビルド 7.0.4709.41184 で現在利用可能です。

## <a name="synchronous-vs-asynchronous-integration-patterns"></a>同期および非同期の統合パターン

処理は、同期または非同期にすることができます。 多くの場合、使用すべき処理タイプは、選択した統合パターンによって決まります。

*同期*パターンは、ブロック要求と応答パターンであり、呼び出し先が実行を終了して応答を返すまで呼び出し元がブロックされます。 *非同期*パターンは非ブロック パターンで、呼び出し元が要求を送信して応答を待たずに続行します。

次のテーブルに、使用可能な受信統合パターンを示します。

| パターン        | タイミング       | バッチ |
|----------------|--------------|-------|
| OData          | 同期  | 無    |
| バッチ データ API | 非同期 | 有   |

同期と非同期パターンを比較する前に、Finance and Operations が提供するすべての REST および SOAP 統合アプリケーション プログラミング インターフェイス (API) を同期または非同期で呼び出すことができるので注意が必要です。

次の例は、このポイントを示しています。 オープン データ プロトコル (OData) が統合のために使用される場合、呼び出し元がブロックされるとは限りません。 通話の仕方によっては、呼び出し元がブロックされない場合があります。

| パターン        | 同期式のプログラミング パラダイム    | 非同期式のプログラミング パラダイム |
|----------------|-------------------------------------|-----------------------------------|
| OData          | DbResourceContextaveChanges         | DbResourceContextaveChangesAsync |
| 顧客サービス | httpRequestetResponse               | httpRequesteginGetResponse |
| SOAP           | UserSessionServiceetUserSessionInfo | UserSessionServiceetUserSessionInfoAsync |
| バッチ データ API | ImportFromPackage                   | [BeginInvoke](/dotnet/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously) |

これらの API が呼び出されると、すぐにビジネス ロジックが Finance and Operations で実行されるため、OData とカスタム サービスの両方は同期統合パターンです。 次にいくつか例を挙げます。

- OData を使用して製品レコードを挿入すると、レコードはすぐに OData 呼び出しの一部として挿入されます。
- 手持ちの在庫を検索するためにカスタム サービスを使用すると、ビジネス ロジックが JSON/SOAP 呼び出しの一部としてすぐに実行され、在庫総額がすぐに返されます。

これらの API が呼び出されると、バッチ モードでデータがインポートまたはエクスポートされるため、バッチ データ API は非同期統合パターンと見なされます。 たとえば、ImportFromPackage API への呼び出しは、同期することができます。 ただし、API は、特定のデータ パッケージのみをインポートするバッチ ジョブをスケジュールします。 スケジューリング ジョブはすぐに戻され、後でバッチ ジョブで処理されます。 したがって、バッチ データ API は非同期として分類されます。

バッチ データ API は大量のデータのインポートとエクスポートを処理するために設計されています。 大量である条件を正確に定義することは困難です。 回答は、エンティティによって、およびインポートまたはエクスポート中に実行されるビジネス ロジックの量によって異なります。 ただし、経験則を次に示します: 容量が数十万レコード以上の場合は、統合のバッチ データ API を使用する必要があります。

一般に、統合パターンを選択しようとしている場合、次の質問を検討することをお勧めします。

- 統合をリアルタイムで行う必要がある業務要件がありますか。
- ピーク時のデータ量の要件は何ですか ?
- 頻度はどのくらいですか ?

### <a name="error-handling"></a>エラー処理 

同期パターンを使用するときは、呼び出し元に成功または失敗の応答が返されます。 たとえば、OData 呼び出しが販売注文を挿入するために使用される場合、販売注文明細行に存在しない製品への無効な参照があると、呼び出し元が受信する応答には、エラー メッセージが含まれます。 呼び出し元は、応答内のエラーを処理します。

非同期パターンを使用するときは、呼び出し元には、スケジューリング呼び出しが成功したかどうかを示す応答がすぐ表示されます。 呼び出し元は、応答内のエラーを処理します。 スケジューリングが完了したら、データのインポートまたはエクスポートのステータスは、呼び出し元にプッシュされません。 呼び出し元は、対応するインポートまたはエクスポート処理の結果をポーリングし、それに応じてエラーを処理する必要があります。

## <a name="typical-scenarios-and-patterns-that-use-odata-integrations"></a>OData 統合を使用する一般的なシナリオとパターン

OData 統合を使用する典型的なシナリオを次に示します。

### <a name="create-and-update-product-information"></a>製品情報の作成および更新

あるメーカーでは、Finance and Operations を実行しますが、その製品は、オンプレミスでホストされているサード パーティ製アプリケーションを使用して定義および構成されます。 この製造元は、生産情報をオンプレミス アプリケーションから Finance and Operations に移行する必要があります。 製品が定義されるとき、またはオンプレミス アプリケーションで変更されるとき、ユーザーは、同じ変更を Finance and Operations でリアルタイムに確認できます。

| 意思決定                    | 情報              |
|-----------------------------|--------------------------|
| リアルタイムな日付が必要ですか。 | 有                      |
| ピーク データ量            | 時間当たり 1,000 レコード\* |
| 頻度                   | アドホック                   |

\* 場合によっては、新しいまたは変更された生産コンフィギュレーションが短時間に多く発生します。

#### <a name="recommended-solution"></a>推奨される解決策

このシナリオは、OData サービス エンドポイントを使用して、Finance and Operations で製品情報を作成および更新することによって最適に実装されます。

Finance and Operations:

- 統合に必要なすべてのエンティティを決定します。
- OData サービス エンドポイントが同じエンティティのセットに対して使用可能であることを確認します。

サード パーティ製アプリケーション:

- 製品情報がサード パーティ製アプリケーションで作成または変更されるときは、同じ変更を加えるために Finance and Operations への OData 呼び出しが行われます。

### <a name="read-the-status-of-customer-orders"></a>客注文のステータスを読み取る

会社は、Finance and Operations を実行しますが、顧客が注文の状況を確認できる自己ホストの顧客ポータルを持っています。 注文ステータス情報は、Finance and Operations で管理されます。

| 意思決定                    | 情報            |
|-----------------------------|------------------------|
| リアルタイムな日付が必要ですか。 | 有                    |
| ピーク データ量            | 時間当たり 5,000 レコード |
| 頻度                   | アドホック                 |

#### <a name="recommended-solution"></a>推奨される解決策

このシナリオは、OData サービス エンドポイントを使用して、Finance and Operations で注文のステータスを読み取ることによって最適に実装されます。

Finance and Operations:

- 注文のステータス情報を読むために必要なエンティティを決定します。
- OData サービス エンドポイントがエンティティに対して使用可能であることを確認します。

顧客のポータル サイトで、次の操作を行います。

- 顧客は注文のステータスをチェックするとき、対応する注文を読み取ってそのステータスを取得するために、Finance and Operations にリアルタイムの OData 呼び出しを行います。

### <a name="approve-boms"></a>BOM の承認

会社は、Finance and Operations を実行しますが、オンプレミスでホストされている製品ライフサイクル管理 (PLM) システムを使用しています。 PLM システムには、承認のために Finance and Operations に完成した部品表 (BOM) 情報を送信するワークフローがあります。

| 意思決定                    | 情報            |
|-----------------------------|------------------------|
| リアルタイムな日付が必要ですか。 | 有                    |
| ピーク データ量            | 時間当たり 1,000 レコード |
| 頻度                   | アドホック                 |

#### <a name="recommended-solution"></a>推奨される解決策

このシナリオは、OData アクションを使用して実装できます。

Finance and Operations:

- 統合に必要なエンティティを決定する
- OData サービス エンドポイントがエンティティに対して使用可能であることを確認します。
- エンティティで、必要なビジネス ロジックを実行するアクションを作成します。

PLM ソリューション:

- PLM システムで、BOM を承認する OData アクションを呼び出します。

> [!NOTE]
> このタイプの OData アクションは **BOMBillOfMaterialsHeaderEntity::approve** で見つけることができます。

## <a name="typical-scenarios-and-patterns-that-use-a-custom-service"></a>カスタム サービスを使用する一般的なシナリオとパターン

カスタム サービスを使用する典型的なシナリオを次に示します。

### <a name="look-up-on-hand-inventory"></a>手持在庫の検索

エネルギー会社にはヒーターのインストール ジョブをスケジュールするフィールド作業者がいます。 この会社はバック オフィスとサード パーティのサービスとしてのソフトウェア (SaaS) のために Finance and Operations を使用して予定をスケジューリングします。 現場作業員が予定をスケジュールするときは、ジョブに使用できるインストール パーツがあることを確認するために、引当可能在庫数を検索する必要があります。

| 意思決定                    | 情報            |
|-----------------------------|------------------------|
| リアルタイムな日付が必要ですか。 | 有                    |
| ピーク データ量            | 時間当たり 1,000 レコード |
| 頻度                   | アドホック                 |

#### <a name="recommended-solution"></a>推奨される解決策

このシナリオは、カスタム サービスを使用して実装できます。

Finance and Operations:

- 特定のアイテムの現物手持在庫を計算するカスタム サービスを作成します。

スケジューリング アプリケーション:

- 選択した品目の在庫情報を取得するために、SOAP または REST を通じてカスタム サービス エンドポイントへのリアルタイムな呼び出しを行います。

> [!NOTE]
> このタイプのカスタム サービスの例は、Retail Real Time Services が実装された **RetailTransactionServiceInventory::inventoryLookup** で見つけることができます。

また、inventorySiteOnHand エンティティを使用して同じ結果を得ることができます。 場合によっては、複数のメソッドを使用して、Finance and Operations で同じデータとビジネス ロジックを公開できます。すべてのメソッドが同じように有効になり、効果を持ちます。 この場合、特定のシナリオを最適に機能して、開発者が最も使いやすいメソッドを選択します。

## <a name="typical-scenarios-and-patterns-that-use-batch-data-integrations"></a>バッチ データ統合を使用する一般的なシナリオとパターン

バッチ データ API を使用する典型的なシナリオを次に示します。

### <a name="import-large-volumes-of-sales-orders"></a>大量の販売注文のインポート

会社は、オンプレミスを実行するフロント エンド システムから大量の販売注文を受信します。 これらの注文は、定期的に処理、管理するために Finance and Operations に送信する必要があります。

| 意思決定                    | 情報                 |
|-----------------------------|-----------------------------|
| リアルタイムな日付が必要ですか。 | 無                          |
| ピーク データ量            | 時間当たり 200,000 レコード    |
| 頻度                   | 5 分間隔で 1 回 |

#### <a name="recommended-solution"></a>推奨される解決策

このシナリオは、バッチ データ API を使用すると最もよく実装されます。

Finance and Operations:

- 統合に必要なすべてのエンティティを決定します。
- エンティティに対してデータ管理が有効であることを確認します。

オンプレミスシステム:

- Finance and Operations にファイルをインポートするには、REST バッチ データ API を使用します。

### <a name="export-large-volumes-of-purchase-orders"></a>大量の発注書をエクスポート

会社は、Finance and Operations で大量の発注書を生成し、オンプレミス在庫管理システムを使用して製品を入庫します。 発注書は、Finance and Operations からオンプレミス インベントリ システムに移動する必要があります。

| 意思決定                    | 情報               |
|-----------------------------|---------------------------|
| リアルタイムな日付が必要ですか。 | 無                        |
| ピーク データ量            | 時間当たり 300,000 レコード  |
| 頻度                   | 1 時間あたり 1 回         |

#### <a name="recommended-solution"></a>推奨される解決策

このシナリオは、バッチ データ API を使用すると最もよく実装されます。

Finance and Operations:

- 統合に必要なすべてのエンティティを決定します。
- エンティティに対してデータ管理が有効であることを確認します。
- 差分プッシュする必要がある場合は、エンティティの変更履歴を有効にできるかを確認します。

オンプレミス在庫システム:

- REST バッチ データ API を使用して、Finance and Operations からファイルをエクスポートし、在庫システムにインポートします。

## <a name="typical-scenarios-and-patterns-that-call-external-web-services"></a>外部の Web サービスを呼び出す一般的なシナリオとパターン

通常、Finance and Operations はオンプレミスまたは別の SaaS プロバイダーによってホストされている外部 Web サービスを呼び出します。 この場合、Finance and Operations は統合クライアントとして機能します。 Finance and Operation の統合クライアントを作成するときは、他のアプリケーションの統合クライアントを作成するときと同じベスト プラクティスおよびガイドラインのセットに従ってください。 単純な例として、[外部 Web サービスの使用](consume-external-web-service.md) を参照してください。

> [!IMPORTANT]
> セキュリティ要件のため、Finance and Operations の生産とサンドボックス環境では、トランスポート層セキュリティ (TLS) 1.2 以降を使用するセキュリティ保護された通信のみがサポートされます。 つまり、Finance and Operations が呼び出すターゲットの Web サービス エンドポイントは、TLS 1.2 以降をサポートする必要があります。 ターゲット サービス エンドポイントがこの要件を満たしていない場合、Finance and Operations からの呼び出しは失敗します。 例外エラー メッセージは、次のメッセージのようになります。
>
> *「転送接続からデータを読み取ることができません: 既存の接続がリモート ホストによって強制的に切断されました。」*
>
> TLS 1.2 またはそれ以降のバージョンを使用することが原因で対象サービスを変更できない場合は、次の図に示すように、ブローカー サービスを導入して 2 ホップ コールを行うことでこの問題を回避できます。
>
> ![TLS の要件](./media/integration-tls.png)
