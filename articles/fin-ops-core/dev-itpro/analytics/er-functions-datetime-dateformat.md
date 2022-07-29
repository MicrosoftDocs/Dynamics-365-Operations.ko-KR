---
title: DATEFORMAT ER 함수
description: 이번에는 DATEFORMAT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 09/08/2021
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
ms.openlocfilehash: 4a6c113f5f8147cbeaab103e86a44d4c66272c13
ms.sourcegitcommit: e7eeca05d738e9e46d6185d1ba349836ebafc1a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2021
ms.locfileid: "8460627"
---
# <a name="dateformat-er-function"></a>DATEFORMAT ER 함수

[!include [banner](../includes/banner.md)]

이 `DATEFORMAT` 함수는 지정된 날짜 값을 지정된 형식과 선택적으로 지정된 [문화권](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes)의 텍스트로 표시하는 *[스트링](er-formula-supported-data-types-primitive.md#string)* 값을 반환합니다. 지원되는 형식에 대한 정보는 [표준](/dotnet/standard/base-types/standard-date-and-time-format-strings) 및 [사용자 지정](/dotnet/standard/base-types/custom-date-and-time-format-strings)를 참조하십시오.

## <a name="syntax-1"></a>구문 1

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a>구문 2

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a>인수

`date`: *[날짜](er-formula-supported-data-types-primitive.md#date)*

서식을 지정할 날짜를 나타내는 날짜 값입니다.

`format`: *스트링*

출력 스트링의 형식입니다. 지원되는 형식에 대한 정보는 [표준](/dotnet/standard/base-types/standard-date-and-time-format-strings) 및 [사용자 지정](/dotnet/standard/base-types/custom-date-and-time-format-strings)를 참조하십시오.

> [!NOTE]
> 표준 형식이나 사용자 지정 형식을 사용할 때 형식 스트링은 대소문자를 구분합니다. 예를 들어 [표준](/dotnet/standard/base-types/standard-date-and-time-format-strings) 'd' 형식 지정자는 짧은 날짜 패턴을 사용하여 날짜를 반환하는 반면, 표준 'D' 형식 지정자는 긴 날짜 패턴을 사용하여 날짜를 반환합니다. 또한 [사용자 지정](/dotnet/standard/base-types/custom-date-and-time-format-strings) 'M' 형식 지정자는 1에서 12까지의 월을 반환하는 반면, 사용자 지정 'm' 형식 지정자는 0에서 59까지의 분을 반환합니다.

`culture`: *스트링*

서식 지정에 사용할 문화권입니다. 지원되는 문화권에 대한 자세한 내용은 [문화권](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes)을 참조하십시오.

## <a name="return-values"></a>반환 값

*스트링*

결과 스트링 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

문화권이 호출된 함수의 인수로 정의되지 않은 경우 `culture` 값은 호출 컨텍스트에 의해 정의됩니다. 예를 들어, 독일 문화권을 사용하도록 구성된 **FILE** 요소에 대해 전자 보고(ER) 형식의 구문 1을 사용하여 `DATEFORMAT` 함수를 호출하는 경우 독일 문화권을 사용하여 변환이 수행됩니다. `culture` 기본값은 **EN-US** 입니다.

## <a name="example-1"></a>예시 1

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` 지정된 사용자 지정 형식을 기반으로 현재 애플리케이션 서버 날짜인 2015년 12월 24일을 **'24-12-2015'** 스트링으로 반환합니다.

## <a name="example-2"></a>예시 2

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` 선택한 독일 문화와 지정된 형식을 기반으로 현재 애플리케이션 세션 날짜인 2015년 12월 24일을 **'24-12-2015'** 스트링으로 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
