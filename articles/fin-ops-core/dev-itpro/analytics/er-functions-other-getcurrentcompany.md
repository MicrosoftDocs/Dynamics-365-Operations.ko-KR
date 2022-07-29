---
title: GETCURRENTCOMPANY ER 함수
description: 이번에는 GETCURRENTCOMPANY 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: c74ffaf1ee134da8d962e054656301d5e99827ff53f560f5d93f9dcb51819c13
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460611"
---
# <a name="getcurrentcompany-er-function"></a>GETCURRENTCOMPANY ER 함수

[!include [banner](../includes/banner.md)]

이 `GETCURRENTCOMPANY` 함수는 사용자가 현재 로그인한 법인(회사)의 코드를 나타내는 *스트링* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="example"></a>예시

`GETCURRENTCOMPANY ()` **Contoso Entertainment System USA** 회사에 로그인한 사용자에 대해 **USMF** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[기타(비즈니스 도메인별) 함수](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]