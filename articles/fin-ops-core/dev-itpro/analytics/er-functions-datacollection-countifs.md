---
title: COUNTIFS ER 함수
description: 이번에는 COUNTIFS 전자 보고(ER) 함수를 사용하는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 23da226fe1ef95ad037c33a5b423968531557896e300c6223b36bc44b0a8a015
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460637"
---
# <a name="countifs-er-function"></a>COUNTIFS ER 함수

[!include [banner](../includes/banner.md)]

이 `COUNTIFS` 함수는 형식 실행 중에 아웃바운드 문서를 생성하기 위해 형식 요소를 사용할 때 수집된 형식 요소의 수를 나타내는 *정수* 값을 반환하고 지정된 조건을 충족합니다. 각 조건은 키 범위와 키 값으로 구성됩니다.

## <a name="syntax"></a>구문

```vb
COUNTIFS (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a>인수

`condition 1 range`: *스트링*

전자 보고(ER) 형식 구성 요소의 **수집된 데이터 키** 이름 속성에 구성된 표현식에서 반환되는 값입니다. 이 인수는 필수입니다.

`condition 1 value`: *스트링*

ER 형식 구성 요소의 **수집된 데이터 키 값** 속성에 구성된 표현식에서 반환되는 값입니다. 이 인수는 필수입니다.

`condition N range`: *스트링*

ER 형식 구성 요소의 **수집된 데이터 키 이름** 속성에 구성된 표현식에서 반환되는 값입니다. 이러한 추가 인수는 선택 사항입니다.

`condition N value`: *스트링*

ER 형식 구성 요소의 **수집된 데이터 키 값** 속성에 구성된 표현식에서 반환되는 값입니다. 이러한 추가 인수는 선택 사항입니다.

## <a name="return-values"></a>반환 값

*정수*

결과 숫자 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

**수집된 데이터 키 이름** 및 **수집된 데이터 키 값** 특성은 **출력 세부 사항 수집** 옵션이 켜져 있는 **Common\\File** 구성 요소 아래에 있는 ER 형식의 **XML 요소 구성 요소** 또는 **시퀀스 구성 요소** 에 대해 구성할 수 있습니다.

이 함수는 현재 **Common\\File** 구성 요소의 **출력 세부 정보 수집** 옵션이 꺼져 있을 때 **0**(영) 값을 반환합니다.

`condition range` 인수에서 와일드카드 문자 **'\*'** 를 사용하여 여러 문자를 나타낼 수 있습니다.

`condition value` 인수에서 와일드카드 문자 **'\*'** 를 사용하여 여러 문자를 나타낼 수 있습니다.

## <a name="example"></a>예시

이 함수를 사용하는 방법에 대한 자세한 내용은 [IT 서비스/솔루션 구성 요소 획득/개발 비즈니스 프로세스](tasks/er-format-counting-summing-1.md)의 일부인 **계산 및 합산 작업 가이드에 ER 형식 출력 데이터 사용** 을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

[데이터 수집 함수](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]