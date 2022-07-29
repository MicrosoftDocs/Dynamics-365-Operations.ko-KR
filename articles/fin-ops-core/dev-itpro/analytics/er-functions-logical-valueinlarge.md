---
title: VALUEINLARGE ER 함수
description: 이번에는 VALUEINLARGE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 08/17/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 57b2246631b31cce10d086da29e76b729059a64aa6a3c2d8cf864dd70085dbfd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460924"
---
# <a name="valueinlarge-er-function"></a>VALUEINLARGE ER 함수

[!include [banner](../includes/banner.md)]

이 `VALUEINLARGE` 함수는 *Int64* 또는 *Integer* 유형의 지정된 입력이 지정된 목록에 있는 지정된 항목의 값과 일치하는지 여부를 결정합니다. 지정된 입력이 지정된 목록의 하나 이상의 기록에 대해 지정된 표현식을 실행한 결과와 일치하는 경우 함수는 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다. `VALUEIN` 함수와의 차이점을 이해하려면 이 항목 뒷부분의 [사용법](#usage_note) 참고 섹션을 참조하십시오.

## <a name="syntax"></a>구문

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a>인수

`input` *필드*

*기록 목록* 유형의 데이터 소스 항목에 대한 유효한 경로입니다. 이 항목의 값이 일치합니다.

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

`list item expression`: *표현*

일치에 사용해야 하는 지정된 목록의 단일 필드를 가리키거나 포함하는 유효한 조건식입니다.

## <a name="return-values"></a>반환 값

*부울*

결과 *부울* 값입니다.

## <a name=""></a><a name="usage_note">사용 참고 사항</a>

지정된 입력이 데이터 소스 항목의 *Int64* 또는 *Integer* 유형을 나타내는 경우 직접 SQL 문으로 변환 가능한 호출, 지정된 목록을 임시 SQL 테이블로 변환하고 단일 `EXISTS JOIN` 쿼리를 실행하여 데이터베이스에서 일치 수행 . 그렇지 않으면 이 함수가 [`VALUEIN`](er-functions-logical-valuein.md) 함수로 작동합니다.

지정된 입력이 *Int64* 및 *Integer* 유형 이외의 항목으로 설계된 데이터 소스 항목을 나타내는 경우 디자인 타임에 해당 `VALUEINLARGE` 함수가 구성된 ER 표현식에 적용되지 않음을 알리는 오류가 발생합니다.

`VALUEINLARGE` 함수 표현식이 실행되고 이 실행 범위에서 둘 이상의 임시 테이블이 사용되면 런타임 오류가 발생합니다.

## <a name="example"></a>예시

모델 매핑에서 다음 데이터 소스를 정의합니다.

- *테이블 기록* 유형의 **In** 데이터 소스입니다.
    - 이 데이터 소스는 **Intrastat** 테이블을 참조합니다.
    - **회사 간** 옵션이 **아니요** 로 설정되어 있습니다.
- *계산된 필드* 유형의 **InMemory** 데이터 소스입니다.
    - 이 데이터 소스에는 `WHERE (In, In.Port <> "")` 표현식이 포함되어 있습니다.
- *계산된 필드* 유형의 **InFiltered** 데이터 소스입니다.
    - 이 데이터 소스에는 `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)` 표현식이 포함되어 있습니다.

데이터 소스 **InFiltered** 가 회사 **DEMF** 의 컨텍스트에서 호출되면 애플리케이션 데이터베이스에 새 임시 테이블이 생성되고 메모리에 수집된 기록 식별 코드 목록이 이 테이블에 삽입되고 다음 SQL 문을 생성하여 반환합니다. **Intrastat** 테이블의 필터링된 기록.

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a>추가 리소스

[논리 함수](er-functions-category-logical.md)

[VALUEIN 함수](er-functions-logical-valuein.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]