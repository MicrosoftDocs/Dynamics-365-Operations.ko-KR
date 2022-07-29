---
title: VALUEIN ER 함수
description: 이번에는 VALUEIN 전자 보고(ER) 함수가 사용되는 방식에 대한 정보를 제공합니다.
author: NickSelin
ms.date: 12/14/2021
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
ms.openlocfilehash: efa811df360b2ca38eb59bac849e70041405fa81
ms.sourcegitcommit: b1c758ec4abfcf3bf9e50f18c1102d4a9c1316d0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2021
ms.locfileid: "8460925"
---
# <a name="valuein-er-function"></a>VALUEIN ER 함수

[!include [banner](../includes/banner.md)]

이 `VALUEIN` 함수는 지정된 입력이 지정된 목록에 있는 지정된 항목의 값과 일치하는지 여부를 결정합니다. 지정된 입력이 지정된 목록의 하나 이상의 기록에 대해 지정된 표현식을 실행한 결과와 일치하면 *부울* 값 **TRUE** 를 반환합니다. 그렇지 않으면 **FALSE** 의 *부울* 값을 반환합니다.

## <a name="syntax"></a>구문

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a>인수

`input` *필드*

*기록 목록* 유형의 데이터 소스 항목에 대한 유효한 경로입니다. 이 항목의 값이 일치합니다.

`list`: *기록 목록*

*기록 목록* 데이터 유형의 데이터 소스의 유효한 경로입니다.

`list item expression`: *부울*

일치에 사용해야 하는 지정된 목록의 단일 필드를 가리키거나 포함하는 유효한 조건식입니다.

## <a name="return-values"></a>반환 값

*부울*

결과 *부울* 값입니다.

## <a name="usage-notes"></a>사용 참고 사항

일반적으로 `VALUEIN` 함수는 **OR** 조건 세트로 변환됩니다. **OR** 조건 목록이 크고 SQL 문의 최대 총 길이를 초과할 수 있는 경우 [`VALUEINLARGE`](er-functions-logical-valueinlarge.md)함수 사용을 고려하십시오.

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

경우에 따라 `EXISTS JOIN` 연산자를 사용하여 데이터베이스 SQL 문으로 변환할 수 있습니다.

> [!NOTE]
> `VALUEIN` 함수가 반환하는 값은 이 함수가 [`WHERE`](er-functions-list-where.md)함수 또는 [`FILTER`](er-functions-list-filter.md)함수에 대한 선택 기준을 지정하는 데 사용되는지 여부에 따라 [다르게](er-functions-list-filter.md#usage-notes) 사용됩니다.

## <a name="example-1"></a>예시 1

모델 매핑에서 *계산된 필드* 유형의 **목록** 데이터 원본을 정의합니다. 이 데이터 소스에는 `SPLIT ("a,b,c", ",")` 표현식이 포함되어 있습니다.

데이터 소스가 호출될 때 `VALUEIN ("B", List, List.Value)` 표현식으로 구성되어 있으면 **TRUE** 를 반환합니다. 이 경우 `VALUEIN` 함수는 다음 조건 세트로 변환됩니다. `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, 여기서 `("B" = "b")` **참** 입니다.

데이터 소스가 호출될 때 `VALUEIN ("B", List, LEFT(List.Value, 0))` 표현식으로 구성된 경우 **FALSE** 를 반환합니다. 이 경우 `VALUEIN` 함수는 다음 조건으로 변환됩니다. `("B" = "")`, **TRUE** 가 아닙니다.

이러한 조건의 텍스트에 있는 문자 수의 상한선은 32,768자입니다. 따라서 런타임 시 이 제한을 초과할 수 있는 데이터 소스를 생성해서는 안 됩니다. 제한을 초과하면 애플리케이션 실행이 중지되고 예외가 발생합니다. 예를 들어, 데이터 원본이 `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`로 구성되고 **List1** 및 **List2** 목록에 많은 양의 기록이 포함된 경우 이러한 상황이 발생할 수 있습니다.

어떤 경우에는 `VALUEIN` 함수가 `EXISTS JOIN` 연산자를 사용하여 데이터베이스 문으로 변환됩니다. 이 동작은 [`FILTER`](er-functions-list-filter.md)함수가 사용되고 다음 조건이 충족될 때 발생합니다.

- **ASK FOR QUERY** 옵션은 기록 목록을 참조하는 `VALUEIN` 함수의 데이터 소스에 대해 꺼져 있습니다. 런타임 시 이 데이터 소스에 추가 조건이 적용되지 않습니다.
- 기록 목록을 참조하는 `VALUEIN` 함수의 데이터 소스에 대해 중첩 표현식이 구성되지 않았습니다.
- `VALUEIN` 함수의 목록 항목은 해당 데이터 소스의 표현식이나 메소드가 아니라 지정된 데이터 소스의 필드를 참조합니다.

이 예의 앞부분에서 설명한 [`WHERE`](er-functions-list-where.md) 함수 대신 이 옵션을 사용하는 것이 좋습니다.

## <a name="example-2"></a>예시 2

모델 매핑에서 다음 데이터 소스를 정의합니다.

- *테이블 기록* 유형의 **In** 데이터 소스입니다. 이 데이터 소스는 Intrastat 테이블을 참조합니다.
- *테이블 기록* 유형의 **포트** 데이터 소스입니다. 이 데이터 소스는 IntrastatPort 테이블을 참조합니다.

`FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` 식으로 구성된 데이터 소스가 호출되면 Intrastat 테이블의 필터링된 기록을 반환하기 위해 다음 SQL 문이 생성됩니다.

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

**dataAreaId** 필드의 경우 최종 SQL 문은 using `IN` 연산자에 의해 생성됩니다.

## <a name="example-3"></a>예시 3

모델 매핑에서 다음 데이터 소스를 정의합니다.

- *계산된 필드* 유형의 **Le** 데이터 소스입니다. 이 데이터 소스에는 `SPLIT ("DEMF,GBSI,USMF", ",")` 표현식이 포함되어 있습니다.
- *테이블 기록* 유형의 **In** 데이터 소스입니다. 이 데이터 소스는 Intrastat 테이블을 참조하며 **회사 간** 옵션이 켜져 있습니다.

표현식으로 구성된 데이터 소스를 호출하면 최종 SQL `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` 문에는 다음과 같은 조건이 포함된다.

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a>추가 리소스

[논리 함수](er-functions-category-logical.md)

[VALUEINLARGE 함수](er-functions-logical-valueinlarge.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
