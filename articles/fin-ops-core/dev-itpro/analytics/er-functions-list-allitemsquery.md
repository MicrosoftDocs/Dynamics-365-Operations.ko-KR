---
title: ALLITEMSQUERY ER 함수
description: 이번에는 ALLITEMSQUERY 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 5db58d91e68d6ce2d1d85c330ca240c71156870bd6fb6625c033191c4c06ef8e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460850"
---
# <a name="allitemsquery-er-function"></a>ALLITEMSQUERY ER 함수

[!include [banner](../includes/banner.md)]

`ALLITEMSQUERY` 함수는 결합된 SQL 쿼리로 실행됩니다. 지정된 경로와 일치하는 모든 항목을 나타내는 *기록 목록* 으로 구성된 새로운 병합된 기록 목록 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a>인수

`path`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다. 최소한 하나의 관계를 포함해야 합니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

지정된 경로는 *기록 목록* 데이터 유형의 데이터 소스 요소에 대한 유효한 데이터 소스 경로로 정의되어야 합니다. 또한 적어도 하나의 관계를 포함해야 합니다. 경로 *스트링* 및 *날짜* 와 같은 데이터 요소는 디자인 타임에 전자 보고(ER) 표현식 작성기에서 오류를 발생시켜야 합니다.

SQL을 사용하여 직접 호출할 수 있는 애플리케이션 개체(예: 테이블, 엔터티, 쿼리)를 참조하는 *기록 목록* 데이터 형식의 데이터 소스에 이 함수를 적용하면 조인된 SQL 쿼리로 실행됩니다. 그렇지 않으면 메모리에서 [ALLITEMS](er-functions-list-allitems.md) 함수로 실행됩니다.

## <a name="example"></a>예시

모델 매핑에서 다음 데이터 소스를 정의합니다.

- CustInvoiceTable 테이블을 참조하는 *테이블 기록* 유형의 **CustInv** 데이터 소스
- 표현식을 포함하는 *계산된 필드* 유형의 **FilteredInv** 데이터 소스 `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`
- 표현식을 포함하는 *계산된 필드* 유형의 **JourLines** `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`

**JourLines** 데이터 소스를 호출하기 위해 모델 매핑을 실행하면 다음 SQL 문이 실행됩니다.

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]