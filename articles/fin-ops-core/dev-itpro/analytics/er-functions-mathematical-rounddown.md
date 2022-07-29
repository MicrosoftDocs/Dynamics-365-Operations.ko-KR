---
title: ROUNDDOWN ER 함수
description: 이번에는 ROUNDDOWN 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 77186dc4d607f419149e4001a7404afba9e80fc7ec2528b840261a329a1e7872
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460921"
---
# <a name="rounddown-er-function"></a>ROUNDDOWN ER 함수

[!include [banner](../includes/banner.md)]

`ROUNDDOWN` 함수는 지정된 소수점 이하 자릿수로 내림한 후 지정된 숫자를 *실수* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>인수

`number`: *실수*

내림해야 하는 숫자 값입니다.

`decimals`: *정수*

소수 자릿수를 나타내는 숫자 값입니다.

## <a name="return-values"></a>반환 값

*실수*

결과 숫자 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

이 함수는 [ROUND](er-functions-mathematical-round.md)처럼 작동하지만 항상 지정된 숫자를 0으로 내림합니다.

## <a name="example-1"></a>예시 1

`ROUNDDOWN (1200.767, 2)` 소수점 이하 두 자리까지 내림하고 **1200.76** 을 반환합니다. 

## <a name="example-2"></a>예시 2

`ROUNDDOWN (1700.767, -3)` **1,000** 의 가장 가까운 배수로 내림하고 1000을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[수학 함수](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]