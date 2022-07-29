---
title: 파워 ER 함수
description: 이번에는 POWER 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 6955d2787b2a9be6d38fe10165a9d5ef8310b108e3a9772709d9d1ff51712424
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460923"
---
# <a name="power-er-function"></a>파워 ER 함수

[!include [banner](../includes/banner.md)]

이 `POWER` 함수는 지정된 양수를 지정된 거듭제곱으로 높인 결과를 나타내는 *실수* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
POWER (number, power)
```

## <a name="arguments"></a>인수

`number`: *실수* 또는 *정수*

지정된 거듭제곱으로 올려야 하는 숫자 값입니다.

`power`: *실수* 또는 *정수*

특정 거듭제곱을 나타내는 숫자 값입니다.

## <a name="return-values"></a>반환 값

*실수*

결과 숫자 값입니다.

## <a name="example-1"></a>예시 1

`POWER (10, 2)` **100** 을 반환합니다.

## <a name="example-2"></a>예시 2

`POWER (4, 0.5)` **2** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[수학 함수](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]