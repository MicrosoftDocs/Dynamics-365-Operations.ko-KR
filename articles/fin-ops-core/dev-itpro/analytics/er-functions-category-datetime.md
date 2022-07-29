---
title: 날짜 및 시간 범주의 ER 함수 목록
description: 이번에는 전자 보고(ER)에서 지원되는 날짜 및 시간 함수에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 09/09/2021
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
ms.openlocfilehash: 0a0322e5490474e21ad91076ecc486f38a776e32
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2021
ms.locfileid: "8460623"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>날짜 및 시간 범주의 ER 함수 목록

[!include [banner](../includes/banner.md)]

전자 보고(ER) 날짜 및 시간 함수를 사용하여 날짜 및 시간 값에서 정보를 추출하고 이에 대한 작업을 수행할 수 있습니다. 이번에는 이러한 함수에 대한 요약을 제공합니다.

## <a name="list-of-supported-functions"></a>지원되는 함수 목록

| 직렬 | 설명 |
|----------|-------------|
| [추가일](er-functions-datetime-adddays.md) | 이 함수는 지정된 시작 날짜 전후의 지정된 일 수인 *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* 값을 반환합니다. |
| [변경시간대](er-functions-datetime-changetimezone.md) | 이 함수는 한 시간대의 주어진 *날짜/시간* 값에서 다른 시간대의 날짜/시간 값으로 변환된 DateTime 값을 반환합니다. |
| [날짜 형식](er-functions-datetime-dateformat.md) | 이 함수는 지정된 날짜 값을 지정된 형식과 선택적으로 지정된 문화권의 텍스트로 표시하는 *[스트링](er-formula-supported-data-types-primitive.md#string)* 값을 반환합니다. |
| [날짜 시간 형식](er-functions-datetime-datetimeformat.md) | 이 함수는 지정된 날짜/시간 값을 지정된 형식과 선택적으로 지정된 문화권의 텍스트로 표시하는 *스트링* 값을 반환합니다. |
| [날짜시간값](er-functions-datetime-datetimevalue.md) | 이 함수는 지정된 형식과 선택적으로 지정된 문화권의 지정된 텍스트 값에서 날짜/시간 값으로 변환된 *DateTime* 값을 반환합니다. |
| [날짜까지 날짜 시간](er-functions-datetime-datetodatetime.md) | 이 함수는 지정된 날짜 값에서 표준 시간대(그리니치 표준시 \[GMT\])의 날짜/시간 값으로 변환된 *DateTime* 값을 반환합니다. |
| [날짜 값](er-functions-datetime-datevalue.md) | 이 함수는 지정된 형식과 선택적으로 지정된 문화권의 지정된 텍스트 값에서 날짜 값으로 변환된 *[날짜](er-formula-supported-data-types-primitive.md#date)* 값을 반환합니다. |
| [일년](er-functions-datetime-dayofyear.md) | 이 함수는 1월 1일과 지정된 날짜 사이의 일 수를 나타내는 *[정수](er-formula-supported-data-types-primitive.md#integer)* 값을 반환합니다. |
| [일](er-functions-datetime-days.md) | 이 함수는 지정된 날짜와 지정된 두 번째 날짜 사이의 일 수를 나타내는 *정수* 값을 반환합니다. |
| [지금](er-functions-datetime-now.md) | 이 함수는 현재 애플리케이션 서버 날짜 및 시간을 나타내는 *DateTime* 값을 반환합니다. |
| [NullDate](er-functions-datetime-nulldate.md) | 이 함수는 **null** 날짜(1900년 1월 1일)를 나타내는 *Date* 값을 반환합니다. |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | 이 함수는 표준 시간대에서 **null** 날짜/시간 값(1900년 1월 1일)을 나타내는 *DateTime* 값을 반환합니다. |
| [지금 세션](er-functions-datetime-sessionnow.md) | 이 함수는 현재 애플리케이션 세션 날짜 및 시간을 나타내는 *DateTime* 값을 반환합니다. |
| [오늘 세션](er-functions-datetime-sessiontoday.md) | 이 함수는 현재 애플리케이션 세션 날짜를 나타내는 *날짜* 값을 반환합니다. |
| [오늘](er-functions-datetime-today.md) | 이 함수는 현재 애플리케이션 서버 날짜를 나타내는 *날짜* 값을 반환합니다. |
| [주 번호](er-functions-datetime-weeknum.md) | 이 함수는 해당 연도의 주를 나타내는 *정수* 값을 반환합니다. |

## <a name="additional-resources"></a>추가 리소스

[전자 보고 개요](general-electronic-reporting.md)

[전자 보고의 공식 디자이너](general-electronic-reporting-formula-designer.md)

[전자 보고 공식 언어](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
