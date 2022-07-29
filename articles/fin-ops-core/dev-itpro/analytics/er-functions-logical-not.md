---
title: NOT ER 함수
description: 이번에는 NOT 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 094c60157d3ac4091fb02b24dcc00dddba2397abe87510952371a779eb3a2f4a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460927"
---
# <a name="not-er-function"></a>NOT ER 함수

[!include [banner](../includes/banner.md)]

이 `NOT` 함수는 지정된 조건의 반전된 논리 값을 *부울* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
NOT (condition)
```

## <a name="arguments"></a>인수

`condition`: *부울*

반전되어야 하는 유효한 조건식입니다.

## <a name="return-values"></a>반환 값

*부울*

결과 *부울* 값입니다.

## <a name="example"></a>예시

`NOT (TRUE)` **FALSE** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[논리 함수](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]