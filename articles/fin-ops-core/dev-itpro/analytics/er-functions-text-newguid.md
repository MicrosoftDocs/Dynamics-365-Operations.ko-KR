---
title: NEWGUID ER 함수
description: 이번에는 NEWGUID 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: 5856a4d765f5136ecb11a34e0255c1ba88818f2c
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2021
ms.locfileid: "8461036"
---
# <a name="newguid-er-function"></a>NEWGUID ER 함수

[!include [banner](../includes/banner.md)]

이 `NEWGUID` 함수는 새로운 전 세계적 단일 식별자(GUID)를 생성하고 이를 *[GUID](er-formula-supported-data-types-primitive.md#guid)* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
NEWGUID ()
```

## <a name="return-values"></a>반환 값

*GUID*

결과 GUID 값입니다.

## <a name="example"></a>예시

`NEWGUID()` 항상 **3afcf7ff-af10-ec11-b6e6-000d3a13209e** 과 같은 새 *GUID* 값을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[텍스트 함수 ](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
