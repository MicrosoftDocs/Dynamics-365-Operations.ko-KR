---
title: LISTDINCT ER 함수
description: 이번에는 LISTDISTINCT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 7/30/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 7cc51695d261a63521ae88e2a9362b6f30b9618ed89300bcaeb606b050c81350
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460798"
---
# <a name="listdistinct-er-function"></a>LISTDINCT ER 함수

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

이 `LISTDISTINCT` 함수는 지정된 목록의 모든 기록에 대한 선택기로 지정된 표현식을 계산합니다. 각 고유 선택기 값에 대한 단일 기록이 포함된 새 *기록 목록* 값을 반환합니다.

## <a name="syntax"></a>구문

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

`selector`: *기본 데이터 유형*

지정된 목록의 모든 기록에 대한 선택기 값을 계산하는 데 사용되는 유효한 표현식입니다.

이 매개 변수에 대해 다음 데이터 유형이 지원됩니다.

- 부울
- 날짜
- 날짜 시간
- GUID
- 정수
- Int64
- 실수
- 스트링

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

생성된 목록의 구조는 지정된 목록의 구조와 일치합니다.

지정된 목록의 여러 기록에 대해 동일한 선택기 값이 계산될 수 있습니다. 이 경우 생성된 목록에서 해당 기록의 필드 값은 선택기 값이 계산되는 지정된 목록의 첫 번째 기록 값과 같습니다.

이 함수의 실행은 메모리에 있는 *기록 목록* 유형의 [전자 보고(ER)](general-electronic-reporting.md) 데이터 소스에서 수행됩니다.

**GROUPBY** 데이터 원본을 사용하여 고유한 값이 있는 선택기가 계산되는 기록 목록을 생성할 수도 있습니다. 하지만, 성능 및 메모리 소모 측면에서는 `LISTDISTINCT` 함수의 실행이 메모리에서 이루어지기 때문에 **GROUPBY** 데이터 소스보다 함수를 사용하는 것이 좋습니다.

## <a name="example"></a>예시

다음 예는 특정 기간 동안 하나 이상의 판매 송장 또는 프로젝트 송장이 발행된 고유한 고객 계정 번호 목록을 얻는 방법을 보여줍니다.

1. **CustInvoiceJour** 애플리케이션 테이블을 참조하고 특정 기간에 대한 판매 송장을 필터링하는 `Record list` 유형의 **SalesInvoice** 데이터 소스를 입력합니다.

    `InvoiceAccount` 이 데이터 소스의 필드는 송장 발행 고객의 계정 번호를 반환합니다.

2. **ProjInvoiceJour** 애플리케이션 테이블을 참조하는 `Record list` 유형의 **ProjectInvoice** 데이터 소스를 입력하고 특정 기간에 대한 프로젝트 송장을 필터링합니다.

    `InvoiceAccount` 이 데이터 소스의 필드는 송장 발행 고객의 계정 번호를 반환합니다.

3. `Calculated field` 표현식을 포함하는 `LISTJOIN(SalesInvoice, ProjectInvoice)` 유형의 **AllInvoices** 데이터 소스를 구성하십시오.

    이 데이터 소스는 판매 송장과 프로젝트 송장의 결합된 목록을 반환합니다.

4. `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)` 표현식을 포함하는 `Record list` 유형의 **InvoicedCustomer** 데이터 소스를 구성하십시오.

    이 데이터 소스는 정의된 기간 동안 청구된 모든 고유 고객에 대한 단일 기록이 포함된 새 목록을 반환합니다. `InvoiceAccount` 이 목록의 필드에는 고객 계정 번호가 포함됩니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]