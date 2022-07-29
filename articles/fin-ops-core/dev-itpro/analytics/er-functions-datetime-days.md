---
title: DAYS ER 함수
description: 이번에는 DAYS 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 19e363e7bc8b8ad898244702ad6ba14bcf490f5ca2381b006a35dc0ed9309d49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460839"
---
# <a name="days-er-function"></a>DAYS ER 함수

[!include [banner](../includes/banner.md)]

이 `DAYS` 함수는 지정된 날짜와 지정된 두 번째 날짜 사이의 일 수를 나타내는 *정수* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a>인수

`date 1`: *날짜*

일 수 계산의 시작 날짜를 나타내는 날짜 값입니다.

`date 2`: *날짜*

일 수 계산의 종료 날짜를 나타내는 날짜 값입니다.

## <a name="return-values"></a>반환 값

*정수*

결과 숫자 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

`DAYS` 함수는 첫 번째 날짜가 두 번째 날짜보다 나중일 경우 양수 값을 반환하고, 첫 번째 날짜가 두 번째 날짜와 같으면 **0** 을 반환하고, 첫 번째 날짜가 두 번째 날짜보다 빠르면 음수 값을 반환합니다.

## <a name="example"></a>예시

`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` **-1** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]