---
title: GUIDVALUE ER 함수
description: 이번에는 GUIDVALUE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 76b918354be9b5b695cfec9d0fe7aca6c5c9e08e01b6e3d0ddfa28af877942e3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460778"
---
# <a name="guidvalue-er-function"></a>GUIDVALUE ER 함수

[!include [banner](../includes/banner.md)]

이 `GUIDVALUE` 함수는 *스트링* 유형의 지정된 입력을 *GUID* 유형의 데이터 항목으로 변환합니다.

## <a name="syntax"></a>구문

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a>인수

`input`: *스트링*

*스트링* 유형의 데이터 소스의 유효한 경로입니다.

## <a name="return-values"></a>반환 값

*GUID*

결과 전 세계적 단일 식별자(GUID) 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

반대 방향으로 변환을 수행하려면(즉, *GUID* 데이터 유형의 지정된 입력을 *스트링* 데이터 유형의 데이터 항목으로 변환하기 위해) [TEXT](er-functions-text-text.md) 함수를 사용할 수 있습니다.

## <a name="example"></a>예시

모델 매핑에서 다음 데이터 소스를 정의합니다.

- 표현식을 포함하는 *계산된 필드* 유형의 **myID** 데이터 소스 `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`
- UserInfo 테이블을 참조하는 *테이블 기록* 유형의 **사용자** 데이터 소스

이후 *GUID* 데이터 형식의 **objectId** 필드를 기준으로 UserInfo 테이블을 필터링하는 등의 `FILTER (Users, Users.objectId = myID)` 표현식을 사용할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]