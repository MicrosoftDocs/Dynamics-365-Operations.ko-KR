---
title: 데이터 수집 범주의 ER 함수 목록
description: 이번에는 전자 보고(ER)에서 지원되는 데이터 수집 함수에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 2046931732f2d1c1ca040c1c84d4b182c2214f2f44a5a90fceda49298445b743
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460622"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>데이터 수집 범주의 ER 함수 목록

[!include [banner](../includes/banner.md)]

ER(Electronic Reporting) 데이터 수집 함수은 이미 **Text** 또는 **Xml** 형식으로 생성된 출력 데이터를 기반으로 실행 중인 ER 형식으로 카운팅 및 합산을 수행하는 데 사용됩니다. 이 접근 방식은 실행되는 ER 형식의 성능을 개선하고 생성된 문서에 누계 값을 입력하는 등의 다른 용도로 사용됩니다. 이번에는 이러한 함수에 대한 요약을 제공합니다.

## <a name="list-of-supported-functions"></a>지원되는 함수 목록

| 직렬 | 설명 |
|----------|-------------|
| [수집 목록](er-functions-datacollection-collectedlist.md) | 이 함수는 형식 요소의 **수집된 데이터 키 값** 속성에 의해 반환되고 형식 요소가 형식 실행 중에 아웃바운드 문서를 생성하는 데 사용되었을 때 수집된 값 목록을 포함하고 지정된 조건을 충족하는 *기록 목록* 값을 반환합니다. . 각 조건은 키 범위와 키 값으로 구성됩니다. |
| [CountIF](er-functions-datacollection-countif.md) | 이 함수는 형식 요소가 형식 실행 중에 아웃바운드 문서를 생성하는 데 사용되었을 때 수집된 형식 요소의 수를 나타내는 *정수* 값을 반환하고 지정된 조건을 충족합니다. 조건은 키 범위와 키 값으로 구성됩니다. |
| [CountIF](er-functions-datacollection-countifs.md) | 이 함수는 형식 실행 중에 아웃바운드 문서를 생성하기 위해 형식 요소를 사용할 때 수집된 형식 요소의 수를 나타내는 *정수* 값을 반환하고 지정된 조건을 충족합니다. 각 조건은 키 범위와 키 값으로 구성됩니다. |
| [형식 요소 이름](er-functions-datacollection-formatelementname.md) | 이 함수는 현재 ER 형식 요소의 이름을 나타내는 *스트링* 값을 반환합니다. |
| [SumIF](er-functions-datacollection-sumif.md) | 이 함수는 형식 요소의 바인딩에 의해 반환되고 형식 요소를 사용하여 형식 실행 중에 아웃바운드 문서를 생성할 때 수집된 값의 합계를 나타내는 *Real* 값을 반환하며 지정된 조건을 만족합니다. 조건은 키 범위와 키 값으로 구성됩니다. |
| [SumIF](er-functions-datacollection-sumifs.md) | 이 함수는 형식 요소의 바인딩에 의해 반환되고 형식 요소가 형식 실행 중에 아웃바운드 문서를 생성하는 데 사용되었을 때 수집된 값의 합계를 나타내는 *Real* 값을 반환하며 지정된 조건을 충족합니다. 각 조건은 키 범위와 키 값으로 구성됩니다. |

## <a name="additional-resources"></a>추가 리소스

[전자 보고 개요](general-electronic-reporting.md)

[전자 보고의 공식 디자이너](general-electronic-reporting-formula-designer.md)

[전자 보고 공식 언어](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]