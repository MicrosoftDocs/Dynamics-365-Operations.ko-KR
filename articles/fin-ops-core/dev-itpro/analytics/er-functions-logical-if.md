---
title: IF ER 함수
description: 이번에는 IF 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 8bd0a7181b441a0a00163b31d4f1116c8bad0705a7f3b52a2985f1b31ecdb28b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460928"
---
# <a name="if-er-function"></a>IF ER 함수

[!include [banner](../includes/banner.md)]

`IF` 함수는 지정된 조건이 충족되면 첫 번째 지정된 값을 반환합니다. 그렇지 않으면 두 번째 지정된 값을 반환합니다. 반환되는 값은 지원되는 모든 데이터 유형의 값일 수 있습니다.

## <a name="syntax"></a>구문

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a>인수

`condition`: *부울*

테스트해야 하는 유효한 조건식입니다.

`first value`: *지원되는 모든 데이터 유형*

조건이 충족되면 반환되는 결과입니다.

`second value`: *지원되는 모든 데이터 유형*

조건이 충족되지 않은 경우 반환되는 결과입니다.

## <a name="return-values"></a>반환 값

*지원되는 모든 데이터 유형*

지원되는 데이터 유형의 결과 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

`first value` 및 `second value` 인수는 동일한 데이터 유형을 사용하여 지정해야 합니다. 구성된 값의 데이터 형식이 일치하지 않으면 디자인 타임에 예외가 발생합니다.

첫 번째 값과 두 번째 값이 *컨테이너(기록)* 또는 *기록 목록* 데이터 유형의 값인 경우 결과에는 두 값에 모두 존재하는 필드만 있습니다.

## <a name="example"></a>예시

`IF (1=2, "condition is met", "condition is not met")` **'조건이 충족되지 않음'** 스트링을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[논리 함수](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]