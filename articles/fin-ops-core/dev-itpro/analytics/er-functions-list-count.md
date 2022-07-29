---
title: COUNT ER 함수
description: 이번에는 COUNT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 0fc122dafd6be90d090ba3b79a8c2eccab74d77441f82db71cb5e08d13d13518
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460849"
---
# <a name="count-er-function"></a>COUNT ER 함수

[!include [banner](../includes/banner.md)]

이 `COUNT` 함수는 목록이 비어 있지 않은 경우 지정된 목록의 기록 수를 나타내는 *정수* 값을 반환합니다. 목록이 비어 있으면 이 함수는 **0** 을 반환합니다.

## <a name="syntax"></a>구문

```vb
COUNT (list)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

## <a name="return-values"></a>반환 값

*정수*

결과 숫자 값입니다.

## <a name="example"></a>예시

`COUNT (SPLIT("abcd" , 3))` 이 예시에서 사용된 `SPLIT` 함수는 두 개의 기록으로 구성된 목록을 생성하기 때문에 **2** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]