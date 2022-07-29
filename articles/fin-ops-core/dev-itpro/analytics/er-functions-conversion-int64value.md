---
title: INT64VALUE ER 함수
description: 이번에는 INT64VALUE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 375117745b90b9e3e0e15ea45605de5bee6f133e6366d08adf5bae98423abd71
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460644"
---
# <a name="int64value-er-function"></a>INT64VALUE ER 함수

[!include [banner](../includes/banner.md)]

이 `INT64VALUE` 함수는 지정된 스트링을 나타내는 *Int64* 값을 반환합니다.

## <a name="syntax-1"></a>구문 1

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a>구문 2

```vb
INT64VALUE (number)
```

## <a name="arguments"></a>인수

`text`: *스트링*

*Int64* 숫자로 변환해야 하는 텍스트 값입니다.

`number`: *실수* 또는 *정수*

*Int64* 숫자로 변환해야 하는 *숫자* 실수 또는 *정수* 값입니다.

## <a name="return-values"></a>반환 값

*Int64*

결과 숫자 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

소수점 이하 자릿수는 잘립니다.

## <a name="example-1"></a>예시 1

`INT64VALUE ("22565422744")` *Int64* 값 **22565422744** 를 반환합니다.

## <a name="example-2"></a>예시 2

`INT64VALUE ( VALUE("22565422744.77"))` *Int64* 값 **22565422744** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[유형 변환 함수](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]