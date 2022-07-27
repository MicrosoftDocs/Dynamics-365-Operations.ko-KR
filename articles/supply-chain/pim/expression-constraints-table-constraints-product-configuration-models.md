---
title: 제품 구성 모델의 표현식 제약 조건 및 테이블 제약 조건
description: 이 토픽에서는 표현식 제약 조건 및 테이블 제약 조건의 사용에 대해 설명합니다. 제약 조건은 판매 주문, 판매 견적, 구매 주문 또는 생산 주문에 대해 제품을 구성할 때 선택할 수 있는 특성 값을 제어합니다. 제약 조건을 빌드하는 방법에 따라 표현식 제약 조건 또는 테이블 제약 조건을 사용할 수 있습니다.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8775a9225313c0f5a132dbccbe583470fe23beab
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448339"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a>제품 구성 모델의 표현식 제약 조건 및 테이블 제약 조건

[!include [banner](../includes/banner.md)]

이 토픽에서는 표현식 제약 조건 및 테이블 제약 조건의 사용에 대해 설명합니다. 제약 조건은 판매 주문, 판매 견적, 구매 주문 또는 생산 주문에 대해 제품을 구성할 때 선택할 수 있는 특성 값을 제어합니다. 제약 조건을 빌드하는 방법에 따라 표현식 제약 조건 또는 테이블 제약 조건을 사용할 수 있습니다. 

제약 조건은 판매 주문, 판매 견적, 구매 주문 또는 생산 주문에 대해 제품을 구성할 때 선택할 수 있는 특성 값을 제어하는 데 사용됩니다. 제약 조건을 빌드하는 방법에 따라 표현식 제약 조건 또는 테이블 제약 조건을 사용할 수 있습니다.

## <a name="what-are-expression-constraints"></a>표현 제약이란 무엇입니까?
식 제약 조건은 산술 및 부울 연산자와 함수를 사용하는 식을 특징으로 합니다. 표현식 제약 조건은 제품 구성 모델의 특정 구성 요소에 대해 작성됩니다. 다른 구성 요소에서 재사용하거나 공유할 수 없습니다. 그러나 구성 요소에 대한 표현식 제약 조건은 구성 요소의 하위 구성 요소 특성을 참조할 수 있습니다.

## <a name="what-are-table-constraints"></a>테이블 제약이란 무엇입니까?
테이블 제약 조건은 제품을 구성할 때 특성에 허용되는 값 조합을 나열합니다. 테이블 제약 조건 정의는 일반적으로 사용할 수 있습니다. 제품 구성 모델의 구성 요소에 대한 테이블 제약 조건을 생성할 때 테이블 제약 조건 정의를 선택합니다. 허용되는 조합을 생성하려면 특정 유형의 특성을 구성 요소에 추가합니다. 각 특성 유형에는 특정 값이 있습니다.

### <a name="example-of-a-table-constraint"></a>테이블 제약 조건의 예

이 예는 스피커 구성을 특정 캐비닛 마감재 및 전면으로 제한하는 방법을 보여줍니다. 첫 번째 테이블은 일반적으로 구성에 사용할 수 있는 캐비닛 마감재와 전면을 보여줍니다. 값은 **캐비닛 마감** 및 **전면 그릴** 특성 유형에 대해 정의됩니다.

| 특성 유형 | 값                      |
|----------------|-----------------------------|
| 캐비닛 마감 | 검정, 오크, 로즈우드, 화이트 |
| 전면 그릴    | 검정, 메탈, 화이트         |

다음 테이블은 **색상 및 마감** 테이블 제약 조건에 의해 정의된 조합을 보여줍니다. 이 테이블 제약 조건을 사용하여 오크 마감 및 검은색 그릴, 로즈우드 마감 및 흰색 그릴 등이 있는 스피커를 구성할 수 있습니다.

| 마감         | 그릴                       |
|----------------|-----------------------------|
| 오크            | 검정                       |
| 로즈우드       | 흰색                       |
| 흰색          | 검정                       |
| 흰색          | 흰색                       |
| 검정          | 검정                       |
| 검정          | 메탈                       | 

시스템 정의 및 사용자 정의 테이블 제약 조건을 생성할 수 있습니다. 자세한 내용은 [시스템 정의 및 사용자 정의 테이블 제약 조건](system-defined-user-defined-table-constraints.md)을 참조하세요.

