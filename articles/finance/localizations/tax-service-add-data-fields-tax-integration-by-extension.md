---
title: 확장을 사용하여 세금 통합에 데이터 필드 추가
description: 이 항목에서는 X++ 확장을 사용하여 세금 통합에서 데이터 필드를 추가하는 방법을 설명합니다.
author: qire
ms.date: 02/17/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: acbe8070424febf24883362448ea56857d9d72d9
ms.sourcegitcommit: 68114cc54af88be9a3a1a368d5964876e68e8c60
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2022
ms.locfileid: "8451627"
---
# <a name="add-data-fields-in-the-tax-integration-by-using-extension"></a>확장을 사용하여 세금 통합에 데이터 필드 추가

[!include [banner](../includes/banner.md)]


이 항목에서는 X++ 확장을 사용하여 세금 통합에서 데이터 필드를 추가하는 방법을 설명합니다. 이러한 필드는 세금 서비스의 세금 데이터 모델로 확장할 수 있으며 세금 코드를 결정하는 데 사용할 수 있습니다. 자세한 내용은 [세금 구성에 데이터 필드 추가](tax-service-add-data-fields-tax-configurations.md)를 참고하세요.

## <a name="data-model"></a>데이터 모델

데이터 모델의 데이터는 개체로 전달되고 클래스로 구현됩니다.

다음은 주요 개체 목록입니다.

* AxClass/TaxIntegration **Document** Object
* AxClass/TaxIntegration **Line** Object
* AxClass/TaxIntegration **TaxLine** Object

다음 그림은 이러한 개체가 어떻게 연관되어 있는지 보여줍니다.

[![데이터 모델 개체 관계.](./media/tax-service-customize-image1.png)](./media/tax-service-customize-image1.png)

**문서** 개체는 여러 **라인** 개체를 포함할 수 있습니다. 각 개체에는 세금 서비스에 대한 메타데이터가 포함되어 있습니다.

- `TaxIntegrationDocumentObject`에는 원본 주소에 대한 정보가 포함된 `originAddress` 메타데이터와 라인 금액에 판매세가 포함되는지를 나타내는 `includingTax` 메타데이터가 있습니다.
- `TaxIntegrationLineObject`에는 `itemId`, `quantity`, `categoryId` 메타데이터가 있습니다.

> [!NOTE]
> `TaxIntegrationLineObject`는 또한 **요금** 개체를 구현합니다.

## <a name="integration-flow"></a>통합 흐름

흐름의 데이터는 활동에 의해 조작됩니다.

### <a name="key-activities"></a>핵심 활동

* AxClass/TaxIntegration **Calculation** ActivityOnDocument
* AxClass/TaxIntegration **CurrencyExchange** ActivityOnDocument
* AxClass/TaxIntegration **DataPersistence** ActivityOnDocument
* AxClass/TaxIntegration **DataRetrieval** ActivityOnDocument
* AxClass/TaxIntegration **SettingRetrieval** ActivityOnDocument

활동은 다음 순서로 실행됩니다.

1. 설정 검색
2. 데이터 검색
3. 서비스 계산
4. 통화 환율
5. 데이터 지속성

예를 들어 **계산 서비스** 전에 **데이터 검색** 을 확장합니다.

#### <a name="data-retrieval-activities"></a>데이터 검색 활동

**데이터 검색** 활동은 데이터베이스에서 데이터를 검색합니다. 다른 거래를 위한 어댑터를 사용하여 다른 거래 테이블에서 데이터를 검색할 수 있습니다.

- AxClass/TaxIntegration **PurchTable** DataRetrieval
- AxClass/TaxIntegration **PurchParmTable** DataRetrieval
- AxClass/TaxIntegration **PurchREQTable** DataRetrieval
- AxClass/TaxIntegration **PurchRFQTable** DataRetrieval
- AxClass/TaxIntegration **VendInvoiceInfoTable** DataRetrieval
- AxClass/TaxIntegration **SalesTable** DataRetrieval
- AxClass/TaxIntegration **SalesParm** DataRetrieval

이러한 **데이터 검색** 활동에서 데이터는 데이터베이스에서 `TaxIntegrationDocumentObject` 및 `TaxIntegrationLineObject`로 복사됩니다. 이러한 모든 활동은 같은 추상 템플릿 클래스를 확장하므로 공통 메서드가 있습니다.

#### <a name="calculation-service-activities"></a>계산 서비스 활동

**계산 서비스** 활동은 세금 서비스와 세금 통합 간의 연결입니다. 이 활동은 다음 기능을 담당합니다.

