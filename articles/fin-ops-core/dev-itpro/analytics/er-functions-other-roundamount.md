---
title: ROUNDAMOUNT ER 함수
description: 이번에는 ROUNDAMOUNT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 1b05c6024d9eeecfe74022df10d793055a026d5a159e9c011f37708f6a4e6e0d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460601"
---
# <a name="roundamount-er-function"></a>ROUNDAMOUNT ER 함수

[!include [banner](../includes/banner.md)]

이 `ROUNDAMOUNT` 함수는 지정된 반올림 규칙에 따라 지정된 숫자를 다른 숫자의 가장 가까운 배수로 반올림한 결과로 *실수* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a>인수

`number`: *정수* 또는 *실수*

반올림해야 하는 숫자 값입니다.

`decimals`: *정수* 또는 *실수*

`number` 매개 변수 값을 배수로 반올림해야 하는 숫자입니다.

`round rule`: *열거형 값*

반올림 규칙을 정의하는 **RoundOffType** 열거형의 열거형 값입니다. 이 열거형은 다음 값을 제공합니다.

- 일반(보통)
- 아래로(내림)
- 위로(올림)

## <a name="return-values"></a>반환 값

*실수*

결과 숫자 값은 `decimals` 매개 변수로 지정된 값의 배수이며 `number` 매개 변수로 지정된 값에 가장 가깝습니다.

## <a name="usage-notes"></a>사용 참고 사항

`number` 매개 변수가 0이면 이 함수는 항상 0을 반환합니다.

`decimals` 매개 변수가 0이면 이 함수는 기본 반올림 값으로 반올림합니다. `round rule` 매개 변수가 **RoundOffType.Ordinary** 로 설정되면 기본 반올림 값은 **0.01** 입니다. 그렇지 않으면 기본 반올림 값은 **1.0** 입니다.

`round rule` 매개 변수가 **RoundOffType.Ordinary** 로 설정되면 이 함수는 가장 가까운 반올림 양으로 반올림합니다.

`round rule` 매개 변수가 **RoundOffType.RoundDown** 으로 설정되면 이 함수는 가장 가까운 반올림 양으로 0을 향해 반올림합니다.

`round rule` 매개 변수가 **RoundOffType.RoundUp** 으로 설정되면 이 함수는 0에서 가장 가까운 반올림 양으로 반올림합니다.

`round rule` 매개 변수가 **RoundOffType.Ordinary** 로 설정되면 이 함수는 [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel 함수 및 [ROUND](../dev-ref/xpp-math-run-time-functions.md#round) X++ 함수처럼 작동합니다.

## <a name="remarks"></a>참고

숫자 값을 지정된 소수 자릿수로 반올림하려면 [ROUND](er-functions-mathematical-round.md) 함수를 사용합니다.

## <a name="example"></a>예시

**model.RoundOff** 매개 변수가 **RoundOffType.Ordinary** 로 설정된 경우 `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 7.35를 반환합니다. 

**model.RoundOff** 매개 변수가 **RoundOffType.RoundDown** 으로 설정된 경우 `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 7.35를 반환합니다. 

**model.RoundOff** 매개 변수가 **RoundOffType.RoundUp** 으로 설정된 경우 `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` 8.4를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[기타(비즈니스 도메인별) 함수](er-functions-category-other.md)

[수학 함수](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]