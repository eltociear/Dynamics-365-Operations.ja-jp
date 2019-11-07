---
title: 自分のデータベースの持ち込み (BYOD)
description: このトピックでは、エンティティを 独自の Azure SQL データベースにエクスポートする方法について説明します。
author: Sunil-Garg
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: bf8fc33463c9219b6faac3e120db344a2fb5882c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183400"
---
# <a name="bring-your-own-database-byod"></a>自分のデータベースの持ち込み (BYOD)

[!include [banner](../includes/banner.md)]

このトピックでは、管理者がアプリケーションからのデータ エンティティを自分の Microsoft Azure SQL データベースにエクスポートする方法について説明します。 この機能は、*自分のデータベースの持ち込み* (BYOD) とも呼ばれます。 BYOD 機能は、Microsoft Dynamics AX でプラットフォーム更新プログラム 2 (2016 年 8 月) によってリリースされました。 マイナーな改良およびバグ修正は、後続のプラットフォーム更新プログラムに含まれています。

BYOD 機能により、管理者は、独自のデータベースを構成し、アプリケーションで使用できる 1 つまたは複数のデータ エンティティをデータベースにエクスポートできます。 (現時点では、1,700 以上のデータ エンティティが使用可能です。) 具体的には、この機能により次のタスクを実行できます。

- エンティティ データをエクスポートできる 1 つ以上の SQL データベースを定義します。
- すべてのレコード (*完全にプッシュ*) または変更または削除されたレコードのみ (*差分プッシュ*) を、エキスポートします。
- 定期的なエクスポートを有効にするには、バッチ フレームワークの豊富なスケジューリング機能を使用します。
- トランザクション SQL (T-SQL) を使用してエンティティ データベースにアクセスし、さらにテーブルを追加してデータベースを拡張します。

## <a name="entity-store-or-byod"></a>エンティティ格納または BYOD か

[Microsoft Power BI 統合についてのブログ投稿](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/)のシリーズに従った場合、エンティティ格納に精通できます。 エンティティ格納は運用データ ウェアハウスです。 エンティティ格納では、Power BI の実稼働レポートの組み込み統合を提供します。 既製のレポートと分析ワークスペースでエンティティ格納を使用します。 アプリケーションの環境のデータを使用して Power BI レポートを作成する場合は、エンティティ格納を使用する必要があります。

ただし、次のシナリオでは BYOD 機能をお勧めします。

- データを独自のデータ ウェアハウスにエクスポートする必要があります。
- Power BI 以外の分析ツールを使用し、これらのツールはデータに対して T-SQL アクセスを必要とします。
- 他のシステムとのバッチ統合を実行する必要があります。

> [!NOTE]
> アプリケーションは、生産データベースへの T-SQL 接続を許可しません。 Finance and Operations の以前のバージョンをアップグレードする場合、データベースへの直接的な T-SQL アクセスを必要とする統合ソリューションがある場合は、BYOD は推奨するアップグレード パスになります。

エンティティ格納または BYOD のいずれかを使用できます。 使用可能な既定の業務レポートは、埋め込み Power BI とエンティティ格納を利用します。 最初の選択として、既定の業務レポートを使用することをお勧めします。 また、要件に合わせて、既成のオペレーション レポートを拡張することができます。 BYOD を必要に応じて利用する補足的なオプションと見なす必要があります。

## <a name="creating-a-sql-database"></a>SQL データベースを作成しています

エンティティのエクスポート オプションをコンフィギュレーションして BYOD 機能を使用する前に、Azure ポータルを使用して SQL データベースを作成する必要があります。

1 ボックス開発環境では、ローカルの Microsoft SQL Server データベースでデータベースを作成できます。 ただし、このデータベースは、開発およびテスト目的でのみ使用される必要があります。 実稼働環境については、Azure SQL データベースを作成する必要があります。

