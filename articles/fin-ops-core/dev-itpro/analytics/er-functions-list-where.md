---
title: WHERE ER 함수
description: 이번에는 WHERE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: dd021381e04e8794a5668041dbd71e5c981577a19141581fdde078a9d5801f49
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460932"
---
# <a name="where-er-function"></a>WHERE ER 함수

[!include [banner](../includes/banner.md)]

이 `WHERE` 함수는 지정된 조건에 따라 필터링된 후 지정된 목록을 *기록 목록* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
WHERE (list, condition)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

`condition`: *부울*

지정된 목록의 기록을 필터링하는 데 사용되는 유효한 조건식입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

지정된 조건이 메모리에 있는 *기록 목록* 유형의 전자 보고(ER) 데이터 소스에 적용된다는 점에서 이 함수는 [FILTER](er-functions-list-filter.md) 함수와 다릅니다.

이 함수(`list` 및 `condition`)에 대해 구성된 인수를 통해 이 요청을 직접 SQL 호출로 변환할 수 있는 경우 디자인 타임에 경고 메시지가 발생합니다. 이 메시지는 `WHERE` 대신 [FILTER](er-functions-list-filter.md) 함수를 사용하면 성능이 향상될 수 있음을 사용자에게 알려줍니다.

## <a name="example-1"></a>예시 1

**Vendor** 가 VendTable 테이블을 참조하는 ER 데이터 소스로 구성된 경우 `WHERE (Vendors, Vendors.VendGroup = "40")` 표현식은 공급 업체 그룹 40에 속하는 공급 업체의 목록만 반환합니다.

## <a name="example-2"></a>예시 2

*계산된 필드* 유형의 데이터 소스 **DS** 를 입력하고 `SPLIT ("A|B|C", "|")` 표현식이 포함된 경우 `WHERE( DS, DS.Value = "B")` 표현식은 **값** 필드에 텍스트 **'B'** 가 포함된 기록 하나만 목록으로 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]