---
title: NULLDATE ER 함수
description: 이번에는 NULLDATE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 657766a838fbcd32c6b8bb0ba1f728e9dbbac92e103c219f3eeeab7ecd8c747d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460837"
---
# <a name="nulldate-er-function"></a>NULLDATE ER 함수

[!include [banner](../includes/banner.md)]

이 `NULLDATE` 함수는 *null* 날짜(1900년 1월 1일)를 나타내는 **Date** 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
NULLDATE () as 
```

## <a name="return-values"></a>반환 값

*날짜*

결과 날짜 값입니다.

## <a name="example-1"></a>예시 1

`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` 지정된 사용자 지정 형식에 따라 **null** 날짜인 1900년 1월 1일을 **'1900-01-01'** 로 반환합니다.

## <a name="example-2"></a>예시 2

`IF( Invoice.DocumentDate = NULLDATE(), true, false)` **DocumentDate** 필드의 값이 **null** 날짜와 같을 때 표현식은 **True를** 반환합니다. 이 예에서 **Invoice** 는 **재무/테이블 기록** 유형의 전자 보고(ER) 데이터 소스이며 CustInvoiceJour 테이블을 참조합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]