また、データベースにサインインするには、SQL ユーザー アカウントを作成する必要があります。 サーバー名、データベース名、および SQL ユーザー ID とパスワードを記述します。 この情報は、次のセクションで、エンティティのエクスポート オプションをコンフィギュレーションするときに使用します。

ビジネス インテリジェンス (BI) ツールとの統合に BYOD 機能を使用している場合、クラスター化された縦棒ストア インデックス (CCI) の使用を検討する必要があります。 CCI は、分析およびレポートのワークロードで一般的な読取りクエリのパフォーマンスを向上させるメモリ内インデックスです。

## <a name="configuring-the-entity-export-option"></a>エンティティのエクスポート オプションのコンフィギュレーション

1. クライアントを起動し、**データ管理**ワークスペースで、**データベースへのエンティティ エクスポートの構成**タイルを選択します。
2. いくつかのデータベースを構成した場合、一覧が表示されます。 それ以外の場合、新しいデータベースをコンフィギュレーションする必要があります。 この場合、**新規**を選択して、新しいデータベースに一意の名前と説明を入力します。 複数のデータベースにエンティティをエクスポートできることに注意してください。
3. 次の形式で、接続文字列を入力します。

    データ ソース =&lt; 論理サーバー名 &gt;、1433。最初のカタログ =&lt; DB名 &gt;。統合セキュリティ = False。ユーザー ID =&lt; SQL ユーザー ID &gt; 。パスワード =&lt; パスワード &gt;

    この接続文字列では、論理サーバー名を **nnnn.database.windows.net** のようにする必要があります。 Azure ポータル内の論理サーバー名を検索できる必要があります。 次の図は、接続文字列の例を示します。

    ![新しいレコード ページの接続文字列](media/NewRecord.png)

4. **検証** を選択し、接続が正常に行われたことを確認します。

    - **クラスター化された縦棒ストア インデックスを作成**オプションは、コピーされるエンティティの CCI を定義することで選択したクエリの出力先データベースを最適化します。 ただし、CCI は現在 SQL プレミアム データベースでのみサポートされています。 したがって、このオプションを有効にするには、SQL プレミアム データベースを作成する必要があります。
    - **ターゲット データベースでトリガーを有効にする** オプションは、ターゲット データベースで SQL トリガーを有効にするためにエクスポート ジョブを設定します。 このオプションを使用すると、レコードを挿入した後に開始する必要がある操作を調整するために、ダウンストリーム プロセスをトリガーにフックできます。 1 つのトリガーは一括挿入の操作ごとにサポートされています。 一括挿入のサイズは、データ管理フレームワークの **最大挿入コミット サイズ** パラメーターによって決まります。

BYOD からデータを読み取るレポート システムのシナリオでは、同期の実行中に、レポート システムが BYOD から一貫したデータを取得することを確認するという課題が常にあります。 BYOD プロセスで作成されたステージング テーブルから報告システムが直接読み取りしないようにすることにより、この結果を達成することができます。 ステージング テーブルは、データがインスタンスから同期されている間データを保持するため、常に変化します。 SQL トリガー機能を使用して、データ同期が完了した時点を判断し、下流のレポーティング システムに通知します。

検証に合格すると、次の図に示すように、エンティティのエクスポートに向けてコンフィギュレーションされたデータベースがデータベースのリストに表示されます。

![エンティティ エクスポートのデータベース](media/e3bcecdb0ff1532d890915903b378c60.png)

メニュー上で **公開** オプションを選択することにより、1 つまたは複数のエンティティを新しいデータベースに公開することができるようになりました。

### <a name="publishing-the-entity-schema-to-the-database"></a>エンティティ スキーマをデータベースに公開

**発行** ページは、いくつかのシナリオを有効にします。

- データベースに新しいエンティティを公開します。
- 以前に公開されたエンティティをデータベースから削除します。 (たとえば、スキーマを再作成することができます。)
- 公開されたエンティティをエンティティ スキーマと比較します。 (たとえば、新しいフィールドを後で追加する場合、フィールドをデータベース スキーマと比較できます。)
- データの差分更新を可能にする変更追跡機能をコンフィギュレーションします。

