---
title: 라운드 ER 함수
description: 이번에는 ROUND 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 10/21/2020
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
ms.openlocfilehash: b0c28ba2faebf117aa008106f8a77f79af8f4de3122df858825aa15a6dae3616
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460922"
---
# <a name="round-er-function"></a>라운드 ER 함수

[!include [banner](../includes/banner.md)]

`ROUND` 함수는 지정된 소수점 이하 자릿수로 반올림된 후 지정된 숫자를 *실수* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a>인수

`number`: *실수*

반올림해야 하는 숫자 값입니다.

`decimals`: *정수*

소수 자릿수를 나타내는 숫자 값입니다.

## <a name="return-values"></a>반환 값

*실수*

결과 숫자 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

`decimals` 인수의 값이 0(영)보다 크면 지정된 숫자는 소수 자릿수로 반올림됩니다.

`decimals` 인수의 값이 **0**(영)이면 지정된 숫자는 가장 가까운 짝수 정수로 반올림됩니다.

`decimals` 인수의 값이 0(영)보다 작으면 지정된 숫자가 소수점 왼쪽으로 반올림됩니다.

## <a name="example-1"></a>예시 1

`ROUND (1200.767, 2)` 소수점 이하 두 자리로 반올림하고 **1200.77** 을 반환합니다.

## <a name="example-2"></a>예시 2

`ROUND (1200.767, -3)` **1,000** 의 가장 가까운 배수로 반올림하고 1000을 반환합니다.

## <a name="example-3"></a>예시 3

`ROUND (1200.5, 0)` 가장 가까운 짝수로 반올림하여 **1200** 을 반환하는 반면 `ROUND (1201.5, 0)` 동일한 작업을 수행하여 **1202** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[수학 함수](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]