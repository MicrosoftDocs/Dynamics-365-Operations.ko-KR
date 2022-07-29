---
title: NUMERALSTOTEXT ER 함수
description: 이번에는 NUMERALSTOTEXT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 76431642a6d6961c5c9a2bf15534ad58f83d312dfb3723e75c94fa844717930b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460755"
---
# <a name="numeralstotext-er-function"></a>NUMERALSTOTEXT ER 함수

[!include [banner](../includes/banner.md)]

이 `NUMERALSTOTEXT` 함수는 지정된 언어로 철자를 입력한(즉, 텍스트 스트링으로 변환된) 지정된 숫자를 *스트링* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a>인수

`number`: *정수* 또는 *실수*

철자가 있어야 하는 숫자를 지정하는 숫자 값입니다.

`language`: *스트링*

언어 코드를 나타내는 *스트링* 값입니다.

`currency`: *스트링*

통화 코드를 나타내는 *스트링* 값입니다.

`print currency name flag`: *부울*

통화 이름을 철자 텍스트에 추가해야 하는지 여부를 나타내는 *부울* 값입니다.

`decimal points`: *정수*

철자가 있어야 하는 텍스트의 소수 자릿수를 나타내는 *정수* 값입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

언어 코드는 선택 사항입니다. 빈 스트링으로 정의된 경우 실행 중인 컨텍스트에 대한 언어 코드가 사용됩니다. 기본 언어 코드는 **EN-US** 입니다. 실행 중인 컨텍스트에 대한 언어 코드는 실행 중인 전자 보고(ER) 형식의 **폴더** 또는 **파일** 요소에 정의됩니다.

통화 코드는 선택 사항입니다. 빈 스트링으로 정의된 경우 실행 중인 컨텍스트에 대한 회사 통화가 사용됩니다.

> [!NOTE] 
> `print currency name flag` 및 `decimal points` 인수는 다음 언어 코드에 대해서만 분석됩니다.  **CS**, **ET**, **HU**, **LT**, **LV**, **PL** 및 **RU**. 또한 해당 국가 또는 지역의 컨텍스트가 통화 이름의 감소를 지원하는 회사에 대해서만 `print currency name flag` 인수를 분석합니다.

## <a name="example-1"></a>예시 1

`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` **'천이백삼십사 56'** 을 반환합니다.

## <a name="example-2"></a>예시 2

`NUMERALSTOTEXT (120, "PL", "", false, 0)` **'Sto dwadzieścia'** 를 반환합니다. 

## <a name="example-3"></a>예시 3

`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` **'Сто двадцать евро 21 евроцент'** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]