次のセクションでは、各オプションについて説明します。

#### <a name="publish"></a>パブリッシュ

**発行** オプションは、ターゲット データベースにエンティティ データベース スキーマを定義します。 1 つまたは複数のエンティティを選択してから、**公開** オプションを選択すると、バッチ ジョブが開始します。 このジョブは、出力先データベースにエンティティを作成します。 データベース定義ジョブが完了すると、メッセージが表示されます。このメッセージには、右上のベル記号を使用してアクセスできます。

実際のデータの更新は、データをエクスポートするときに実行されます。 この時点では、スキーマを作成するだけです。

#### <a name="drop-entity"></a>エンティティの削除

**エンティティを削除** オプションは、出力先のデータベースからデータとエンティティ定義を削除します。

#### <a name="compare-source-names"></a>ソース名の比較

**ソース名を比較**オプションでは、出力先のエンティティ スキーマをアプリケーション内のエンティティ スキーマと比較することができます。 このオプションは、バージョン管理に使用されます。 また、出力先テーブルから不要な列を削除するためにこのオプションを使用することができます。

#### <a name="configure-change-tracking"></a>変更追跡のコンフィギュレーション

変更の追跡は、SQL Server および SQL データベースで提供される機能です。 変更追跡を使用すると、データベースでテーブルに加えられた変更 (削除を含む) を追跡できます。 変更の追跡を使用して、トランザクションとしてテーブルに加えられた変更を識別します。 ただし、アプリケーションはデータ エンティティ レベルで変更を追跡する必要があるため、この機能が動作するための SQL 変更追跡の上に追加のロジックがあります。 変更追跡を有効にする手順については、このセクションで後述します。

**発行** ページの **変更の追跡** オプションでは、基になるエンティティの変更の追跡方法を設定できます。

![基礎となるエンティティの変更追跡](media/8918ed89bcc966252727af5a1b75e0fb.png)

次のテーブルでは、使用可能な変更追跡オプションについて説明します。

| オプション               | 説明 |
|----------------------|-------------|
| プライマリ テーブルの有効化 | エンティティは複数のテーブルで構成されます。 エンティティの主テーブルに加えられたすべての変更を追跡するには、このオプションを選択します。 プライマリ テーブルに変更を加えると、対応するレコードが出力先データベースに挿入されるか、またはそのデータベース内で更新されます。 エンティティ全体からのデータは出力先テーブルに書き込まれますが、プライマリ テーブルが変更された場合にのみ、システムの挿入または更新オプションがトリガーされます。 |
| エンティティ全体の有効化 | エンティティのすべての変更を追跡するには、このオプションを選択します。 (これらの変更は、エンティティを構成するすべてのテーブルへの変更を含みます。) エンティティへの変更を加えるときに、対応する更新が宛先に対して行われます。 |
| カスタム クエリの有効化  | このオプションを使用すると、開発者は、システムが変更を評価するために実行するカスタム クエリを提供できます。 このオプションは、選択したフィールドのセットのみから変更を追跡するという複雑な要件がある場合に便利です。 エクスポートされるエンティティが入れ子になったビューの階層を使用して構築されたときも、このオプションを選択することができます。 詳細については、[カスタム クエリを使用してエンティティの変更追跡を有効にする](../data-entities/entity-change-track.md) を参照してください。 |

変更追跡を使用するには、データ管理で上に示すように**変更追跡**オプションを有効にする必要があります。 このアクションは、**データ管理 > データ エンティティ**に移動し、**データ エンティティ** リスト ページで使用できます。 データ エンティティで変更追跡を有効にするには、エンティティを選択し、上のオプションのいずれかから選択する必要があります。

