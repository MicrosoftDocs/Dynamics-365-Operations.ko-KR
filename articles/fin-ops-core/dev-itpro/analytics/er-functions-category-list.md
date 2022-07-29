---
title: 목록 범주의 ER 함수 목록
description: 이번에는 전자 보고(ER)에서 지원되는 목록 함수에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 04/01/2020
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
ms.openlocfilehash: 4f0d9f83a1750ff51d76716147f5d16e96c0fb415608256a5dcc7524a1f2bd2f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460621"
---
# <a name="list-of-er-functions-in-the-list-category"></a>목록 범주의 ER 함수 목록

[!include [banner](../includes/banner.md)]

전자 보고(ER) 목록 함수를 사용하여 *기록 목록* 및 *컨테이너(기록)* 데이터 유형의 데이터 소스에서 정보를 추출하고 작업을 수행할 수 있습니다. 이번에는 이러한 함수에 대한 요약을 제공합니다.

## <a name="list-of-supported-functions"></a>지원되는 함수 목록

| 직렬 | 설명 |
|----------|-------------|
| [모든 아이템](er-functions-list-allitems.md)                 | 이 함수은 메모리 내 선택으로 실행됩니다. 지정된 경로와 일치하는 모든 항목을 나타내는 *기록 목록* 으로 구성된 새로운 병합된 기록 목록 값을 반환합니다. |
| [AllItemsQuery](er-functions-list-allitemsquery.md)       | 이 함수는 결합된 SQL 쿼리로 실행됩니다. 지정된 경로와 일치하는 모든 항목을 나타내는 *기록 목록* 으로 구성된 새로운 병합된 기록 목록 값을 반환합니다. |
| [개수,](er-functions-list-count.md)                       | 이 함수는 목록이 비어 있지 않은 경우 지정된 목록의 기록 수를 나타내는 *정수* 값을 반환합니다. 목록이 비어 있으면 이 함수는 **0** 을 반환합니다. |
| [빈 목록](er-functions-list-emptylist.md)               | 이 함수는 지정된 목록을 *목록* 구조의 소스로 사용하여 빈 기록 목록 값을 반환합니다.|
| [세다](er-functions-list-enumerate.md)               | 이 함수는 지정된 목록의 열거된 기록으로 구성된 새 *기록 목록* 값을 반환합니다. |
| [필터:](er-functions-list-filter.md)                     | 이 함수는 쿼리가 지정된 조건을 필터링하도록 변경된 후 지정된 목록을 *기록 목록* 값으로 반환합니다. |
| [먼저](er-functions-list-first.md)                       | 이 함수는 지정된 목록의 첫 번째 기록을 해당 목록이 비어 있지 않은 경우 *컨테이너(기록)* 값으로 반환합니다. 목록이 비어 있으면 이 함수는 예외를 throw합니다. |
| [FirstOrNull](er-functions-list-firstornull.md)           | 이 함수는 지정된 목록의 첫 번째 기록을 해당 기록이 비어 있지 않은 경우 *컨테이너(기록)* 값으로 반환합니다. 기록이 비어 있으면 이 함수는 null *컨테이너(기록)* 값을 반환합니다. |
| [색인](er-functions-list-index.md)                       | 이 함수는 지정된 목록에서 지정된 숫자 색인을 사용하여 선택한 *컨테이너(기록)* 값을 반환합니다. 색인가 지정된 목록의 기록 범위를 벗어나면 이 함수는 예외를 발생시킵니다. |
| [비었다](er-functions-list-isempty.md)                   | 이 함수는 지정된 목록에 기록이 없는 경우 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다. |
| [목록](er-functions-list-list.md)                         | 이 함수는 지정된 인수에서 생성된 새 목록으로 구성된 *기록 목록* 값을 반환합니다.|
| [ListDistinct](er-functions-list-listdistinct.md)         | 이 함수는 지정된 목록의 모든 기록에 대한 선택기로 지정된 표현식을 계산합니다. 각 고유 선택기 값에 대한 단일 기록이 포함된 새 *기록 목록* 값을 반환합니다.|
| [리스트조인](er-functions-list-listjoin.md)                 | 이 함수는 지정된 인수에서 생성된 새 조인 목록을 나타내는 *기록 목록* 값을 반환합니다.|
| [필드 목록](er-functions-list-listoffields.md)         | 이 함수는 *열거형* 또는 *컨테이너(기록)* 유형의 지정된 인수 구조를 기반으로 생성된 *기록 목록* 값을 반환합니다. |
| [ListOfFirstItem](er-functions-list-listoffirstitem.md)   | 이 함수는 지정된 목록의 첫 번째 기록으로만 구성된 *기록 목록* 값을 반환합니다.|
| [주문](er-functions-list-orderby.md)                   | 이 함수는 지정된 인수에 따라 정렬된 후 지정된 목록을 *기록 목록* 값으로 반환합니다. 이러한 인수는 표현식으로 정의할 수 있습니다. |
| [역전](er-functions-list-reverse.md)                   | 이 함수는 지정된 목록을 역순으로 *기록 목록* 값으로 반환합니다. |
| [스플릿:](er-functions-list-split.md)                       | 이 함수는 지정된 입력 스트링을 하위 스트링으로 분할하고 결과를 새 *기록 목록* 값으로 반환합니다. |
| [분할 목록](er-functions-list-splitlist.md)               | 이 함수는 지정된 목록을 하위 목록(또는 일괄 처리)으로 분할하며, 각 하위 목록에는 지정된 수의 기록이 포함됩니다. 이후 배치로 구성된 새 *기록 목록* 값으로 결과를 반환합니다. |
| [SplitListByLimit](er-functions-list-splitlistbylimit.md) | 이 함수는 지정된 목록을 새 하위 목록(배치) 목록으로 분할합니다. 각 배치의 기록 수는 동적으로 계산됩니다. 이후 이 함수는 배치로 구성된 새 *기록 목록* 값으로 결과를 반환합니다. |
| [스트링 조인](er-functions-list-stringjoin.md)             | 이 함수는 지정된 목록에서 지정된 필드의 연결된 값으로 구성된 *스트링* 값을 반환합니다. 값은 지정된 구분 기호로 구분할 수 있습니다. |
| [어디로?](er-functions-list-where.md)                       | 이 함수는 지정된 조건에 따라 필터링된 후 지정된 목록을 *기록 목록* 값으로 반환합니다. |

## <a name="additional-resources"></a>추가 리소스

[전자 보고 개요](general-electronic-reporting.md)

[전자 보고의 공식 디자이너](general-electronic-reporting-formula-designer.md)

[전자 보고 공식 언어](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]