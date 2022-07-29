---
title: 런타임 문제를 방지하기 위해 구성된 ER 구성 요소 검사
description: 이번에는 발생할 수 있는 런타임 문제를 방지하기 위해 구성된 전자 보고(ER) 구성 요소를 검사하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 01/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c63ffc6316d21d36bb2aad57194b8aa1c477607e
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8460999"
---
# <a name="inspect-the-configured-er-component-to-prevent-runtime-issues"></a>런타임 문제를 방지하기 위해 구성된 ER 구성 요소 검사

[!include[banner](../includes/banner.md)]

구성된 모든 [ER(Electronic Reporting)](general-electronic-reporting.md) [형식](er-overview-components.md#format-components-for-outgoing-electronic-documents)과 [모델 매핑](er-overview-components.md#model-mapping-component) 구성 요소는 설계 시 [검증](er-fillable-excel.md#validate-an-er-format)할 수 있습니다. 이 유효성 검사 중에 일관성 검사가 실행되어 실행 오류 및 성능 저하와 같이 발생할 수 있는 런타임 문제를 방지합니다. 발견된 모든 문제에 대해 검사는 문제가 있는 요소의 경로를 제공합니다. 일부 문제의 경우 자동 수정을 사용할 수 있습니다.

기본적으로 유효성 검사는 이전에 언급한 ER 구성 요소가 포함된 ER 구성에 대해 다음과 같은 경우에 자동으로 적용됩니다.

- 새 [버전](general-electronic-reporting.md#component-versioning)의 ER 구성을 Microsoft Dynamics 365 Finance 인스턴스로 [가져옵니다](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally).
- 편집 가능한 ER 구성의 [상태](general-electronic-reporting.md#component-versioning)를 **초안** 에서 **완료** 로 변경합니다.
- 새 기본 버전을 적용하여 편집 가능한 ER 구성을 [리베이스](general-electronic-reporting.md#upgrading-a-format-selecting-a-new-version-of-base-format-rebase)합니다.

이 유효성 검사를 명시적으로 실행할 수 있습니다. 다음 세 가지 옵션 중 하나를 선택하고 제공된 단계를 따릅니다.

- 옵션 1:

    1. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
    2. 왼쪽 창의 구성 트리에서 ER 형식 또는 ER 모델 매핑 구성 요소가 포함된 원하는 ER 구성을 선택합니다.
    3. **버전** FastTab에서 선택한 ER 구성의 원하는 버전을 선택합니다.
    4. 작업 창에서 **송장** 을 선택합니다.

- ER 형식의 경우 옵션 2:

    1. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
    2. 왼쪽 창의 구성 트리에서 ER 형식 구성 요소가 포함된 원하는 ER 구성을 선택합니다.
    3. **버전** FastTab에서 선택한 ER 구성의 원하는 버전을 선택합니다.
    4. 작업 창에서 **디자이너** 를 선택합니다.
    5. **형식 디자이너** 페이지의 작업 창에서 **유효성 검사** 를 선택합니다.

- ER 모델 매핑의 경우 옵션 3:

    1. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
    2. 왼쪽 창의 구성 트리에서 ER 모델 매핑 구성 요소가 포함된 원하는 ER 구성을 선택합니다.
    3. **버전** FastTab에서 선택한 ER 구성의 원하는 버전을 선택합니다.
    4. 작업 창에서 **디자이너** 를 선택합니다.
    5. **모델과 데이터 원본 간 매핑** 페이지의 작업 창에서 **디자이너** 를 선택합니다.
    6. **모델 매핑 디자이너** 페이지의 작업 창에서 **유효성 검사** 를 선택합니다.

구성을 가져올 때 유효성 검사를 건너뛰려면 다음 단계를 따르십시오.

1. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **가져온 후 구성 확인** 옵션을 **아니요** 로 설정합니다.

버전 상태를 변경하거나 리베이스할 때 유효성 검사를 건너뛰려면 다음 단계를 따르십시오.

1. **조직 관리 \> 전자 \> 보고 구성** 으로 이동합니다.
2. **작업** 페이지의 작업 창에 있는 **작업** 탭에 있는 **작업** 그룹에서 **작업 취소** 를 선택합니다.
3. **구성 상태 변경 및 리베이스 시 유효성 검사 건너뛰기** 옵션을 **예** 로 설정합니다.

ER은 다음 범주를 사용하여 일관성 검사 검사를 그룹화합니다.

- **실행 가능성** – 런타임에 발생할 수 있는 중요한 문제를 감지하는 검사입니다. 이러한 문제는 대부분 **오류** 수준에 있습니다. 
- **성능** – 구성된 ER 구성 요소의 비효율적인 실행을 유발할 수 있는 문제를 감지하는 검사입니다. 이러한 문제는 대부분 **경고** 수준에 있습니다.
- **데이터 무결성** – 데이터 손실 또는 런타임 문제를 일으킬 수 있는 문제를 감지하는 검사입니다. 이러한 문제는 대부분 **경고** 수준에 있습니다.

## <a name="list-of-inspections"></a>검사 목록

다음 표는 ER에서 제공하는 검사에 대한 개요를 제공합니다. 이러한 검사에 대한 자세한 내용을 보려면 첫 번째 열의 링크를 사용하여 이 항목의 관련 섹션으로 이동하십시오. 이러한 섹션에서는 ER이 검사를 제공하는 구성 요소 유형과 문제를 방지하는 데 도움이 되도록 ER 구성 요소를 재구성하는 방법을 설명합니다.

<table>
<thead>
<tr>
<th>이름</th>
<th>카테고리</th>
<th>수준</th>
<th>메시지</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href='#i1'>유형 변환</a></td>
<td>'임원',</td>
<td>오류</td>
<td>
<p>&lt;유형&gt; 유형의 표현식을 &lt;유형&gt; 유형의 필드로 변환할 수 없습니다.</p>
<p><b>런타임 에러:</b> 유형에 대한 예외</p>
</td>
</tr>
<tr>
<td><a href='#i2'>유형 호환성</a></td>
<td>'임원',</td>
<td>오류</td>
<td>
<p>구성된 식은 데이터 원본에 대한 현재 형식 요소의 바인딩으로 사용할 수 없습니다. 이 식은 &lt;형식&gt; 유형의 현재 &lt;형식&gt; 요소에서 지원하는 데이터 형식 범위를 벗어나는 데이터 형식 값을 반환하기 때문입니다.</p>
<p><b>런타임 에러:</b> 유형의 예외</p>
</td>
</tr>
<tr>
<td><a href='#i3'>구성 요소 누락</a></td>
<td>'임원',</td>
<td>오류</td>
<td>
<p>&lt;경로&gt;를 찾을 수 없습니다.</p>
<p><b>런타임 에러:</b> 구성 &lt;경로&gt; 요소를 찾을 수 없습니다.</p>
</td>
</tr>
<tr>
<td><a href='#i4'>FILTER 함수가 있는 표현식의 실행 가능성</a></td>
<td>'임원',</td>
<td>오류</td>
<td>
<p>FILTER 함수의 목록 표현식은 쿼리할 수 없습니다.</p>
<p><b>런타임 에러:</b> 필터링은 지원되지 않습니다. 이에 대한 자세한 내용을 보려면 구성을 확인하십시오.</p>
</td>
</tr>
<tr>
<td rowspan='2'><a href='#i5'>GROUPBY 데이터 소스의 실행 가능성</a></td>
<td>'임원',</td>
<td>오류</td>
<td>경로 &lt;경로&gt;는 쿼리를 지원하지 않습니다.</td>
</tr>
<tr>
<td>'임원',</td>
<td>오류</td>
<td>
<p>Group by function은 쿼리로 실행할 수 없습니다.</p>
<p><b>런타임 에러:</b> 함수별 그룹화는 쿼리로 실행할 수 없습니다.</p>
</td>
</tr>
<tr>
<td><a href='#i6'>JOIN 데이터 소스의 실행 가능성</a></td>
<td>'임원',</td>
<td>오류</td>
<td>
<p>쿼리의 필터가 아닌 목록 &lt;경로&gt;는 조인할 수 없습니다.</p>
<p><b>런타임 에러:</b> 함수 결합 데이터 소스는 필터 표현식이어야 합니다. 계산된 필드가 잘못 호출되었습니다.</p>
</td>
</tr>
<tr>
<td><a href='#i7'>FILTER 대 WHERE 함수의 선호도</a></td>
<td>성능</td>
<td>경고</td>
<td>성능 측면에서 WHERE보다 표현식에 FILTER 함수를 사용하는 것이 좋습니다. 수정을 선택하여 자동으로 교체합니다.</td>
</tr>
<tr>
<td><a href='#i8'>ALLITEMSQUERY 대 ALLITEMS 함수의 선호도</a></td>
<td>성능</td>
<td>경고</td>
<td>성능 측면에서 ALLITEMS보다 표현식에 ALLITEMSQUERY 함수를 사용하는 것이 좋습니다. 수정을 선택하여 자동으로 교체합니다.</td>
</tr>
<tr>
<td><a href='#i9'>빈 목록의 경우 고려</a></td>
<td>'임원',</td>
<td>경고</td>
<td>
<p>목록 &lt;경로&gt;에는 빈 목록 케이스에 대한 검사가 없으므로 런타임에 오류가 발생할 수 있습니다. 빈 목록 케이스에 대한 검사를 추가하십시오.</p>
<p><b>런타임 에러:</b> &lt;경로&gt;에서 목록이 비어 있습니다.</p>
<p><b><a href='#i9a'>잠재적인 문제</a>:</b> 라인이 채워진 데이터 소스에 여러 기록이 포함되어 있는 동안 라인이 한 번 채워집니다.</p>
</td>
</tr>
<tr>
<td><a href='#i10'>FILTER 함수(캐싱)가 있는 표현식의 실행 가능성</a></td>
<td>'임원',</td>
<td>오류</td>
<td>
<p>FILTER 함수는 선택한 데이터 소스 유형에 적용할 수 없습니다. 테이블 기록 유형의 데이터 원본은 캐시되지 않고 수동으로 추가된 중첩 데이터 원본이 없는 경우에만 적용할 수 있습니다.</p>
<p><b>런타임 에러:</b> 필터링은 지원되지 않습니다. 이에 대한 자세한 내용을 보려면 구성을 확인하십시오.</p>
</td>
</tr>
<tr>
<td><a href='#i11'>바인딩 누락</a></td>
<td>'임원',</td>
<td>경고</td>
<td>
<p>경로 &lt;경로&gt;는 모델의 매핑을 사용할 때 데이터 소스에 대한 바인딩이 없습니다.</p>
<p><b>런타임 에러:</b> 경로 &lt;경로&gt;가 바인딩되지 않음</p>
</td>
</tr>
<tr>
<td><a href='#i12'>연결되지 않은 템플릿</a></td>
<td>데이터 무결성</td>
<td>경고</td>
<td>파일 &lt;이름&gt;은 파일 구성 요소에 연결되어 있지 않으며 구성 버전의 상태를 변경한 후 제거됩니다.</td>
</tr>
<tr>
<td><a href='#i13'>동기화되지 않은 형식</a></td>
<td>데이터 무결성</td>
<td>경고</td>
<td>정의된 이름 &lt;구성 요소 이름&gt;이 Excel 시트 &lt;시트 이름에 존재하지 않습니다.&gt;</td>
</tr>
<tr>
<td><a href='#i14'>동기화되지 않은 형식</a></td>
<td>데이터 무결성</td>
<td>경고</td>
<td>
<p>&lt;태그가 지정된 Word 콘텐츠 제어&gt; 태그가 Word 템플릿 파일에 존재하지 않습니다.</p>
<p><b>런타임 에러:</b> &lt;태그가 지정된 Word 콘텐츠 제어&gt; 태그가 Word 템플릿 파일에 존재하지 않습니다.</p>
</td>
</tr>
<tr>
<td><a href='#i15'>기본 매핑 없음</a></td>
<td>데이터 무결성</td>
<td>오류</td>
<td>
<p>쉼표로 구분된 구성 구성 이름의 &lt;모델 이름(루트 설명자)&gt; 데이터 모델에 대해 &lt;둘 이상의 모델 매핑&gt;이 존재합니다. 구성 중 하나를 기본값으로 설정</p>
<p><b>런타임 에러:</b> 쉼표로 구분된 구성 구성 이름의 &lt;모델 이름(루트 설명자)&gt; 데이터 모델에 대해 &lt;둘 이상의 모델 매핑&gt;이 존재합니다. 구성 중 하나를 기본값으로 설정합니다.</p>
</td>
</tr>
<tr>
<td><a href='#i16'>머리글 또는 바닥글 구성 요소의 일관되지 않은 설정</a></td>
<td>데이터 무결성</td>
<td>오류</td>
<td>
<p>머리글/바닥글(&lt;구성 요소 유형: 머리글 또는 바닥글&gt;)이 일치하지 않습니다.</p>
<p><b>실행 시간:</b> 구성된 ER 형식의 초안 버전이 실행되는 경우 런타임에 마지막으로 구성된 구성 요소가 사용됩니다.</p>
</td>
</tr>
<tr>
<td><a href='#i17'>페이지 구성 요소의 일관되지 않은 설정</a></td>
<td>데이터 무결성</td>
<td>오류</td>
<td>복제가 없는 범위 구성 요소가 두 개 이상 있습니다. 불필요한 구성 요소를 제거하십시오.</td>
</tr>
<tr>
<td><a href='#i18'>ORDERBY 함수가 있는 표현식의 실행 가능성</a></td>
<td>'임원',</td>
<td>오류</td>
<td>
<p>ORDERBY 함수의 목록 표현식은 쿼리할 수 없습니다.</p>
<p><b>런타임 에러:</b> 정렬은 지원되지 않습니다. 이에 대한 자세한 내용을 보려면 구성을 확인하십시오.</p>
</td>
</tr>
</tbody>
</table>

## <a name="type-conversion"></a><a id="i1"></a>유형 변환

ER은 데이터 모델 필드의 데이터 유형이 해당 필드의 바인딩으로 구성된 표현식의 데이터 유형과 호환되는지 확인합니다. 데이터 형식이 호환되지 않으면 ER 모델 매핑 디자이너에서 유효성 검사 오류가 발생합니다. 받는 메시지에는 ER이 A 유형의 표현식을 B 유형의 필드로 변환할 수 없다는 내용이 나와 있습니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 데이터 모델과 ER 모델 매핑 구성 요소를 동시에 구성하기 시작합니다.
2. 데이터 모델 트리에서 **X** 라는 필드를 추가하고 데이터 형식으로 **정수** 를 선택합니다.

    ![데이터 모델 페이지의 데이터 모드 트리에 X 필드 및 정수 데이터 유형이 추가되었습니다.](./media/er-components-inspections-01.png)

3. 모델 매핑 디자이너의 **데이터 원본** 창에서 **계산된 필드** 유형의 데이터 원본을 추가합니다.
4. 새 데이터 소스의 이름을 **Y** 로 지정하고 표현식 `INTVALUE(100)`을 포함하도록 구성하십시오.
5. **X** 를 **Y** 에 바인딩합니다.
6. 데이터 모델 디자이너에서 **X** 필드의 데이터 형식을 **Integer** 에서 **Int64** 로 변경합니다.
7. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사합니다.

    ![모델 매핑 디자이너 페이지에서 편집 가능한 모델 매핑 구성 요소의 유효성을 검사합니다.](./media/er-components-inspections-01.gif)

8. **구성** 페이지에서 선택한 ER 구성의 모델 매핑 구성 요소를 검사하려면 **확인** 을 선택합니다.

    ![구성 페이지에서 모델 매핑 구성 요소를 검사합니다.](./media/er-components-inspections-01a.png)

9. 유효성 검사 오류가 발생합니다. 메시지는 **Y** 데이터 원본의 `INTVALUE(100)` 식이 반환하는 **Integer** 형식의 값을 **Int64** 형식의 **X** 데이터 모델 필드에 저장할 수 없다고 말합니다.

다음 그림은 경고를 무시하고 **실행** 을 선택하여 모델 매핑을 사용하도록 구성된 형식을 실행하는 경우 발생하는 런타임 오류를 보여줍니다.

![형식 디자이너 페이지의 런타임 오류입니다.](./media/er-components-inspections-01b.png)

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

해당 필드의 바인딩에 대해 구성된 표현식의 데이터 유형과 일치하도록 데이터 모델 필드의 데이터 유형을 변경하여 데이터 모델 구조를 업데이트하십시오. 앞의 예시에서 **X** 필드의 데이터 유형은 다시 **정수** 로 변경되어야 합니다.

#### <a name="option-2"></a>옵션 2

데이터 모델 필드와 바인딩된 데이터 원본의 식을 변경하여 모델 매핑을 업데이트합니다. 앞의 예시에서 **Y** 데이터 소스의 표현식은 `INT64VALUE(100)`로 변경되어야 합니다.

## <a name="type-compatibility"></a><a id="i2"></a>유형 호환성

ER은 형식 요소의 데이터 형식이 해당 형식 요소의 바인딩으로 구성된 표현식의 데이터 형식과 호환되는지 확인합니다. 데이터 유형이 호환되지 않으면 ER 작업 디자이너에서 유효성 검사 오류가 발생합니다. 받는 메시지는 식이 지원되는 데이터 형식의 범위를 벗어나는 데이터 형식 A의 값을 반환하기 때문에 구성된 식이 데이터 원본에 대한 현재 형식 요소의 바인딩으로 사용할 수 없다는 내용입니다. B 유형의 현재 형식 요소에 의해

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 데이터 모델과 ER 형식 구성 요소를 동시에 구성하기 시작합니다.
2. 데이터 모델 트리에서 **X** 라는 필드를 추가하고 데이터 형식으로 **정수** 를 선택합니다.
3. 형식 구조 트리에서 **숫자** 유형의 형식 요소를 추가합니다.
4. 새 형식 요소의 이름을 **Y** 로 지정합니다. **숫자 유형** 필드에서 데이터 유형으로 **정수** 를 선택하십시오.
5. **X** 를 **Y** 에 바인딩합니다.
6. 형식 구조 트리에서 **Y** 형식 요소의 데이터 형식을 **Integer** 에서 **Int64** 로 변경합니다.
7. **형식 디자이너** 페이지에서 편집 가능한 형식 구성 요소를 검사하려면 **유효성 검사** 를 선택합니다.

    ![형식 디자이너 페이지에서 형식 호환성을 확인합니다.](./media/er-components-inspections-02.gif)

8. 유효성 검사 오류가 발생합니다. 구성된 식은 **Int64** 값만 수락할 수 있다는 메시지가 표시됩니다. 따라서 **Integer** 유형의 **X** 데이터 모델 필드 값은 **Y** 형식 요소에 입력할 수 없습니다.

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

해당 요소의 바인딩에 대해 구성한 표현식의 데이터 유형과 일치하도록 **숫자** 형식 요소의 데이터 유형을 변경하여 형식 구조를 업데이트하십시오. 앞의 예시에서 **X** 형식 요소의 **숫자 유형** 값은 다시 **정수** 로 변경되어야 합니다.

#### <a name="option-2"></a>옵션 2

표현식을 `model.X`에서 `INT64VALUE(model.X)`로 변경하여 **X** 형식 요소의 형식 매핑을 업데이트합니다.

## <a name="missing-configuration-element"></a><a id="i3"></a>구성 요소 누락

ER은 바인딩 식에 편집 가능한 ER 구성 요소에 구성된 데이터 소스만 포함되어 있는지 확인합니다. 편집 가능한 ER 구성 요소에 누락된 데이터 원본이 포함된 모든 바인딩에 대해 ER 작업 디자이너 또는 ER 모델 매핑 디자이너에서 유효성 검사 오류가 발생합니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 데이터 모델과 ER 모델 매핑 구성 요소를 동시에 구성하기 시작합니다.
2. 데이터 모델 트리에서 **X** 라는 필드를 추가하고 데이터 형식으로 **정수** 를 선택합니다.

    ![데이터 모델 페이지의 X 필드 및 정수 데이터 유형이 있는 데이터 모델 트리.](./media/er-components-inspections-01.png)

3. 모델 매핑 디자이너의 **데이터 원본** 창에서 **계산된 필드** 유형의 데이터 원본을 추가합니다.
4. 새 데이터 소스의 이름을 **Y** 로 지정하고 표현식 `INTVALUE(100)`을 포함하도록 구성하십시오.
5. **X** 를 **Y** 에 바인딩합니다.
6. 모델 매핑 디자이너의 **데이터 원본** 창에서 **Y** 데이터 원본을 삭제합니다.
7. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사합니다.

    ![모델 매핑 디자이너 페이지에서 편집 가능한 ER 모델 매핑 구성 요소를 검사합니다.](./media/er-components-inspections-03.gif)

8. 유효성 검사 오류가 발생합니다. 메시지는 **X** 데이터 모델 필드의 바인딩이 **Y** 데이터 소스를 참조하는 경로를 포함하지만 이 데이터 소스를 찾을 수 없다고 말합니다.

### <a name="automatic-resolution"></a>자동 해결

누락된 데이터 원본 **바인딩을 제거** 하여 이 문제를 자동으로 수정하려면 바인딩 해제를 선택합니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

존재하지 않는 **Y** 데이터 소스에 대한 참조를 중지하려면 **X** 데이터 모델 필드의 바인딩을 해제합니다.

#### <a name="option-2"></a>옵션 2

모델 매핑 디자이너의 **데이터 원본** 창에서 **Y** 데이터 원본을 다시 추가합니다.

## <a name="executability-of-an-expression-with-filter-function"></a><a id="i4"></a>FILTER 함수가 있는 표현식의 실행 가능성

기본 제공 [FILTER](er-functions-list-filter.md) ER 함수는 단일 SQL 호출을 배치하여 필요한 데이터를 기록 목록으로 가져옴으로써 애플리케이션 테이블, 보기 또는 데이터 엔터티에 액세스하는 데 사용됩니다. **기록 목록** 유형의 데이터 소스는 이 함수의 인수로 사용되며 호출에 대한 애플리케이션 소스를 지정합니다. ER은 `FILTER` 함수에서 참조하는 데이터 소스에 직접 SQL 쿼리를 설정할 수 있는지 여부를 확인합니다. 직접 쿼리를 설정할 수 없으면 ER 모델 매핑 디자이너에서 유효성 검사 오류가 발생합니다. 수신되는 메시지에는 `FILTER` 함수를 포함하는 ER 표현식이 런타임에 실행할 수 없다는 내용이 나와 있습니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 모델 매핑 구성 요소 구성을 시작합니다.
2. **Dynamics 365 for Operations \\ 테이블 기록** 유형의 데이터 소스를 추가하십시오.
3. 새 데이터 소스의 이름을 **공급 업체** 로 지정합니다. **테이블** 필드에서 **VendTable** 을 선택하여 이 데이터 소스가 VendTable 테이블을 요청하도록 지정합니다.
4. **계산된 필드** 유형의 데이터 소스를 추가하십시오.
5. 새 데이터 원본의 이름을 **FilteredVendor** 로 지정하고 `FILTER(Vendor, Vendor.AccountNum="US-101")` 식을 포함하도록 구성합니다.
6. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사하고 **공급 업체** 데이터 원본의 `FILTER(Vendor, Vendor.AccountNum="US-101")` 식을 쿼리할 수 있는지 확인합니다.
7. 잘린 공급 업체 계정 번호를 얻기 위해 **계산된 필드** 유형의 중첩된 필드를 추가하여 **공급 업체** 데이터 소스를 수정합니다.
8. 새 중첩 필드의 이름을 **$AccNumber** 로 지정하고 `TRIM(Vendor.AccountNum)` 표현식을 포함하도록 구성합니다.
9. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사하고 **공급 업체** 데이터 원본의 `FILTER(Vendor, Vendor.AccountNum="US-101")` 식을 쿼리할 수 있는지 확인합니다.

    ![모델 매핑 디자이너 페이지에서 FILTER 함수가 있는 식을 쿼리할 수 있는지 확인합니다.](./media/er-components-inspections-04.gif)

10. **Vendor** 데이터 원본에 **FilteredVendor** 데이터 원본의 식을 직접 SQL 문으로 변환할 수 없는 **계산된 필드** 유형의 중첩 필드가 포함되어 있기 때문에 유효성 검사 오류가 발생합니다.

다음 그림은 경고를 무시하고 **실행** 을 선택하여 모델 매핑을 사용하도록 구성된 형식을 실행하는 경우 발생하는 런타임 오류를 보여줍니다.

![형식 디자이너 페이지에서 편집 가능한 형식을 실행할 때 발생하는 런타임 오류입니다.](./media/er-components-inspections-04a.png)

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

**계산된 필드** 유형의 중첩 필드를 **공급 업체** 데이터 소스에 추가하는 대신 **$AccNumber** 중첩 필드를 **FilteredVendor** 데이터 소스에 추가하고 `TRIM(FilteredVendor.AccountNum)` 표현식을 포함하도록 구성하십시오. 이런 `FILTER(Vendor, Vendor.AccountNum="US-101")` 식으로 표현식은 SQL 수준에서 실행될 수 있으며 나중에 **$AccNumber** 중첩 필드를 계산할 수 있습니다.

#### <a name="option-2"></a>옵션 2

**FilteredVendors** 데이터 소스의 표현식을 `FILTER(Vendor, Vendor.AccountNum="US-101")`에서 `WHERE(Vendor, Vendor.AccountNum="US-101")`로 변경하십시오. 많은 양의 데이터가 있는 테이블(트랜잭션 테이블)의 표현식은 변경하지 않는 것이 좋습니다. 모든 기록을 가져오고 필요한 기록의 선택이 메모리에서 수행되기 때문입니다. 따라서 이 방법은 성능이 저하될 수 있습니다. 자세한 내용은 [WHERE ER 함수](er-functions-list-where.md)를 참조하십시오.

## <a name="executability-of-a-groupby-data-source"></a><a id="i5"></a>GROUPBY 데이터 소스의 실행 가능성

**GROUPBY** 데이터 소스는 일반적으로 각 그룹에 대해 하나 이상의 집계를 수행하기 위해 쿼리 결과를 기록 그룹으로 나눕니다. 모든 **GROUPBY** 데이터 원본은 데이터베이스 수준이나 메모리에서 실행되도록 구성할 수 있습니다. **GROUPBY** 데이터 원본이 데이터베이스 수준에서 실행되도록 구성된 경우 ER은 해당 데이터 원본에서 참조되는 데이터 원본에 대해 직접 SQL 쿼리를 설정할 수 있는지 여부를 확인합니다. 직접 쿼리를 설정할 수 없으면 ER 모델 매핑 디자이너에서 유효성 검사 오류가 발생합니다. 수신되는 메시지는 구성된 **GROUPBY** 데이터 소스를 런타임에 실행할 수 없다는 내용입니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 모델 매핑 구성 요소 구성을 시작합니다.
2. **Dynamics 365 for Operations \\ 테이블 기록** 유형의 데이터 소스를 추가하십시오.
3. 새 데이터 소스의 이름을 **Trans**. **테이블** 필드에서 **VendTrans** 를 선택하여 이 데이터 소스가 VendTrans 테이블을 요청하도록 지정합니다.
4. **Group by** type의 데이터 소스를 추가합니다.
5. 새 데이터 소스의 이름을 **GroupedTrans로** 지정하고 다음과 같이 구성합니다.

    - 그룹화해야 하는 기록의 원본으로 **Trans** 데이터 원본을 선택합니다.
    - **실행 위치** 필드에서 **쿼리를** 선택하여 데이터베이스 수준에서 이 데이터 소스를 실행하도록 지정합니다.

    !['그룹화 기준' 매개 변수 편집 페이지에서 데이터 소스 구성](./media/er-components-inspections-05a.gif)

6. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사하고 구성된 **GroupedTrans** 데이터 원본을 쿼리할 수 있는지 확인합니다.
7. 잘린 공급 업체 계정 번호를 얻기 위해 **계산된 필드** 유형의 중첩된 필드를 추가하여 **Trans** 데이터 원본을 수정합니다.
8. 새 데이터 소스의 이름을 **$AccNumber** 로 지정하고 `TRIM(Trans.AccountNum)` 표현식을 포함하도록 구성합니다.

    ![모델 매핑 디자이너 페이지에서 데이터 소스를 구성합니다.](./media/er-components-inspections-05a.png)

9. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사하고 구성된 **GroupedTrans** 데이터 원본을 쿼리할 수 있는지 확인합니다.

    ![모델 매핑 디자이너 페이지에서 ER 모델 매핑 구성 요소의 유효성을 검사하고 GroupedTrans 데이터 원본을 쿼리할 수 있는지 확인합니다.](./media/er-components-inspections-05b.png)

10. **Trans** 데이터 원본에 **GroupedTrans** 데이터 원본에 대한 호출을 직접 SQL 문으로 변환할 수 없는 **계산된 필드** 유형의 중첩 필드가 포함되어 있기 때문에 유효성 검사 오류가 발생합니다.

다음 그림은 경고를 무시하고 **실행** 을 선택하여 모델 매핑을 사용하도록 구성된 형식을 실행하는 경우 발생하는 런타임 오류를 보여줍니다.

![형식 디자이너 페이지에서 경고를 무시할 때 발생하는 런타임 오류입니다.](./media/er-components-inspections-05c.png)

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

**계산된 필드** 유형의 중첩 필드를 **Trans** 데이터 원본에 추가하는 대신 **GroupedTrans** 데이터 원본의 **GroupedTrans.lines** 항목에 대해 **$AccNumber** 중첩 필드를 추가하고 `TRIM(GroupedTrans.lines.AccountNum)` 식을 포함하도록 구성합니다. 이러한 방식으로 **GroupedTrans** 데이터 소스는 SQL 수준에서 실행될 수 있으며 나중에 **$AccNumber** 중첩 필드를 계산할 수 있습니다.

#### <a name="option-2"></a>옵션 2

**GroupedTrans** 데이터 소스의 **실행 위치** 필드 값을 **쿼리** 에서 **메모리 내** 로 변경합니다. 데이터의 양이 많은 테이블(트랜잭션 테이블)의 값은 변경하지 않는 것이 좋습니다. 모든 기록을 가져오고 그룹화 및 집계가 메모리에서 수행되기 때문입니다. 따라서 이 방법은 성능이 저하될 수 있습니다.

## <a name="executability-of-a-join-data-source"></a><a id="i6"></a>JOIN 데이터 소스의 실행 가능성

[JOIN](er-join-data-sources.md) 데이터 소스는 관련 필드를 기반으로 두 개 이상의 데이터베이스 테이블에서 기록을 결합합니다. 모든 **JOIN** 데이터 원본은 데이터베이스 수준이나 메모리에서 실행되도록 구성할 수 있습니다. **JOIN** 데이터 원본이 데이터베이스 수준에서 실행되도록 구성되면 ER은 해당 데이터 원본에서 참조되는 데이터 원본에 대해 직접 SQL 쿼리를 설정할 수 있는지 여부를 확인합니다. 하나 이상의 참조 데이터 원본으로 직접 SQL 쿼리를 설정할 수 없는 경우 ER 모델 매핑 디자이너에서 유효성 검사 오류가 발생합니다. 구성된 **JOIN** 데이터 소스를 런타임에 실행할 수 없다는 메시지가 표시됩니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 모델 매핑 구성 요소 구성을 시작합니다.
2. **Dynamics 365 for Operations \\ 테이블 기록** 유형의 데이터 소스를 추가하십시오.
3. 새 데이터 소스의 이름을 **공급 업체** 로 지정합니다. **테이블** 필드에서 **VendTable** 을 선택하여 이 데이터 소스가 VendTable 테이블을 요청하도록 지정합니다.
4. **Dynamics 365 for Operations \\ 테이블 기록** 유형의 데이터 소스를 추가하십시오.
5. 새 데이터 소스의 이름을 **Trans**. **테이블** 필드에서 **VendTrans** 를 선택하여 이 데이터 소스가 VendTrans 테이블을 요청하도록 지정합니다.
6. **계산 필드** 유형의 데이터 소스를 **공급 업체** 데이터 소스의 중첩 필드로 추가하십시오.
7. 새 데이터 원본의 이름을 **FilteredTrans로** 지정하고 `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)` 식을 포함하도록 구성합니다.
8. **조인** 유형의 데이터 소스를 추가하십시오.
9. 새 데이터 원본의 이름을 **JoinedList로** 지정하고 다음과 같이 구성합니다.

    1. 조인할 첫 번째 기록 집합으로 **공급 업체** 데이터 원본을 추가합니다.
    2. **Vendor.FilteredTrans** 데이터 원본을 조인할 두 번째 기록 집합으로 추가합니다. 유형으로 **INNER** 를 선택합니다.
    3. **실행** 필드에서 **쿼리** 를 선택하여 데이터베이스 수준에서 이 데이터 소스를 실행하도록 지정합니다.

    ![조인 디자이너 페이지에서 데이터 소스를 구성합니다.](./media/er-components-inspections-06a.gif)

10. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사하고 구성된 **JoinedList** 데이터 원본을 쿼리할 수 있는지 확인합니다.
11. **Vendor.FilteredTrans** 데이터 소스의 `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)` 표현식을 `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)`에서 로 변경하십시오.
12. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사하고 구성된 **JoinedList** 데이터 원본을 쿼리할 수 있는지 확인합니다.

    ![편집 가능한 모델 매핑 구성 요소의 유효성을 검사하고 모델 매핑 디자이너 페이지에서 JoinedList 데이터 소스를 쿼리할 수 있는지 확인합니다.](./media/er-components-inspections-06b.png)

13. Vendor.**FilteredTrans** 데이터 원본의 식이 직접 SQL 호출로 변환될 수 없기 때문에 유효성 검사 오류가 발생합니다. 또한 직접 SQL 호출은 **JoinedList** 데이터 소스에 대한 호출을 직접 SQL 문으로 변환하는 것을 허용하지 않습니다.

    ![모델 매핑 디자이너 페이지에서 JoinedList 데이터 원본의 유효성 검사 실패로 인한 런타임 오류입니다.](./media/er-components-inspections-06c.png)

다음 그림은 경고를 무시하고 **실행** 을 선택하여 모델 매핑을 사용하도록 구성된 형식을 실행하는 경우 발생하는 런타임 오류를 보여줍니다.

![형식 디자이너 페이지에서 편집 가능한 형식을 실행합니다.](./media/er-components-inspections-06e.png)

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

경고에 따라 **Vendor.FilteredTrans** 데이터 소스의 표현식을 `WHERE(Trans, Trans.AccountNum=Vendor.AccountNum)` back에서 `FILTER(Trans, Trans.AccountNum=Vendor.AccountNum)`로 변경하십시오.

![모델 매핑 디자이너 페이지에서 데이터 소스의 업데이트된 표현.](./media/er-components-inspections-06d.png)

#### <a name="option-2"></a>옵션 2

**JoinedList** 데이터 원본에 대한 **실행** 필드 값을 **쿼리** 에서 **메모리 내** 로 변경합니다. 많은 양의 데이터가 있는 테이블(트랜잭션 테이블)의 값은 변경하지 않는 것이 좋습니다. 모든 기록이 페치되고 메모리에서 조인이 발생하기 때문입니다. 따라서 이 방법은 성능이 저하될 수 있습니다. 이 위험에 대해 알려주는 유효성 검사 경고가 표시됩니다.

## <a name="preferability-of-filter-vs-where-function"></a><a id="i7"></a>FILTER 대 WHERE 함수의 선호도

기본 제공 [FILTER](er-functions-list-filter.md) ER 함수는 단일 SQL 호출을 배치하여 필요한 데이터를 기록 목록으로 가져옴으로써 애플리케이션 테이블, 보기 또는 데이터 엔터티에 액세스하는 데 사용됩니다. [WHERE](er-functions-list-where.md) 함수는 주어진 소스에서 모든 기록을 가져오고 메모리에서 기록 선택을 수행합니다. **기록 목록** 유형의 데이터 소스는 두 함수의 인수로 사용되며 기록을 가져오기 위한 소스를 지정합니다. ER은 **WHERE** 함수에서 참조되는 데이터 소스에 대한 직접 SQL 호출을 설정할 수 있는지 여부를 확인합니다. 직접 호출을 설정할 수 있는 경우 ER 모델 매핑 디자이너에서 유효성 검사 경고가 발생합니다. 받은 메시지는 효율성을 높이려면 **WHERE** 함수 대신 **FILTER** 함수를 사용할 것을 권장합니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 모델 매핑 구성 요소 구성을 시작합니다.
2. **Dynamics 365 for Operations \\ 테이블 기록** 유형의 데이터 소스를 추가하십시오.
3. 새 데이터 소스의 이름을 **Trans**. **테이블** 필드에서 **VendTrans** 를 선택하여 이 데이터 소스가 VendTrans 테이블을 요청하도록 지정합니다.
4. **계산 필드** 유형의 데이터 소스를 **공급 업체** 데이터 소스의 중첩 필드로 추가하십시오.
5. 새 데이터 원본의 이름을 **FilteredTrans** 로 지정하고 `WHERE(Trans, Trans.AccountNum="US-101")` 식을 포함하도록 구성합니다.
6. **Dynamics 365 for Operations \\ 테이블 기록** 유형의 데이터 소스를 추가하십시오.
7. 새 데이터 소스의 이름을 **공급 업체** 로 지정합니다. **테이블** 필드에서 **VendTable** 을 선택하여 이 데이터 소스가 VendTable 테이블을 요청하도록 지정합니다.
8. **계산된 필드** 유형의 데이터 소스를 추가하십시오.
9. 새 데이터 원본의 이름을 **FilteredVendor** 로 지정하고 `WHERE(Vendor, Vendor.AccountNum="US-101")` 식을 포함하도록 구성합니다.
10. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사합니다.

    ![모델 매핑 디자이너 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사합니다.](./media/er-components-inspections-07a.png)

11. 유효성 검사 경고에서는 **FilteredVendor** 및 **FilteredTrans** 데이터 소스에 대해 **WHERE** 함수 대신 **FILTER** 함수를 사용할 것을 권장합니다.

    ![모델 매핑 디자이너 페이지에서 WHERE 함수 대신 FILTER 함수를 사용하는 것이 좋습니다.](./media/er-components-inspections-07b.png)

### <a name="automatic-resolution"></a>자동 해결

이 유형의 검사에 대한 **경고** 탭의 그리드에 표시되는 모든 데이터 원본의 표현식에서 **WHERE** 함수를 **FILTER** 함수로 자동 바꾸려면 **수정** 을 선택합니다.

또는 그리드에서 단일 경고에 대한 행을 선택한 다음 **선택 항목 수정** 을 선택할 수 있습니다. 이 경우 선택한 경고에 언급된 데이터 소스에서만 표현식이 자동으로 변경됩니다.

![수정을 선택하여 모델 매핑 디자이너 페이지에서 WHERE 함수를 FILTER 함수로 자동 교체합니다.](./media/er-components-inspections-07c.png)

### <a name="manual-resolution"></a>수동 해상도

**WHERE** 함수를 **FILTER** 함수로 교체하여 유효성 검사 그리드에 있는 모든 데이터 소스의 표현식을 수동으로 조정할 수 있습니다.

## <a name="preferability-of-allitemsquery-vs-allitems-function"></a><a id="i8"></a>ALLITEMSQUERY 대 ALLITEMS 함수의 선호도

기본 제공 [ALLITEMS](er-functions-list-allitems.md) 및 [ALLITEMSQUERY](er-functions-list-allitemsquery.md) ER 함수는 지정된 경로와 일치하는 모든 항목을 나타내는 **기록 목록** 으로 구성된 병합된 기록 목록 값을 반환합니다. ER은 **ALLITEMS** 함수에서 참조되는 데이터 소스에 대한 직접 SQL 호출을 설정할 수 있는지 여부를 확인합니다. 직접 호출을 설정할 수 있는 경우 ER 모델 매핑 디자이너에서 유효성 검사 경고가 발생합니다. 받은 메시지는 효율성을 개선하는 데 도움이 되도록 **ALLITEMS** 함수 대신 **ALLITEMSQUERY** 함수를 사용할 것을 권장합니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 모델 매핑 구성 요소 구성을 시작합니다.
2. **Dynamics 365 for Operations \\ 테이블 기록** 유형의 데이터 소스를 추가하십시오.
3. 새 데이터 소스의 이름을 **공급 업체** 로 지정합니다. **테이블** 필드에서 **VendTable** 을 선택하여 이 데이터 소스가 VendTable 테이블을 요청하도록 지정합니다.
4. 여러 공급 업체에 대한 기록을 가져오려면 **계산된 필드** 유형의 데이터 소스를 추가하십시오.
5. 새 데이터 원본의 이름을 **FilteredVendor** 로 지정하고 `FILTER(Vendor, OR(Vendor.AccountNum="US-101",Vendor.AccountNum="US-102"))` 식을 포함하도록 구성합니다.
6. 필터링된 모든 공급 업체의 트랜잭션을 가져오려면 **계산된 필드** 유형의 데이터 소스를 추가하십시오.
7. 새 데이터 원본의 이름을 **FilteredVendorTrans로** 지정하고 `ALLITEMS(FilteredVendor.'<Relations'.'VendTrans.VendTable_AccountNum')` 식을 포함하도록 구성합니다.
8. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사합니다.

    ![모델 매핑 디자이너 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사합니다.](./media/er-components-inspections-08a.png)

9. 유효성 검사 경고가 발생합니다. 메시지는 **FilteredVendorTrans** 데이터 소스에 대해 **ALLITEMS** 함수 대신 **ALLITEMSQUERY** 함수를 사용할 것을 권장합니다.

    ![모델 매핑 디자이너 페이지에서 ALLITEMS 함수 대신 ALLITEMSQUERY 함수를 사용하는 것이 좋습니다.](./media/er-components-inspections-08b.png)

### <a name="automatic-resolution"></a>자동 해결

이 유형의 검사에 대한 **경고** 탭의 그리드에 표시되는 모든 데이터 소스의 표현식에서 **ALLITEMS** 함수를 **ALLITEMSQUERY** 함수로 자동 바꾸려면 **수정** 을 선택합니다.

또는 그리드에서 단일 경고에 대한 행을 선택한 다음 **선택 항목 수정** 을 선택할 수 있습니다. 이 경우 선택한 경고에 언급된 데이터 소스에서만 표현식이 자동으로 변경됩니다.

![모델 매핑 디자이너 페이지에서 Fix를 선택합니다.](./media/er-components-inspections-08c.png)

### <a name="manual-resolution"></a>수동 해상도

**ALLITEMS** 함수를 **ALLITEMSQUERY** 함수로 대체하여 유효성 검사 그리드에 언급된 모든 데이터 소스의 표현식을 수동으로 조정할 수 있습니다.

## <a name="consideration-of-empty-list-cases"></a><a id="i9"></a>빈 목록의 경우 고려

**기록 목록** 유형의 데이터 소스 필드 값을 가져오도록 ER 형식 또는 모델 매핑 구성 요소를 구성할 수 있습니다. ER은 존재하지 않는 기록의 필드에서 값을 가져올 때 런타임 오류를 방지하기 위해 호출된 데이터 소스에 기록이 없는 경우(즉, 비어 있는 경우) 디자인이 고려하는지 여부를 확인합니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 데이터 모델, ER 모델 매핑 및 ER 형식 구성 요소를 동시에 구성하기 시작합니다.
2. 데이터 모델 트리에서 **Root3** 이라는 루트 항목을 추가합니다.
3. **기록 목록** 유형의 중첩 항목을 추가하여 **Root3** 항목을 수정하십시오.
4. 새 중첩 항목의 이름을 **공급 업체** 로 지정합니다.
5. 다음과 같은 방법으로 **공급 업체** 항목을 수정합니다.

    - **스트링** 유형의 중첩 필드를 추가하고 이름을 **이름** 으로 지정합니다.
    - **스트링** 유형의 중첩 필드를 추가하고 이름을 **AccountNumber로** 지정합니다.

    ![데이터 모델 페이지에 중첩 필드 추가](./media/er-components-inspections-09a.png)

6. 모델 매핑 디자이너의 **데이터 원본** 창에서 테이블 **Dynamics 365 for Operations \\ 기록 유형** 의 데이터 원본을 추가합니다.
7. 새 데이터 소스의 이름을 **공급 업체** 로 지정합니다. **테이블** 필드에서 **VendTable** 을 선택하여 이 데이터 소스가 VendTable 테이블을 요청하도록 지정합니다.
8. 런타임 대화 상자에서 공급 업체 계정을 검색하려면 **일반 \\ 사용자 입력 매개 변수** 유형의 데이터 소스를 추가하십시오.
9. 새 데이터 소스의 이름을 **RequestedAccountNum** 으로 지정합니다. **레이블** 필드에 **공급 업체 계정 번호** 를 입력합니다. **작업 데이터 유형 이름** 필드에서 기본값인 **설명** 을 그대로 둡니다.
10. 조회되는 벤더를 필터링하기 위해 **계산된 필드** 유형의 데이터 소스를 추가하십시오.
11. 새 데이터 원본의 이름을 **FilteredVendor로** 지정하고 `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)` 식을 포함하도록 구성합니다.
12. 다음과 같은 방식으로 데이터 모델 항목을 구성된 데이터 원본에 바인딩합니다.

    - **FilteredVendor** 를 **Vendor** 에 바인딩합니다.
    - **FilteredVendor.AccountNum** 을 **Vendor.AccountNumber** 에 바인딩합니다.
    - **FilteredVendor.'name()'** 을 **Vendor.Name** 에 바인딩합니다.

    ![모델 매핑 디자이너 페이지에서 데이터 모델 항목을 바인딩합니다.](./media/er-components-inspections-09b.png)

13. 형식 구조 트리에서 다음 항목을 추가하여 공급 업체 세부 정보가 포함된 XML 형식의 아웃바운드 문서를 생성합니다.

    1. **명령문** 루트 XML 요소를 추가하십시오.
    2. **명령문** XML 요소의 경우 중첩된 **당사자** XML 요소를 추가하십시오.
    3. **Party** XML 요소의 경우 다음 중첩 XML 속성을 추가합니다.

        - 이름
        - 계정 번호

14. 다음과 같은 방식으로 제공된 데이터 소스에 형식 요소를 바인딩합니다.

    - **이름\\형식\\요소** 를 **model.Vendor.Name** 데이터 소스 필드에 바인딩하십시오.
    - **계정 번호\\형식\\요소** 를 **model.Vendor.AccountNumber** 데이터 소스 필드에 바인딩합니다.

15. **형식 디자이너** 페이지에서 편집 가능한 형식 구성 요소를 검사하려면 **유효성 검사** 를 선택합니다.

    ![형식 디자이너 페이지에서 데이터 원본에 바인딩한 형식 요소의 유효성을 검사합니다.](./media/er-components-inspections-09c.png)

16. 유효성 검사 오류가 발생합니다. 이 메시지는 `model.Vendor` 목록이 비어 있는 경우 **런타임에\\구성된\\이름** 및 **계정 번호\\형식\\구성 요소** 에 대해 오류가 발생할 수 있음을 나타냅니다.

    ![구성된 형식 구성 요소에 대한 잠재적 오류에 대한 유효성 검사 오류입니다.](./media/er-components-inspections-09d.png)

다음 그림은 경고를 무시하고 실행을 선택하여 형식을 **실행** 하고 존재하지 않는 공급 업체의 계정 번호를 선택하는 경우 발생하는 런타임 오류를 보여줍니다. 요청한 공급 업체가 존재하지 않기 때문에 `model.Vendor` 목록이 비어 있습니다(즉, 기록이 포함되지 않음).

![형식 매핑 실행 중에 발생하는 런타임 오류입니다.](./media/er-components-inspections-09e.png)

### <a name="automatic-resolution"></a>자동 해결

**경고** 탭의 그리드에서 선택한 행에 대해 **바인딩 해제** 를 선택할 수 있습니다. **경로** 열에서 가리키는 바인딩은 형식 요소에서 자동으로 제거됩니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

**Statement\\Party\\Name** 형식 요소를 `model.Vendor` 데이터 소스 항목에 바인딩할 수 있습니다. 런타임 시 이 바인딩은 `model.Vendor` 데이터 소스를 먼저 호출합니다. `model.Vendor` 빈 기록 목록을 반환하면 중첩된 형식 요소가 실행되지 않습니다. 따라서 이 형식 구성에 대해 유효성 검사 경고가 발생하지 않습니다.

![형식 디자이너 페이지에서 형식 요소를 데이터 소스 항목에 바인딩합니다.](./media/er-components-inspections-09e.gif)

#### <a name="option-2"></a>옵션 2

**이름\\형식\\요소** 의 바인딩을 `model.Vendor.Name`에서 `FIRSTORNULL(model.Vendor).Name`로 변경하십시오. 업데이트된 바인딩은 조건부로 **기록** 목록 유형의 `model.Vendor` 데이터 소스의 첫 번째 기록을 **기록 유형** 의 새 데이터 소스로 변환합니다. 이 새 데이터 원본에는 동일한 필드 집합이 포함되어 있습니다.

- `model.Vendor` 데이터 소스에서 하나 이상의 기록을 사용할 수 있는 경우 해당 기록의 필드는 `model.Vendor` 데이터 소스의 첫 번째 기록 필드 값으로 채워집니다. 이 경우 업데이트된 바인딩은 공급 업체 이름을 반환합니다.
- 그렇지 않으면 생성된 기록의 모든 필드가 해당 필드의 데이터 유형에 대한 기본값으로 채워집니다. 이 경우 **스트링** 데이터 유형의 기본값으로 공백 스트링이 반환됩니다.

따라서 `FIRSTORNULL(model.Vendor).Name` 표현식에 바인딩된 경우 **Statement\\Party\\Name** 형식 요소에 대해 유효성 검사 경고가 발생하지 않습니다.

![변경된 바인딩은 형식 디자이너 페이지의 유효성 검사 경고를 해결합니다.](./media/er-components-inspections-09f.gif)

#### <a name="option-3"></a>옵션 3

**기록 목록** 유형의 `model.Vendor` 데이터 소스가 기록을 반환하지 않을 때 생성된 문서에 입력된 데이터를 명시적으로 지정하려면(이 예시에서는 **사용할 수 없음** 텍스트) **Statement\\Party\\Name** 형식 요소의 바인딩을 `model.Vendor.Name`에서 `IF(NOT(ISEMPTY(model.Vendor)), model.Vendor.Name, "Not available")`로 변경하십시오. `IF(COUNT(model.Vendor)=0, model.Vendor.Name, "Not available")` 표현식을 사용할 수도 있습니다.

### <a name="additional-consideration"></a><a id="i9a"></a>추가 고려 사항

검사는 또한 다른 잠재적인 문제에 대해 경고합니다. 기본적으로 **Statement\\Party\\Name** 및 **Statement\\Party\\AccountNum** 형식 요소를 **기록 목록** 유형의 `model.Vendor` 데이터 소스의 적절한 필드에 바인딩하면 해당 바인딩이 실행되고 다음과 같은 경우 `model.Vendor` 데이터 소스의 첫 번째 기록에 대한 적절한 필드 값을 사용합니다. 그 목록은 비어 있지 않습니다.

**Statement\\Party** 형식 요소를 `model.Vendor` 데이터 소스와 바인딩하지 않았기 때문에 **Statement\\Party** 요소는 형식 실행 중에 `model.Vendor` 데이터 소스의 모든 기록에 대해 반복되지 않습니다. 대신, 목록에 여러 기록이 포함된 경우 생성된 문서는 기록 목록의 첫 번째 기록의 정보로만 채워집니다. 따라서 형식이 `model.Vendor` 데이터 소스의 모든 공급 업체에 대한 정보로 생성된 문서를 채우도록 의도된 경우 문제가 있을 수 있습니다. 이 문제를 해결하려면 **Statement\\Party** 요소를 `model.Vendor` 데이터 소스와 바인딩하십시오.

## <a name="executability-of-an-expression-with-filter-function-caching"></a><a id="i10"></a>FILTER 함수(캐싱)가 있는 표현식의 실행 가능성

[FILTER](er-functions-list-filter.md) 및 [ALLITEMSQUERY](er-functions-list-allitemsquery.md)를 포함한 여러 내장 ER 함수는 단일 SQL 호출을 배치하여 필요한 데이터를 기록 목록으로 가져옴으로써 애플리케이션 테이블, 보기 또는 데이터 엔터티에 액세스하는 데 사용됩니다. **기록 목록** 유형의 데이터 소스는 이러한 각 함수의 인수로 사용되며 호출에 대한 애플리케이션 소스를 지정합니다. ER은 이러한 함수 중 하나에서 참조되는 데이터 소스에 대한 직접 SQL 호출을 설정할 수 있는지 여부를 확인합니다. 데이터 원본이 [캐시된](trace-execution-er-troubleshoot-perf.md#improve-the-model-mapping-based-on-information-from-the-execution-trace) 것으로 표시되어 직접 호출을 설정할 수 없는 경우 ER 모델 매핑 디자이너에서 유효성 검사 오류가 발생합니다. 수신되는 메시지에는 이러한 함수 중 하나가 포함된 ER 표현식이 런타임에 실행할 수 없다는 내용이 나와 있습니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 모델 매핑 구성 요소 구성을 시작합니다.
2. **Dynamics 365 for Operations \\ 테이블 기록** 유형의 데이터 소스를 추가하십시오.
3. 새 데이터 소스의 이름을 **공급 업체** 로 지정합니다. **테이블** 필드에서 **VendTable** 을 선택하여 이 데이터 소스가 VendTable 테이블을 요청하도록 지정합니다.
4. 런타임 대화 상자에서 공급 업체 계정을 검색하려면 **일반 \\ 사용자 입력 매개 변수** 유형의 데이터 소스를 추가하십시오.
5. 새 데이터 소스의 이름을 **RequestedAccountNum** 으로 지정합니다. **레이블** 필드에 **공급 업체 계정 번호** 를 입력합니다. **작업 데이터 유형 이름** 필드에서 기본값인 **설명** 을 그대로 둡니다.
6. 조회되는 벤더를 필터링하기 위해 **계산된 필드** 유형의 데이터 소스를 추가하십시오.
7. 새 데이터 원본의 이름을 **FilteredVendor로** 지정하고 `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)` 식을 포함하도록 구성합니다.
8. 구성된 **공급 업체** 데이터 소스를 캐시된 것으로 표시합니다.

    ![모델 매핑 디자이너 페이지에서 모델 매핑 구성 요소를 구성합니다.](./media/er-components-inspections-10a.gif)

9. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사합니다.

    ![모델 매핑 디자이너 페이지에서 캐시된 공급 업체 데이터 소스에 적용되는 FILTER 함수의 유효성을 검사합니다.](./media/er-components-inspections-10a.png)

10. 유효성 검사 오류가 발생합니다. 캐시된 **공급 업체** 데이터 소스에 **FILTER** 함수를 적용할 수 없다는 메시지가 표시됩니다.

다음 그림은 경고를 무시하고 **실행** 을 선택하여 형식을 실행하는 경우 발생하는 런타임 오류를 보여줍니다.

![형식 디자이너 페이지에서 형식 매핑을 실행하는 동안 발생하는 런타임 오류입니다.](./media/er-components-inspections-10b.png)

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

**공급 업체** 데이터 소스에서 **캐시** 플래그를 제거합니다. 그러면 **FilteredVendor** 데이터 소스가 실행 가능하게 되지만 **VendTable** 테이블에서 참조되는 Vendor 데이터 소스는 **FilteredVendor** 데이터 소스가 호출될 때마다 액세스됩니다.

#### <a name="option-2"></a>옵션 2

**FilteredVendors** 데이터 소스의 표현식을 `FILTER(Vendor, Vendor.AccountNum="US-101")`에서 `WHERE(Vendor, Vendor.AccountNum="US-101")`로 변경하십시오. 이 경우 VendTable 테이블에서 참조되는 **Vendor** 데이터 소스는 **Vendor** 데이터 소스의 첫 번째 호출 중에만 액세스됩니다. 그러나 기록 선택은 메모리에서 수행됩니다. 따라서 이 방법은 성능이 저하될 수 있습니다.

## <a name="missing-binding"></a><a id="i11"></a>바인딩 누락

ER 형식 구성 요소를 구성하면 기본 ER 데이터 모델이 ER 형식의 기본 데이터 소스로 제공됩니다. 구성된 ER 형식이 실행되면 [기본 모델](er-country-dependent-model-mapping.md)에 대한 기본 모델 매핑을 사용하여 데이터 모델을 애플리케이션 데이터로 채웁니다. 편집 가능한 형식에 대한 기본 모델 매핑으로 현재 선택된 모델 매핑의 데이터 소스에 바인딩되지 않은 데이터 모델 항목에 형식 요소를 바인딩하면 ER 형식 디자이너에 경고가 표시됩니다. 실행되는 형식이 바인딩된 요소를 애플리케이션 데이터로 채울 수 없기 때문에 이러한 유형의 바인딩은 런타임에 실행할 수 없습니다. 따라서 런타임에 오류가 발생합니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 데이터 모델, ER 모델 매핑 및 ER 형식 구성 요소를 동시에 구성하기 시작합니다.
2. 데이터 모델 트리에서 **Root3** 이라는 루트 항목을 추가합니다.
3. **기록 목록** 유형의 새 중첩 항목을 추가하여 **Root3** 항목을 수정하십시오.
4. 새 중첩 항목의 이름을 **공급 업체** 로 지정합니다.
5. 다음과 같은 방법으로 **공급 업체** 항목을 수정합니다.

    - **스트링** 유형의 중첩 필드를 추가하고 이름을 **이름** 으로 지정합니다.
    - **스트링** 유형의 중첩 필드를 추가하고 이름을 **AccountNumber로** 지정합니다.

    ![데이터 모델 페이지의 공급 업체 항목에 중첩 필드 추가](./media/er-components-inspections-11a.png)

6. 모델 매핑 디자이너의 **데이터 원본** 창에서 테이블 **Dynamics 365 for Operations \\ 기록 유형** 의 데이터 원본을 추가합니다.
7. 새 데이터 소스의 이름을 **공급 업체** 로 지정합니다. **테이블** 필드에서 **VendTable** 을 선택하여 이 데이터 소스가 VendTable 테이블을 요청하도록 지정합니다.
8. 런타임 대화 상자에서 벤더 계정을 조회하려면 **일반 \\ 사용자 입력 매개 변수** 유형의 데이터 소스를 추가하십시오.
9. 새 데이터 소스의 이름을 **RequestedAccountNum** 으로 지정합니다. **레이블** 필드에 **공급 업체 계정 번호** 를 입력합니다. **작업 데이터 유형 이름** 필드에서 기본값인 **설명** 을 그대로 둡니다.
10. 조회되는 벤더를 필터링하기 위해 **계산된 필드** 유형의 데이터 소스를 추가하십시오.
11. 새 데이터 원본의 이름을 **FilteredVendor로** 지정하고 `FILTER(Vendor, Vendor.AccountNum=RequestedAccountNum)` 식을 포함하도록 구성합니다.
12. 다음과 같은 방식으로 데이터 모델 항목을 구성된 데이터 원본에 바인딩합니다.

    - **FilteredVendor** 를 **Vendor** 에 바인딩합니다.
    - **FilteredVendor.AccountNum** 을 **Vendor.AccountNumber** 에 바인딩합니다.

    > [!NOTE]
    > **Vendor.Name** 데이터 모델 필드는 바인딩되지 않은 상태로 유지됩니다.

    ![구성된 데이터 원본에 바인딩된 데이터 모델 항목 및 모델 매핑 디자이너 페이지에서 바인딩되지 않은 상태로 유지되는 데이터 모드 항목입니다.](./media/er-components-inspections-11b.png)

13. 형식 구조 트리에서 다음 항목을 추가하여 조회하는 공급 업체의 세부 정보가 포함된 XML 형식의 아웃바운드 문서를 생성합니다.

    1. **명령문** 루트 XML 요소를 추가하십시오.
    2. **명령문** XML 요소의 경우 중첩된 **당사자** XML 요소를 추가하십시오.
    3. **Party** XML 요소의 경우 다음 중첩 XML 속성을 추가합니다.

        - 이름
        - 계정 번호

14. 다음과 같은 방법으로 제공된 데이터 소스에 형식 요소를 바인딩합니다.

    - **Statement\\Party** 형식 요소를 `model.Vendor` 데이터 소스 항목에 바인딩합니다.
    - **이름\\형식\\요소** 를 **model.Vendor.Name** 데이터 소스 필드에 바인딩하십시오.
    - **계정 번호\\형식\\요소** 를 **model.Vendor.AccountNumber** 데이터 소스 필드에 바인딩합니다.

15. **형식 디자이너** 페이지에서 편집 가능한 형식 구성 요소를 검사하려면 **유효성 검사** 를 선택합니다.

    ![형식 디자이너 페이지에서 ER 형식 구성 요소의 유효성을 검사합니다.](./media/er-components-inspections-11c.png)

16. 유효성 검사 경고가 발생합니다. 이 메시지는 **model.Vendor.Name** 데이터 원본 필드가 형식에서 사용하도록 구성된 모델 매핑의 데이터 원본에 바인딩되지 않았다고 나타냅니다. 따라서 **Statement\\Party\\Name** 형식 요소는 런타임에 채워지지 않을 수 있으며 런타임 예외가 발생할 수 있습니다.

    ![형식 디자이너 페이지에서 ER 형식 구성 요소의 유효성을 검사합니다.](./media/er-components-inspections-11d.png)

다음 그림은 경고를 무시하고 **실행** 을 선택하여 형식을 실행하는 경우 발생하는 런타임 오류를 보여줍니다.

![형식 디자이너 페이지에서 편집 가능한 형식을 실행합니다.](./media/er-components-inspections-11e.png)

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

**model.Vendor.Name** 데이터 소스 필드에 대한 바인딩을 추가하여 구성된 모델 매핑을 수정합니다.

#### <a name="option-2"></a>옵션 2

**Statement\\Party\\Name** 형식 요소에 대한 바인딩을 제거하여 구성된 형식을 수정하십시오.

## <a name="not-linked-template"></a><a id="i12"></a>연결되지 않은 템플릿

템플릿을 사용하여 아웃바운드 문서를 생성하도록 ER 형식 구성 요소를 [수동으로](er-fillable-excel.md#manual-entry) 구성하는 경우 **Excel\\File** 요소를 수동으로 추가하고 필요한 템플릿을 편집 가능한 구성 요소의 첨부 파일로 추가하고 추가된 **Excel\\File** 요소에서 해당 첨부 파일을 선택해야 합니다. 이러한 방식으로 추가된 요소가 런타임에 선택한 템플릿을 채울 것임을 나타냅니다. **초안** [상태](general-electronic-reporting.md#component-versioning)에서 형식 구성 요소 버전을 구성할 때 편집 가능한 구성 요소에 여러 템플릿을 추가한 다음 **Excel\\File** 요소에서 각 템플릿을 선택하여 ER 형식을 실행할 수 있습니다. 이러한 방식으로 런타임에 다른 템플릿이 어떻게 채워지는지 확인할 수 있습니다. **Excel\\File** 요소에서 선택하지 않은 템플릿이 있는 경우 ER 형식 디자이너는 상태가 **초안** 에서 **완료** 로 변경될 때 편집 가능한 ER 형식 구성 요소 버전에서 해당 템플릿이 삭제된다는 경고를 표시합니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 형식 구성 요소 구성을 시작합니다.
2. 형식 구조 트리에서 **Excel\\File** 요소를 추가합니다.
3. 방금 추가한 **Excel\\File** 요소에 대해 Excel 통합 문서 파일 **A.xlsx** 를 첨부 파일로 추가합니다. [ER 매개 변수](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)에 구성된 문서 유형을 사용하여 ER 형식 템플릿의 저장을 지정합니다.
4. **Excel\\File** 요소의 경우 다른 Excel 통합 문서 파일인 **B.xlsx** 를 첨부 파일로 추가합니다. 통합 문서 파일 A에 사용된 것과 동일한 문서 유형을 사용하십시오.
5. **Excel\\File** 요소에서 통합 문서 파일 A를 선택합니다.
6. **형식 디자이너** 페이지에서 편집 가능한 형식 구성 요소를 검사하려면 **유효성 검사** 를 선택합니다.

    ![형식 디자이너 페이지에서 통합 문서 파일의 편집 가능한 형식 구성 요소를 확인합니다.](./media/er-components-inspections-12a.gif)

7. 유효성 검사 경고가 발생합니다. 이 메시지는 통합 문서 파일 B.xlsx가 어떤 구성 요소에도 연결되어 있지 않으며 구성 버전의 상태가 변경된 후에 제거될 것임을 나타냅니다.

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

**Excel\\File** 요소에 연결되지 않은 모든 템플릿을 제거하여 구성된 형식을 수정합니다.

## <a name="not-synced-format"></a><a id="i13"></a>동기화되지 않은 형식

Excel 템플릿을 사용하여 아웃바운드 문서를 생성하도록 ER 형식 구성 요소를 [구성](er-fillable-excel.md)할 때 **Excel\\File** 요소를 수동으로 추가하고 필요한 템플릿을 편집 가능한 구성 요소의 첨부 파일로 추가하고 추가된 **Excel\\File** 요소에서 해당 첨부 파일을 선택할 수 있습니다. 이러한 방식으로 추가된 요소가 런타임에 선택한 템플릿을 채울 것임을 나타냅니다. 추가된 Excel 템플릿은 외부에서 설계되었기 때문에 편집 가능한 ER 형식에는 추가된 템플릿에서 누락된 Excel 이름이 포함될 수 있습니다. ER 형식 디자이너는 추가된 Excel 템플릿에 포함되지 않은 이름을 참조하는 ER 형식 요소의 속성 간의 불일치에 대해 경고합니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 형식 구성 요소 구성을 시작합니다.
2. 형식 구조 트리에서 **Excel\\File** 요소 **보고서** 를 추가합니다.
3. 방금 추가한 **Excel\\File** 요소에 대해 Excel 통합 문서 파일 **A.xlsx** 를 첨부 파일로 추가합니다. [ER 매개 변수](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents)에 구성된 문서 유형을 사용하여 ER 형식 템플릿의 저장을 지정합니다.

    > [!IMPORTANT]
    > 추가된 Excel 통합 문서에 **ReportTitle** 이라는 이름이 포함되어 있지 않은지 확인합니다.

4. **Excel\\Cell** 요소 **Title** 을 **Report** 요소의 중첩 요소로 추가합니다. **Excel 범위** 필드에 **ReportTitle** 을 입력합니다.
5. **형식 디자이너** 페이지에서 편집 가능한 형식 구성 요소를 검사하려면 **유효성 검사** 를 선택합니다.

    ![형식 디자이너 페이지에서 중첩된 요소 및 필드의 유효성을 검사합니다.](./media/er-components-inspections-13a.png)

6. 유효성 검사 경고가 발생합니다. 사용 중인 Excel 템플릿의 **Sheet1** 시트에 **ReportTitle** 이라는 이름이 존재하지 않는다는 메시지가 표시됩니다.

    ![ReportTitle이라는 이름이 Excel 템플릿의 Sheet1에 존재하지 않는다는 유효성 검사 경고.](./media/er-components-inspections-13b.png)

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

템플릿에서 누락된 Excel 이름을 참조하는 모든 요소를 제거하여 구성된 형식을 수정합니다.

#### <a name="option-2"></a>옵션 2

Excel 템플릿을 가져와 편집 가능한 ER 형식을 [업데이트합니다](er-fillable-excel.md#template-import). 편집 가능한 ER 형식의 구조는 가져온 Excel 템플릿의 구조와 [동기화됩니다](modify-electronic-reporting-format-reapply-excel-template.md).

### <a name="additional-consideration"></a>추가 고려 사항

[비즈니스 문서 관리](er-business-document-management.md)의 템플릿 편집기에서 형식 구조를 ER 템플릿과 동기화하는 방법을 알아보려면 [비즈니스 문서 템플릿의 구조 업데이트](er-bdm-update-structure.md)를 참조하십시오.

## <a name="not-synced-with-a-word-template-format"></a><a id="i14"></a>Word 템플릿 형식과 동기화되지 않음

Word 템플릿을 사용하여 아웃바운드 문서를 생성하도록 ER 형식 구성 요소를 [구성](er-fillable-excel.md)할 때 **Excel\\File** 요소를 수동으로 추가하고 필요한 Word 템플릿을 편집 가능한 구성 요소의 첨부 파일로 추가하고 추가된 **Excel\\File** 요소에서 해당 첨부 파일을 선택할 수 있습니다.

> [!NOTE]
> Word 문서가 첨부되면 ER 형식 디자이너는 편집 가능한 요소를 **Word\\File** 로 표시합니다.

이러한 방식으로 추가된 요소가 런타임에 선택한 템플릿을 채울 것임을 나타냅니다. 추가된 Word 템플릿은 외부에서 설계되었기 때문에 편집 가능한 ER 형식에는 추가된 템플릿에서 누락된 Word 콘텐츠 컨트롤에 대한 참조가 포함될 수 있습니다. ER 형식 디자이너는 추가된 Word 템플릿에 포함되지 않은 콘텐츠 컨트롤을 참조하는 ER 형식 요소의 속성 간의 불일치에 대해 경고합니다.

이 문제가 어떻게 발생하는지 보여주는 예는 [요약 섹션을 표시하지 않도록 편집 가능한 형식 구성](er-design-configuration-word-suppress-controls.md#configure-to-suppress-control)을 참조하십시오.

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

유효성 검사 경고에 언급된 형식 요소에서 **제거된** 수식을 삭제하여 구성된 형식을 수정합니다.

#### <a name="option-2"></a>옵션 2

관련 Word 콘텐츠 컨트롤에 필요한 태그를 [추가하여](er-design-configuration-word-suppress-controls.md#tag-control) 사용 Word 템플릿을 수정합니다.

## <a name="no-default-mapping"></a><a id="i15"></a>기본 매핑 없음

[누락된 바인딩](#i11) 검사가 완료되면 검사된 형식 바인딩이 관련 모델 매핑 구성 요소의 바인딩에 대해 평가됩니다. [여러](./tasks/er-manage-model-mapping-configurations-july-2017.md) ER 모델 매핑 구성을 Finance 인스턴스로 가져올 수 있고 각 구성에 적용 가능한 모델 매핑 구성 요소가 포함될 수 있으므로 하나의 구성을 기본 구성으로 선택해야 합니다. 그렇지 않으면 검사한 ER 형식을 실행, 편집 또는 확인하려고 하면 예외가 발생하고 다음 메시지가 표시됩니다. \<configuration names separated by comma\> 구성의 '()' \<model name (root descriptor)\> 데이터 모델에 대해 둘 이상의 모델 매핑이 존재합니다. 구성 중 하나를 기본값으로 설정

이 문제가 어떻게 발생하고 어떻게 해결할 수 있는지 보여주는 예는 [단일 모델 루트에 대한 여러 파생 매핑 관리](er-multiple-model-mappings.md)를 참조하십시오.

## <a name="inconsistent-setting-of-header-or-footer-components"></a><a id="i16"></a>머리글 또는 바닥글 구성 요소의 일관되지 않은 설정

Excel 템플릿을 사용하여 아웃바운드 문서를 생성하도록 ER 형식 구성 요소를 [구성](er-fillable-excel.md)할 때 **Excel\\Header** 구성 요소를 추가하여 Excel 통합 문서의 워크시트 상단에 있는 머리글을 채울 수 있습니다. **Excel\\Footer** 구성 요소를 추가하여 워크시트 하단의 바닥글을 채울 수도 있습니다. 추가하는 모든 **Excel\\Header** 또는 **Excel\\Footer** 구성 요소에 대해 **머리글/바닥글 모양** 속성을 설정하여 구성 요소가 실행되는 페이지를 지정해야 합니다. 단일 시트 구성 요소에 대해 여러 **Excel\\Header** 또는 **Excel\\Footer** 구성 요소를 구성할 수 있고 Excel **워크시트의** 다양한 페이지 유형에 대해 서로 다른 머리글 또는 바닥글을 생성할 수 있으므로 머리글/의 특정 값에 대해 단일 **Excel\\Header** 또는 **Excel\\Footer** 구성 요소를 구성해야 합니다. **Header/footer appearance** 속성. **머리글/바닥글 모양** 속성의 특정 값에 대해 둘 이상의 **Excel\\Header** 또는 **Excel\\Footer** 구성 요소가 구성된 경우 유효성 검사 오류가 발생하고 다음 오류 메시지가 나타납니다. 머리글/바닥글(&lt;구성 요소 유형: 머리글 또는 바닥글&gt;)이 일치하지 않습니다.

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

일치하지 않는 **Excel\\Header** 또는 **Excel\\Footer** 구성 요소 중 하나를 삭제하여 구성된 형식을 수정합니다.

#### <a name="option-2"></a>옵션 2

일치하지 않는 **Excel\\Header** 또는 **Excel\\Footer** 구성 요소 중 하나에 대한 **머리글/바닥글 모양** 속성 값을 수정합니다.

## <a name="inconsistent-setting-of-page-component"></a><a id="i17"></a>페이지 구성 요소의 일관되지 않은 설정

Excel 템플릿을 사용하여 아웃바운드 문서를 생성하도록 ER 형식 구성 요소를 [구성](er-fillable-excel.md)할 때 **Excel\\Page** 구성 요소를 추가하여 ER 수식을 사용하여 생성된 문서에 페이지를 매길 수 있습니다. 추가하는 모든 **Excel\\Page** 구성 요소에 대해 많은 중첩된 [Range](er-fillable-excel.md#range-component) 구성 요소를 추가할 수 있으며 여전히 다음 [구조](er-fillable-excel.md#page-component-structure)를 준수합니다.

- **복제 방향** 속성이 **복제 없음** 으로 설정되도록 첫 번째 중첩 **범위** 구성 요소를 구성할 수 있습니다. 이 범위는 생성된 문서에서 페이지 헤더를 만드는 데 사용됩니다.
- **복제 방향** 속성이 **수직** 으로 설정된 다른 여러 중첩 **범위** 구성 요소를 추가할 수 있습니다. 이 범위는 생성된 문서를 채우는 데 사용됩니다.
- 마지막 중첩 **범위** 구성 요소는 **복제 방향** 속성이 **복제 없음** 으로 설정되도록 구성할 수 있습니다. 이 범위는 생성된 문서에서 페이지 바닥글을 만들고 필요한 페이지 나누기를 추가하는 데 사용됩니다.

디자인 타임에 ER 형식 디자이너에서 ER 형식에 대해 이 구조를 따르지 않으면 유효성 검사 오류가 발생하고 다음 오류 메시지가 나타납니다. 복제가 없는 범위 구성 요소가 두 개 이상 있습니다. 불필요한 구성 요소를 제거하십시오.

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

일치하지 않는 모든 **Excel\\Range** 구성 요소에 대한 **복제 방향** 속성을 변경하여 구성된 형식을 수정합니다.

## <a name="executability-of-an-expression-with-orderby-function"></a><a id="i18"></a>ORDERBY 함수가 있는 표현식의 실행 가능성

내장 [ORDERBY](er-functions-list-orderby.md) ER 함수는 함수의 인수로 지정된 **[기록 목록](er-formula-supported-data-types-composite.md#record-list)** 유형의 ER 데이터 소스의 기록을 정렬하는 데 사용됩니다.

`ORDERBY` 함수의 인수는 정렬된 데이터를 기록 목록으로 가져오기 위해 단일 데이터베이스 호출을 배치하여 애플리케이션 테이블, 보기 또는 데이터 엔터티의 기록을 정렬하도록 [지정할](er-functions-list-orderby.md#syntax-2) 수 있습니다. **기록 목록** 유형의 데이터 소스는 함수의 인수로 사용되며 호출에 대한 애플리케이션 소스를 지정합니다.

ER은 `ORDERBY` 함수에서 참조하는 데이터 소스에 대해 직접 데이터베이스 쿼리를 설정할 수 있는지 여부를 확인합니다. 직접 쿼리를 설정할 수 없으면 ER 모델 매핑 디자이너에서 유효성 검사 오류가 발생합니다. 수신되는 메시지에는 `ORDERBY` 함수를 포함하는 ER 표현식이 런타임에 실행할 수 없다는 내용이 나와 있습니다.

다음 단계는 이 문제가 어떻게 발생하는지 보여줍니다.

1. ER 모델 매핑 구성 요소 구성을 시작합니다.
2. **Dynamics 365 for Operations \\ 테이블 기록** 유형의 데이터 소스를 추가하십시오.
3. 새 데이터 소스의 이름을 **공급 업체** 로 지정합니다. **테이블** 필드에서 **VendTable을** 선택하여 이 데이터 소스가 **VendTable** 테이블을 요청하도록 지정합니다.
4. **계산된 필드** 유형의 데이터 소스를 추가하십시오.
5. 새 데이터 소스의 이름을 **OrderedVendors로** 지정하고 `ORDERBY("Query", Vendor, Vendor.AccountNum)` 표현식을 포함하도록 구성합니다.
 
    ![모델 매핑 디자이너 페이지에서 데이터 소스 구성](./media/er-components-inspections-18-1.png)

6. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사하고 **OrderedVendors** 데이터 원본의 식을 쿼리할 수 있는지 확인합니다.
7. 잘린 공급 업체 계정 번호를 얻기 위해 **계산된 필드** 유형의 중첩된 필드를 추가하여 **공급 업체** 데이터 소스를 수정합니다.
8. 새 중첩 필드의 이름을 **$AccNumber** 로 지정하고 `TRIM(Vendor.AccountNum)` 표현식을 포함하도록 구성합니다.
9. **유효성 검사** 를 선택하여 **모델 매핑 디자이너** 페이지에서 편집 가능한 모델 매핑 구성 요소를 검사하고 **공급 업체** 데이터 원본의 식을 쿼리할 수 있는지 확인합니다.

    ![모델 매핑 디자이너 페이지에서 공급 업체 데이터 소스의 표현식을 쿼리할 수 있는지 확인합니다.](./media/er-components-inspections-18-2.png)

10. **Vendor** 데이터 원본에 **OrderedVendors** 데이터 원본의 식을 직접 데이터베이스 문으로 변환할 수 없는 **계산된 필드** 유형의 중첩 필드가 포함되어 있기 때문에 유효성 검사 오류가 발생합니다. 유효성 검사 오류를 무시하고 **실행** 을 선택하여 이 모델 매핑을 실행하면 런타임에 동일한 오류가 발생합니다.

### <a name="automatic-resolution"></a>자동 해결

이 문제를 자동으로 수정하는 옵션이 없습니다.

### <a name="manual-resolution"></a>수동 해상도

#### <a name="option-1"></a>옵션 1

**계산된 필드** 유형의 중첩 필드를 **공급 업체** 데이터 소스에 추가하는 대신 **$AccNumber** 중첩 필드를 **FilteredVendors** 데이터 소스에 추가하고 `TRIM(FilteredVendor.AccountNum)` 표현식을 포함하도록 필드를 구성합니다. 이런 식으로 `ORDERBY("Query", Vendor, Vendor.AccountNum)` 표현식은 데이터베이스 수준에서 실행될 수 있으며 **$AccNumber** 중첩 필드의 계산은 이후에 수행될 수 있습니다.

#### <a name="option-2"></a>옵션 2

**FilteredVendors** 데이터 소스의 표현식을`ORDERBY("Query", Vendor, Vendor.AccountNum)` 에서 `ORDERBY("InMemory", Vendor, Vendor.AccountNum)`로 변경하십시오. 많은 양의 데이터가 있는 테이블(트랜잭션 테이블)의 표현식은 변경하지 않는 것이 좋습니다. 모든 기록을 가져오고 필요한 기록의 순서가 메모리에서 수행되기 때문입니다. 따라서 이 방법은 성능이 저하될 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

[모든 항목 ER 함수](er-functions-list-allitems.md)

[ALLITEMSQUERY ER 함수](er-functions-list-allitemsquery.md)

[INT64VALUE ER 함수](er-functions-conversion-int64value.md)

[INTVALUE ER 함수](er-functions-conversion-intvalue.md)

[필터 ER 함수](er-functions-list-filter.md)

[WHERE ER 함수](er-functions-list-where.md)

[JOIN 데이터 소스를 사용하여 ER 모델 매핑의 여러 애플리케이션 테이블에서 데이터 가져오기](er-join-data-sources.md)

[ER 형식의 실행을 추적하여 성능 문제 해결](trace-execution-er-troubleshoot-perf.md)

[비즈니스 문서 관리 개요](er-business-document-management.md)

[생성된 보고서에서 Word 콘텐츠 제어 억제](er-design-configuration-word-suppress-controls.md)

[단일 모델 루트에 대한 여러 파생 매핑 관리](er-multiple-model-mappings.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
