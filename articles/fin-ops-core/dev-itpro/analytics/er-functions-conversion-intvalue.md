---
title: INTVALUE ER 함수
description: 이번에는 INTVALUE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 5d54543a6f9878feb3482c1c1e6c1f1f468718489fbc46aded84a5a84bdfb04e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460642"
---
# <a name="intvalue-er-function"></a>INTVALUE ER 함수

[!include [banner](../includes/banner.md)]

이 `INTVALUE` 함수는 지정된 스트링을 나타내는 *Int* 값을 반환합니다.

## <a name="syntax-1"></a>구문 1

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a>구문 2

```vb
INTVALUE (number)
```

## <a name="arguments"></a>인수

`text`: *스트링*

*Int* 숫자로 변환해야 하는 텍스트 값입니다.

`number`: *실수* 또는 *정수*

*Int* 숫자로 변환해야 하는 숫자 *실수* 또는 *정수* 값입니다.

## <a name="return-values"></a>반환 값

*정수*

결과 숫자 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

소수점 이하 자릿수는 잘립니다.

## <a name="example-1"></a>예시 1

`INTVALUE ("100.77")` *Int* 값 **100** 을 반환합니다.

## <a name="example-2"></a>예시 2

`INTVALUE (-100.77)` *Int* 값 **-100** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[유형 변환 함수](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]