1. 요청을 구성합니다.
2. 세금 서비스에 요청을 게시합니다.
3. 세금 서비스에서 응답을 받습니다.
4. 응답을 구문 분석합니다.

요청에 추가하는 데이터 필드는 다른 메타데이터와 함께 게시됩니다. 

## <a name="extension-implementation"></a>확장 구현

이 섹션에서는 확장을 구현하는 방법을 설명하는 자세한 단계를 제공합니다. **비용 센터** 및 **프로젝트** 재무 차원을 예로 사용합니다.

### <a name="step-1-add-the-data-variable-in-the-object-class"></a>1단계. 개체 클래스에 데이터 변수 추가

개체 클래스에는 데이터 변수와 데이터에 대한 getter/setter 메서드가 포함됩니다. 필드의 수준에 따라 `TaxIntegrationDocumentObject` 또는 `TaxIntegrationLineObject`에 데이터 필드를 추가합니다. 다음 예는 라인 수준을 사용하며 파일 이름은 `TaxIntegrationLineObject_Extension.xpp`입니다.

> [!NOTE]
> 추가하는 데이터 필드가 문서 수준인 경우 파일 이름을 `TaxIntegrationDocumentObject_Extension.xpp`로 변경합니다.

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

**비용 센터** 와 **프로젝트** 는 전용 변수로 추가됩니다. 데이터를 조작하기 위해 이러한 데이터 필드에 대한 getter 및 setter 메서드를 만듭니다.

### <a name="step-2-retrieve-data-from-the-database"></a>2단계. 데이터베이스에서 데이터 검색

거래를 지정하고 적절한 어댑터 클래스를 확장하여 데이터를 검색합니다. 예를 들어 **구매 주문** 거래를 사용하는 경우 `TaxIntegrationPurchTableDataRetrieval` 및 `TaxIntegrationVendInvoiceInfoTableDataRetrieval`을 확장해야 합니다. 

> [!NOTE]
> `TaxIntegrationPurchParmTableDataRetrieval`은 `TaxIntegrationPurchTableDataRetrieval`에서 상속됩니다. `purchTable` 및 `purchParmTable` 테이블의 논리가 다른 경우가 아니면 변경하면 안 됩니다.

모든 거래에 대해 데이터 필드를 추가해야 하는 경우 모든 `DataRetrieval` 클래스를 확장합니다.

모든 **데이터 검색** 활동은 같은 템플릿 클래스를 확장하므로 클래스 구조, 변수, 메서드가 비슷합니다.

```X++
protected TaxIntegrationDocumentObject document;

/// <summary>
/// Copies to the document.
/// </summary>
protected abstract void copyToDocument()
{
    // It is recommended to implement as:
    //
    // this.copyToDocumentByDefault();
    // this.copyToDocumentFromHeaderTable();
    // this.copyAddressToDocument();
}
 
/// <summary>
/// Copies to the current line of the document.
/// </summary>
/// <param name = "_line">The current line of the document.</param>
protected abstract void copyToLine(TaxIntegrationLineObject _line)
{
    // It is recommended to implement as:
    //
    // this.copyToLineByDefault(_line);
    // this.copyToLineFromLineTable(_line);
    // this.copyQuantityAndTransactionAmountToLine(_line);
    // this.copyAddressToLine(_line);
    // this.copyToLineFromHeaderTable(_line);
}
```

다음 예제는 `PurchTable` 테이블을 사용할 때의 기본 구조를 보여줍니다.

```X++
public class TaxIntegrationPurchTableDataRetrieval extends TaxIntegrationAbstractDataRetrievalTemplate
{
    protected PurchTable purchTable;
    protected PurchLine purchLine;

    // Query builder methods
    [Replaceable]
    protected SysDaQueryObject getDocumentQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineQueryObject()
    [Replaceable]
    protected SysDaQueryObject getDocumentChargeQueryObject()
    [Replaceable]
    protected SysDaQueryObject getLineChargeQueryObject()

    // Data retrieval methods
    protected void copyToDocument()
    protected void copyToDocumentFromHeaderTable()
    protected void copyToLine(TaxIntegrationLineObject _line)
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    ...
}
```

`CopyToDocument` 메소드가 호출되면`this.purchTable` 버퍼가 이미 존재합니다. 이 메서드의 목적은 `DocumentObject` 클래스에서 생성된 setter 메서드를 사용하여 `this.purchTable`에서 `document` 개체로 필요한 모든 데이터를 복사하는 것입니다.

