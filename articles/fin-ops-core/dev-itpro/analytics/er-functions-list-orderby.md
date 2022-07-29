---
title: ORDERBY ER 함수
description: 이번에는 ORDERBY 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 963d55bcf98a9109c8b6ceb57edf5b55f15a2b0f
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460794"
---
# <a name="orderby-er-function"></a>ORDERBY ER 함수

[!include [banner](../includes/banner.md)]

`ORDERBY` 함수는 지정된 인수에 따라 정렬된 후 지정된 목록을 *기록 목록* 값으로 반환합니다. 이러한 인수는 표현식으로 정의할 수 있습니다.

## <a name="syntax-1"></a><a name="syntax-1"></a>구문 1

```vb
ORDERBY (list, expression 1[, expression 2, …, expression N])
```

## <a name="syntax-2"></a><a name="syntax-2"></a>구문 2

```vb
ORDERBY (location, list, expression 1[, expression 2, …, expression N])
```

> [!NOTE]
> 이 구문은 Microsoft Dynamics 365 Finance 버전 10.0.25 이상에서 지원됩니다.

## <a name="arguments"></a>인수

`location` *[스트링](er-formula-supported-data-types-primitive.md#string)*

정렬을 실행해야 하는 위치입니다. 다음 옵션이 유효합니다.

- 문의
- 인메모리

`list`: *[기록 목록](er-formula-supported-data-types-composite.md#record-list)*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

`expression 1` *필드*

호출된 함수의 `list` 인수가 참조하는 데이터 소스 필드의 유효한 경로입니다. 참조된 필드는 기본 데이터 유형의 필드여야 합니다. 이 인수는 필수입니다.

`expression N` *필드*

호출된 함수의 `list` 인수가 참조하는 데이터 소스 필드의 유효한 경로입니다. 참조된 필드는 기본 데이터 유형의 필드여야 합니다. 이러한 추가 인수는 선택 사항입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

### <a name="syntax-1"></a>구문 1

데이터 정렬은 항상 애플리케이션 서버의 메모리에서 수행됩니다. 자세한 내용은 [예 1](#example-1)을 참조하십시오.

### <a name="syntax-2"></a>구문 2

### <a name="sorting-in-memory"></a>메모리에서 정렬

`location` 인수가 **InMemory** 로 지정되면 애플리케이션 서버의 메모리에서 데이터 정렬이 수행됩니다. 자세한 내용은 [예 2](#example-2)를 참조하십시오.

### <a name="sorting-in-database"></a>데이터베이스에서 정렬

`location` 인수가 **Query** 로 지정되면 데이터 정렬은 데이터베이스 수준에서 수행됩니다. 이 경우 `list` 인수는 직접 데이터베이스 쿼리를 설정할 수 있는 애플리케이션 소스를 지정하는 다음 [전자 보고(ER)](general-electronic-reporting.md) 데이터 소스 중 하나를 가리켜야 합니다.

- *테이블 기록* 유형의 데이터 소스
- *테이블 기록* 유형의 데이터 소스 관계
- *계산 필드* 유형의 데이터 소스

`expression 1` 및 `expression N` 인수는 직접 데이터베이스 쿼리도 설정할 수 있는 애플리케이션 소스의 관련 필드를 지정하는 ER 데이터 소스의 필드를 가리켜야 합니다.

직접 데이터베이스 쿼리를 설정할 수 없으면 ER 모델 매핑 디자이너에서 유효성 검사 [오류](er-components-inspections.md#i18)가 발생합니다. 수신되는 메시지에는 `ORDERBY` 함수를 포함하는 ER 표현식이 런타임에 실행할 수 없다는 내용이 나와 있습니다.

더 나은 성능을 위해 많은 수의 기록을 포함할 수 있는 애플리케이션 데이터 원본(예: 트랜잭션 애플리케이션 테이블)에 대해 정렬이 구성된 경우 **쿼리** 옵션을 사용하는 것이 좋습니다.

> [!NOTE]
> `ORDEBY` 함수 자체는 직접 데이터베이스 쿼리로 변환할 수 없습니다. 따라서 이 함수가 포함된 ER 데이터 원본은 쿼리할 수 없습니다. 또한 쿼리 가능한 데이터 소스만 사용할 수 있는 [FILTER](er-functions-list-filter.md) 및 [ALLITEMSQUERY](er-functions-list-allitemsquery.md)와 같은 ER 함수의 범위에서는 사용할 수 없습니다.

자세한 내용은 [예 3](#example-3) 및 [예 4](#example-4)를 참조하십시오.

### <a name="comparability"></a>비교 가능성

SQL 데이터베이스 엔진과 Finance 애플리케이션 서버는 단일 문자에 대해 다른 순위 값을 사용할 수 있으므로 정렬에 [스트링](er-formula-supported-data-types-primitive.md#string) 필드를 사용하는 경우 동일한 기록 목록의 정렬 결과가 다를 수 있습니다. 자세한 내용은 [예 5](#example-5)를 참조하십시오.

## <a name="example-1-in-memory-default-execution"></a><a name="example-1"></a>예 1 : 메모리 내 기본 실행

*계산된 필드* 유형의 데이터 소스 **DS** 를 입력하고 여기에 `SPLIT ("C|B|A", "|")` 표현식이 포함된 경우 `FIRST( ORDERBY( DS, DS. Value)).Value` 표현식은 텍스트 값 **'A'** 를 반환합니다.

## <a name="example-2-in-memory-explicit-execution"></a><a name="example-2"></a>예 2 : 메모리 내 명시적 실행

**Vendor** 가 **VendTable** 테이블을 참조하는 *테이블 기록* 유형의 ER 데이터 소스로 구성된 경우 `ORDERBY (Vendor, Vendor.'name()')` 식과 `ORDERBY ("InMemory", Vendor, Vendor.'name()')` 식 모두 이름별로 오름차순으로 정렬된 공급 업체 목록을 반환합니다.

ER 모델 매핑 디자이너에서 `ORDERBY ("Query", Vendor, Vendor.'name()')` 식을 구성하면 `Vendor.'name()'` 경로가 직접 데이터베이스 쿼리로 변환할 수 없는 논리가 있는 애플리케이션 메서드를 참조하기 때문에 디자인 타임에 유효성 검사 [오류](er-components-inspections.md#i8)가 발생합니다.

## <a name="example-3-database-query"></a><a name="example-3"></a>예 3 : 데이터베이스 쿼리

**TaxTransaction** 이 **TaxTrans** 테이블을 참조하는 *테이블 기록* 유형의 ER 데이터 소스로 구성된 경우 `ORDERBY ("Query", TaxTransaction, TaxTransaction.TaxCode)` 표현식은 애플리케이션 데이터베이스 수준에서 기록을 정렬하고 세금 코드별로 오름차순으로 정렬된 세금 트랜잭션 목록을 반환합니다.

## <a name="example-4-queryable-data-sources"></a><a name="example-4"></a>예 4 : 쿼리 가능한 데이터 소스

**TaxTransaction** 이 **TaxTrans** 테이블을 참조하는 *테이블 기록* 유형의 ER 데이터 소스로 구성된 경우 지정된 세금 코드에 대한 트랜잭션을 가져올 `FILTER(TaxTransaction, TaxCode="VAT19")` 표현식이 포함되도록 **TaxTransactionFiltered** ER 데이터 소스를 구성할 수 있습니다. 구성된 **TaxTransactionFiltered** ER 데이터 원본을 쿼리할 수 있으므로 거래 날짜별로 오름차순으로 정렬된 필터링된 세금 거래 목록을 반환하도록 `ORDERBY ("Query", TaxTransactionFiltered, TaxTransactionFiltered.TransDate)` 표현식을 구성할 수 있습니다.

**TaxTransactionOrdered** 를 식을 포함하는 *계산된 필드* 유형의 ER 데이터 원본과 `ORDERBY ("Query", TaxTransaction, TaxTransaction.TransDate)` 식을 포함하는 *계산된 필드* 유형의 `FILTER(TaxTransactionOrdered, TaxCode="VAT19")` ER 데이터 원본으로 구성하면 ER 모델 매핑 디자이너에서 디자인 타임에 유효성 검사 [오류](er-components-inspections.md#i18)가 발생합니다. 이 오류는 [FILTER](er-functions-list-filter.md#usage-notes) 함수의 첫 번째 인수가 쿼리 가능한 ER 데이터 원본을 참조해야 하지만 `ORDERBY` 함수가 포함된 **TaxTransactionOrdered** 데이터 원본을 쿼리할 수 없기 때문에 발생합니다.

## <a name="example-5-comparability"></a><a name="example-5"></a>예 5 : 비교 가능성

### <a name="prerequisites"></a>전제 조건

1. `SPLIT ("D1|_D2|D3", "|")` 표현식을 포함하는 *계산된 필드* 유형의 데이터 소스 **DS1** 을 입력하십시오.
2. **[재무 차원 값](../../../finance/general-ledger/financial-dimensions.md)** 페이지를 열고 **CostCenter** 차원을 선택합니다.
3. 다음 차원 값을 입력합니다. **D1**, **\_D2** 및 **D3**.

### <a name="sorting-in-memory"></a>메모리에서 정렬

1. `ORDERBY("InMemory", DS1, DS1.Value)` 표현식을 포함하는 *계산된 필드* 유형의 데이터 소스 **DS2** 를 구성하십시오.
2. `FIRST(DS2).Value` 표현식은 텍스트 값 **'D1'** 을 반환하고 `INDEX(DS2, COUNT(DS2)).Value` 표현식은 텍스트 값 **\_'D2'** 를 반환하며 `STRINGJOIN(DS2, DS2.Value, "|")` 표현식은 텍스트 값 **"D1\|D3\|\_D2"** 를 반환합니다.

### <a name="sorting-in-database"></a>데이터베이스에서 정렬

1. **FinancialDimensionValueEntity** 엔티티를 참조하는 *테이블 기록* 유형의 데이터 소스 **DS3** 을 입력하십시오.
2. `FILTER(DS3, DS3.FinancialDimension="CostCenter")` 표현식을 포함하는 *계산된 필드* 유형의 데이터 소스 **DS4** 를 구성하십시오.
3. `ORDERBY(DS4, DS4.DimensionValue)` 표현식을 포함하는 *계산된 필드* 유형의 데이터 소스 **DS5** 를 구성하십시오.
4. `FIRST(DS5).Value` 표현식은 텍스트 값 **\_'D2'** 를 반환하고 `INDEX(DS5, COUNT(DS5)).Value` 표현식은 텍스트 값 **'D3**'을 반환하며 `STRINGJOIN(DS5, DS5.Value, "|")` 표현식은 텍스트 값 **"\_D2\|D1\|D3"** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
