---
title: CHAR ER 함수
description: 이번에는 CHAR 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: e422ccc406e919b2191f4bccb1ac8198bba84b09e9f01f6971876e2c6507d6d3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460734"
---
# <a name="char-er-function"></a>CHAR ER 함수

[!include [banner](../includes/banner.md)]

이 `CHAR` 함수는 지정된 유니코드 번호가 참조하는 단일 문자를 나타내는 *스트링* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
CHAR (number)
```

## <a name="arguments"></a>인수

`number`: *정수*

예상되는 단일 문자에 해당하는 숫자입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

이 함수가 반환하는 스트링은 상위 **FILE** 형식 요소에서 선택한 인코딩에 따라 다릅니다. 지원되는 인코딩 목록은 [인코딩 클래스](/dotnet/api/system.text.encoding)를 참조하십시오.

## <a name="example"></a>예시

`CHAR (255)` **'ÿ'** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]