出力先のデータベースに存在するエンティティを再発行する場合、システムでは、既存のデータが新しい操作が原因で削除されることを警告されます。

発行操作を確認すると、システムがスキーマをデータベースに発行し、その操作が完了すると通知を受け取ります。

**公開**ページで**公開済のみを表示**オプションを選択することにより、指定した出力先データベースに公開されたエンティティのみを表示できます。 発行機能は、データベース内のエンティティ スキーマを作成します。 データベースに移動して、対応するインデックスとともに、作成されたテーブル スキーマを表示することができます。

> [!NOTE]
> 現在、データベースに複合エンティティをエクスポートするのに BYOD を使用することはできません。 複合エンティティの各エンティティをエクスポートする必要があります。

## <a name="exporting-data-into-your-database"></a>データベースへのエクスポート データ

エンティティが宛先データベースに公開された後、**データ管理**ワークスペースのエクスポート機能を使用してデータを移動することができます。 エクスポート関数を使用すると、1 つまたは複数のエンティティが含まれるデータ移動ジョブを定義できます。

**エクスポート** ページを使用すると、データをコンマ区切り値 (CSV) ファイルなどの多くのターゲット データ書式にエクスポートすることができます。 このページは、別の宛先として SQL データベースもサポートしています。

![ページをエクスポート](media/091eb0da74bf94c620c3785bca92b41e.png)

複数のエンティティを持つデータ プロジェクトを作成することができます。 バッチ フレームワークを使用することにより、このデータ プロジェクトの実行をスケジュールすることができます。 また、**バッチ処理でのエクスポート** オプションを選択することにより、データ エクスポート ジョブを定期的に実行するようにスケジュールします。

同じジョブを使用してすべての会社からデータをエクスポートすることもできます。 プラットフォーム更新プログラム 27 以前では、[データ管理でフライトされる機能とフライトされた機能の有効化](../data-entities/data-entities-data-packages.md) で説明されているように、この機能はフライト DMFEnableAllCompanyExport を有効にすることで有効にできます。 プラットフォーム更新プログラム 27 以降では、この機能はデータ管理フレームワークのパラメーターで有効にすることができます。 この機能を有効にすると、データプロジェクトにエンティティを追加する際に新しいオプションが表示されます。 このオプションを有効にすると、すべての会社から特定のエンティティのデータをエクスポートすることができます。 

> [!NOTE]
> BYOD のために **管理 > 定期的なデータ ジョブの管理** で定期的なエクスポートを使用することはお勧めしません。 **バッチ処理でのエクスポート** オプションを使用する必要があります。

### <a name="incremental-export"></a>差分エクスポート
データ エクスポートのエンティティを追加するとき、増分エクスポート (増分プッシュとも呼ばれます) またはフル プッシュをするかを選択できます。 作業する増分プッシュについては、このトピックで前述されているように、データベースで**変更追跡**オプションを有効にし、適切な変更追跡オプションを指定する必要があります。

>[!NOTE]
> 完全なプッシュは、エンティティからすべての既存のレコードを削除し、選択したエンティティから現在のレコードのセットを挿入します。

広域増分プッシュを選択した場合、最初のプッシュは常に完全なプッシュになります。 これは、後続の変更を追跡できるようにするために、SQL でどのレコードが「追跡済み」であるかを知る必要があるためです。 新しいレコードが挿入される、またはレコードが追加または削除されるたびに、対応する変更が宛先エンティティに反映されます。

最初のプッシュは常にフルプッシュであるため、変更の追跡を有効にしていない場合、明示的なフルプッシュを行うことは推奨しません。

最初に変更トラッキングを有効にし、増分プッシュでエクスポート ジョブをスケジュールすることをお勧めします。 これにより、最初の完全プッシュと後続の差分エクスポートが処理されます。

