---
title: STRINGJOIN ER 함수
description: 이번에는 STRINGJOIN 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 651cc261e6a33b1a824feb94afa767e439196e249bb13b0fc4886dc72bfdd184
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460931"
---
# <a name="stringjoin-er-function"></a>STRINGJOIN ER 함수

[!include [banner](../includes/banner.md)]

이 `STRINGJOIN` 함수는 지정된 목록에서 지정된 필드의 연결된 값으로 구성된 *스트링* 값을 반환합니다. 값은 지정된 구분 기호로 구분할 수 있습니다.

## <a name="syntax"></a>구문

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

`field` *필드*

지정된 목록에 있는 *스트링* 데이터 형식 필드의 유효한 경로입니다.

`delimiter`: *스트링*

하위 스트링을 구분하는 데 사용되는 구분 기호입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="example"></a>예시

`SPLIT("abc" , 1)` 데이터 소스 **DS** 로 입력하면 `STRINGJOIN (DS, DS.Value, "-")` 표현식은 **'abc'** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]