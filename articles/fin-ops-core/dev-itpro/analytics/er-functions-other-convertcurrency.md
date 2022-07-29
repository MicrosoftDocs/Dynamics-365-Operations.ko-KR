---
title: CONVERTCURRENCY ER 함수
description: 이번에는 CONVERTCURRENCY 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: dc71ccedcdfc8a3dc9d7e087d29467bd3bbe72c3c5588872dbeaf3aa1dd35d2b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460917"
---
# <a name="convertcurrency-er-function"></a>CONVERTCURRENCY ER 함수

[!include [banner](../includes/banner.md)]

이 `CONVERTCURRENCY` 함수는 지정된 날짜에 지정된 회사의 설정을 사용하여 지정된 통화 금액을 지정된 소스 통화에서 지정된 대상 통화로 변환한 결과를 나타내는 *Real* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a>인수

`amount`: *정수* 또는 *실수*

변환해야 하는 금액을 나타내는 숫자 값입니다.

`source currency`: *스트링*

소스 통화의 코드입니다.

`target currency`: *스트링*

대상 통화의 코드입니다.

`date`: *날짜*

변환에 대한 환율을 결정하는 데 사용되는 날짜를 나타내는 *날짜* 값입니다.

`company`: *스트링*

변환에 사용되는 설정을 제공하는 회사의 코드를 나타내는 *스트링* 값입니다.

## <a name="return-values"></a>반환 값

*실수*

결과 숫자 값입니다.

## <a name="example"></a>예시

`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` **DEMF** 회사의 설정에 따라 현재 세션 날짜에 1유로에 해당하는 미국 달러를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[기타(비즈니스 도메인별) 함수](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]