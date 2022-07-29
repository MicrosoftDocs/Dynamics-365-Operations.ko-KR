---
title: ADDDAYS ER 함수
description: 이번에는 ADDDAYS 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/03/2019
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
ms.openlocfilehash: 8877bf5a1b6c06e1a25fa9ddaca9c3b039bd2e4d01f39eea9065125977f73e9a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460844"
---
# <a name="adddays-er-function"></a>ADDDAYS ER 함수

[!include [banner](../includes/banner.md)]

이 `ADDDAYS` 함수는 지정된 시작 날짜 전후의 지정된 일 수인 *DateTime* 값을 계산합니다.

## <a name="syntax"></a>구문

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a>인수

`datetime`: *날짜 시간*

시작 날짜를 나타내는 날짜/시간 값입니다.

`days`: *정수*

`datetime` 이전 또는 이후의 일 수입니다.

## <a name="return-values"></a>반환 값

*날짜 시간*

결과 날짜/시간 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

`days` 양수 값은 미래 날짜를 생성합니다. 음수 값은 과거 날짜를 생성합니다.

## <a name="example-1"></a>예시 1

`ADDDAYS (NOW(), 7)` 7일 후의 날짜와 시간을 반환합니다.

## <a name="example-2"></a>예시 2

`ADDDAYS (NOW(), -3)` 3일 전의 날짜와 시간을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[날짜 및 시간 함수](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]