## <a name="what-syntax-should-be-used-to-write-constraints"></a>제약 조건을 작성하려면 어떤 구문을 사용해야 합니까?
제약 조건을 작성할 때 OML(최적화 모델링 언어) 구문을 사용해야 합니다. 시스템은 Microsoft Solver Foundation 제약 조건 솔버를 사용하여 제약 조건을 해결합니다.

## <a name="should-i-use-table-constraints-or-expression-constraints"></a>테이블 제약 조건 또는 표현식 제약 조건을 사용해야 합니까?
제약 조건을 빌드하는 방법에 따라 표현식 제약 조건 또는 테이블 제약 조건을 사용할 수 있습니다. 테이블 제약 조건은 행렬로 작성하는 반면 표현식 제약 조건은 개별 명령문입니다. 제품을 구성할 때 어떤 종류의 제약 조건이 사용되는지는 중요하지 않습니다. 다음 예는 두 가지 방법이 어떻게 다른지 보여줍니다.  

다음 제약 조건 설정을 사용하여 제품을 구성할 때 다음 조합이 허용됩니다.

-   색상 검정, 사이즈 30 또는 50의 제품
-   색상 빨강, 사이즈 20의 제품

### <a name="table-constraint-setup"></a>테이블 제약 조건 설정

| 색 | 크기 |
|-------|------|
| 검정 | 30   |
| 검정 | 50   |
| 빨강   | 20   |

### <a name="expression-constraint-setup"></a>표현식 제약 설정

(색상 == "검정" & (크기 == "30" | 크기 == "50")) | (색상 == "빨강" & 크기 = "20")

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a>표현식 제약 조건을 작성할 때 연산자 또는 중위 표기법을 사용해야 합니까?
사용 가능한 접두사 연산자 또는 중위 표기법을 사용하여 표현식 제약 조건을 작성할 수 있습니다. **Min**, **최대** 및 **Abs** 연산자의 경우 중위 표기법을 사용할 수 없습니다. 이러한 연산자는 대부분의 프로그래밍 언어에서 표준 연산자로 포함됩니다.

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a>표현식 제약 조건을 작성할 때 어떤 연산자와 중위 표기법을 사용할 수 있습니까?
다음 테이블에는 제품 구성 모델의 구성 요소에 대한 표현식 제약 조건을 작성할 때 사용할 수 있는 연산자 및 중위 표기법이 나열되어 있습니다. 첫 번째 표의 예는 중위 표기법이나 연산자를 사용하여 표현식을 작성하는 방법을 보여줍니다.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>연산자</th>
<th>설명</th>
<th>통사론</th>
<th>예</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>암시</td>
<td>첫 번째 조건이 false이거나 두 번째 조건이 true이거나 둘 다인 경우 true입니다.</td>
<td>Implies[a, b], infix: a -: b</td>
<td><ul>
<li><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</li>
<li><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</li>
</ul></td>
</tr>
<tr class="even">
<td>및</td>
<td>이것은 모든 조건이 true인 경우에만 true입니다. 조건의 수가 0(영)이면 <strong>True</strong>를 생성합니다.</td>
<td>And[args], infix: a &amp; b &amp; ... &amp; z</td>
<td><ul>
<li><strong>Operator:</strong> And[x == 2, y &lt;= 2]</li>
<li><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</li>
</ul></td>
</tr>
<tr class="odd">
<td>또는</td>
<td>조건이 true면 true입니다. 조건의 수가 0(영)이면 <strong>False</strong>를 생성합니다.</td>
<td>Or[args], infix: a | b | ... | z</td>
<td><ul>
<li><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</li>
<li><strong>Infix notation:</strong> x == 2 | y &lt;= 2</li>
</ul></td>
</tr>
<tr class="even">
<td>Plus</td>
<td>이것은 조건을 합산합니다. 조건 수가 0(영)이면 <strong>0</strong>을 생성합니다.</td>
<td>Plus[args], infix: a + b + ... + z</td>
<td><ul>
<li><strong>Operator:</strong> Plus[x, y, 2] == z</li>
<li><strong>Infix notation:</strong> x + y + 2 == z</li>
</ul></td>
</tr>
<tr class="odd">
<td>Minus</td>
<td>이는 인수를 부정합니다. 정확히 하나의 조건이 있어야 합니다.</td>
<td>Minus[expr], infix: -expr</td>
<td><ul>
<li><strong>Operator:</strong> Minus[x] == y</li>
<li><strong>Infix notation:</strong> -x == y</li>
</ul></td>
</tr>
<tr class="even">
<td>Abs</td>
<td>이것은 조건의 절대값을 취합니다. 정확히 하나의 조건이 있어야 합니다.</td>
<td>Abs[expr]</td>
<td><strong>Operator:</strong> Abs[x]</td>
</tr>
<tr class="odd">
<td>Times</td>
<td>이것은 조건의 곱을 취합니다. 조건 수가 0(영)이면 <strong>1</strong>을 생성합니다.</td>
<td>Times[args], infix: a * b * ... * z</td>
<td><ul>
<li><strong>Operator:</strong> Times[x, y, 2] == z</li>
<li><strong>Infix notation:</strong> x * y * 2 == z</li>
</ul></td>
</tr>
<tr class="even">
<td>Power</td>
<td>지수가 필요합니다. 오른쪽에서 왼쪽으로 지수를 적용합니다. (즉, 오른쪽 결합입니다.) 따라서 <strong>Power[a, b, c]</strong>은 <strong>Power[a, Power[b, c]]</strong>과 같습니다. <strong>Power</strong> 지수가 양의 상수인 경우에만 사용할 수 있습니다.</td>
<td>Power[args], infix: a ^ b ^ ... ^ z</td>
<td><ul>
<li><strong>Operator:</strong> Power[x, 2] == y</li>
<li><strong>Infix notation:</strong> x ^ 2 == y</li>
</ul></td>
</tr>
<tr class="odd">
<td>최대</td>
<td>이것은 가장 큰 조건을 생성합니다. 조건의 수가 0(영)이면 <strong>Infinity</strong>를 생성합니다.</td>
<td>Max[args]</td>
<td><strong>Operator:</strong> Max[x, y, 2] == z</td>
</tr>
<tr class="even">
<td>Min</td>
<td>이것은 가장 작은 조건을 생성합니다. 조건의 수가 0(영)이면 <strong>Infinity</strong>를 생성합니다.</td>
<td>Min[args]</td>
<td><strong>Operator:</strong> Min[x, y, 2] == z</td>
</tr>
<tr class="odd">
<td>Not</td>
<td>이것은 조건의 논리적 역을 생성합니다. 정확히 하나의 조건이 있어야 합니다.</td>
<td>Not[expr], infix: !expr</td>
<td><ul>
<li><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</li>
<li><strong>Infix notation:</strong> !x!(y == 3)</li>
</ul></td>
</tr>
</tbody>
</table>

