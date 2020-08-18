---
title: FormBuildComboBoxControl クラス
description: このトピックでは、FormBuildComboBoxControl クラスについて説明します。
author: robinarh
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: rhaertle
ms.search.scope: Operations
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: adfb4803b2ec86a0ac3f60ca5cf040dfe9fb67b6
ms.sourcegitcommit: 7b0cec2e898ef8ee33baf72f18cdd9cba0e9399c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2020
ms.locfileid: "3502974"
---
# <a name="class-formbuildcomboboxcontrol"></a>クラス FormBuildComboBoxControl

[!include [banner](../../includes/banner.md)]

```xpp
class FormBuildComboBoxControl extends FormBuildControl
```

FormBuildComboBoxControl クラスを使用すると、X++ コードとメタデータの作成、読み取り、更新、および削除を行うことができます。

## <a name="remarks"></a>備考

この API が呼び出される前に、ユーザーが開発セキュリティ キー (SysDevelopment) にアクセスできることを確認します。

## <a name="examples"></a>例

## <a name="methods"></a>メソッド

| 方法                                                                                                      | 説明                                                                                                                                   |
|-------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| public boolean alignControl(\[boolean value\])                                                              | コントロールを配置するかどうかを決定します。                                                                                                      |
| public boolean allowEdit(\[boolean value\])                                                                 | ユーザーがコントロールの内容を変更できるかどうかを決定します。                                                                           |
| public boolean appendNew(\[boolean value\])                                                                 |                                                                                                                                               |
| public int arrayIndex(\[int value\])                                                                        |                                                                                                                                               |
| public boolean autoDeclaration(\[boolean value\])                                                           | システムがコントロールと同じ名前を持つメンバー変数を宣言できるかどうかを決定します。                                            |
| public int backgroundColor(\[int value\])                                                                   | コントロールの背景色を取得または設定します。                                                                                             |
| public int backStyle(\[int value\])                                                                         | コントロールの背景色を透明にできるかどうかを決定します。                                                                                |
| public int bold(\[int value\])                                                                              | コントロール内のテキストを出力するのに使用されるフォントの重量を取得または設定します。                                                                   |
| public int border(\[int value\])                                                                            | コントロールの境界線のスタイルを取得または設定します。                                                                                      |
| public int cacheDataMethod(\[int value\])                                                                   |                                                                                                                                               |
| public int characterSet(\[int value\])                                                                      | フォントの文字セットを取得または設定します。                                                                                                   |
| public int colorScheme(\[int value\])                                                                       | コントロールの配色を取得または設定します。                                                                                                 |
| public int comboType(\[int value\])                                                                         |                                                                                                                                               |
| public ConfigurationKeyId configurationKey(\[ConfigurationKeyId value\])                                    | コントロールに割り当てられるコンフィギュレーション キーを取得または設定します。                                                                           |
| public int containerId()                                                                                    | コントロールの親コンテナーの ID を取得します。                                                                                     |
| public str countryRegionCodes(\[str value\])                                                                |                                                                                                                                               |
| public FieldId countryRegionContextField(\[FieldId value\])                                                 |                                                                                                                                               |
| public FieldId dataField(\[FieldId value\])                                                                 |                                                                                                                                               |
| public str dataMethod(\[str value\])                                                                        |                                                                                                                                               |
| public str dataRelationPath(\[str value\])                                                                  |                                                                                                                                               |
| public int dataSource(\[AnyType value\])                                                                    | コントロールまたはフォームで使用されるデータ ソースを取得または設定します。                                                                      |
| public int displayLength(\[int value\], \[AutoMode mode\])                                                  |                                                                                                                                               |
| public AutoMode displayLengthMode(\[AutoMode mode\])                                                        |                                                                                                                                               |
| public int displayLengthValue(\[int value\])                                                                |                                                                                                                                               |
| public int displayTarget(\[int value\])                                                                     |                                                                                                                                               |
| public int dragDrop(\[int value\])                                                                          | コントロールのドラッグ アンド ドロップ操作を有効または無効にするかどうかを決定します。                                                             |
| public boolean enabled(\[boolean value\])                                                                   | オブジェクトを有効または無効にするかどうかを決定します。                                                                                           |
| public EnumId enumType(\[EnumId value\])                                                                    |                                                                                                                                               |
| public ExtendedTypeId extendedDataType(\[ExtendedTypeId value\])                                            |                                                                                                                                               |
| public int fastTabSummary(\[int value\])                                                                    |                                                                                                                                               |
| public str font(\[str value\])                                                                              | 使用するコントロールのフォントの名前を取得または設定します。                                                                                     |
| public int fontSize(\[int value\])                                                                          | 使用するコントロールのフォントのサイズを取得または設定します。                                                                                     |
| public int foregroundColor(\[int value\])                                                                   | 使用するコントロールのテキストの色を取得または設定します。                                                                                           |
| public int height(int value, \[int mode\])                                                                  | コントロールの高さを取得または設定します。                                                                                                       |
| public int heightMode(\[int value\])                                                                        | コントロールの高さの計算方法を取得または設定します。                                                                                |
| public int heightValue(\[int value\])                                                                       | コントロールの高さを取得または設定します。                                                                                                       |
| public str helpText(\[str value\])                                                                          | フィールドやコントロールのポイント時に、画面の下部に表示されるヘルプ テキストを取得または設定します。                                      |
| public boolean hideFirstEntry(\[boolean value\])                                                            |                                                                                                                                               |
| public str hierarchyParent(\[str value\])                                                                   |                                                                                                                                               |
| public int id()                                                                                             | コントロールの ID を取得します。                                                                                                              |
| public boolean isContainer()                                                                                | コントロールがコンテナー コントロールかどうかを示す値を取得します。                                                                  |
| public boolean italic(\[boolean value\])                                                                    |                                                                                                                                               |
| public int item(\[int value\])                                                                              |                                                                                                                                               |
| public int items(\[int value\])                                                                             |                                                                                                                                               |
| public str label(\[str value\])                                                                             | コントロールのラベルを取得または設定します。                                                                                                         |
| public int labelAlignment(\[int value\])                                                                    |                                                                                                                                               |
| public int labelBold(\[int value\])                                                                         |                                                                                                                                               |
| public int labelCharacterSet(\[int value\])                                                                 |                                                                                                                                               |
| public str labelFont(\[str value\])                                                                         |                                                                                                                                               |
| public int labelFontSize(\[int value\])                                                                     |                                                                                                                                               |
| public int labelForegroundColor(\[int value\])                                                              |                                                                                                                                               |
| public int labelGuide(\[int value\])                                                                        |                                                                                                                                               |
| public int labelHeight(int value, \[int mode\])                                                             |                                                                                                                                               |
| public int labelHeightMode(\[int value\])                                                                   |                                                                                                                                               |
| public int labelHeightValue(\[int value\])                                                                  |                                                                                                                                               |
| public boolean labelItalic(\[boolean value\])                                                               |                                                                                                                                               |
| public int labelPosition(\[int value\])                                                                     |                                                                                                                                               |
| public boolean labelUnderline(\[boolean value\])                                                            |                                                                                                                                               |
| public int labelWidth(int value, \[int mode\])                                                              |                                                                                                                                               |
| public int labelWidthMode(\[int value\])                                                                    |                                                                                                                                               |
| public int labelWidthValue(\[int value\])                                                                   |                                                                                                                                               |
| public int left(int value, \[int mode\])                                                                    |                                                                                                                                               |
| public int leftMode(\[int value\])                                                                          |                                                                                                                                               |
| public int leftValue(\[int value\])                                                                         |                                                                                                                                               |
| public str name(\[str value\])                                                                              | フォーム、レポート、テーブル、クエリ、または別のアプリケーション オブジェクトを識別するためのコードで使用される名前を取得または設定します。 |
| public int neededPermission(\[int value\])                                                                  |                                                                                                                                               |
| public int promptrect(\[int value\])                                                                        |                                                                                                                                               |
| public SecurityKeyId securityKey(\[SecurityKeyId value\])                                                   |                                                                                                                                               |
| public int selection(\[int value\])                                                                         |                                                                                                                                               |
| public boolean showLabel(\[boolean value\])                                                                 |                                                                                                                                               |
| public boolean skip(\[boolean value\])                                                                      | ユーザーが Tab キーを押してコントロールに移動するときにコントロールがスキップされるかどうかを示す値を設定するか返します。               |
| public str text(\[str value\])                                                                              |                                                                                                                                               |
| public int top(int value, \[int mode\])                                                                     |                                                                                                                                               |
| public int topMode(\[int value\])                                                                           |                                                                                                                                               |
| public int topValue(\[int value\])                                                                          |                                                                                                                                               |
| public int type(\[int value\])                                                                              |                                                                                                                                               |
| public boolean underline(\[boolean value\])                                                                 | コントロール内のテキストの下線プロパティを設定するか返します。                                                                           |
| public int userData(\[int value\])                                                                          |                                                                                                                                               |
| public int userDataItem(\[int value\])                                                                      |                                                                                                                                               |
| public int userDataItems(\[int value\])                                                                     |                                                                                                                                               |
| public int verticalSpacing(\[int value\], \[AutoMode mode\])                                                |                                                                                                                                               |
| public AutoMode verticalSpacingMode(\[AutoMode mode\])                                                      |                                                                                                                                               |
| public int verticalSpacingValue(\[int value\])                                                              |                                                                                                                                               |
| public int viewEditMode(\[int value\])                                                                      |                                                                                                                                               |
| public boolean visible(\[boolean value\])                                                                   |                                                                                                                                               |
| public int width(int value, \[int mode\])                                                                   | コントロールの幅を取得または設定します。                                                                                                        |
| public int widthMode(\[int value\])                                                                         | コントロールの幅の計算方法を取得または設定します。                                                                                |
| public int widthValue(\[int value\])                                                                        | コントロールの幅を取得または設定します。                                                                                                        |
| public void registerOverrideMethod(str methodToOverride, str objectMethodToCall, \[Object overrideObject\]) |                                                                                                                                               |

