---
title: LISTOFFIRSTITEM ER 함수
description: 이번에는 LISTOFFIRSTITEM 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: e0497a4ee2c44efd4ee8d1551440bd2984ebb0cff9980206b058670a16928986
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460795"
---
# <a name="listoffirstitem-er-function"></a>LISTOFFIRSTITEM ER 함수

[!include [banner](../includes/banner.md)]

이 `LISTOFFIRSTITEM` 함수는 지정된 목록의 첫 번째 기록으로만 구성된 *기록 목록* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="example"></a>예시

`FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` 표현식은 텍스트 값 **'A'** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]