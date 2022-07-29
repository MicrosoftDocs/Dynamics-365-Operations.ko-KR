---
title: 오른쪽 ER 함수
description: 이번에는 RIGHT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 45696d0498f712218126af8557521a2317d584eea5059ac3b588d3792d42495c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460604"
---
# <a name="right-er-function"></a>오른쪽 ER 함수

[!include [banner](../includes/banner.md)]

이 `RIGHT` 함수는 지정된 스트링의 끝에서 지정된 문자 수를 나타내는 *스트링* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
RIGHT (text, number)
```

## <a name="arguments"></a>인수

`text`: *스트링*

원본 텍스트를 나타내는 *스트링* 값입니다.

`number`: *정수*

원본 텍스트의 끝에서 반환되어야 하는 문자 수입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="example"></a>예시

`RIGHT ("Sample", 3)` **'ple'** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]