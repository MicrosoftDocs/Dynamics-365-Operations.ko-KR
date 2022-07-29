---
title: SESSIONTODAY ER 함수
description: 이번에는 SESSIONTODAY 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: caadfbe9d82c967b84abd362211a2ecec1bdd0481c7f3907816b7aec23883175
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460833"
---
# <a name="sessiontoday-er-function"></a>SESSIONTODAY ER 함수

[!include [banner](../includes/banner.md)]

이 `SESSIONTODAY` 함수는 현재 애플리케이션 세션 날짜를 나타내는 *Date* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a>반환 값

*날짜*

결과 날짜 값입니다.

## <a name="example"></a>예시

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` 선택한 독일 문화와 지정된 형식을 기반으로 현재 애플리케이션 세션 날짜인 2015년 12월 24일을 **'24-12-2015'** 스트링으로 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]