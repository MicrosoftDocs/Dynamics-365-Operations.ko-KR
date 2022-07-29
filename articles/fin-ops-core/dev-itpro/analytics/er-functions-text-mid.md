---
title: 중간 ER 함수
description: 이번에는 MID 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 33a8d02e937b3d88d98cac96ae28a30345ccffb23be37d7add67f721dfb9cc70
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460941"
---
# <a name="mid-er-function"></a>중간 ER 함수

[!include [banner](../includes/banner.md)]

이 `MID` 함수는 지정된 위치에서 시작하여 지정된 스트링에서 지정된 수의 문자를 나타내는 *스트링* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a>인수

`text`: *스트링*

문자를 반환할 텍스트를 지정하는 *스트링* 값입니다.

`starting position`: *정수*

지정된 텍스트에서 반환되어야 하는 첫 번째 문자의 위치를 지정하는 *정수* 값입니다.

`number of characters`: *정수*

지정된 시작 위치에서 시작하여 반환되어야 하는 문자 수를 지정하는 *정수* 값입니다.

## <a name="return-values"></a>반환 값

*스트링*

결과 텍스트 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

`starting position` 인수의 값이 0보다 작으면 반환되는 문자는 지정된 스트링의 첫 번째 위치부터 계산됩니다.

`starting position` 인수 값이 지정된 스트링의 길이를 초과하면 빈 스트링이 반환됩니다.

## <a name="example"></a>예시

`MID ("Sample", 2, 3)` **'amp'** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]