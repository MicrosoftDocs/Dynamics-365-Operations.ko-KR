---
title: 논리적 범주의 ER 함수 목록
description: 이번에는 전자 보고(ER)에서 지원되는 논리적 함수에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 02/11/2021
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
ms.openlocfilehash: 43cbecf80ff70dac058977932c3a0bb03662cd98a88c68407051bdc584609d84
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460620"
---
# <a name="list-of-er-functions-in-the-logical-category"></a>논리적 범주의 ER 함수 목록

[!include [banner](../includes/banner.md)]

전자 보고(ER) 논리 함수는 논리 값으로 작업하여 단일 표현식에서 둘 이상의 비교를 수행하거나 여러 조건을 테스트하는 데 사용할 수 있습니다. 이번에는 이러한 함수에 대한 요약을 제공합니다.

## <a name="list-of-supported-functions"></a>지원되는 함수 목록

| 직렬 | 설명 |
|----------|-------------|
| [및](er-functions-logical-and.md)                       | 이 함수는 지정된 모든 조건이 참인 경우 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다. |
| [케이스](er-functions-logical-case.md)                     | 이 함수는 지정된 대체 옵션에 대해 지정된 표현식의 값을 평가하고 지정된 표현식의 값과 동일한 첫 번째 옵션의 결과를 반환합니다. 그렇지 않고 기본 결과가 옵션이 선행되지 않는 호출된 함수의 마지막 인수로 지정된 경우 선택적 기본 결과를 반환합니다. 반환되는 값은 지원되는 모든 데이터 유형의 값일 수 있습니다. |
| [Contains](er-functions-logical-contains.md)             | 이 함수는 지정된 입력에 지정된 텍스트가 포함되어 있는지 여부를 결정합니다. 지정된 입력에 지정된 텍스트가 포함되어 있으면 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다. |
| [로 끝나다](er-functions-logical-endswith.md)             | 이 함수는 지정된 입력이 지정된 텍스트로 끝나는지 여부를 결정합니다. 지정된 입력이 지정된 텍스트로 끝나면 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다. |
| [만약,](er-functions-logical-if.md)                         | 이 함수는 지정된 조건이 충족되면 첫 번째 지정된 값을 반환합니다. 그렇지 않으면 두 번째 지정된 값을 반환합니다. 반환되는 값은 지원되는 모든 데이터 유형의 값일 수 있습니다. |
| [아니다](er-functions-logical-not.md)                       | 이 함수는 지정된 조건의 반전된 논리 값을 *부울* 값으로 반환합니다. |
| [또는](er-functions-logical-or.md)                         | 이 함수는 지정된 모든 조건이 거짓이면 **FALSE** 의 *부울* 값을 반환합니다. 지정된 조건이 true이면 함수는 **TRUE** 의 *부울* 값을 반환합니다. |
| [다음으로 시작](er-functions-logical-startswith.md)         | 이 함수는 지정된 입력이 지정된 텍스트로 시작하는지 여부를 결정합니다. 지정된 입력이 지정된 텍스트로 시작하는 경우 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다. |
| [값 입력](er-functions-logical-valuein.md)               | 이 함수는 지정된 입력이 지정된 목록에 있는 지정된 항목의 값과 일치하는지 여부를 결정합니다. 지정된 입력이 지정된 목록의 하나 이상의 기록에 대해 지정된 표현식을 실행한 결과와 일치하면 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다. |
| [큰 값](er-functions-logical-valueinlarge.md)     | 이 함수는 *Int64* 또는 *Integer* 유형의 지정된 입력이 지정된 목록에 있는 지정된 항목의 값과 일치하는지 여부를 결정합니다. 지정된 입력이 지정된 목록의 하나 이상의 기록에 대해 지정된 표현식을 실행한 결과와 일치하면 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다. |


## <a name="additional-resources"></a>추가 리소스

[전자 보고 개요](general-electronic-reporting.md)

[전자 보고의 공식 디자이너](general-electronic-reporting-formula-designer.md)

[전자 보고 공식 언어](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]