---
title: パーソナライズされた推奨事項のオプト アウト
description: このトピックでは、顧客がMicrosoft Dynamics 365 Commerceでパーソナライズされた推奨事項を受け取ることができるようにする方法について説明します。
author: bebeale
manager: AnnBe
ms.date: 01/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8e7b800218f68167901d86d61ae483680a04cfab
ms.sourcegitcommit: b5ecde955a69f577de46e7db10e89caaedeb2b49
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "3025261"
---
# <a name="opt-out-of-personalized-recommendations"></a>パーソナライズされた推奨事項のオプト アウト

[!include [banner](includes/banner.md)]

このトピックでは、顧客がMicrosoft Dynamics 365 Commerceでパーソナライズされた推奨事項を受け取ることができるようにする方法について説明します。

## <a name="overview"></a>概要

アカウントの作成時、新規顧客はパーソナライズされた推奨事項を受け取るように自動的に設定されます。 ただし、Dynamics 365 Commerce は、ユーザーがこれらの推奨事項のオプト アウトを選択したり、個人データの処理を制限したりできるようにするさまざまな方法を、小売業者に提供しています。 パーソナライズされた推奨事項の受信をオプト アウトした認証済ユーザーは、ただちにパーソナライズされたリストを見ることができなくなります。 また、パーソナライズのために収集された個人データは、パーソナライズされた推奨モデルから削除されます。

パーソナライズされた製品推奨事項の詳細については、[パーソナライズされた推奨事項の有効化](personalized-recommendations.md) を参照してください。

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a>小売業者がオプトアウト エクスペリエンスを実装する方法

小売業者がオプトアウト エクスペリエンスを実装する方法は、3 つあります。

### <a name="opting-out-on-behalf-of-users"></a>ユーザーに代わってオプト アウトする

Commerce バック オフィスのアカウント管理では、小売業者はユーザーに代わってオプト アウトを行うことができます。

1. バックオフィスのホームページから、**すべての顧客**を検索します。
1. 顧客を検索して選択し、**小売**クイックタブを選択します。

    ![小売クイックタブ](./media/Disablepersonalizationpart1.png)

1. **プライバシー**で、**個人用設定を無効にする**オプションを**はい**に設定します。

    ![プライバシー設定](./media/Disablepersonalizationpart2.png)

1. **保存**を選択して、ページを閉じます。

### <a name="module-based-opt-out-experience"></a>モジュールベースのオプトアウト エクスペリエンス

小売業者は、認証済ユーザーがパーソナライズされた推奨事項を自分でオプト アウトできるようにすることができます。 このオプトアウト エクスペリエンスを提供するには、顧客アカウント プロファイル ページにユーザーのオプトアウト モジュールを追加します。

### <a name="custom-extensions"></a>カスタムの拡張機能

小売業者は、ユーザーのオプトアウト エクスペリエンスを管理するための独自の拡張機能を作成できます。 詳細については、[Retail サーバー API](e-commerce-extensibility/call-retail-server-apis.md) および [オンライン チャネルの拡張性](e-commerce-extensibility/overview.md)を参照してください。

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a>認証済ユーザーに代わって、パーソナライズされた推奨事項データのデジタル コピーを取得する

顧客は、個人データのデジタル コピーを取得して、その推奨結果をエクスポートして表示することができます。 顧客がこの情報を要求した場合、小売業者は、顧客の顧客 ID に基づいて、Retail Server のアプリケーション プログラミング インターフェイス (API) を呼び出す、カスタマイズされた拡張機能を作成し、**おすすめ**リストからすべての結果をクエリする必要があります。 その後、結果をコンマ区切り値 (CSV) 形式でエクスポートして、顧客と共有することができます。

次の例は、小売業者がこのタスクを実行する方法を示しています。

1. 小売業者は、ユーザーに代わって個人的な推奨事項データを取得するカスタム拡張機能を作成します。 モジュールの作成、既存のモジュールの複製、Retail Server API の呼び出し、データ アクションの呼び出しの詳細については、[オンライン チャネルの拡張性](e-commerce-extensibility/overview.md)を参照してください。
2. カスタム拡張機能は、**推奨を取得**のコア データ アクションに対する呼び出しを行い、リストの要件に基づいて必要な情報を渡します。 **おすすめ**リストの場合は、拡張機能によって、正しいリスト名と顧客 ID がデータ アクションに渡される必要があります。

    カスタム拡張機能を作成する 1 つの方法として、推奨結果を返すために使用される既存の製品収集モジュールを複製する方法があります。 この既存のモジュールを複製することによって、小売業者は既存のコードを変更し、推奨結果を CSV ファイルにエクスポートする新しいボタンを追加することができます。 詳細については、[スタート キット モジュールの複製](e-commerce-extensibility/clone-starter-module.md)および[製品収集モジュール](product-collection-module-overview.md)を参照してください。

    Retail Server API ライブラリの完全表示については、[Retail Server の顧客およびコンシューマー API](dev-itpro/retail-server-customer-consumer-api.md)を参照してください。

3. カスタム拡張機能が作成されると、小売業者は、認証済ユーザーの固有の顧客 ID に基づいて、すべての推奨結果の CSV ファイルをエクスポートできます。
4. 小売業者は、パーソナライズされた推奨製品リストを含むエクスポートされた CSV ファイルを、認証済ユーザーと共有することができます。

## <a name="additional-resources"></a>追加リソース

[製品推奨事項の概要](product-recommendations.md)

[製品推奨事項の有効化](enable-product-recommendations.md)

[パーソナライズされた推奨事項の有効化](personalized-recommendations.md)

[ページへの製品推奨リストの追加](add-reco-list-to-page.md)

[POS デバイスへの推奨事項パネルの追加](add-recommendations-control-pos-screen.md)

[製品収集モジュールの概要](product-collection-module-overview.md)
