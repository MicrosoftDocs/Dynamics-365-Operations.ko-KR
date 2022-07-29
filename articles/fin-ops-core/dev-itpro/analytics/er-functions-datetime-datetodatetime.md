---
title: DATETODATETIME ER 함수
description: 이번에는 DATETODATETIME 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 1e5fa64b776ed2702ac65a2f6416adcf657c748caa1156a71b4c3e99ee188880
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460613"
---
# <a name="datetodatetime-er-function"></a>DATETODATETIME ER 함수

[!include [banner](../includes/banner.md)]

이 `DATETODATETIME` 함수는 지정된 날짜 값에서 표준 시간대(그리니치 표준시 \[GMT\])의 날짜/시간 값으로 변환된 *DateTime* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a>인수

`date` *날짜* 시험 감독관

변환할 날짜를 나타내는 날짜 값입니다.

## <a name="return-values"></a>반환 값

*날짜 시간*

결과 날짜/시간 값입니다.

## <a name="example-1"></a>예시 1

`DATETODATETIME (CompInfo. 'getCurrentDate()')` 2015년 12월 24일 현재 Microsoft Dynamics 365 Finance 세션의 날짜를 **2015년 12월 24일 오전** 12:00:00로 반환합니다. 이 예시에서 **CompInfo** 는 **재무 및 운영/테이블** 유형의 전자 보고(ER) 데이터 소스이며 CompanyInfo 테이블을 참조합니다.

## <a name="example-2"></a>예시 2

`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` 날짜/시간 값 **11/12/2019 12:00:00 AM** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]