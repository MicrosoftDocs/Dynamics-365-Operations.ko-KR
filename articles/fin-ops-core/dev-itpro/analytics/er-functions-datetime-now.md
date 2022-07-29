---
title: 지금 ER 함수
description: 이번에는 NOW 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: cbbc3623249338c8af943974717a077f68945acfeea2b5e8c4d33c544c58734b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460838"
---
# <a name="now-er-function"></a>지금 ER 함수

[!include [banner](../includes/banner.md)]

이 `NOW` 함수는 현재 애플리케이션 서버 날짜 및 시간을 나타내는 *DateTime* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
NOW ()
```

## <a name="return-values"></a>반환 값

*날짜 시간*

결과 날짜/시간 값입니다.

## <a name="example"></a>예시

`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` 지정된 사용자 지정 형식을 기반으로 **2015년 12월 24일** 현재 애플리케이션 서버 날짜/시간 값을 '24-12-2015'로 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]