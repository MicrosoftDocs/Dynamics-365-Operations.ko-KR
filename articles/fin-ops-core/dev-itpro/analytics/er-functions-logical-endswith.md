---
title: ENDSWITH ER 함수
description: 이번에는 ENDSWITH 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 02/11/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: d2fa1c0e61e964de9b7dff36fe6a8c2813802e1cc22341ce4ddd73a17751a9c7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8461015"
---
# <a name="endswith-er-function"></a>ENDSWITH ER 함수

[!include [banner](../includes/banner.md)]

이 `ENDSWITH` 함수는 지정된 입력이 지정된 텍스트로 끝나는지 여부를 결정합니다. 지정된 입력이 지정된 텍스트로 끝나면 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
ENDSWITH (input, end text)
```

## <a name="arguments"></a>인수

`input`: *스트링*

*스트링* 유형 또는 스트링 상수의 데이터 소스 항목의 유효한 경로(값은 두 번째 인수로 끝날 수 있음).

`start text`: *스트링*

*스트링* 데이터 유형 또는 스트링 상수의 데이터 소스의 유효한 경로. 값은 첫 번째 인수의 끝에 있을 수 있습니다.

## <a name="return-values"></a>반환 값

*부울*

결과 *부울* 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

이 함수는 [Microsoft Dataverse](/power-platform/admin/data-integrator)관련 매핑이 [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md)에서 액세스하도록 구성된 경우에만 [FILTER](er-functions-list-filter.md) 함수의 조건 표현식을 지정하는 데 사용할 수 있습니다. 그렇지 않으면 디자인 타임에 예외가 throw됩니다. 받은 메시지는 `FILTER` 함수 대신 [WHERE](er-functions-list-where.md) 함수를 사용할 것을 권장합니다.

## <a name="example-1"></a>예시 1

`ENDSWITH ("abc", "d")` 표현식은 **FALSE** 를 반환하는 반면 `ENDSWITH ("abc", "C")` 표현식은 **TRUE** 를 반환합니다.

## <a name="example-2"></a>예시 2

**모델** 데이터 소스의 **주소** 필드 값이 **USA** 스트링으로 끝나는 경우 `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` 표현식은 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[논리 함수](er-functions-category-logical.md)
