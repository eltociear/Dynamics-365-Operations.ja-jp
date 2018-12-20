---
title: "X++ の SQL 接続エラー例外"
description: "このトピックでは、X++ での SQL 接続エラー例外のタイプについて説明します。"
author: yiqju
manager: AnnBe
ms.date: 09/27/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 150373
ms.assetid: f06da12e-911c-442c-97fd-280cbc970061
ms.search.region: Global
ms.author: robinr
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Plaform update 21
ms.translationtype: HT
ms.sourcegitcommit: d456b70ff81f28ce6dd7758bf4ed758550e4ba13
ms.openlocfilehash: 5f387c7ae6225951529cdae51be614f467c764ab
ms.contentlocale: ja-jp
ms.lasthandoff: 10/08/2018

---

# <a name="sql-connection-error-x-exception"></a>X++ の SQL 接続エラー例外

[!include [banner](../includes/banner.md)]

このトピックでは、X++ での SQL 接続エラー例外のタイプについて説明します。

## <a name="transientsqlconnectionerror-x-exception"></a>TransientSqlConnectionError X++ 例外
X++ SQL クエリの実行中、サーバー側で一時的な SQL 接続エラーが発生すると、TransientSqlConnectionError X++ 例外が発生します。 アプリケーションの要件に応じて、アプリケーションは例外をキャッチして処理する必要があります。

この例外は通常、大規模なトランザクションの際に、またはデータベースに大きな処理負荷がかかっている場合に発生します。

TransientSqlConnectionError 例外は、トランザクション内ではキャッチできません。 この例外が検出された X++ トランザクションは、例外が発生する前にキャンセルされます (**ttsAbort** を呼び出す)。 つまり、汎用 X++ エラー例外ではなく一時的な SQL 接続エラーを特定するためにキャッチ ブロックを使用した後、最上位のトランザクションを再試行するか、新しいセッションでアプリケーション コード ロジックを再試行する必要があります。 この例外は、一時的なサーバーの障害時にアプリケーションの設計を許可します。

アプリケーション トランザクションの処理に時間がかかる場合、複数の増分遅延を使用して TransientSqlConnectionError 例外をキャッチできます。 新しいセッションでアプリケーション コードを再実行すると、例外をキャッチした後に成功する可能性が最も高くなります。


### <a name="example"></a>例
```
public static void LargeTransactionWrapper()
{
    try
    {
        LargeTransaction();
    }
    catch (Exception::TransientSqlConnectionError)
    {
        info("Caught transient SQL connection error, ttslevel=" + int2Str(appl.ttsLevel()));
        // At this point, transaction is canceled
        // Code that indicates retry is possible
    }
    finally
    {
        // Do clean up
    }
}
```
