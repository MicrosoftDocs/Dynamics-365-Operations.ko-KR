---
title: DATETIMEVALUE ER 함수
description: 이번에는 DATETIMEVALUE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 7a9da0b9461926b1033d6a97b37d4b43a86d8dad
ms.sourcegitcommit: e7eeca05d738e9e46d6185d1ba349836ebafc1a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2021
ms.locfileid: "8460614"
---
# <a name="datetimevalue-er-function"></a>DATETIMEVALUE ER 함수

[!include [banner](../includes/banner.md)]

이 `DATETIMEVALUE` 함수는 지정된 형식과 선택적으로 지정된 [문화권](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes)의 지정된 텍스트 값에서 *[날짜/시간](er-formula-supported-data-types-primitive.md#datetime)* 값으로 변환된 DateTime 값을 반환합니다. 지원되는 형식에 대한 정보는 [표준](/dotnet/standard/base-types/standard-date-and-time-format-strings) 및 [사용자 지정](/dotnet/standard/base-types/custom-date-and-time-format-strings)를 참조하십시오.

## <a name="syntax-1"></a>구문 1

```vb
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a>구문 2

```vb
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a>인수

`text` *[스트링](er-formula-supported-data-types-primitive.md#string)*

서식을 지정할 값을 나타내는 텍스트입니다.

`format`: *스트링*

주어진 텍스트의 형식입니다. 지원되는 형식에 대한 정보는 [표준](/dotnet/standard/base-types/standard-date-and-time-format-strings) 및 [사용자 지정](/dotnet/standard/base-types/custom-date-and-time-format-strings)를 참조하십시오.

`culture`: *스트링*

지정된 텍스트의 서식을 지정하는 데 사용되는 문화권입니다. 지원되는 문화권에 대한 자세한 내용은 [문화권](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes)을 참조하십시오.

## <a name="return-values"></a>반환 값

*날짜 시간*

결과 날짜/시간 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

문화권이 호출된 함수의 인수로 정의되지 않은 경우 `culture`의 값은 호출 컨텍스트에 의해 정의됩니다. 예를 들어, 독일 문화권을 사용하도록 구성된 **FILE** 요소에 대해 전자 보고(ER) 형식의 구문 1을 사용하여 `DATETIMEVALUE` 함수를 호출하는 경우 독일 문화권을 사용하여 변환이 수행됩니다. `culture` 기본값은 **EN-US** 입니다.

## <a name="example-1"></a>예시 1

`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` 지정된 사용자 지정 형식과 기본 애플리케이션의 **EN-US** 문화권을 기반으로 **2016년 12월 21일 오전 2시 55분** 을 반환합니다.

## <a name="example-2"></a>예시 2

`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` 지정된 사용자 지정 형식 및 문화권에 따라 **2016년 12월 21일 오전 2시 55분** 을 반환합니다.

그러나 `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` 지정된 스트링이 지정된 문화권에 대한 유효한 날짜/시간 값으로 인식되지 않는다는 것을 사용자에게 알리는 예외가 발생합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
