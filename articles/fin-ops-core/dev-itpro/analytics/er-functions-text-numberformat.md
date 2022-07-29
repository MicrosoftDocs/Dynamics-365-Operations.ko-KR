---
title: NUMBERFORMAT ER 함수
description: 이번에는 NUMBERFORMAT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 0208796382bd6564539ebbe3d902cc41dedce235adafefe1126961774cdb2076
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460629"
---
# <a name="numberformat-er-function"></a>NUMBERFORMAT ER 함수

[!include [banner](../includes/banner.md)]

이 `NUMBERFORMAT` 함수는 지정된 형식과 선택적으로 지정된 [문화권](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes)에서 지정된 숫자를 나타내는 *스트링* 값을 반환합니다. 지원되는 형식에 대한 정보는 [표준](/dotnet/standard/base-types/standard-numeric-format-strings) 및 [사용자 지정](/dotnet/standard/base-types/custom-numeric-format-strings)를 참조하십시오.

## <a name="syntax-1"></a>구문 1

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a>구문 2

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a>인수

`number`: *정수* 또는 *실수*

서식을 지정해야 하는 숫자를 지정하는 숫자 값입니다.

`format` : *스트링*

형식을 나타내는 *스트링* 값입니다.

`culture`: *스트링*

서식 지정에 사용할 문화권을 나타내는 *스트링* 값입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

문화권이 호출된 함수의 인수로 정의되지 않은 경우 이 함수가 실행되는 컨텍스트에 따라 숫자 서식을 지정하는 데 사용되는 문화권이 결정됩니다.

## <a name="example-1"></a>예시 1

**EN-US** 문화권의 `NUMBERFORMAT (0.45, "p")` 경우 **'45.00%'** 를 `NUMBERFORMAT (10.45, "#")` 반환하고 **'10'** 을 반환합니다.

## <a name="example-2"></a>예시 2

`NUMBERFORMAT (10/3, "F2", "de")` **3,33** 을 반환하는 `NUMBERFORMAT (10/3, "F2", "en-us")` 반면 **3.33** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]