비슷하게 `this.purchLine` 버퍼는 `CopyToLine` 메서드에 이미 존재합니다. 이 메서드의 목적은 `LineObject` 클래스에서 생성된 setter 메서드를 사용하여 `this.purchLine`에서 `_line` 개체로 필요한 모든 데이터를 복사하는 것입니다.

가장 간단한 접근 방식은 `CopyToDocument` 및 `CopyToLine` 메서드를 확장하는 것입니다. 그러나 먼저 `copyToDocumentFromHeaderTable` 및 `copyToLineFromLineTable` 메소드를 사용해보는 것이 좋습니다. 원하는 대로 작동하지 않으면 직접 메서드를 구현하고 `CopyToDocument` 및 `CopyToLine`에서 호출하세요. 이 접근 방식을 사용할 수 있는 세 가지 일반적인 상황이 있습니다.

- 필수 필드는 `PurchTable` 또는 `PurchLine`에 있습니다. 이 상황에서 `copyToDocumentFromHeaderTable` 및 `copyToLineFromLineTable`을 확장할 수 있습니다. 다음은 샘플 코드입니다.

    ```X++
    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        next copyToLineFromLineTable(_line);
        // if we already added XXX in TaxIntegrationLineObject
        _line.setXXX(this.purchLine.XXX);
    }
    ```

- 필수 데이터가 거래의 기본 테이블에 없습니다. 그러나 기본 테이블과 일부 조인 관계가 있으며 필드는 대부분의 라인에 필요합니다. 이 경우 `getDocumentQueryObject` 또는 `getLineObject`를 대체하여 조인 관계로 테이블을 쿼리합니다. 다음 예에서 **지금 배달** 필드는 라인 수준에서 판매 주문과 통합됩니다.

    ```X++
    public class TaxIntegrationSalesTableDataRetrieval
    {
        protected MCRSalesLineDropShipment mcrSalesLineDropShipment;

        /// <summary>
        /// Gets the query for the lines of the document.
        /// </summary>
        /// <returns>The query for the lines of the document</returns>
        [Replaceable]
        protected SysDaQueryObject getLineQueryObject()
        {
            return SysDaQueryObjectBuilder::from(this.salesLine)
                .where(this.salesLine, fieldStr(SalesLine, SalesId)).isEqualToLiteral(this.salesTable.SalesId)
                .outerJoin(this.mcrSalesLineDropShipment)
                .where(this.mcrSalesLineDropShipment, fieldStr(MCRSalesLineDropShipment, SalesLine)).isEqualTo(this.salesLine, fieldStr(SalesLine, RecId))
                .toSysDaQueryObject();
        }
    }
    ```

    이 예에서는 `mcrSalesLineDropShipment` 버퍼가 선언되었고 쿼리는 `getLineQueryObject`에 정의되어 있습니다. 쿼리는 관계 `MCRSalesLineDropShipment.SalesLine == SalesLine.RecId`를 사용합니다. 이 상황에서 확장하는 동안 `getLineQueryObject`를 자신이 만든 쿼리 개체로 바꿀 수 있습니다. 그러나 다음 사항을 확인하세요.

    * `getLineQueryObject` 메서드의 반환 값은 `SysDaQueryObject`이므로 SysDa 접근 방식을 사용하여 이 개체를 구성해야 합니다.
    * 기존 테이블은 제거할 수 없습니다.

- 필요한 데이터가 거래 테이블과 복잡한 조인 관계로 연결되거나 관계가 일대일(1:1)이 아닌 일대다(1:N) 관계입니다. 이 경우에서는 상황이 조금 복잡합니다. 이 상황은 재무 차원의 예에 적용됩니다. 

    이 상황에서 데이터를 검색하는 메서드를 직접 구현할 수 있습니다. 다음은 `TaxIntegrationPurchTableDataRetrieval_Extension.xpp` 파일에 있는 샘플 코드입니다.

    ```X++
    [ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
    final class TaxIntegrationPurchTableDataRetrieval_Extension
    {
        private const str CostCenterKey = 'CostCenter';
        private const str ProjectKey = 'Project';

        /// <summary>
        /// Copies to the current line of the document from.
        /// </summary>
        /// <param name = "_line">The current line of the document.</param>
        protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
        {
            Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
            if (dimensionAttributeMap.exists(CostCenterKey))
            {
                _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
            }
            if (dimensionAttributeMap.exists(ProjectKey))
            {
                _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
            }
            next copyToLineFromLineTable(_line);
        }
        private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
        {
            DimensionAttribute dimensionAttribute;
            DimensionAttributeValue dimensionAttributeValue;
            DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
            Map ret = new Map(Types::String, Types::String);

            select Name, RecId from dimensionAttribute
                join dimensionAttributeValue
                    where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
                join DimensionAttributeValueSetItem
                    where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                        && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;

            while(dimensionAttribute.RecId)
            {
                ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
                next dimensionAttribute;
            }
            return ret;
        }
    }
    ```

