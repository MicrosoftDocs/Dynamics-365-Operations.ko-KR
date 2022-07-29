---
title: NULLDATETIME ER 함수
description: 이번에는 NULLDATETIME 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 79bdcaa90ce4002d92a4a0d959c9b94d8c47d7c7c855584d49818fb713bda4b7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460835"
---
# <a name="nulldatetime-er-function"></a>NULLDATETIME ER 함수

[!include [banner](../includes/banner.md)]

이 `NULLDATETIME` 함수는 표준 시간대(그리니치 표준시 \[GMT\])로 **null** 날짜/시간 값(1900년 1월 1일)을 나타내는 *DateTime* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
NULLDATETIME ()
```

## <a name="return-values"></a>반환 값

*날짜 시간*

결과 날짜/시간 값입니다.

## <a name="example"></a>예시

`DATETIMEFORMAT( NULLDATETIME(), "O")` **언어 및 국가/지역 기본 설정** 섹션에서 **표준 시간대 값(GMT)** 이 있는 애플리케이션 사용자가 시작한 프로세스 중에 호출될 때 스트링 값 **1900-01-01T00:00:00.0000000+00:00** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]