다음 테이블의 예는 중위 표기법을 작성하는 방법을 보여줍니다.


|  중위 표기법   |                                          설명                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     x + y + z     |                                           더하기                                            |
|    x \* y \* z    |                                        곱셈                                         |
|       x - y       | 이진 빼기는 음수 초가 있는 이진 더하기와 동일하게 변환됩니다. |
|     x ^ y ^ z     |                          올바른 연관성이 있는 지수                          |
|        !x         |                                          부울 아님                                          |
|      x -: y       |                                      부울 의미                                      |
|         x         |                                               y                                               |
|     x & y & z     |                                          부울 및                                          |
|    x == y == z    |                                           균등                                            |
|    x != y != z    |                                           구분                                            |
|  x &lt; y &lt; z  |                                           Less than                                           |
|  x &gt; y &gt; z  |                                         Greater than                                          |
| x &lt;= y &lt;= z |                                     이하                                     |
| x &gt;= y &gt;= z |                                   이상                                    |
|        (x)        |                           괄호는 기본 우선 순위를 재정의합니다.                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a>내 표현 제약 조건이 올바르게 검증되지 않는 이유는 무엇입니까?
예약된 키워드를 제품 구성 모델의 특성, 구성 요소 또는 하위 구성 요소에 대한 솔버 이름으로 사용할 수 없습니다. 다음은 사용할 수 없는 예약 키워드 목록입니다.

-   Ceiling
-   Element
-   Equal
-   플로어
-   If
-   Less
-   Greater
-   암시
-   로그
-   최대
-   Min
-   Minus
-   Plus
-   Power
-   Times
-   Slot
-   모델
-   결정
-   목표


## <a name="additional-resources"></a>추가 리소스

[식 제약 조건 생성](tasks/add-expression-constraint-product-configuration-model.md)

[제품 구성 모델에 계산 추가](tasks/add-calculation-product-configuration-model.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]