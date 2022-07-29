---
title: ISVALIDCHARACTERISO7064 ER 함수
description: 이번에는 ISVALIDCHARACTERISO7064 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 884fbf7371ea9d9ac931655f8b11ec1e13c83a46aaa831c96f5d558209205e09
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460618"
---
# <a name="isvalidcharacteriso7064-er-function"></a>ISVALIDCHARACTERISO7064 ER 함수

[!include [banner](../includes/banner.md)]

지정된 스트링이 유효한 국제 은행 계좌 번호(IBAN)를 나타내는 경우 `ISVALIDCHARACTERISO7064` 함수는 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>인수

`text`: *스트링*

IBAN을 나타내는 텍스트 값입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="example"></a>예시

`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` **TRUE** 을 반환합니다. 

`ISVALIDCHARACTERISO7064 ("AT61")` **FALSE** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[기타(비즈니스 도메인별) 함수](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]