---
title: "製品コンフィギュレーションの計算はよく寄せられる質問をシミュレーションできます。"
description: "この記事では、製品コンフィギュレーション モデルの計算について、制約とともに計算を使用する方法を説明します。"
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PCConstraintEditor, PCProductConfigurationModelDetails, PCRuntimeConfigurator
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19191
ms.assetid: 8993f9a1-d1c0-49f5-afd3-5e1077ded0fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3d02a15387231160f5b8a237aa11008b91ef1223
ms.openlocfilehash: 3a82fdb8532c79e33c167c43554a3de7d3061fcb
ms.lasthandoff: 03/31/2017


---

# <a name="calculations-for-product-configuration-models-faq"></a>製品コンフィギュレーションの計算はよく寄せられる質問をシミュレーションできます。

この記事では、製品コンフィギュレーション モデルの計算について、制約とともに計算を使用する方法を説明します。

計算は、算術または論理工程に使用できます。 これらは、製品コンフィギュレーション モデルの式の制約を補足します。 計算を [**制約ベースの製品コンフィギュレーション モデルの詳細**] ページで定義し、式エディターで計算式を作成できます。 計算の詳細については、「計算の作成」を参照してください。

## <a name="what-is-a-calculation"></a>計算とは
計算とは、製品コンフィギュレーション モデルで使用できる要素のことです。 計算は、製品をコンフィギュレーションする際に、小数を使用した値の計算を可能にして、制約を補完します。 さらに、計算には、制約よりも多くの演算子を使用できます。  

制約と同様に、計算は、製品コンフィギュレーション モデルの特定のコンポーネントに関連付けられ、別のコンポーネントが再利用することも共有することもできません。 計算と制約の重要な違いの 1 つは、計算は必須 (単一方向) で、制約は宣言です (双方向)。 制約に関する詳細については、「[式の制約およびテーブル制約](expression-constraints-table-constraints-product-configuration-models.md)」を参照してください。  

計算は、ターゲット属性と計算式で構成されます。

## <a name="what-is-a-target-attribute"></a>ターゲット属性とは
ターゲット属性とは、計算式の結果を受け取る属性のことです。  

次の式で、ターゲット属性はテーブルクロスの測定です:  

**式: **\[decimalAttribute1 = &lt;decimalAttribute2は、trueの、falseの\]  

** DecimalAttribute1 **表の期間があり、** decimalAttribute2 **テーブルクロスの期間です。 この式は、**decimalAttribute2** が **decimalAttribute1** より大きいか等しい場合は **True** 値をターゲット属性に返します。 それ以外の場合は、**False** が返されます。 したがって、テーブルクロスの測定は、テーブルクロスの長さがテーブルの長さに等しいかまたは超える場合に受け入れることができます。

## <a name="what-attribute-types-can-be-set-to-target-attributes"></a>ターゲット属性に設定できるのはどの属性タイプか
固定リストのないテキストを除いて、製品コンフィギュレーターでサポートされているすべての属性タイプはターゲット属性に設定できます。

## <a name="can-the-value-of-a-target-attribute-restrict-the-values-of-the-input-attributes-in-a-calculation"></a>ターゲット属性の値は計算の入力属性の値を制限できますか
計算は一方向なので、ターゲット属性の値は入力属性の値を制限できません。 したがって、入力属性値の変更に基づいてターゲット属性の値が設定されますが、ターゲットの値を変更しても入力属性の値には影響しません。 この動作は制約の動作とは異なります。 制約は両方の方向で行います。

### <a name="example"></a>例

次の式で、計算のターゲットに電源コードの期間であり、入力値は、色があります:  

**式: ** \[色の場合== 「の」、1.5、1.0\]  

品目のコンフィギュレーション時に、能力コードの期間は** **の指定する**色属性値として、** 1.5に設定されます。 他の色を指定した場合、長さは **1.0** に設定されます。 ただし、計算は一方向なので、**1.5** の長さを指定するとき、計算では色の属性値は [**緑**] に設定されません。

## <a name="what-happens-if-a-calculation-has-a-target-attribute-of-the-integer-type-but-a-calculation-generates-a-decimal-number"></a>計算のターゲット属性が整数タイプで、計算で小数を生成するとき、何が起きますか
ターゲットの属性が整数タイプで、計算が小数を生成した場合、計算結果の整数部分だけが返されます。 小数部分は削除され、結果を丸められません。 たとえば、12.70 の結果は 12 として表示されます。

## <a name="when-do-calculations-occur"></a>計算はいつ発生しますか
計算は、すべて入力属性の値が用意されたときに発生します。

## <a name="can-i-overwrite-the-value-that-is-calculated-for-the-target-attribute"></a>ターゲット属性に対して計算された値を上書きできますか
ターゲット属性が非表示または読み取り専用に設定されていなければ、ターゲット属性に対して計算された値を上書きできます。

## <a name="how-do-i-set-a-target-attribute-as-hidden-or-readonly"></a>どのように非表示のように、対象の属性の値を読み取り専用設定しますか。
属性を非表示または読み取り専用に設定するには、次の手順に従います。

1.  [**製品情報管理** &gt; **普通** &gt; **製品コンフィギュレーションは、シミュレーション**。
2.  製品コンフィギュレーション モデルを選択し、[アクション ペイン] で、[**編集**] をクリックします。
3.  [**制約ベースの製品コンフィギュレーション モデルの詳細**] ページで、ターゲット属性として使用する属性を選択します。
4.  [**属性**] クイック タブで、[**非表示**] または [**読み取り専用**] を選択します。

## <a name="can-a-calculation-overwrite-the-values-that-i-set"></a>計算はユーザーが設定した値を上書きできますか
一連番号 製品を設定するときに設定する値が使用される金額です。 計算の入力値を変更したときに行われる計算は、特定の属性に対して与えた値を上書きすることはできません。

## <a name="what-happens-if-i-remove-an-input-value-in-a-calculation"></a>計算の入力値を削除すると、何が発生しますか
計算の入力値を削除すると、ターゲット属性の値も削除されます。

## <a name="why-do-i-receive-an-error-message-that-says-that-my-model-is-in-contradiction"></a>自分のモデルが矛盾しているというエラー メッセージが表示される理由は
このメッセージは、計算にエラーがあるか、または矛盾が 1 つ以上の制約に存在する場合に表示されます。 制約での矛盾の詳細については、「[式の制約およびテーブル制約](expression-constraints-table-constraints-product-configuration-models.md)」を参照してください。 次に、計算でエラーが発生する状況を示します。

-   値を 0 (ゼロ) で割る。
-   次の 2 つの要素間に不一致が存在する。
    -   属性に対して使用できて、制約によって限定されている値。
    -   計算によって生成される値
-   計算によって返される値が属性の範囲外にある。 たとえば、0に計算される \[1..10\] の整数です。

## <a name="why-do-i-receive-an-error-message-even-though-i-successfully-validated-my-product-model"></a>自分のプロダクト モデルの検証に成功しても、エラー メッセージが出力される理由は
計算は検証に含まれていません。 計算エラーを探すには、製品コンフィギュレーション モデルをテストする必要があります。 製品コンフィギュレーション モデルをテストするには、次の手順に従います。

1.  [**製品情報管理** &gt; **普通** &gt; **製品コンフィギュレーションは、シミュレーション**。
2.  製品コンフィギュレーション モデルを選択し、[アクション ペイン] で、[**実行**] グループ内の [**テスト**] をクリックします。