## <a name="method-aligncontrol"></a>メソッド alignControl

コントロールを配置するかどうかを決定します。

```xpp
public boolean alignControl([boolean value])
```

### <a name="parameters---aligncontrol"></a>パラメーター - alignControl

値  

### <a name="return-value---aligncontrol"></a>戻り値 - alignControl

コントロールをアラインする必要がある場合は true。それ以外の場合は false。

### <a name="remarks---aligncontrol"></a>備考 - alignControl

コントロールの左上隅は、最も長いラベルに従って配置されます。

## <a name="method-allowedit"></a>メソッド allowEdit

ユーザーがコントロールの内容を変更できるかどうかを決定します。

```xpp
public boolean allowEdit([boolean value])
```

### <a name="parameters---allowedit"></a>パラメーター - allowEdit

値  

### <a name="return-value---allowedit"></a>戻り値 - allowEdit

コントロールを編集することができる場合は true。それ以外の場合は、false。

### <a name="remarks---allowedit"></a>備考 - allowEdit

コンテナー コントロールにこのプロパティが設定されると、コンテナー内のすべてのコントロールの変更は無効または有効になります。

## <a name="method-appendnew"></a>メソッド appendNew

```xpp
public boolean appendNew([boolean value])
```

### <a name="parameters---appendnew"></a>パラメーター - appendNew

