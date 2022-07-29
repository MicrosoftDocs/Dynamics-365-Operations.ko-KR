---
title: OR ER 함수
description: 이번에는 OR 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: f6751c70599b5e3c05b9d1c69a95e82673b230210170cfead1e6a87c57d59c7f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460926"
---
# <a name="or-er-function"></a>OR ER 함수

[!include [banner](../includes/banner.md)]

이 `OR` 함수는 지정된 모든 조건이 거짓이면 **FALSE** 의 *부울* 값을 반환합니다. 지정된 조건이 true이면 함수는 **TRUE** 의 *부울* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>인수

`condition 1`: *부울*

테스트해야 하는 유효한 조건식입니다. 이 인수는 필수입니다.

`condition N`: *부울*

테스트해야 하는 유효한 조건식입니다. 이러한 추가 인수는 선택 사항입니다.

## <a name="return-values"></a>반환 값

*부울*

결과 *부울* 값입니다.

## <a name="example"></a>예시

`OR (1=2, "a"="a")` **TRUE** 를 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[논리 함수](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]