### <a name="step-3-add-data-to-the-request"></a>3단계. 요청에 데이터 추가

요청에 데이터를 추가하려면 `copyToTaxableDocumentHeaderWrapperFromTaxIntegrationDocumentObject` 또는 `copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine` 메서드를 확장합니다. 다음은 `TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp` 파일에 있는 샘플 코드입니다.

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```

이 코드에서 `_destination`은 게시 요청을 생성하는 데 사용되는 래퍼 개체이고 `_source`는 `TaxIntegrationLineObject` 개체입니다.

> [!NOTE]
> 요청 양식에 사용되는 키를 **private const str** 으로 정의합니다. 문자열은 [세금 구성에 데이터 필드 추가](tax-service-add-data-fields-tax-configurations.md) 항목에 추가된 측정값 이름과 정확히 같아야 합니다.
> **SetField** 메서드를 사용하여 **copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine** 메서드의 필드를 설정합니다. 두 번째 매개 변수의 데이터 형식은 **문자열** 이어야 합니다. 데이터 형식이 **문자열** 이 아닌 경우 변환합니다.
> X++ **열거형** 이 확장된 경우 해당 값, 레이블 및 이름의 차이를 확인합니다.
> 
>   - 열거형의 값은 정수입니다.
>   - 열거형의 레이블은 기본 설정 언어에 따라 다를 수 있습니다. 열거형을 문자열로 변환하기 위해 **enum2Str** 을 사용하지 마세요.
>   - 열거형의 이름은 고정되어 있으므로 권장됩니다. **enum2Symbol** 은 열거형을 해당 이름으로 변환하는 데 사용할 수 있습니다. 세금 구성에 추가된 열거형 값은 열거형 이름과 정확히 같아야 합니다.

## <a name="model-dependency"></a>모델 종속성

프로젝트를 성공적으로 빌드하려면 모델 종속성에 다음 참조 모델을 추가합니다.

- ApplicationPlatform
- ApplicationSuite
- 세금 엔진
- 차원(재무 차원이 사용되는 경우)
- 코드에서 참조되는 기타 필요한 모델

## <a name="validation"></a>유효성 검사

이전 단계를 완료한 후 변경 사항의 유효성을 검사할 수 있습니다.

1. Finance에서 **지급 계정** 으로 이동하고 URL에 **&debug=vs%2CconfirmExit&** 를 추가합니다. 예: https://usnconeboxax1aos.cloud.onebox.dynamics.com/?cmp=DEMF&mi=PurchTableListPage&debug=vs%2CconfirmExit&. 마지막 **&** 는 필수입니다.
2. **구매 주문** 페이지를 열고 **새로 만들기** 를 선택하여 구매 주문을 만듭니다.
3. 사용자 지정 필드의 값을 설정한 다음 **판매세** 를 선택합니다. 접두사가 **TaxServiceTroubleshootingLog** 인 문제 해결 파일이 자동으로 다운로드됩니다. 이 파일에는 세금 계산 서비스에 게시된 거래 정보가 포함되어 있습니다. 
4. 추가된 사용자 지정 필드가 **세금 서비스 계산 입력 JSON** 섹션에 존재하고 값이 올바른지 확인합니다. 값이 올바르지 않으면 이 문서의 단계를 다시 확인하세요.

파일 예:

```
===Tax service calculation input JSON:===
{
  "TaxableDocument": {
    "Header": [
      {
        "Lines": [
          {
            "Line Type": "Normal",
            "Item Code": "",
            "Item Type": "Item",
            "Quantity": 0.0,
            "Amount": 1000.0,
            "Currency": "EUR",
            "Transaction Date": "2022-1-26T00:00:00",
            ...
            /// The new fields added at line level
            "Cost Center": "003",
            "Project": "Proj-123"
          }
        ],
        "Amount include tax": true,
        "Business Process": "Journal",
        "Currency": "",
        "Vendor Account": "DE-001",
        "Vendor Invoice Account": "DE-001",
        ...
        // The new fields added at header level, no new fields in this example
        ...
      }
    ]
  },
}
...
```

## <a name="appendix"></a>부록

이 부록은 재무 차원, **비용 센터** 및 **프로젝트** 를 라인 수준에서 통합하기 위한 전체 샘플 코드를 보여줍니다.

### <a name="taxintegrationlineobject_extensionxpp"></a>TaxIntegrationLineObject_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationLineObject))]
final class TaxIntegrationLineObject_Extension
{
    private OMOperatingUnitNumber costCenter;
    private ProjId projectId;

    /// <summary>
    /// Gets a costCenter.
    /// </summary>
    /// <returns>The cost center.</returns>
    public final OMOperatingUnitNumber getCostCenter()
    {
        return this.costCenter;
    }

    /// <summary>
    /// Sets the cost center.
    /// </summary>
    /// <param name = "_value">The cost center.</param>
    public final void setCostCenter(OMOperatingUnitNumber _value)
    {
        this.costCenter = _value;
    }

    /// <summary>
    /// Gets a project ID.
    /// </summary>
    /// <returns>The project ID.</returns>
    public final ProjId getProjectId()
    {
        return this.projectId;
    }

    /// <summary>
    /// Sets the project ID.
    /// </summary>
    /// <param name = "_value">The project ID.</param>
    public final void setProjectId(ProjId _value)
    {
        this.projectId = _value;
    }
}
```

