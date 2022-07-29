---
title: EMPTYRECORD ER 함수
description: 이번에는 EMPTYRECORD 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 5aea5533f5d0530cdc9ccae0b0b8355245599bc77e37fde87a13e8e5a1443695
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460790"
---
# <a name="emptyrecord-er-function"></a>EMPTYRECORD ER 함수

[!include [banner](../includes/banner.md)]

이 `EMPTYRECORD` 함수는 지정된 기록 목록 또는 기록와 구조가 동일한 null *컨테이너(기록)* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a>인수

`list`: *기록 목록* 또는 *컨테이너(기록)*

*기록 목록* 또는 *컨테이너(기록)* 유형의 데이터 소스의 유효한 경로입니다.

## <a name="return-values"></a>반환 값

*컨테이너(기록)*

결과 기록 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

> [!NOTE] 
> null 기록은 모든 필드에 빈 값이 있는 기록입니다. 빈 값은 숫자의 경우 **0**, 스트링의 경우 빈 스트링 등입니다.

## <a name="example"></a>예시

`EMPTYRECORD (SPLIT ("abc", 1))` 함수에서 반환하는 목록과 동일한 구조를 가진 `SPLIT` 새 빈 기록을 반환합니다. 자세한 내용은 [분할](er-functions-list-split.md)을 참조하십시오.

## <a name="additional-resources"></a>추가 리소스

[기록 함수](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]