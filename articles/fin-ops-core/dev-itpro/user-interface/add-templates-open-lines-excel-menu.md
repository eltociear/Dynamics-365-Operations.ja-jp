---
title: '[Excel で明細行を開く] メニューへのテンプレートの追加'
description: このトピックでは、仕訳帳のページで利用できる [Excel] メニューの [Open] 行にテンプレートを表示させる方法について説明します。
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Developer
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 77432
ms.assetid: 9793bf54-cfb8-4ba1-bc8f-ba49ef37884a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 29fdb629c5c34a533683a280fb011f8fa712dcdf
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025817"
---
# <a name="add-templates-to-the-open-lines-in-excel-menu"></a>[Excel で明細行を開く] メニューへのテンプレートの追加

[!include [banner](../includes/banner.md)]

このトピックでは、仕訳帳のページで利用できる [Excel] メニューの [Open] 行にテンプレートを表示させる方法について説明します。

頻繁に使用される一部のテンプレートは、仕訳帳テンプレートです。 これらの仕訳帳テンプレートの一部はプロモーションされたため、**Excel で明細行を開く** メニューに既定で表示されます。 しかし、システムに新しいテンプレートを追加するときに、既定では、**Office で開く** メニューで利用可能です。 テンプレートを **Excel で行を開く** メニューで利用できるようにするには、次の手順に従います。

1.  Microsoft Excel テンプレートを作成し、ローカルに保存します。 詳細については、「Excel で開くエクスペリエンスの作成」の記事を参照してください。

2.  Microsoft Visual Studio で、ApplicationSuite モデルへの参照を含むモデルに新しいプロジェクトを作成します。 

       [![Visual Studio で新しいプロジェクトを作成する](./media/110-1024x523.png)](./media/110.png)

