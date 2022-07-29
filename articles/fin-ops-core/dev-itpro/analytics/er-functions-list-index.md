---
title: 색인 ER 함수
description: 이번에는 INDEX 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 05/20/2021
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
ms.openlocfilehash: e68f1690d6f852b0db560ef67a36fbde9e099715942a4b8a6e486d759af46682
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460801"
---
# <a name="index-er-function"></a>색인 ER 함수

[!include [banner](../includes/banner.md)]

이 `INDEX` 함수는 지정된 목록에서 지정된 숫자 색인을 사용하여 선택한 *컨테이너(기록)* 값을 반환합니다. 색인이 지정된 목록의 기록 범위를 벗어나면 예외가 발생합니다.

## <a name="syntax"></a>구문

```vb
INDEX (list, index)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

`index`: *정수*

지정된 목록에서 원하는 기록의 위치를 나타내는 숫자 색인입니다.

> [!NOTE]
> 이 함수에는 **1** 부터 시작하는 번호 매기기가 사용되므로 값 1을 지정하여 지정된 목록의 첫 번째 기록을 반환합니다.

## <a name="return-values"></a>반환 값

*컨테이너(기록)*

결과 기록 값입니다.

## <a name="example-1"></a>예시 1

*계산된 필드* 유형의 데이터 소스 **DS** 를 입력하고 `SPLIT ("A|B|C", "|")` 표현식이 포함된 경우 `DS.Value` 표현식은 이 기록 목록의 두 번째 기록에 대한 텍스트 값 **'B'** 를 반환합니다. `INDEX (SPLIT ("A|B|C", "|"), 2).Value` 표현식은 텍스트 값 **'B'** 도 반환합니다.

## <a name="example-2"></a>예시 2

*계산된 필드* 유형의 데이터 소스 **DS** 를 입력하고 여기에 `SPLIT ("A|B|C", "|")` 표현식이 포함되어 있으면 `INDEX (SPLIT ("A|B|C", "|"), 4).Value` 표현식에서 런타임에 예외가 발생합니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
