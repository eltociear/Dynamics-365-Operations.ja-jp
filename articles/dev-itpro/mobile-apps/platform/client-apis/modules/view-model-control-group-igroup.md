---
title: "グループ モジュール"
description: "グループ コントロールは、任意の数のコントロールを子として持つコンテナー コントロールです。"
author: shadykdc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Developer
ms.reviewer: robinr
ms.search.scope: 
ms.search.region: Global
ms.author: kashea
ms.search.validFrom: 
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 6d236345ce35707a99cb39943b10fb1eed1c0830
ms.contentlocale: ja-jp
ms.lasthandoff: 08/09/2018

---

# <a name="group-module"></a>グループ モジュール

[!include [banner](../../../../includes/banner.md)]

グループ コントロールは、任意の数のコントロールを子として持つコンテナー コントロールです。

## <a name="index"></a>指数

### <a name="types"></a>種類

* [グループ](../interfaces/view-model-control-group-igroup-igroup.md)
* [GroupDesign](../interfaces/view-model-control-group-igroup-igroupdesign.md)
* [GroupMetadata](../interfaces/view-model-control-group-igroup-igroupmetadata.md)

## <a name="types"></a>種類


### <a name="group"></a>グループ化

#### <a name="hierarchy"></a>階層

[ContainerControl](../interfaces/view-model-control-container-icontainercontrol-icontainercontrol.md) <br>&nbsp;&nbsp;&nbsp;└─ グループ <br>

#### <a name="properties"></a>プロパティ

