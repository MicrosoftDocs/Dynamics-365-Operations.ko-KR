---
title: REPLACE ER 함수
description: 이번에는 REPLACE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: e7bee3ed0531df64e813423f7280a62fd2afe77432ae05c1fb21264578c9e4ca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460992"
---
# <a name="replace-er-function"></a>REPLACE ER 함수

[!include [banner](../includes/banner.md)]

이 `REPLACE` 함수는 전체 또는 일부가 다른 스트링으로 대체된 후 지정된 텍스트 스트링을 *스트링* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a>인수

`text`: *스트링*

*스트링* 유형의 데이터 소스의 유효한 경로입니다.

`pattern`: *스트링*

`regular expression flag` 인수가 **FALSE** 이면 이 인수에는 대체되어야 하는 텍스트가 포함됩니다.

`regular expression flag` 인수가 **TRUE** 이면 이 인수에는 검색 패턴과 대체 텍스트를 모두 정의하는 정규식이 포함됩니다.

`replacement`: *스트링*

`regular expression flag` 인수가 **FALSE** 이면 이 인수는 대체로 사용할 텍스트를 포함합니다.

`regular expression flag` 인수가 **TRUE** 이면 이 인수는 사용되지 않습니다.

`regular expression flag`: *부울*

대체를 수행하는 데 정규식이 사용되는지 여부를 나타내는 *부울* 값입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

`regular expression flag` 인수가 **TRUE** 인 경우 이 함수는 `pattern` 인수로 지정된 정규식을 적용하여 변경된 후 지정된 스트링을 반환합니다. 정규식은 대체되어야 하는 문자를 찾는 데 사용됩니다.

`regular expression flag` 인수가 **FALSE** 이면 이 함수는 `pattern` 인수에 정의된 문자 집합이 `replacement` 인수의 문자로 대체된 후 지정된 스트링을 반환합니다. 

## <a name="example-1"></a>예시 1

`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` 숫자가 아닌 모든 기호를 제거하는 정규식을 적용하고 **'19234564971'** 을 반환합니다. 

## <a name="example-2"></a>예시 2

`REPLACE ("abcdef", "cd", "GH", false)` 패턴 **'cd'** 를 스트링 **'GH'** 로 바꾸고 **'abGHef'** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]