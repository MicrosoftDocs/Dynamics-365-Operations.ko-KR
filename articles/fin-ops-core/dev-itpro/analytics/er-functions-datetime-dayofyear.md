---
title: DAYOFYEAR ER 함수
description: 이번에는 DAYOFYEAR 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: ab252b6194267836ba9e1d85f3b96fb100c9f598c783bd9c849c6490c2e54e21
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460615"
---
# <a name="dayofyear-er-function"></a>DAYOFYEAR ER 함수

[!include [banner](../includes/banner.md)]

이 `DAYOFYEAR` 함수는 1월 1일과 지정된 날짜 사이의 일 수를 나타내는 *정수* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a>인수

`date` *날짜*

일 수 계산에 사용할 날짜를 나타내는 날짜 값입니다.

## <a name="return-values"></a>반환 값

*정수*

결과 숫자 값입니다.

## <a name="example-1"></a>예시 1

`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` **61** 을 반환합니다.

## <a name="example-2"></a>예시 2

`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` **1** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]