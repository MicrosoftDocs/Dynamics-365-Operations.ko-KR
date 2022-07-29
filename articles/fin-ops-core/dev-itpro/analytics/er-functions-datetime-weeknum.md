---
title: WEEKNUM ER 함수
description: 이번에는 WEEKNUM 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 01/15/2022
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 37e62b32896e2030b3322a89ac4acdd6c18d5e3c
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8461039"
---
# <a name="weeknum-er-function"></a>WEEKNUM ER 함수

[!include [banner](../includes/banner.md)]

이 `WEEKNUM` 함수는 지정된 *[날짜](er-formula-supported-data-types-primitive.md#date)* 값을 포함하는 주를 나타내는 *[정수](er-formula-supported-data-types-primitive.md#integer)* 값을 반환합니다. 계산은 달력상의 주와 주의 첫째 요일을 정의하는 문화권 종속 규칙을 기반으로 합니다.

## <a name="syntax"></a>구문

```vb
WEEKNUM (date, culture) as Integer
```

## <a name=""></a><a name="arguments">인수</a>

`date`: *날짜*

주를 계산하는 데 사용할 날짜를 나타내는 날짜 값입니다.

`culture` *[스트링](er-formula-supported-data-types-primitive.md#string)*

계산에 사용할 문화권입니다. .NET [표준](/dotnet/api/system.globalization.cultureinfo.getcultures?view=net-5.0)에 따라 지원되는 문화권 코드를 사용할 수 있습니다.

## <a name="return-values"></a>반환 값

*정수*

결과 숫자 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

런타임 시 로케일이 제공되는 국가 또는 지역에서 이 표준을 채택한 경우 연도의 주는 [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) 표준을 기반으로 계산됩니다. 그렇지 않으면 계산은 국가/지역별 국가 표준을 기반으로 합니다.

지원되지 않는 [문화권](#arguments) 코드가 런타임에 함수의 `WEEKNUM` 인수로 제공되면 예외가 throw됩니다. 공백 스트링이 문화권 코드로 제공되는 경우 영어 국가 중립 달력이 주 번호를 계산하는 데 사용됩니다.

## <a name="examples"></a>예

`WEEKNUM (DATEVALUE ("01-01-2020", "de"))` **1** 을 반환합니다.

`WEEKNUM (DATEVALUE ("01-01-2021", "de"))` **53** 을 반환합니다.

`WEEKNUM (DATEVALUE ("01-01-2022", "de"))` **52** 을 반환합니다.

`WEEKNUM (DATEVALUE ("01-01-2022", "ar"))` **21** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
