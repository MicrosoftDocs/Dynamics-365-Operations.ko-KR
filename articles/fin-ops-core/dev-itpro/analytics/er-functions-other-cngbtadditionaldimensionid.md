---
title: CN_GBT_ADDITIONALDIMENSIONID ER 함수
description: 이번에는 CN_GBT_ADDITIONALDIMENSIONID 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 9217b70076a369c18a94f820f19ca371c2d8aca61ab72b6be762592f39fa1160
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460918"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a>CN_GBT_ADDITIONALDIMENSIONID ER 함수

[!include [banner](../includes/banner.md)]

이 `CN_GBT_ADDITIONALDIMENSIONID` 함수는 지정된 스트링에서 가져온 단일 재무 차원 ID를 나타내는 *스트링* 값을 반환합니다. 지정된 스트링은 모든 차원을 쉼표로 구분된 ID 목록으로 표시합니다.

## <a name="syntax"></a>구문

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a>인수

`text`: *스트링*

모든 차원을 쉼표로 구분된 ID 목록으로 표시하는 *스트링* 값입니다.

`number`: 정수

지정된 스트링에서 요청된 차원의 시퀀스 코드를 정의하는 *정수* 값입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="example"></a>예시

`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` **'CC'** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[기타(비즈니스 도메인별) 함수](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]