値  

### <a name="return-value---appendnew"></a>戻り値 - appendNew

## <a name="method-arrayindex"></a>メソッド arrayIndex

```xpp
public int arrayIndex([int value])
```

### <a name="parameters---arrayindex"></a>パラメーター - arrayIndex

値  

### <a name="return-value---arrayindex"></a>戻り値 - arrayIndex

## <a name="method-autodeclaration"></a>メソッド autoDeclaration

システムがコントロールと同じ名前を持つメンバー変数を宣言できるかどうかを決定します。

```xpp
public boolean autoDeclaration([boolean value])
```

### <a name="parameters---autodeclaration"></a>パラメーター - autoDeclaration

値  

### <a name="return-value---autodeclaration"></a>戻り値 - autoDeclaration

このコントロールのためにメンバー変数を宣言することができる場合は true。それ以外の場合は、false。

### <a name="remarks---autodeclaration"></a>備考 - autoDeclaration

コントロールには同じ名前を付けることはできません。

## <a name="method-backgroundcolor"></a>メソッド backgroundColor

コントロールの背景色を取得または設定します。

```xpp
public int backgroundColor([int value])
```

### <a name="parameters---backgroundcolor"></a>パラメーター - backgroundColor

値  

### <a name="return-value---backgroundcolor"></a>戻り値 - backgroundColor

パックされた RGB カラーを含む整数。

### <a name="remarks---backgroundcolor"></a>備考 - backgroundColor

返される整数には、次のようにパックされた RGB カラーが含まれます。

-   下位バイトには赤の相対強度の値が含まれています。
-   2 番目のバイトには緑の値が入っています。
-   3 番目のバイトには青の値が入っています。
-   上位バイトはゼロでなければなりません。
-   1 バイトの最大値は 255 です。

## <a name="method-backstyle"></a>メソッド backStyle

コントロールの背景色を透明にできるかどうかを決定します。

```xpp
public int backStyle([int value])
```

### <a name="parameters---backstyle"></a>パラメーター - backStyle

値  

### <a name="return-value---backstyle"></a>戻り値 - backStyle

コントロールの背景が透明の場合は 1、それ以外の場合は、0 です。

## <a name="method-bold"></a>メソッド bold

コントロール内のテキストを出力するのに使用されるフォントの重量を取得または設定します。

```xpp
public int bold([int value])
```

### <a name="parameters---bold"></a>パラメーター - bold

値  

### <a name="return-value---bold"></a>戻り値 - bold

0 から 9 までの間の整数値。

### <a name="remarks---bold"></a>備考 - bold

返される整数には、次のようなフォントの重量が含まれます。

-   0 既定のフォントの重量を使用します。
-   1 シン。
-   2 エクストラ ライト。
-   3. ライト。
-   4 標準。
-   5 中。
-   6 セミボールド。
-   7 太字。
-   8 極太。
-   9 ヘビー。

## <a name="method-border"></a>メソッド border

コントロールの境界線のスタイルを取得または設定します。

```xpp
public int border([int value])
```

### <a name="parameters---border"></a>パラメーター - border

値  

### <a name="return-value---border"></a>戻り値 - border

ゼロから 4 までの整数。

### <a name="remarks---border"></a>備考 - border

返される整数には、次のようなコントロールの境界線のスタイルが含まれます。

| 値です。 | 説明。 |
|--------|--------------|
| 0      | 自動。        |
| 1      | 3D。          |
| 2      | 単一明細行。 |
| 3      | 均一。        |
| 4      | なし。        |

## <a name="method-cachedatamethod"></a>メソッド cacheDataMethod

```xpp
public int cacheDataMethod([int value])
```

### <a name="parameters---cachedatamethod"></a>パラメーター - cacheDataMethod

値  

### <a name="return-value---cachedatamethod"></a>戻り値 - cacheDataMethod

## <a name="method-characterset"></a>メソッド characterSet

フォントの文字セットを取得または設定します。

```xpp
public int characterSet([int value])
```

### <a name="parameters---characterset"></a>パラメーター - characterSet

値  

### <a name="return-value---characterset"></a>戻り値 - characterSet

フォントの文字セット示す整数値。

### <a name="remarks---characterset"></a>備考 - characterSet

返される整数の値は、次のテーブルに従って文字セットを示します。

| 値です。 | 説明。         |
|--------|----------------------|
| 0      | ANSI\_CHARSET        |
| 1      | DEFAULT\_CHARSET     |
| 2      | SYMBOL\_CHARSET      |
| 77     | MAC\_CHARSET         |
| 128    | SHIFTJIS\_CHARSET    |
| 129    | HANGUL\_CHARSET      |
| 134    | GB2312\_CHARSET      |
| 136    | CHINESEBIG5\_CHARSET |
| 161    | GREEK\_CHARSET       |
| 162    | TURKISH\_CHARSET     |
| 163    | VIETNAMESE\_CHARSET  |
| 186    | BALTIC\_CHARSET      |
| 204    | RUSSIAN\_CHARSET     |
| 238    | EASTEUROPE\_CHARSET  |
| 255    | OEM\_CHARSET         |

次のテーブルの値は、韓国語版 Microsoft Windows の値です。

| 値です。 | 説明。   |
|--------|----------------|
| 130    | JOHAB\_CHARSET |

次のテーブルの値は、中東言語版用 Microsoft Windows の値です。

| 値です。 | 説明。    |
|--------|-----------------|
| 177    | HEBREW\_CHARSET |
| 178    | ARABIC\_CHARSET |

次のテーブルの値は、タイ語版 Microsoft Windows の値です。

| 値です。 | 説明。  |
|--------|---------------|
| 222    | THAI\_CHARSET |

