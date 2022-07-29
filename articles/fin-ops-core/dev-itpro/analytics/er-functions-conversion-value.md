---
title: VALUE ER 함수
description: 이번에는 VALUE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 04d3320276bc1e23436bd9baa7a84da36314d6c3bf7f84694aa2e01e31230a0b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460640"
---
# <a name="value-er-function"></a>VALUE ER 함수

[!include [banner](../includes/banner.md)]

이 `VALUE` 함수는 지정된 스트링에서 변환된 *실수* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
VALUE (text)
```

## <a name="arguments"></a>인수

`text`: *스트링*

숫자 값으로 변환해야 하는 스트링 값입니다.

## <a name="return-values"></a>반환 값

*실수*

결과 숫자 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

쉼표와 점 문자(.)는 소수 구분 기호로 간주되고 선행 하이픈(-)은 음수 기호로 사용됩니다. 지정된 스트링에 숫자가 아닌 다른 문자가 포함된 경우 런타임에 예외가 발생합니다.

## <a name="example-1"></a>예시 1

`VALUE ("1 234,56")` 예외를 throw합니다.

## <a name="example-2"></a>예시 2

`VALUE ("1234,56")` **1234.56** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[유형 변환 함수](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]