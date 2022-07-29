---
title: AND ER 함수
description: 이번에는 AND 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 4d327f0f961a11fecdbc055ffbb1f3d8bc15bcfdd732e2565d0a5e9e2c0a31ca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460929"
---
# <a name="and-er-function"></a>AND ER 함수

[!include [banner](../includes/banner.md)]

`AND` 함수는 지정된 모든 조건이 참인 경우 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>인수

`condition 1`: *부울*

테스트해야 하는 유효한 조건식입니다. 이 인수는 필수입니다.

`condition N`: *부울*

테스트해야 하는 유효한 조건식입니다. 이러한 추가 인수는 선택 사항입니다.

## <a name="return-values"></a>반환 값

*부울*

결과 *부울* 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

논리 함수의 인수에서 데이터 소스 참조, 숫자 및 텍스트 값, 부울 값, 비교 연산자 및 기타 전자 보고(ER) 함수를 사용할 수 있습니다. 그러나 모든 인수는 **TRUE** 또는 **FALSE** 의 *부울* 값으로 평가되어야 합니다.

## <a name="example"></a>예시

`AND (1=1, "a"="a")` **TRUE** 를 반환합니다.

`AND (1=2, "a"="a")` **FALSE** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[논리 함수](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]