---
title: NUMBERVALUE개의 ER 함수
description: 이번에는 NUMBERVALUE개의 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: bcb76310a53c86b68f18085e203d11f405b16946a25fe1be67e649f83335d1f8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460641"
---
# <a name="numbervalue-er-function"></a>NUMBERVALUE개의 ER 함수

[!include [banner](../includes/banner.md)]

이 `NUMBERVALUE` 함수는 지정된 *스트링* 값에서 변환된 *Real* 값을 반환합니다. 변환하는 동안 지정된 소수 및 자릿수 그룹화 구분 기호가 고려됩니다.

## <a name="syntax"></a>구문

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a>인수

`text`: *스트링*

*실수* 로 변환해야 하는 텍스트 값입니다.

`decimal separator`: 스트링

소수 구분 기호입니다. 십진수의 정수와 소수 부분을 구분하는 데 사용됩니다.

`digit grouping separator`: *스트링*

숫자 그룹화 구분 기호입니다. 천 단위 구분 기호로 사용됩니다.

## <a name="return-values"></a>반환 값

*실수*

결과 숫자 값입니다.

## <a name="example"></a>예시

`NUMBERVALUE( "1 234,56", ",", " ")` **1234.56** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[유형 변환 함수](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]