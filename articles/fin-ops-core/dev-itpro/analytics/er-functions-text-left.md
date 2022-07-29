---
title: 왼쪽 ER 함수
description: 이번에는 LEFT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/11/2019
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
ms.openlocfilehash: 5d0056dbe46b20432aacb35a971895b987fdbf1b8ebc0d2679bb1e52eb3c4cc2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460936"
---
# <a name="left-er-function"></a>왼쪽 ER 함수

[!include [banner](../includes/banner.md)]

이 `LEFT` 함수는 지정된 스트링의 시작 부분부터 지정된 문자 수를 나타내는 *스트링* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
LEFT (text, number)
```

## <a name="arguments"></a>인수

`text`: *스트링*

원본 텍스트를 나타내는 *스트링* 값입니다.

`number`: *정수*

원본 텍스트의 시작 부분에서 반환되어야 하는 문자 수입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="example"></a>예시

`LEFT ("Sample", 3)` **'샘'** 을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]