### <a name="taxintegrationpurchtabledataretrieval_extensionxpp"></a>TaxIntegrationPurchTableDataRetrieval_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationPurchTableDataRetrieval))]
final class TaxIntegrationPurchTableDataRetrieval_Extension
{
    private const str CostCenterKey = 'CostCenter';
    private const str ProjectKey = 'Project';

    /// <summary>
    /// Copies to the current line of the document from.
    /// </summary>
    /// <param name = "_line">The current line of the document.</param>
    protected void copyToLineFromLineTable(TaxIntegrationLineObject _line)
    {
        Map dimensionAttributeMap = this.getDimensionAttributeMapByDefaultDimension(this.purchline.DefaultDimension);
        if (dimensionAttributeMap.exists(CostCenterKey))
        {
            _line.setCostCenter(dimensionAttributeMap.lookup(CostCenterKey));
        }
        if (dimensionAttributeMap.exists(ProjectKey))
        {
            _line.setProjectId(dimensionAttributeMap.lookup(ProjectKey));
        }
        next copyToLineFromLineTable(_line);
    }
    private Map getDimensionAttributeMapByDefaultDimension(RefRecId _defaultDimension)
    {
        DimensionAttribute dimensionAttribute;
        DimensionAttributeValue dimensionAttributeValue;
        DimensionAttributeValueSetItem dimensionAttributeValueSetItem;
        Map ret = new Map(Types::String, Types::String);
        select Name, RecId from dimensionAttribute
            join dimensionAttributeValue
                where dimensionAttributeValue.dimensionAttribute == dimensionAttribute.RecId
            join DimensionAttributeValueSetItem
                where DimensionAttributeValueSetItem.DimensionAttributeValue == DimensionAttributeValue.RecId
                    && DimensionAttributeValueSetItem.DimensionAttributeValueSet == _defaultDimension;
        while(dimensionAttribute.RecId)
        {
            ret.insert(dimensionAttribute.Name, dimensionAttributeValue.DisplayValue);
            next dimensionAttribute;
        }
        return ret;
    }
}
```

### <a name="taxintegrationcalculationactivityondocument_calculationservice_extensionxpp"></a>TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension.xpp

```X++
[ExtensionOf(classStr(TaxIntegrationCalculationActivityOnDocument_CalculationService))]
final static class TaxIntegrationCalculationActivityOnDocument_CalculationService_Extension
{
    // Define key for the form in post request
    private const str IOCostCenter = 'Cost Center';
    private const str IOProject = 'Project';

    /// <summary>
    /// Copies to <c>TaxableDocumentLineWrapper</c> from <c>TaxIntegrationLineObject</c> by line.
    /// </summary>
    /// <param name = "_destination"><c>TaxableDocumentLineWrapper</c>.</param>
    /// <param name = "_source"><c>TaxIntegrationLineObject</c>.</param>
    protected static void copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(Microsoft.Dynamics.TaxCalculation.ApiContracts.TaxableDocumentLineWrapper _destination, TaxIntegrationLineObject _source)
    {
        next copyToTaxableDocumentLineWrapperFromTaxIntegrationLineObjectByLine(_destination, _source);
        // Set the field we need to integrated for tax service
        _destination.SetField(IOCostCenter, _source.getCostCenter());
        _destination.SetField(IOProject, _source.getProjectId());
    }
}
```