既定の文字セットは、現在のシステム ロケールに応じて、値に対して設定されます。 たとえば、システム ロケールが英語 (米国) である場合、ANSI\_CHARSET として設定されます。 詳細については [MSDN Web サイト](https://go.microsoft.com/fwlink/?LinkID=85972) で LOGFONT 構造を参照してください。

## <a name="method-colorscheme"></a>メソッド colorScheme

コントロールの配色を取得または設定します。

```xpp
public int colorScheme([int value])
```

### <a name="parameters---colorscheme"></a>パラメーター - colorScheme

値  

### <a name="return-value---colorscheme"></a>戻り値 - colorScheme

ゼロから 2 までの整数。

### <a name="remarks---colorscheme"></a>備考 - colorScheme

配色は次の表に従って定義されます。

| 値です。 | スタイル。                        |
|--------|-------------------------------|
| 0      | 既定。                      |
| 1      | Microsoft Windows パレット。 |
| 2      | 真の配色。        |

## <a name="method-combotype"></a>メソッド comboType

```xpp
public int comboType([int value])
```

### <a name="parameters---combotype"></a>パラメーター - comboType

値  

### <a name="return-value---combotype"></a>戻り値 - comboType

## <a name="method-configurationkey"></a>メソッド configurationKey

コントロールに割り当てられるコンフィギュレーション キーを取得または設定します。

```xpp
public ConfigurationKeyId configurationKey([ConfigurationKeyId value])
```

### <a name="parameters---configurationkey"></a>パラメーター - configurationKey

値  

### <a name="return-value---configurationkey"></a>戻り値 - configurationKey

コントロールに割り当てられるコンフィギュレーションの ID。

### <a name="remarks---configurationkey"></a>備考 - configurationKey

コンフィギュレーション キーは、このコントロールを表示するかどうかを決定するために使用されます。 コンフィギュレーション キーがシステムで無効な場合、コントロールはフォームで表示されません。

## <a name="method-containerid"></a>メソッド containerId

コントロールの親コンテナーの ID を取得します。

```xpp
public int containerId()
```

### <a name="return-value---containerid"></a>戻り値 - containerId

親コンテナーの ID。

## <a name="method-countryregioncodes"></a>メソッド countryRegionCodes

```xpp
public str countryRegionCodes([str value])
```

### <a name="parameters---countryregioncodes"></a>パラメーター - countryRegionCodes

値  

### <a name="return-value---countryregioncodes"></a>戻り値 - countryRegionCodes

## <a name="method-countryregioncontextfield"></a>メソッド countryRegionContextField

```xpp
public FieldId countryRegionContextField([FieldId value])
```

### <a name="parameters---countryregioncontextfield"></a>パラメーター - countryRegionContextField

値  

### <a name="return-value---countryregioncontextfield"></a>戻り値 - countryRegionContextField

## <a name="method-datafield"></a>メソッド dataField

```xpp
public FieldId dataField([FieldId value])
```

### <a name="parameters---datafield"></a>パラメーター - dataField

値  

### <a name="return-value---datafield"></a>戻り値 - dataField

## <a name="method-datamethod"></a>メソッド dataMethod

```xpp
public str dataMethod([str value])
```

### <a name="parameters---datamethod"></a>パラメーター - dataMethod

値  

### <a name="return-value---datamethod"></a>戻り値 - dataMethod

## <a name="method-datarelationpath"></a>メソッド dataRelationPath

```xpp
public str dataRelationPath([str value])
```

### <a name="parameters---datarelationpath"></a>パラメーター - dataRelationPath

値  

### <a name="return-value---datarelationpath"></a>戻り値 - dataRelationPath

## <a name="method-datasource"></a>メソッド dataSource

コントロールまたはフォームで使用されるデータ ソースを取得または設定します。

```xpp
public int dataSource([AnyType value])
```

### <a name="parameters---datasource"></a>パラメーター - dataSource

値  

### <a name="return-value---datasource"></a>戻り値 - dataSource

使用されるデータ ソースの ID。

## <a name="method-displaylength"></a>メソッド displayLength

```xpp
public int displayLength([int value], [AutoMode mode])
```

### <a name="parameters---displaylength"></a>パラメーター - displayLength

値  

<!-- -->

モード  

### <a name="return-value---displaylength"></a>戻り値 - displayLength

## <a name="method-displaylengthmode"></a>メソッド displayLengthMode

```xpp
public AutoMode displayLengthMode([AutoMode mode])
```

### <a name="parameters---displaylengthmode"></a>パラメーター - displayLengthMode

モード  

### <a name="return-value---displaylengthmode"></a>戻り値 - displayLengthMode

## <a name="method-displaylengthvalue"></a>メソッド displayLengthValue

```xpp
public int displayLengthValue([int value])
```

### <a name="parameters---displaylengthvalue"></a>パラメーター - displayLengthValue

値  

### <a name="return-value---displaylengthvalue"></a>戻り値 - displayLengthValue

## <a name="method-displaytarget"></a>メソッド displayTarget

```xpp
public int displayTarget([int value])
```

### <a name="parameters---displaytarget"></a>パラメーター - displayTarget

値  

### <a name="return-value---displaytarget"></a>戻り値 - displayTarget

## <a name="method-dragdrop"></a>メソッド dragDrop

コントロールのドラッグ アンド ドロップ操作を有効または無効にするかどうかを決定します。

```xpp
public int dragDrop([int value])
```

### <a name="parameters---dragdrop"></a>パラメーター - dragDrop

値  

### <a name="return-value---dragdrop"></a>戻り値 - dragDrop

ドラッグ アンド ドロップ操作が有効な場合は 1、それ以外の場合は、false です。

## <a name="method-enabled"></a>メソッド enabled

オブジェクトを有効または無効にするかどうかを決定します。

```xpp
public boolean enabled([boolean value])
```

### <a name="parameters---enabled"></a>パラメーター - enabled

値  

### <a name="return-value---enabled"></a>戻り値 - enabled

オブジェクトが有効である場合は true。それ以外の場合は、false。

### <a name="remarks---enabled"></a>備考 - enabled

有効になっているプロパティを使用すると、実行時にコントロールを有効または無効にできます。 たとえば、アプリケーションの現在の状態には適用されないオブジェクトを無効にすることができます。 また、読み取り専用情報を提供する、エラー メッセージなどの、表示のためにのみ使用されるコントロールを無効にすることもできます。

## <a name="method-enumtype"></a>メソッド enumType

```xpp
public EnumId enumType([EnumId value])
```

### <a name="parameters---enumtype"></a>パラメーター - enumType

値  

### <a name="return-value---enumtype"></a>戻り値 - enumType

## <a name="method-extendeddatatype"></a>メソッド extendedDataType

```xpp
public ExtendedTypeId extendedDataType([ExtendedTypeId value])
```

### <a name="parameters---extendeddatatype"></a>パラメーター - extendedDataType

値  

### <a name="return-value---extendeddatatype"></a>戻り値 - extendedDataType

## <a name="method-fasttabsummary"></a>メソッド fastTabSummary

```xpp
public int fastTabSummary([int value])
```

### <a name="parameters---fasttabsummary"></a>パラメーター - fastTabSummary

値  

### <a name="return-value---fasttabsummary"></a>戻り値 - fastTabSummary

## <a name="method-font"></a>メソッド font

使用するコントロールのフォントの名前を取得または設定します。

```xpp
public str font([str value])
```

### <a name="parameters---font"></a>パラメーター - font

値  

### <a name="return-value---font"></a>戻り値 - font

Tahoma や Verdana など、使用するフォントの名前。

## <a name="method-fontsize"></a>メソッド fontSize

使用するコントロールのフォントのサイズを取得または設定します。

```xpp
public int fontSize([int value])
```

### <a name="parameters---fontsize"></a>パラメーター - fontSize

値  

### <a name="return-value---fontsize"></a>戻り値 - fontSize

ポイント単位のフォントの高さ。

## <a name="method-foregroundcolor"></a>メソッド foregroundColor

使用するコントロールのテキストの色を取得または設定します。

```xpp
public int foregroundColor([int value])
```

### <a name="parameters---foregroundcolor"></a>パラメーター - foregroundColor

値  

### <a name="return-value---foregroundcolor"></a>戻り値 - foregroundColor

パックされた RGB カラーを含む整数。

### <a name="remarks---foregroundcolor"></a>備考 - foregroundColor

返される整数には、次のようにパックされた RGB カラーが含まれます。

-   下位バイトには赤の相対強度の値が含まれています。
-   2 番目のバイトには緑の値が入っています。
-   3 番目のバイトには青の値が入っています。
-   上位バイトはゼロでなければなりません。
-   1 バイトの最大値は 255 です。

## <a name="method-height"></a>メソッド height

コントロールの高さを取得または設定します。

```xpp
public int height(int value, [int mode])
```

### <a name="parameters---height"></a>パラメーター - height

値  

<!-- -->

モード  

### <a name="return-value---height"></a>戻り値 - height

ピクセル単位のコントロールの高さ。

### <a name="remarks---height"></a>備考 - height

値のパラメータを省略すると、正確なモードが使用されます。 次の表に従って高さを計算します:

| モード。            | 高さの計算。                                                                       |
|------------------|-------------------------------------------------------------------------------------------|
| -1 正確。        | コントロールのピクセル単位の正確な高さが使用されます。                                       |
| 0 自動。          | コントロールの高さは自動的に計算され、value パラメーターは無視されます。 |
| 1 列の高さ。 | フォームのレイアウトによって、コントロールの高さが決まります。                              |

高さと高さ計算モードは別々に設定できます。

## <a name="method-heightmode"></a>メソッド heightMode

コントロールの高さの計算方法を取得または設定します。

```xpp
public int heightMode([int value])
```

### <a name="parameters---heightmode"></a>パラメーター - heightMode

値  

### <a name="return-value---heightmode"></a>戻り値 - heightMode

計算モード。

### <a name="remarks---heightmode"></a>備考 - heightMode

次の表に従って高さを計算します:

| モード。          | 高さの計算。                                                                       |
|----------------|-------------------------------------------------------------------------------------------|
| 正確。         | コントロールのピクセル単位の正確な高さが使用されます。                                       |
| 自動。          | コントロールの高さは自動的に計算され、value パラメーターは無視されます。 |
| 列の高さ | フォームのレイアウトによって、コントロールの高さが決まります。                              |

計算モードが [自動] または [列の高さ] に設定されている場合は、コントロールの高さが変わることがあります。

## <a name="method-heightvalue"></a>メソッド heightValue

コントロールの高さを取得または設定します。

```xpp
public int heightValue([int value])
```

### <a name="parameters---heightvalue"></a>パラメーター - heightValue

値  

### <a name="return-value---heightvalue"></a>戻り値 - heightValue

ピクセル単位の高さ。

### <a name="remarks---heightvalue"></a>備考 - heightValue

正確な高さ計算モードが使用されていない限り、コントロールの高さは変更されません。

## <a name="method-helptext"></a>メソッド helpText

フィールドやコントロールのポイント時に、画面の下部に表示されるヘルプ テキストを取得または設定します。

```xpp
public str helpText([str value])
```

### <a name="parameters---helptext"></a>パラメーター - helpText

値  

### <a name="return-value---helptext"></a>戻り値 - helpText

画面の下部に表示される文字列。

### <a name="remarks---helptext"></a>備考 - helpText

プロパティ ダイアログ ボックスを使用してオブジェクトの HelpText プロパティを設定します。 ヘルプ テキストは 250 文字を超えてはいけません。

## <a name="method-hidefirstentry"></a>メソッド hideFirstEntry

```xpp
public boolean hideFirstEntry([boolean value])
```

### <a name="parameters---hidefirstentry"></a>パラメーター - hideFirstEntry

値  

### <a name="return-value---hidefirstentry"></a>戻り値 - hideFirstEntry

## <a name="method-hierarchyparent"></a>メソッド hierarchyParent

```xpp
public str hierarchyParent([str value])
```

### <a name="parameters---hierarchyparent"></a>パラメーター - hierarchyParent

値  

### <a name="return-value---hierarchyparent"></a>戻り値 - hierarchyParent

## <a name="method-id"></a>メソッド id

コントロールの ID を取得します。

```xpp
public int id()
```

### <a name="return-value---id"></a>戻り値 - id

コントロールの ID。

## <a name="method-iscontainer"></a>メソッド isContainer

コントロールがコンテナー コントロールかどうかを示す値を取得します。

```xpp
public boolean isContainer()
```

### <a name="return-value---iscontainer"></a>戻り値 - isContainer

コントロールがコンテナー コントロールかどうかを示すブール値。

## <a name="method-italic"></a>メソッド italic

```xpp
public boolean italic([boolean value])
```

### <a name="parameters---italic"></a>パラメーター - italic

値  

### <a name="return-value---italic"></a>戻り値 - italic

## <a name="method-item"></a>メソッド item

```xpp
public int item([int value])
```

### <a name="parameters---item"></a>パラメーター - item

値  

### <a name="return-value---item"></a>戻り値 - item

## <a name="method-items"></a>メソッド items

```xpp
public int items([int value])
```

### <a name="parameters---items"></a>パラメーター - items

値  

### <a name="return-value---items"></a>戻り値 - items

## <a name="method-label"></a>メソッド label

コントロールのラベルを取得または設定します。

```xpp
public str label([str value])
```

### <a name="parameters---label"></a>パラメーター - label

値  

### <a name="return-value---label"></a>戻り値 - label

ラベル文字列の現在の値。

### <a name="remarks---label"></a>備考 - label

ラベルは、コントロール内に表示されているテキストまたはそれに隣接するテキストを指定します。 ラベルのプロパティ値は 250 文字を超えることはできません。

## <a name="method-labelalignment"></a>メソッド labelAlignment

```xpp
public int labelAlignment([int value])
```

### <a name="parameters---labelalignment"></a>パラメーター - labelAlignment

値  

### <a name="return-value---labelalignment"></a>戻り値 - labelAlignment

## <a name="method-labelbold"></a>メソッド labelBold

```xpp
public int labelBold([int value])
```

### <a name="parameters---labelbold"></a>パラメーター - labelBold

値  

### <a name="return-value---labelbold"></a>戻り値 - labelBold

## <a name="method-labelcharacterset"></a>メソッド labelCharacterSet

```xpp
public int labelCharacterSet([int value])
```

### <a name="parameters---labelcharacterset"></a>パラメーター - labelCharacterSet

値  

### <a name="return-value---labelcharacterset"></a>戻り値 - labelCharacterSet

## <a name="method-labelfont"></a>メソッド labelFont

```xpp
public str labelFont([str value])
```

### <a name="parameters---labelfont"></a>パラメーター - labelFont

値  

### <a name="return-value---labelfont"></a>戻り値 - labelFont

## <a name="method-labelfontsize"></a>メソッド labelFontSize

```xpp
public int labelFontSize([int value])
```

### <a name="parameters---labelfontsize"></a>パラメーター - labelFontSize

値  

### <a name="return-value---labelfontsize"></a>戻り値 - labelFontSize

## <a name="method-labelforegroundcolor"></a>メソッド labelForegroundColor

```xpp
public int labelForegroundColor([int value])
```

### <a name="parameters---labelforegroundcolor"></a>パラメーター - labelForegroundColor

値  

### <a name="return-value---labelforegroundcolor"></a>戻り値 - labelForegroundColor

## <a name="method-labelguide"></a>メソッド labelGuide

```xpp
public int labelGuide([int value])
```

### <a name="parameters---labelguide"></a>パラメーター - labelGuide

値  

### <a name="return-value---labelguide"></a>戻り値 - labelGuide

## <a name="method-labelheight"></a>メソッド labelHeight

```xpp
public int labelHeight(int value, [int mode])
```

### <a name="parameters---labelheight"></a>パラメーター - labelHeight

値  

<!-- -->

モード  

### <a name="return-value---labelheight"></a>戻り値 - labelHeight

## <a name="method-labelheightmode"></a>メソッド labelHeightMode

```xpp
public int labelHeightMode([int value])
```

### <a name="parameters---labelheightmode"></a>パラメーター - labelHeightMode

値  

### <a name="return-value---labelheightmode"></a>戻り値 - labelHeightMode

## <a name="method-labelheightvalue"></a>メソッド labelHeightValue

```xpp
public int labelHeightValue([int value])
```

### <a name="parameters---labelheightvalue"></a>パラメーター - labelHeightValue

値  

### <a name="return-value---labelheightvalue"></a>戻り値 - labelHeightValue

## <a name="method-labelitalic"></a>メソッド labelItalic

```xpp
public boolean labelItalic([boolean value])
```

### <a name="parameters---labelitalic"></a>パラメーター - labelItalic

値  

### <a name="return-value---labelitalic"></a>戻り値 - labelItalic

## <a name="method-labelposition"></a>メソッド labelPosition

```xpp
public int labelPosition([int value])
```

### <a name="parameters---labelposition"></a>パラメーター - labelPosition

値  

### <a name="return-value---labelposition"></a>戻り値 - labelPosition

## <a name="method-labelunderline"></a>メソッド labelUnderline

```xpp
public boolean labelUnderline([boolean value])
```

### <a name="parameters---labelunderline"></a>パラメーター - labelUnderline

値  

### <a name="return-value---labelunderline"></a>戻り値 - labelUnderline

## <a name="method-labelwidth"></a>メソッド labelWidth

```xpp
public int labelWidth(int value, [int mode])
```

### <a name="parameters---labelwidth"></a>パラメーター - labelWidth

値  

<!-- -->

モード  

### <a name="return-value---labelwidth"></a>戻り値 - labelWidth

## <a name="method-labelwidthmode"></a>メソッド labelWidthMode

```xpp
public int labelWidthMode([int value])
```

### <a name="parameters---labelwidthmode"></a>パラメーター - labelWidthMode

値  

### <a name="return-value---labelwidthmode"></a>戻り値 - labelWidthMode

## <a name="method-labelwidthvalue"></a>メソッド labelWidthValue

```xpp
public int labelWidthValue([int value])
```

### <a name="parameters---labelwidthvalue"></a>パラメーター - labelWidthValue

値  

### <a name="return-value---labelwidthvalue"></a>戻り値 - labelWidthValue

## <a name="method-left"></a>メソッド left

```xpp
public int left(int value, [int mode])
```

### <a name="parameters---left"></a>パラメーター - left

値  

<!-- -->

モード  

### <a name="return-value---left"></a>戻り値 - left

## <a name="method-leftmode"></a>メソッド leftMode

```xpp
public int leftMode([int value])
```

### <a name="parameters---leftmode"></a>パラメーター - leftMode

値  

### <a name="return-value---leftmode"></a>戻り値 - leftMode

## <a name="method-leftvalue"></a>メソッド leftValue

```xpp
public int leftValue([int value])
```

### <a name="parameters---leftvalue"></a>パラメーター - leftValue

値  

### <a name="return-value---leftvalue"></a>戻り値 - leftValue

## <a name="method-name"></a>メソッド名

フォーム、レポート、テーブル、クエリ、または別のアプリケーション オブジェクトを識別するためのコードで使用される名前を取得または設定します。

```xpp
public str name([str value])
```

### <a name="parameters---name"></a>パラメーター - 名前

値  

### <a name="return-value---name"></a>戻り値 - name

アプリケーション オブジェクトを識別するためにコードで使用される名前。

### <a name="remarks---name"></a>備考 - 名前

オブジェクトの名前プロパティ値は、コードの競合を避けるために、次の基準を満たしている必要があります。

-   文字で始めます。
-   250 文字を超えないでください。
-   数字とアンダースコア文字を含めることができます。
-   句読点やスペースを含めることはできません。
-   テーブルは、拡張データ型、基本列挙型、クラスなどの他のパブリック オブジェクトと同じ名前を持つことはできません。

## <a name="method-neededpermission"></a>メソッド neededPermission

```xpp
public int neededPermission([int value])
```

### <a name="parameters---neededpermission"></a>パラメーター - neededPermission

値  

### <a name="return-value---neededpermission"></a>戻り値 - neededPermission

## <a name="method-promptrect"></a>メソッド promptrect

```xpp
public int promptrect([int value])
```

### <a name="parameters---promptrect"></a>パラメーター - promptrect

値  

### <a name="return-value---promptrect"></a>戻り値 - promptrect

## <a name="method-securitykey"></a>メソッド securityKey

```xpp
public SecurityKeyId securityKey([SecurityKeyId value])
```

### <a name="parameters---securitykey"></a>パラメーター - securityKey

値  

### <a name="return-value---securitykey"></a>戻り値 - securityKey

## <a name="method-selection"></a>メソッド selection

```xpp
public int selection([int value])
```

### <a name="parameters---selection"></a>パラメーター - selection

値  

### <a name="return-value---selection"></a>戻り値 - selection

## <a name="method-showlabel"></a>メソッド showLabel

```xpp
public boolean showLabel([boolean value])
```

### <a name="parameters---showlabel"></a>パラメーター - showLabel

値  

### <a name="return-value---showlabel"></a>戻り値 - showLabel

## <a name="method-skip"></a>メソッド skip

ユーザーが Tab キーを押してコントロールに移動するときにコントロールがスキップされるかどうかを示す値を設定するか返します。

```xpp
public boolean skip([boolean value])
```

### <a name="parameters---skip"></a>パラメーター - skip

値  
コントロールの skip プロパティに割り当てる値。

### <a name="return-value---skip"></a>戻り値 - skip

コントロールに移動するためにユーザーが TAB キーを押すとコントロールがスキップされる場合は true。それ以外の場合は、false。

## <a name="method-text"></a>メソッド text

```xpp
public str text([str value])
```

### <a name="parameters---text"></a>パラメーター - text

値  

### <a name="return-value---text"></a>戻り値 - text

## <a name="method-top"></a>メソッド top

```xpp
public int top(int value, [int mode])
```

### <a name="parameters---top"></a>パラメーター - top

値  

<!-- -->

モード  

### <a name="return-value---top"></a>戻り値 - top

## <a name="method-topmode"></a>メソッド topMode

```xpp
public int topMode([int value])
```

### <a name="parameters---topmode"></a>パラメーター - topMode

値  

### <a name="return-value---topmode"></a>戻り値 - topMode

## <a name="method-topvalue"></a>メソッド topValue

```xpp
public int topValue([int value])
```

### <a name="parameters---topvalue"></a>パラメーター - topValue

値  

### <a name="return-value---topvalue"></a>戻り値 - topValue

## <a name="method-type"></a>メソッドのタイプ

```xpp
public int type([int value])
```

### <a name="parameters---type"></a>パラメーター - タイプ

値  

### <a name="return-value---type"></a>戻り値 - type

## <a name="method-underline"></a>メソッド underline

コントロール内のテキストの下線プロパティを設定するか返します。

```xpp
public boolean underline([boolean value])
```

### <a name="parameters---underline"></a>パラメーター - underline

値  
コントロールの underline プロパティに割り当てる値。

### <a name="return-value---underline"></a>戻り値 - underline

コントロール内のテキストが下線付きである場合は true。それ以外の場合は、false。

## <a name="method-userdata"></a>メソッド userData

```xpp
public int userData([int value])
```

### <a name="parameters---userdata"></a>パラメーター - userData

値  

### <a name="return-value---userdata"></a>戻り値 - userData

## <a name="method-userdataitem"></a>メソッド userDataItem

```xpp
public int userDataItem([int value])
```

### <a name="parameters---userdataitem"></a>パラメーター - userDataItem

値  

### <a name="return-value---userdataitem"></a>戻り値 - userDataItem

## <a name="method-userdataitems"></a>メソッド userDataItems

```xpp
public int userDataItems([int value])
```

### <a name="parameters---userdataitems"></a>パラメーター - userDataItems

値  

### <a name="return-value---userdataitems"></a>戻り値 - userDataItems

## <a name="method-verticalspacing"></a>メソッド verticalSpacing

```xpp
public int verticalSpacing([int value], [AutoMode mode])
```

### <a name="parameters---verticalspacing"></a>パラメーター - verticalSpacing

値  

<!-- -->

モード  

### <a name="return-value---verticalspacing"></a>戻り値 - verticalSpacing

## <a name="method-verticalspacingmode"></a>メソッド verticalSpacingMode

```xpp
public AutoMode verticalSpacingMode([AutoMode mode])
```

### <a name="parameters---verticalspacingmode"></a>パラメーター - verticalSpacingMode

モード  

### <a name="return-value---verticalspacingmode"></a>戻り値 - verticalSpacingMode

## <a name="method-verticalspacingvalue"></a>メソッド verticalSpacingValue

```xpp
public int verticalSpacingValue([int value])
```

### <a name="parameters---verticalspacingvalue"></a>パラメーター - verticalSpacingValue

値  

### <a name="return-value---verticalspacingvalue"></a>戻り値 - verticalSpacingValue

## <a name="method-vieweditmode"></a>メソッド viewEditMode

```xpp
public int viewEditMode([int value])
```

### <a name="parameters---vieweditmode"></a>パラメーター - viewEditMode

値  

### <a name="return-value---vieweditmode"></a>戻り値 - viewEditMode

## <a name="method-visible"></a>メソッド visible

```xpp
public boolean visible([boolean value])
```

### <a name="parameters---visible"></a>パラメーター - visible

値  

### <a name="return-value---visible"></a>戻り値 - visible

## <a name="method-width"></a>メソッド width

コントロールの幅を取得または設定します。

```xpp
public int width(int value, [int mode])
```

### <a name="parameters---width"></a>パラメーター - width

値  

<!-- -->

モード  

### <a name="return-value---width"></a>戻り値 - width

ピクセル単位のコントロールの幅。

### <a name="remarks---width"></a>備考 - width

値のパラメータを省略すると、正確なモードが使用されます。 次の表に従って幅を計算します:

| モード。           | 幅計算。                                                                       |
|-----------------|------------------------------------------------------------------------------------------|
| -1 正確。       | コントロールのピクセル単位の正確な幅が使用されます。                                       |
| 0 自動。         | コントロールの幅は自動的に計算され、value パラメーターは無視されます。 |
| 1 列の幅。 | フォームのレイアウトによって、コントロールの幅が決まります。                              |

幅と幅計算モードは別々に設定できます。

## <a name="method-widthmode"></a>メソッド widthMode

コントロールの幅の計算方法を取得または設定します。

```xpp
public int widthMode([int value])
```

### <a name="parameters---widthmode"></a>パラメーター - widthValue

値  

### <a name="return-value---widthmode"></a>戻り値 - widthMode

現在の計算モードを示す整数値。

### <a name="remarks---widthmode"></a>備考 - widthMode

次の表に従って幅を計算します:

| モード。         | 幅計算。                                                                       |
|---------------|------------------------------------------------------------------------------------------|
| 正確。        | コントロールのピクセル単位の正確な幅が使用されます。                                       |
| 自動。         | コントロールの幅は自動的に計算され、value パラメーターは無視されます。 |
| 列の幅。 | フォームのレイアウトによって、コントロールの幅が決まります。                              |

モードが [自動] または [列の幅] に設定されている場合は、コントロールの幅が変わることがあります。

## <a name="method-widthvalue"></a>メソッド widthValue

コントロールの幅を取得または設定します。

```xpp
public int widthValue([int value])
```

### <a name="parameters---widthvalue"></a>パラメーター - widthValue

値  

### <a name="return-value---widthvalue"></a>戻り値 - widthValue

ピクセル単位のコントロールの幅。

### <a name="remarks---widthvalue"></a>備考 - widthValue

コントロールの幅を変更するには、正確な幅の計算モードを使用します。

## <a name="method-registeroverridemethod"></a>メソッド registerOverrideMethod

```xpp
public void registerOverrideMethod(str methodToOverride, str objectMethodToCall, [Object overrideObject])
```

### <a name="parameters---registeroverridemethod"></a>パラメーター - registerOverrideMethod

methodToOverride  

<!-- -->

objectMethodToCall  

<!-- -->

overrideObject  
