---
title: 스플릿 ER 함수
description: 이번에는 SPLIT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 04/01/2021
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
ms.openlocfilehash: 4a42b0c7cfa2a8d3dcb7448224c9e88a48276f7d8cdbcce484383a778b8275a5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460791"
---
# <a name="split-er-function"></a>스플릿 ER 함수

[!include [banner](../includes/banner.md)]

이 `SPLIT` 함수는 지정된 입력 스트링을 하위 스트링으로 분할하고 결과를 새 *기록 목록* 값으로 반환합니다.

## <a name="syntax-1"></a>구문 1

```vb
SPLIT (input, length)
```

이 구문은 지정된 입력 스트링을 각각 지정된 길이를 갖는 부분 스트링으로 분할하는 데 사용됩니다.

## <a name="syntax-2"></a>구문 2

```vb
SPLIT (input, delimiter)
```

이 구문은 지정된 구분 기호에 따라 지정된 입력 스트링을 하위 스트링으로 분할하는 데 사용됩니다.

## <a name="arguments"></a>인수

`input`: *스트링*

분할할 텍스트입니다.

`length`: *정수*

단일 부분 스트링의 최대 길이입니다.

`delimiter`: *스트링*

하위 스트링을 구분하는 데 사용되는 구분 기호입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="usage-notes"></a>사용 참고 사항

반환되는 목록의 기록 구조는 *스트링* 유형의 **Value** 필드로 구성됩니다. 반환되는 목록의 모든 기록은 이 필드에 생성된 하위 스트링을 포함합니다.

`delimiter` 인수가 비어 있으면 반환되는 새 목록은 *스트링* 유형의 **값** 필드가 있는 하나의 기록으로 구성됩니다. 이 필드는 입력 텍스트를 포함합니다.

`input` 인수가 비어 있으면 비어 있는 새 목록이 반환됩니다. `input` 또는 `delimiter` 인수가 지정되지 않은 경우(null) 애플리케이션 예외가 발생합니다.

## <a name="example-1"></a>예시 1

`SPLIT ("abcd", 3)` 스트링 유형의 **Value** 필드가 있는 두 개의 기록으로 *구성* 된 새 목록을 반환합니다. 첫 번째 기록의 **값** 필드에는 텍스트 **'abc'** 가 포함되고 두 번째 기록의 **값** 필드에는 텍스트 **'d'** 가 포함됩니다.

## <a name="example-2"></a>예시 2

`SPLIT ("XAb aBy", "aB")` 스트링 유형의 **Value** 필드가 있는 세 개의 기록으로 *구성* 된 새 목록을 반환합니다. 첫 번째 기록의 **값** 필드에는 텍스트 **'X'** 가 포함되고 두 번째 기록의 **값** 필드에는 텍스트 **'&nbsp;'** 가 포함되며 세 번째 기록의 **값** 필드에는 텍스트 **'y'** 가 포함됩니다. 

## <a name="example-3"></a>예시 3

[INDEX](er-functions-list-index.md) 함수를 사용하여 지정된 입력 스트링의 개별 요소에 액세스할 수 있습니다. **계산된 필드** 유형의 **MyList** 데이터 소스를 입력하고 이에 대해 `SPLIT("abc", 1)` 표현식을 구성하면 `INDEX(MyList,2).Value` 표현식은 텍스트 **'b'** 를 반환합니다.

## <a name="example-4"></a>예시 4

[ENUMERATE](er-functions-list-enumerate.md) 함수는 또한 지정된 입력 스트링의 개별 요소에 액세스하는 데 도움이 될 수 있습니다. 먼저 **계산된 필드** 유형의 **MyList** 데이터 원본을 입력하고 이에 대해 `SPLIT("abc", 1)` 식을 구성한 다음 **계산된 필드** 유형의 **EnumeratedList** 데이터 원본을 입력하고 이에 대해 `ENUMERATE(MyList)` 식을 구성하면 `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` 식이 **'b'** 텍스트를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
