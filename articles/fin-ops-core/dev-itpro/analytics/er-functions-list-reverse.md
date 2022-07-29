---
title: REVERSE ER 함수
description: 이번에는 REVERSE 전자 보고(ER) 함수가 사용되는 방법에 대한 정보를 제공합니다.
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
ms.openlocfilehash: 96fc3c2f845f84a5435fd0119a7eaa146caa2dc8da9c931ccfe0915af91ed7cb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460793"
---
# <a name="reverse-er-function"></a>REVERSE ER 함수

[!include [banner](../includes/banner.md)]

이 `REVERSE` 함수는 지정된 목록을 역 정렬 순서로 *기록 목록* 값으로 반환합니다.

## <a name="syntax"></a>구문

```vb
REVERSE (list)
```

## <a name="arguments"></a>인수

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

## <a name="return-values"></a>반환 값

*기록 목록*

결과 기록 목록입니다.

## <a name="example-1"></a>예시 1

*계산된 필드* 유형의 데이터 소스 **DS** 를 입력하고 여기에 `SPLIT ("C|B|A", "|")` 표현식이 포함된 경우 `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` 표현식은 텍스트 값 **'C'** 를 반환합니다.

## <a name="example-2"></a>예시 2

**공급 업체** 가 VendTable 테이블을 참조하는 전자 보고(ER) 데이터 원본으로 구성된 경우 `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` 표현식은 이름을 기준으로 내림차순으로 정렬된 공급 업체 목록을 반환합니다.

## <a name="additional-resources"></a>추가 리소스

[함수 나열](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]