---
title: 受け入れテスト ライブラリ コード生成ウィザード
description: ここでは、受け入れテストライブラリのコード生成ウィザードに関する情報を提供します。
author: MichaelFruergaardPontoppidan
manager: AnnBe
ms.date: 03/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: MichaelFruergaardPontoppidan
ms.search.validFrom: 2018-XX-XX
ms.dyn365.ops.version: App Update 10.0.2
ms.openlocfilehash: 5002e232ea6ecf797f4fbd5ef20224b810071e16
ms.sourcegitcommit: 9f90b194c0fc751d866d3d24d57ecf1b3c5053a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2020
ms.locfileid: "3033038"
---
# <a name="acceptance-test-library-code-generation-wizard"></a>受け入れテスト ライブラリ コード生成ウィザード

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

引受テスト ライブラリ (ATL) コード ジェネレーターはすばやくを生成し、新しいATLエンティティ、クエリ、およびテーブルとデータ エンティティに基づく仕様を更新します。

## <a name="create-the-atlentity-class-by-using-the-wizard"></a>ウィザードを使用して、AtlEntityクラスを作成します。

`AtlEntity` クラスを作成するには、以下の手順に従って **コード生成** ウィザードを使用します。

1. Microsoft Visual Studioを起動し、デザイナー ウィンドウで、テーブルを開きます。
2. テーブルの名前を右クリックし、 **アドイン** メニューで、 **ATLエンティティの生成** を選択します。
3. `AtlEntity` クラスに含めるフィールドを選択し、 **追加** を選択します。
4. 必要に応じてエンティティとフィールド名称を変更します。
5. **生成** を選択してクラスを作成します。

### <a name="additional-optional-steps"></a>追加オプション

`AtlEntity` クラスを作成する際に、以下の作業を同時に実行するができます。

- シナリオに必要なアクションを追加します。
- `default` メソッドを `AtlData` クラスに追加する。
- `setMainRecordField` メソッドを上書きし、テーブル上の `modifiedField(_fieldId)` メソッドを呼び出す。

    ```xpp
    protected void setMainRecordField(FieldId _fieldId, anytype _value)
    {
        super(_fieldId, _value);
        common.modifiedField(_fieldId);
    }
    ```

## <a name="create-the-atlquery-class-by-using-the-wizard"></a>ウィザードを使用して、AtlQueryクラスを作成します。

`AtlQuery` クラスを作成するには、以下の手順に従って **コード生成** ウィザードを使用します。

1. Microsoft Visual Studioを起動し、デザイナー ウィンドウで、テーブルを開きます。
2. テーブルの名前を右クリックし、 **アドイン** メニューで、 **ATLエンティティの生成** を選択します。
3. `AtlQuery` クラスに含めるフィールドと関連付けを選択し、 **追加** を選択します。
4. 必要に応じてクエリ、フィールド名称、関連付けの名称を変更します。
5. **生成** を選択してクラスを作成します。

### <a name="additional-optional-steps"></a>追加オプション

`AtlQuery` クラスを作成する際に、 `query` のメソッドを `AtlData` のクラスに追加することが可能です。 これによりこのトピックの最初に作成した `AtlQuery` クラスのインスタンスを返します。

## <a name="create-the-atlspec-class-by-using-the-wizard"></a>ウィザードを使用して、AtlSpecクラスを作成します。

`AtlSpec` クラスを作成するには、以下の手順に従って **コード生成** ウィザードを使用します。

1. Microsoft Visual Studioを起動し、デザイナー ウィンドウで、テーブルを開きます。
2. テーブルの名前を右クリックし、 **アドイン** メニューで、 **ATL Specificationの生成** を選択します。
3. `AtlSpec` クラスに含めるフィールドを選択し、 **追加** を選択します。
4. 必要に応じてSpecificationとフィールド名称を変更します。
5. **生成** を選択してクラスを作成します。

### <a name="additional-optional-steps"></a>追加オプション

`spec` のメソッドをデータクラスに追加することにより、このトピックの最初に作成した `AtlSpec` クラスのインスタンスを返します。
