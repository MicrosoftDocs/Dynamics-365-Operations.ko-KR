---
title: CASE ER 함수
description: 이번에는 CASE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 97f5e821a635d5d31092a7b27f7ae3c2e603462186449bab5856955371a7f613
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460930"
---
# <a name="case-er-function"></a>CASE ER 함수

[!include [banner](../includes/banner.md)]

이 `CASE` 함수는 지정된 대체 옵션에 대해 지정된 표현식의 값을 평가하고 지정된 표현식의 값과 동일한 첫 번째 옵션의 결과를 반환합니다. 그렇지 않고 기본 결과가 옵션이 선행되지 않는 호출된 함수의 마지막 인수로 지정된 경우 선택적 기본 결과를 반환합니다. 반환되는 값은 지원되는 모든 데이터 유형의 값일 수 있습니다.

## <a name="syntax"></a>구문

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a>인수

`expression`: *기본 데이터 유형*(부울, 숫자 또는 텍스트)

기본 데이터 유형의 값을 반환하는 유효한 표현식입니다.

`option 1`: *기본 데이터 유형*(부울, 숫자 또는 텍스트)

호출된 함수의 `expression` 인수와 동일한 기본 데이터 유형의 값을 리턴하는 유효한 표현식입니다. 이 인수는 필수입니다.

`result 1`: *지원되는 모든 데이터 유형*

이전 옵션에 해당하는 반환된 결과입니다. 이 인수는 필수입니다.

`option N`: *기본 데이터 유형*(부울, 숫자 또는 텍스트)

호출된 함수의 `expression` 인수와 동일한 기본 데이터 유형의 값을 리턴하는 유효한 표현식입니다. 이 인수는 선택 사항입니다.

`result N`: *지원되는 모든 데이터 유형*

이전 옵션에 해당하는 반환된 결과입니다. 이 인수는 선택 사항입니다.

`default result`: *지원되는 모든 데이터 유형*

일치하는 항목이 없는 경우 반환되어야 하는 결과입니다. 이 인수는 선택 사항입니다.

## <a name="return-values"></a>반환 값

*지원되는 모든 데이터 유형*

지원되는 데이터 유형의 결과 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

일치하는 항목이 없고 선택적 기본 결과가 정의되지 않은 경우 런타임에 예외가 발생합니다.

모든 결과는 동일한 데이터 유형을 사용하여 지정해야 합니다. 구성된 결과의 데이터 유형이 일치하지 않으면 디자인 타임에 예외가 발생합니다.

첫 번째 결과 값과 *N* 번째 결과 값이 *컨테이너(기록)* 또는 *기록 목록* 데이터 유형의 값인 경우 결과에는 두 값에 모두 존재하는 필드만 있습니다.

## <a name="example"></a>예시

`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` 현재 애플리케이션 세션 날짜가 10월과 12월 사이인 경우 스트링 **'WINTER'** 를 반환합니다. 그렇지 않으면 빈 스트링을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[논리 함수](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]