### <a name="timeouts"></a>タイムアウト
BYOD エクスポートの既定のタイムアウトは、切り捨て操作では 10 分、実際の一括挿入操作には 1 時間に設定されています。 ボリュームが多い場合、これらのタイムアウト設定が十分でなく、更新する必要がある場合があります。 プラットフォーム更新 18 のリリース以降では、**データ管理** > **フレームワーク パラメーター** > **自分のデータベースの持ち込み** に移動することで、タイムアウト設定を更新できます。 タイムアウトは会社ごとに固有の設定となるため、会社ごとに個別に設定する必要があります。

### <a name="known-limitations"></a>既知の制限

BYOD 機能には、次の制限があります。

#### <a name="there-should-be-no-active-locks-on-your-database-during-synchronization"></a>同期中、データベースにアクティブなロックが存在してはいけません
BYOD は独自のデータベースであるため、データが同期されているときは Azure SQL データベースにアクティブなロックがないことを確認する必要があります。 同期中にデータベースにアクティブなロックがあると、書き込み速度が低下したり Azure SQL データベースへのエクスポートの完全な失敗につながる可能性もあります。

#### <a name="you-cant-export-composite-entities-into-your-own-database"></a>独自のデータベースに複合エンティティをエクスポートすることはできません。

現在、複合エンティティがサポートされていません。 複合エンティティを構成する個々 のエンティティをエクスポートする必要があります。 ただし、同じデータ プロジェクト内の両方のエンティティをエクスポートすることができます。

#### <a name="entities-that-dont-have-unique-keys-cant-be-exported-by-using-incremental-push"></a>固有キーを持たないエンティティは、増分プッシュを使用してエクスポートすることは不可能

この制限は特に、数個の既製エンティティからレコードを段階的にエクスポートする場合に直面する可能性があります。 これらのエンティティはデータをインポートできるように設計されているため、固有のキーはありません。 ただし、変更追跡を、固有のキーがあるエンティティに対してのみ有効にすることができます。 したがって、増分プッシュには制限があります。 1 つの回避策は、必要なエンティティを拡張し、固有のキーを定義することです。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="incremental-push-not-working-correctly"></a>増分プッシュが正常に機能しません

**問題**- あるエンティティに対して完全プッシュが発生すると、SELECT ステートメントにより BYOD に大量のレコードが表示される可能性があります。 ただし、増分プッシュの結果は BYOD のレコード数個だけになります。 増分プッシュによってすべてのレコードが削除され、BYOD で変更されたレコードのみが追加されます。 

**ソリューション**- このような場合、質問のエンティティの変更追跡を無効にしてから再度有効にすることをお勧めします。 SQL変更追跡テーブルの状態が、予期された状態になっていない可能性があります。 また、同じテーブル (DMF、MR、Retail) をカバーする他の増分エクスポートがないことを確認してください。

### <a name="ssis-error-code-dts_e_oledberror--an-ole-db-error-has-occurred-error-code-0x80004005"></a>SSIS Error Code DTS_E_OLEDBERROR.  OLE DB エラーが発生しました。 エラー コード: 0x80004005

**問題** - BYOD へのエクスポートが失敗し、次のような SSIS 例外が発生します。

    An OLE DB error has occurred. Error code: 0x80004005.

    An OLE DB record is available. Source: "Microsoft SQL Server Native Client 11.0"  Hresult: 0x80004005  Description: "Communication link failure".

    An OLE DB record is available. Source: "Microsoft SQL Server Native Client 11.0"  Hresult: 0x80004005  Description: "TCP Provider: An existing connection was forcibly closed by the remote host.

    Failed to open a fastload rowset for <entityStaging>. Check that the object exists in the database.

    OLE DB Destination failed the pre-execute phase and returned error code 0xC0202040.

**解決策** - AZURE SQL BYOD サーバーの接続ポリシーがプロキシに設定されている場合に、この問題が発生することがあります。 [SQL DB 接続アーキテクチャ](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-connectivity-architecture) の説明に従って、これを「リダイレクト」に変更する必要があります。
