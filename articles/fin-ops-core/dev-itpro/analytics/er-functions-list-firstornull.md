---
title: FIRSTORNULL ER 함수
description: 이번에는 FIRSTORNULL 전자 보고(ER) 함수가 사용되는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 11/29/2019
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
ms.openlocfilehash: 18c8f79d7d6306d9973c5a3f129b9cde38d05d58502a2c83ac89a2bd10aaaeab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460802"
---
# <a name="firstornull-er-function"></a>FIRSTORNULL ER 함수

[!include [banner](../includes/banner.md)]

이 `FIRSTORNULL` 함수는 해당 기록이 비어 있지 않은 경우 지정된 목록의 첫 번째 기록을 *컨테이너(기록)* 값으로 반환합니다. 기록이 비어 있으면 이 함수는 null *컨테이너(기록)* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

## <a name="return-values"></a>반환 값

*컨테이너(기록)*

결과 기록 값입니다.

## <a name="example"></a>예시

`FIRSTORNULL(SPLIT("",1)).Value` 표현식은 빈 스트링(**''**)을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]