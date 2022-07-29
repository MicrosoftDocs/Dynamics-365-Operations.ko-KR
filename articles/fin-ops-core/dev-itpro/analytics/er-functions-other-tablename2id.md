---
title: TABLENAME2ID ER 함수
description: 이번에는 TABLENAME2ID 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: a500eda75fbb5867f74b56753ee45016c60803b06f508340540764a6cd0399cc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460617"
---
# <a name="tablename2id-er-function"></a>TABLENAME2ID ER 함수

[!include [banner](../includes/banner.md)]

이 `TABLENAME2ID` 함수는 지정된 테이블 이름에 대한 테이블 ID의 숫자 표현을 *정수* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a>인수

`text`: *스트링*

유효한 테이블 이름을 나타내는 텍스트 값입니다.

## <a name="return-values"></a>반환 값

*정수*

결과 숫자 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

이 함수를 실행하면 동일한 회사 이름을 사용하더라도 Microsoft Dynamics 365 Finance의 다른 인스턴스에서 다른 결과를 얻을 수 있습니다.

## <a name="example"></a>예시

`TABLENAME2ID ("Intrastat")` **1510** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[기타(비즈니스 도메인별) 함수](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]