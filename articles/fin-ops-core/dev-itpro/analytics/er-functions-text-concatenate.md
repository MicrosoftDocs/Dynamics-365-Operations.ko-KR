---
title: 연결 ER 함수
description: 이번에는 CONCATENATE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 1507e1b8a31ed45e7c540e4e2ff31b79e8de3b866ffbace9de17d7b3e169e877
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460630"
---
# <a name="concatenate-er-function"></a>연결 ER 함수

[!include [banner](../includes/banner.md)]

이 `CONCATENATE` 함수는 지정된 모든 텍스트 스트링을 하나의 스트링으로 결합한 후 *스트링* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>인수

`text 1`: *스트링*

*스트링* 데이터 유형의 데이터 소스에 대한 참조입니다. 이 인수는 필수입니다.

`text N`: *스트링*

*스트링* 데이터 유형의 데이터 소스에 대한 참조입니다. 이러한 추가 인수는 선택 사항입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="example"></a>예시

`CONCATENATE ("abc", "def")` **'abcdef'** 를 반환합니다.

## <a name="usage-notes"></a>사용 참고 사항

`"abc" & "def"` 표현식은 **'abcdef'** 도 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]