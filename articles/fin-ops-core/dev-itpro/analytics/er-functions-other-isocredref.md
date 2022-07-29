---
title: ISOCREDREF ER 함수
description: 이번에는 ISOCREDREF 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: e13b9bacc642917e6a520968630fc75fb30bc9dc3fd02b2d9aa3cfb2ceb33790
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460619"
---
# <a name="isocredref-er-function"></a>ISOCREDREF ER 함수

[!include [banner](../includes/banner.md)]

이 `ISOCREDREF` 함수는 지정된 송장 번호의 숫자와 알파벳 기호를 기반으로 국제 표준화 기구(ISO) 채권자 참조를 나타내는 *스트링* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a>인수

`invoice number digits`: *스트링*

송장 번호의 자릿수를 나타내는 텍스트 값입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

> [!NOTE] 
> ISO 규격이 아닌 알파벳에서 기호를 제거하려면 `invoice number digits` 인수가 이 함수에 전달되기 전에 변환되어야 합니다.

## <a name="example"></a>예시

`ISOCredRef ("VEND-200002")` **'RF23VEND-200002'** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[기타(비즈니스 도메인별) 함수](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]