3.  新しいクラスを作成し、**LedgerIJournalExcelTemplate** インターフェイスを実装し、**DocuTemplateRegistrationBase** を拡張します。 実装 (仕訳帳タイプなどによってサポートされる) では、「Excel で開く」エクスペリエンスで、テンプレートをオプションとして使用できるコンテキストが定義されます。 この例では、LedgerJournalHeaderEntity と LedgerJournalLineEntity を使用していますが、これらのエンティティに限定されません。 エンティティが仕訳帳ヘッダー/明細行のエンティティ パターンに従うという条件で、自分自身のエンティティを定義することができます。 **LedgerDailyJournalExcelTemplate** クラスからの例を次に示します。

    ```xpp
    using Microsoft.Dynamics.Platform.Integration.Office;  
    public class TestNewTemplate extends DocuTemplateRegistrationBase implements LedgerIJournalExcelTemplate
    {
        private const DocuTemplateName ExcelTemplateName = resourceStr(TestNewTemplate);
        private const EntityName LineEntityName = tableStr(LedgerJournalLineEntity);
        private const FieldName LineEntityJournalNum = fieldStr(LedgerJournalLineEntity, JournalBatchNumber);
        private const FieldName LineEntityDataAreaId = fieldStr(LedgerJournalLineEntity, dataAreaId);
        private const FieldName HeaderEntityName = tableStr(LedgerJournalHeaderEntity);
        private const FieldName HeaderEntityJournalNum = fieldStr(LedgerJournalHeaderEntity, JournalBatchNumber);
        private const FieldName HeaderEntityDataAreaId = fieldStr(LedgerJournalHeaderEntity, dataAreaId);
        /// <summary>
        /// A boolean value which indicates whether the journal type is supported for the Excel template.
        /// </summary>
        /// <param name = "_ledgerJournalType">The ledger journal type.</param>
        /// <returns>True if the journal type is supported; otherwise, false.</returns>
        public boolean isJournalTypeSupported(LedgerJournalType _ledgerJournalType)
        {
            return _ledgerJournalType == LedgerJournalType::Daily;
        }
        /// <summary>
        /// Gets the document template name.
        /// </summary>
        /// <returns>The document template name</returns>
        public DocuTemplateName documentTemplateName()
        {
            return ExcelTemplateName;
        }
        /// <summary>
        /// Gets a collection of the supported account types for the entity.
        /// </summary>
        /// <returns>A collection of <c>LedgerJournalACType</c> values.</returns>
        public Set supportedAccountTypes()
        {
            Set accountTypeSet = new Set(Types::Integer);
            accountTypeSet.add(LedgerJournalACType::Ledger);
            return accountTypeSet;
        }
        /// <summary>
        /// Gets a collection of the supported offset account types for the entity.
        /// </summary>
        /// <returns>A collection of <c>LedgerJournalACType</c> values.</returns>
        public Set supportedOffsetAccountTypes()
        {
            Set offsetAccountTypeSet = new Set(Types::Integer);
            offsetAccountTypeSet.add(LedgerJournalACType::Ledger);
            return offsetAccountTypeSet;
        }
        /// <summary>
        /// Validates the journal is valid for the template.
        /// </summary>
        /// <param name = "_ledgerJournalTable">The <c>LedgerJournalTable</c> record.</param>
        /// <returns>True if the journal is valid for the template; otherwise, false.</returns>
        public boolean validateJournalForTemplate(LedgerJournalTable _ledgerJournalTable)
        {
            return LedgerJournalExcelTemplate::validateJournalForTemplate(_ledgerJournalTable, this);
        }
        public void registerTemplates()
        {
            this.addTemplate(
                OfficeAppApplicationType::Excel,
                ExcelTemplateName,
                ExcelTemplateName,
                'Test new template',
                'Test new template',
                NoYes::No,
                NoYes::No,
                NoYes::No);
        }
        /// <summary>
        /// The resource name of the header entity.
        /// </summary>
        /// <returns>The resource name of the header entity.</returns>
        public EntityName headerEntityName()
        {
            return HeaderEntityName;
        }
        /// <summary>
        /// The resource name of the line entity.
        /// </summary>
        /// <returns>The resource name of the line entity.</returns>
        public EntityName lineEntityName()
        {
            return LineEntityName;
        }
        /// <summary>
        /// The field name for the header journal batch number.
        /// </summary>
        /// <returns>The field name for the header journal batch number.</returns>
        public FieldName headerJournalBatchNumberFieldName()
        {
            return HeaderEntityJournalNum;
        }
        /// <summary>
        /// The field name for the header data area.
        /// </summary>
        /// <returns>The field name for the header data area.</returns>
        public FieldName headerDataAreaFieldName()
        {
            return HeaderEntityDataAreaId;
        }
        /// <summary>
        /// The field name for the line journal batch number.
        /// </summary>
        /// <returns>The field name for the line journal batch number.</returns>
        public FieldName lineJournalBatchNumberFieldName()
        {
            return LineEntityJournalNum;
        }
        /// <summary>
        /// The field name for the line data area.
        /// </summary>
        /// <returns>The field name for the line data area.</returns>
        public FieldName lineDataAreaFieldName()
        {
            return LineEntityDataAreaId;
        }
        /// <summary>
        /// Append additional filter to the default filtering behavior.
        /// </summary>
        /// <returns>The original filter with new filter(s) appended; Otherwise, the original filter</returns>
        public FilterCollectionNode appendHeaderEntityFilters(FilterCollectionNode _headerFilter, ExportToExcelFilterTreeBuilder _headerFilterBuilder)
        {
            return _headerFilter;
        }
        /// <summary>
        /// Append additional filter to the default filtering behavior.
        /// </summary>
        /// <returns>The original filter with new filter(s) appended; Otherwise, the original filter</returns>
        public FilterCollectionNode appendLineEntityFilters(FilterCollectionNode _lineFilter, ExportToExcelFilterTreeBuilder _lineFilterBuilder)
        {
            FilterCollectionNode lineFilter = _lineFilterBuilder.and(
                _lineFilterBuilder.areEqual(fieldStr(LedgerJournalLineEntity, AccountType), LedgerJournalACType::Ledger),
                _lineFilterBuilder.areEqual(fieldStr(LedgerJournalLineEntity, OffsetAccountType), LedgerJournalACType::Ledger));
            return _lineFilterBuilder.and(_lineFilter, lineFilter);
        }
    }
    ```

4.  新しいリソースを含むプロジェクト/モデルを構築します。 新しいリソース 1 つと、新しいクラス 1 つが必要です。 

       [![構築されたプロジェクト](./media/22.png)](./media/22.png)

5.  クライアントで、**共通** &gt; **共通** &gt; **Office 統合** &gt; **ドキュメント テンプレート** &gt; **システム テンプレートの再読み込み**と移動します。 一覧に新しいテンプレートが表示され、そのテンプレートを仕訳帳ページに追加した場合、そのテンプレートは **Excel で明細行を開く** メニューにも表示されます。


<a name="additional-resources"></a>その他のリソース
--------

[[Excel で開く] エクスペリエンスの作成](../office-integration/office-integration-edit-excel.md)