| 氏名 | 署名 | 説明 |
| ---- | --------- | ----------- |
| [コンテナー](../interfaces/view-model-control-group-igroup-igroup.md#container) |container: ブール値 <br>|コントロールがコンテナーの場合は true です。<br>  [ContainerControl](../interfaces/view-model-control-container-icontainercontrol-icontainercontrol.md).[container](../interfaces/view-model-control-container-icontainercontrol-icontainercontrol.md#container) から継承 <br> [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md).[container](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md#container) をオーバーライドします。 <br> |
| [ジェネリック](../interfaces/view-model-control-group-igroup-igroup.md#generic) |generic: boolean (省略可)  <br>|  [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md).[generic](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md#generic) から継承 <br> |
| [getDataSource](../interfaces/view-model-control-group-igroup-igroup.md#getdatasource) |getDataSource: function(): any <br>|  [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md).[getDataSource](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md#getdatasource) から継承 <br> |
| [非表示](../interfaces/view-model-control-group-igroup-igroup.md#hidden) |hidden: boolean <br>|コントロールが非常時の場合は true です。<br>  [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md).[hidden](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md#hidden) から継承 <br> |

#### <a name="methods"></a>メソッド

| 氏名 | 署名 | 説明 |
| ---- | --------- | ----------- |
| [applyDesign](../interfaces/view-model-control-group-igroup-igroup.md#applydesign) |applyDesign(IDesign: [GroupDesign](../interfaces/view-model-control-group-igroup-igroupdesign.md)): void|付与されたデザインをコントロールのデザインに適用します。<br>  [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md).[applyDesign](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md#applydesign) をオーバーライドします。 <br> |
| [dataContext](../interfaces/view-model-control-group-igroup-igroup.md#datacontext) |dataContext(): any|  [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md).[dataContext](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md#datacontext) から継承 <br> |
| [getChildren](../interfaces/view-model-control-group-igroup-igroup.md#getchildren) |getChildren(): [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md) [ ]|このグループ コントロールに関連付けられている子のリストを返します。<br>  |
| [getControl](../interfaces/view-model-control-group-igroup-igroup.md#getcontrol) |getControl(controlName: string): [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md)|コントロールの名前の場合、コントロール インスタンスを返します。<br>  [ContainerControl](../interfaces/view-model-control-container-icontainercontrol-icontainercontrol.md).[getControl](../interfaces/view-model-control-container-icontainercontrol-icontainercontrol.md#getcontrol) から継承 <br> |
| [getControlById](../interfaces/view-model-control-group-igroup-igroup.md#getcontrolbyid) |getControlById(id: string): [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md)|コントロールの ID の場合、コントロール インスタンスを返します。<br>  [ContainerControl](../interfaces/view-model-control-container-icontainercontrol-icontainercontrol.md).[getControlById](../interfaces/view-model-control-container-icontainercontrol-icontainercontrol.md#getcontrolbyid) から継承 <br> |
| [getDesign](../interfaces/view-model-control-group-igroup-igroup.md#getdesign) |getDesign(): [Design](../interfaces/view-model-ipage-idesign.md)|このコントロールのデザイン オブジェクトを返します。<br>  [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md).[getDesign](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md#getdesign) から継承 <br> |
| [isEditable](../interfaces/view-model-control-group-igroup-igroup.md#iseditable) |isEditable(): boolean|コントロールが編集可能かどうかを示すブール値。<br>  [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md).[isEditable](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md#iseditable) から継承 <br> |
| [メタデータ](../interfaces/view-model-control-group-igroup-igroup.md#metadata) |metadata(): [GroupMetadata](../interfaces/view-model-control-group-igroup-igroupmetadata.md)|このコントロールのメタデータ オブジェクトを返します。<br>  [ContainerControl](../interfaces/view-model-control-container-icontainercontrol-icontainercontrol.md).[metadata](../interfaces/view-model-control-container-icontainercontrol-icontainercontrol.md#metadata) をオーバーライドします。 <br> |
| [親](../interfaces/view-model-control-group-igroup-igroup.md#parent) |parent(): [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md) &#124; [Page](../interfaces/view-model-ipage-ipage.md)|このコントロールの親 (コントロールまたはページ) を返します。<br>  [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md).[parent](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md#parent) から継承 <br> |
| [ルート](../interfaces/view-model-control-group-igroup-igroup.md#root) |root(): [Page](../interfaces/view-model-ipage-ipage.md)|このコントロールのルート フォーム インスタンス (ページ) を返します。<br>  [Control](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md).[root](../interfaces/view-model-control-basecontrol-icontrol-icontrol.md#root) から継承 <br> |


### <a name="groupdesign"></a>GroupDesign

#### <a name="hierarchy"></a>階層

[ContainerControlDesign](../interfaces/view-model-control-container-icontainercontrol-icontainercontroldesign.md) <br>&nbsp;&nbsp;&nbsp;└─ GroupDesign <br>

#### <a name="properties"></a>プロパティ

| 氏名 | 署名 | 説明 |
| ---- | --------- | ----------- |
| [alignItems](../interfaces/view-model-control-group-igroup-igroupdesign.md#alignitems) |alignItems: string (optional)  <br>|このプロパティは、CSS プロパティ「align-items」のエイリアスです。<br>  [Design](../interfaces/view-model-ipage-idesign.md).[alignItems](../interfaces/view-model-ipage-idesign.md#alignitems) から継承 <br> |
| [alignSelf](../interfaces/view-model-control-group-igroup-igroupdesign.md#alignself) |alignSelf: string (optional)  <br>|  [Design](../interfaces/view-model-ipage-idesign.md).[alignSelf](../interfaces/view-model-ipage-idesign.md#alignself) から継承 <br> |
| [allowScroll](../interfaces/view-model-control-group-igroup-igroupdesign.md#allowscroll) |allowScroll: string (optional)  <br>|アイテムがコンテナーの空き領域に収まらないときにコンテナーがスクロールできる場合は true です。 コンテナーにスクロール可能なアイテムがある場合、スクロール領域が入れ子にならないように、このプロパティを false に設定します。<br>  [ContainerControlDesign](../interfaces/view-model-control-container-icontainercontrol-icontainercontroldesign.md).[allowScroll](../interfaces/view-model-control-container-icontainercontrol-icontainercontroldesign.md#allowscroll) から継承 <br> |
| [バックグラウンド](../interfaces/view-model-control-group-igroup-igroupdesign.md#background) |background: string (optional)  <br>|コンテナーの背景色。<br>  [ContainerControlDesign](../interfaces/view-model-control-container-icontainercontrol-icontainercontroldesign.md).[background](../interfaces/view-model-control-container-icontainercontrol-icontainercontroldesign.md#background) から継承 <br> |
| [バインディング](../interfaces/view-model-control-group-igroup-igroupdesign.md#bindings) |bindings: any (optional)  <br>|  [Design](../interfaces/view-model-ipage-idesign.md).[bindings](../interfaces/view-model-ipage-idesign.md#bindings) から継承 <br> |
| [枠線](../interfaces/view-model-control-group-igroup-igroupdesign.md#border) |border: "none" &#124; "solid" &#124; "left" &#124; "right" &#124; "top" &#124; "bottom" (optional)  <br>|コントロールの境界動作。 このプロパティは、子によって継承されません。<br>  [Design](../interfaces/view-model-ipage-idesign.md).[border](../interfaces/view-model-ipage-idesign.md#border) から継承 <br> |
| [色](../interfaces/view-model-control-group-igroup-igroupdesign.md#color) |color: string (optional)  <br>|コンテナーの前景色。<br>  [Design](../interfaces/view-model-ipage-idesign.md).[color](../interfaces/view-model-ipage-idesign.md#color) から継承 <br> |
| [flexFlow](../interfaces/view-model-control-group-igroup-igroupdesign.md#flexflow) |flexFlow: string (省略可)  <br>|このプロパティを指定すると、コンポーネントがフレックス コンテナー コンポーネントになります。<br>  [Design](../interfaces/view-model-ipage-idesign.md).[flexFlow](../interfaces/view-model-ipage-idesign.md#flexflow) から継承 <br> |
| [flexSize](../interfaces/view-model-control-group-igroup-igroupdesign.md#flexsize) |flexSize: string (省略可)  <br>|1 つの番号または 2 つの番号が文字列として書き込まれています。 E.g. 「(サイズを拡大) [(サイズの縮小)]」して、即時フレックス コンテナの使用可能領域に対応します。<br>  [Design](../interfaces/view-model-ipage-idesign.md).[flexSize](../interfaces/view-model-ipage-idesign.md#flexsize) から継承 <br> |
| [fontSize](../interfaces/view-model-control-group-igroup-igroupdesign.md#fontsize) |fontSize: "medium" &#124; "xx-small" &#124; "x-small" &#124; "small" &#124; "large" &#124; "x-large" &#124; "xx-large" (省略可)  <br>|比例テキスト サイズ<br>  [Design](../interfaces/view-model-ipage-idesign.md).[fontSize](../interfaces/view-model-ipage-idesign.md#fontsize) から継承 <br> |
| [fontWeight](../interfaces/view-model-control-group-igroup-igroupdesign.md#fontweight) |fontWeight: "normal" &#124; "bold" (省略可)  <br>|標準または太字のテキスト。<br>  [Design](../interfaces/view-model-ipage-idesign.md).[fontWeight](../interfaces/view-model-ipage-idesign.md#fontweight) から継承 <br> |
| [itemBorder](../interfaces/view-model-control-group-igroup-igroupdesign.md#itemborder) |itemBorder: "solid" &#124; "none" (省略可)  <br>|True の場合、リストの各行の周りに境界線が表示されます。<br>  [ContainerControlDesign](../interfaces/view-model-control-container-icontainercontrol-icontainercontroldesign.md).[itemBorder](../interfaces/view-model-control-container-icontainercontrol-icontainercontroldesign.md#itemborder) から継承 <br> |
| [品目](../interfaces/view-model-control-group-igroup-igroupdesign.md#items) |items: string &#124; [Design](../interfaces/view-model-ipage-idesign.md) \[ \] (省略可)  <br>|コンテナーの内部で配置するコンポーネントを含む配列です。<br>  [ContainerControlDesign](../interfaces/view-model-control-container-icontainercontrol-icontainercontroldesign.md).[items](../interfaces/view-model-control-container-icontainercontrol-icontainercontroldesign.md#items) から継承 <br> |
| [justifyItems](../interfaces/view-model-control-group-igroup-igroupdesign.md#justifyitems) |justifyItems: "flex-start" &#124; "flex-end" &#124; "center" &#124; "space-between" (省略可)  <br>|このプロパティは CSS プロパティ「justify-content」のエイリアスです。<br>  [Design](../interfaces/view-model-ipage-idesign.md).[justifyItems](../interfaces/view-model-ipage-idesign.md#justifyitems) から継承 <br> |
| [ラベル](../interfaces/view-model-control-group-igroup-igroupdesign.md#label) |label: string (省略可)  <br>|  [Design](../interfaces/view-model-ipage-idesign.md).[label](../interfaces/view-model-ipage-idesign.md#label) から継承 <br> |
| [labelPosition](../interfaces/view-model-control-group-igroup-igroupdesign.md#labelposition) |labelPosition: "stacked" &#124; "hidden" &#124; "inline" (省略可)  <br>|ラベルの配置方法を決定します (行われる場合)。 既定では、labelPosition が stacked に設定されています。<br>  [Design](../interfaces/view-model-ipage-idesign.md).[labelPosition](../interfaces/view-model-ipage-idesign.md#labelposition) から継承 <br> |
| [名前](../interfaces/view-model-control-group-igroup-igroupdesign.md#name) |name: string (省略可)  <br>|  [Design](../interfaces/view-model-ipage-idesign.md).[name](../interfaces/view-model-ipage-idesign.md#name) から継承 <br> |
| [スペース](../interfaces/view-model-control-group-igroup-igroupdesign.md#padding) |padding: "none" &#124; "small" &#124; "std" (省略可)  <br>|コンポーネントのスペース動作を指定できるように許可します。<br>  [Design](../interfaces/view-model-ipage-idesign.md).[padding](../interfaces/view-model-ipage-idesign.md#padding) から継承 <br> |
| [タイプ](../interfaces/view-model-control-group-igroup-igroupdesign.md#type) |type: [ControlType](view-model-control-basecontrol-icontrol.md#controltype) (省略可)  <br>|文字列としてのコントロールのタイプ。<br>  [Design](../interfaces/view-model-ipage-idesign.md).[type](../interfaces/view-model-ipage-idesign.md#type) から継承 <br> |


### <a name="groupmetadata"></a>GroupMetadata

#### <a name="hierarchy"></a>階層

[ContainerControlMetadata](../interfaces/view-model-control-container-icontainercontrol-icontainercontrolmetadata.md) <br>&nbsp;&nbsp;&nbsp;└─ GroupMetadata <br>

#### <a name="properties"></a>プロパティ

| 氏名 | 署名 | 説明 |
| ---- | --------- | ----------- |
| [BoundEntity](../interfaces/view-model-control-group-igroup-igroupmetadata.md#boundentity) |BoundEntity: 文字列 (オプション)  <br>|コントロールがバインドされるエンティティ。<br>  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[BoundEntity](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#boundentity) から継承 <br> |
| [BoundField](../interfaces/view-model-control-group-igroup-igroupmetadata.md#boundfield) |BoundField: 文字列 (オプション)  <br>|  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[BoundField](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#boundfield) から継承 <br> |
| [子](../interfaces/view-model-control-group-igroup-igroupmetadata.md#children) |子: [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md) \[ \] (オプション)  <br>|各子コントロールの管理メタデータのリスト。<br>  |
| [説明](../interfaces/view-model-control-group-igroup-igroupmetadata.md#description) |説明:文字列 (オプション)  <br>|コントロールの説明。<br>  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[Description](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#description) から継承 <br> |
| [編集可能](../interfaces/view-model-control-group-igroup-igroupmetadata.md#editable) |編集可能: プール値 (省略可)  <br>|コントロールが編集可能かどうかを示すブール値。<br>  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[Editable](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#editable) から継承 <br> |
| [ExtType](../interfaces/view-model-control-group-igroup-igroupmetadata.md#exttype) |ExtType: [ControlType](view-model-control-basecontrol-icontrol.md#controltype) (省略可)  <br>|拡張されたコントロール タイプです。 E.g. コントロール タイプ Input に、拡張タイプ Barcode が含まれる場合があります。<br>  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[ExtType](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#exttype) から継承 <br> |
| [HelpText](../interfaces/view-model-control-group-igroup-igroupmetadata.md#helptext) |HelpText: 文字列 (オプション)  <br>|コマンドのキーボード ショートカットです。 E.g. 「(Shift + F5)」<br>  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[HelpText](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#helptext) から継承 <br> |
| [非表示](../interfaces/view-model-control-group-igroup-igroupmetadata.md#hidden) |非表示: ブール値 (オプション)  <br>|コントロールを非表示にするかどうかを示すブール値。<br>  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[Hidden](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#hidden) から継承 <br> |
| [ID](../interfaces/view-model-control-group-igroup-igroupmetadata.md#id) |Id: string (オプション)  <br>|コントロールの ID 文字列です。<br>  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[Id](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#id) から継承 <br> |
| [ラベル](../interfaces/view-model-control-group-igroup-igroupmetadata.md#label) |ラベル: 文字列 (省略可)  <br>|コントロールのラベル。 E.g. 個人の名を表すコントロールに「氏名」というラベルが付いている場合があります。<br>  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[Label](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#label) から継承 <br> |
| [名前](../interfaces/view-model-control-group-igroup-igroupmetadata.md#name) |Name: 文字列 (省略可)  <br>|コントロールの名前です。<br>  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[Name](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#name) から継承 <br> |
| [注文](../interfaces/view-model-control-group-igroup-igroupmetadata.md#order) |注文: 番号 (オプション)  <br>|コントロールがページに表示される順序を示す番号。<br>  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[Order](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#order) から継承 <br> |
| [[タイプ](../interfaces/view-model-control-group-igroup-igroupmetadata.md#type)] |Type: [ControlType](view-model-control-basecontrol-icontrol.md#controltype) (省略可)  <br>|コントロール タイプを示す文字列。<br>  [ControlMetadata](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md).[Type](../interfaces/view-model-control-basecontrol-icontrol-icontrolmetadata.md#type) から継承 <br> |

