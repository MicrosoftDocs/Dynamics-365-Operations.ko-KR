---
title: 번역 ER 함수
description: 이번에는 TRANSLATE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 04/02/2020
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
ms.openlocfilehash: 0b43c1edb2a26ebe01e8d5cf69e1ff377c6c8bf84e889b6bb3d1828d3dc84b53
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460741"
---
# <a name="translate-er-function"></a>번역 ER 함수

[!include [banner](../includes/banner.md)]

이 `TRANSLATE` 함수는 제공된 다른 세트의 문자에서 지정된 텍스트의 문자 교체 결과를 포함하는 *스트링* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a>인수

`text`: *스트링*

*스트링* 유형의 데이터 소스의 유효한 경로입니다.

`pattern`: *스트링*

교체해야 하는 텍스트입니다.

`replacement`: *스트링*

대체 텍스트로 사용할 텍스트입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

이 `TRANSLATE` 함수는 한 번에 한 문자를 바꿉니다. 이 함수는 `text` 인수의 첫 번째 문자를 `pattern` 인수의 첫 번째 문자로 바꾼 다음 두 번째 문자를 바꾸고 완료될 때까지 동일한 흐름을 따릅니다. `text` 및 `pattern` 인수의 문자가 일치하면 `replacement` 인수의 문자와 동일한 위치에 있는 `pattern` 인수의 문자로 대체됩니다. 문자가 `pattern` 인수에 여러 번 나타나는 경우 이 문자의 첫 번째 발생에 해당하는 `replacement` 인수 매핑이 사용됩니다.

## <a name="example-1"></a>예시 1

`TRANSLATE ("abcdef", "cd", "GH")` 다음과 같은 이유로 지정된 **'abcdef'** 텍스트의 **'c'** 문자를 `replacement` 텍스트의 **'G'** 문자로 바꿉니다.
-   **'c'** 문자는 `pattern` 텍스트의 첫 번째 위치에 표시됩니다.
-   `replacement` 텍스트의 첫 번째 위치에는 **'G'** 문자가 포함됩니다.

## <a name="example-2"></a>예시 2

`TRANSLATE ("abcdef", "ccd", "GH")` **'abGdef'** 를 반환합니다.

## <a name="example-3"></a>예시 3

`TRANSLATE ("abccba", "abc", "123")` **'123321'** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]