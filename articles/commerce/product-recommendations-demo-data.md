---
title: デモ データを使用した製品推奨事項の取得
description: このドキュメントでは、事前設定されたカスタマイズ可能なデモ データを使用して、レベル 1 シングル ボックス環境でのオムニ チャネル製品の推奨事項を活用する方法についてのガイダンスを提供します。
author: bebeale
manager: AnnBe
ms.date: 10/01/19
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 1456feb0665b6ec79a36a3704f17da80ffd759a0
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042783"
---
# <a name="get-product-recommendations-using-demo-data"></a>デモ データを使用した製品推奨事項の取得
このドキュメントでは、事前設定されたカスタマイズ可能なデモ データを使用して、レベル 1 シングル ボックス環境でのオムニ チャネル製品の推奨事項を活用する方法についてのガイダンスを提供します。

オムニ チャネルの製品推奨事項は、編集上精選された、またはプログラムで生成された製品一覧を提供します。 これらの一覧は、ビジネスのニーズに応じて、いくつかのシナリオで使用できます。 製品推奨事項一覧の詳細については、[製品推奨事項の概要](product-recommendations.md) を参照してください。

レベル 2 およびそれ以上の Dynamics 365 環境では、製品推奨事項は顧客データに基づいて自動的に計算されます。 製品推奨事項のデモ データを使用しても、環境で既にプロビジョニングされている製品推奨ソリューション、およびその使用に関連するコストが無効になることはありません。

レベル 1 環境では、製品推奨事項は、.csv ファイルに格納された静的デモ データのみに基づいています。

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a>環境内の製品推奨事項デモ データの有効化
製品推奨事項デモ日付を有効にするには、それぞれの環境に Dynamics 365 Commerce プレビュー デモ拡張機能を配置する必要があります。 これを行うと、製品推奨事項デモ データが自動的に有効になります。

## <a name="default-demo-data"></a>既定のデモ データ
各 Onebox タイプの環境には、コンマで区切られた 'reco_demo_data.csv' ファイルに格納されたプリロード済の一連の製品推奨事項のデモ データが含まれ、Commerce Scale Unit 上にあります。

データは、次の列に沿って構成されています。

| 列名         | 必須          | 説明                                                                                                                                 | 有効値                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| レコリスト            | :ヘビー_チェック_マーク: | デモ データ ポイントが生成する、特定の製品推奨事項リスト タイプ。                                                    | <ul><li>レコベストセリング</li><li>レコニュー</li><li>レコトレンディング</li><li>レコカート</li><li>レコピーポーオールソーバイ</li></ul> |
| オペレーティングユニットナンバー | :ヘビー_チェック_マーク: | 製品推奨事項が提示される特定の作業単位番号。                                        |                                                                              |
| カテゴリ            |                    |    特定のリストが返されるカテゴリ。 カテゴリが指定されていない場合、リストはナビゲーション階層の上部にのみ表示されます。    |                                                                              |
| SeedItemId          |                    |    シードを必要とするリスト (RecoPeopleAlsoBuy および RecoCart) については、それらのリストの製品には追加の製品が表示されます。            |                                                                              |
| ItemIds             | :ヘビー_チェック_マーク: | 「;」 で区切られ、結果として返される 1 つ以上の製品。                                                                  |                                                                              |

## <a name="customize-demo-data"></a>デモ データのカスタマイズ
本社でコンフィギュレーションされた製品およびカテゴリ情報を使用して、既定のデモ データを編集できます。 .csv を更新すると、顧客に返される製品推奨事項は変更をすぐに反映します。

拡張機能には、「RecoMockDataset.csv」と呼ばれるデータファイルが含まれています。これによりモックの推奨結果の出力に使用するデータセットを制御できます。 ファイル名は、**ext.Recommendations.DemoFilePath** 設定を使用して、拡張コンフィギュレーションによって制御できます。 これにより、コンフィギュレーション時に簡単に切り替えることができる複数のデータセットを利用できるようになります。


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a>追加リソース

[製品推奨事項の概要](product-recommendations.md)

[環境計画](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
