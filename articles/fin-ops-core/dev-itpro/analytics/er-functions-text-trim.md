---
title: TRIM ER 함수
description: 이번에는 TRIM 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 02/28/2022
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
ms.openlocfilehash: 816f6d6623bb778c9186d294c9b67db7edddd671
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2022
ms.locfileid: "8460680"
---
# <a name="trim-er-function"></a>TRIM ER 함수

[!include [banner](../includes/banner.md)]

이 `TRIM` 함수는 탭, 캐리지 리턴, 줄 바꿈 및 양식 피드 문자가 단일 공백 문자로 대체된 후, 선행 및 후행 공백이 잘린 후, 단어 사이의 여러 공백이 제거된 후 지정된 텍스트 스트링을 *스트링* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
TRIM (text)
```

## <a name="arguments"></a>인수

`text`: *스트링*

*스트링* 유형의 데이터 소스의 유효한 경로입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

경우에 따라 선행 공백과 후행 공백을 자르고 싶지만 지정된 텍스트의 서식을 유지하려는 경우가 있습니다. 예를 들어, 이 텍스트가 여러 줄 텍스트 상자에 입력할 수 있고 줄 바꿈 및 캐리지 리턴 형식을 포함할 수 있는 주소를 나타내는 경우가 있습니다. 이 경우 다음 표현식을 사용하십시오. `REPLACE(text,"^[ \t]+|[ \t]+$","", true)` 여기서 `text`은(는) 지정된 텍스트 스트링을 참조하는 인수입니다.

## <a name="example-1"></a>예시 1

`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` **'샘플 텍스트'** 를 반환합니다.

## <a name="example-2"></a>예시 2

`TRIM (CONCATENATE (CHAR(10), "`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(9),"`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(13)))` **'샘플 텍스트'** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)

[REPLACE ER 함수](er-functions-text-replace.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
