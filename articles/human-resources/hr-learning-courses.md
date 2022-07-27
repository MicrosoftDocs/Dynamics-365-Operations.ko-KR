---
title: 교육 과정 설정
description: Human Resources 관리자와 운영자는 과정 기능을 사용하여 근로자에게 제공되는 교육에 대한 정보를 유지할 수 있습니다.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c66459a044419535d66875cddac7eb73af744ca7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452263"
---
# <a name="set-up-training-courses"></a>교육 과정 설정


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Human Resources 관리자와 운영자는 과정 기능을 사용하여 근로자에게 제공되는 교육에 대한 정보를 유지할 수 있습니다.

##  <a name="set-up-prerequisites"></a>전제 조건 설정

과정을 만들기 전에 다음 정보를 준비하고 설정해야 합니다.
-   **과정 유형**

다음 정보는 과정에 지정할 수 있는 선택적 정보입니다. 과정에 대해 이 정보를 입력할 것을 알고 있다면 과정 레코드를 만들기 전에 이 정보를 설정해야 합니다.
-   **강의실 그룹**
-   **과정 그룹**
-   **과정 위치**
-   **강의실**
-   **강사**

## <a name="course-types"></a>과정 유형
과정 유형을 사용하여 과정의 구조나 내용에 따라 과정을 분류할 수 있습니다. **과정 유형** 페이지에서 과정 유형을 만들 수 있습니다. 과정 레코드를 생성할 때 과정 유형을 선택해야 합니다.

## <a name="course-setup-type"></a>과정 설정 유형
다음 표에는 과정의 세 가지 설정 유형이 나와 있습니다. 설정 유형은 과정의 구조를 결정합니다.

<table>
<thead>
<tr class="header">
<th>설정 유형</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>표준</strong></td>
<td>일일 의제가 없는 과정의 경우 이 유형을 선택합니다. 이것은 새 과정을 만들 때 기본 설정 유형입니다.</td>
</tr>
<tr class="even">
<td><strong>의제</strong></td>
<td>여러 날에 걸쳐 진행되는 과정의 각 날짜에 대한 세부 정보를 계획하려면 이 유형을 선택합니다.</td>
</tr>
<tr class="odd">
<td><strong>의제 + 세션</strong></td>
<td>더 복잡한 과정의 경우 이 유형을 선택합니다. 예를 들어 과정의 의제를 트랙과 세션으로 나눌 수 있습니다.
<ul>
<li><strong>트랙</strong> – 트랙은 과정의 특정 주제 영역입니다.</li>
<li><strong>세션</strong> – 세션은 트랙을 나누고 트랙과 관련된 특정 프로세스 또는 기술을 식별하는 데 도움이 됩니다.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a>과정 작업
각 과정에 대해 다음 작업을 완료할 수 있습니다.
- 참가자 등록
- 등록 마감일 지정
- 최소 및 최대 참가자 수 정의
- 과정 위치 및 강의실 할당
- 과정 참가자에게 호텔 추천
- 과정 설명을 만든 다음 **직원 셀프 서비스** 에 광고할 수 있음

  >**참고** 등록한 사람이 없는 경우에만 과정을 삭제할 수 있습니다. 

## <a name="course-statuses"></a>과정 상태
다음 표에는 가능한 과정 상태와 과정이 특정 상태일 때 완료할 수 있는 작업이 나열되어 있습니다.

<table>
<thead>
<tr class="header">
<th>상태</th>
<th>작업</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>생성됨</strong></td>
<td><ul>
<li>과정 정보를 입력하고 수정합니다.</li>
<li>작업자가 과정에 등록할 수 있도록 과정 상태를 <strong>열림</strong>으로 변경합니다.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>열림</strong></td>
<td><ul>
<li>과정 참가자를 등록합니다.</li>
<li>과정에서 참가자를 제거합니다.</li>
<li>과정 참가자를 확인합니다.</li>
<li>과정 상태를 <strong>닫힘</strong> 또는 <strong>취소됨</strong>으로 변경합니다.</li>
<li>상태가 <strong>확인됨</strong>인 참가자를 위한 설문지를 계획합니다.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>닫힘</strong></td>
<td>과정을 재개할 수 있습니다.</td>
</tr>
<tr class="even">
<td><strong>취소됨</strong></td>
<td>과정을 재개할 수 있습니다.</td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a>과정 참가자
과정 참가자는 교육 과정 또는 이벤트에 참여하는 작업자입니다. 열린 강좌에만 참가 등록할 수 있습니다. 과정에 등록할 수 있는 최소 및 최대 참가자 수는 **과정** 페이지의 **일반** 빠른 탭에서 정의됩니다.

## <a name="workflow"></a>워크플로

**직원 셀프 서비스** 페이지를 통해 과정에 등록한 직원은 승인을 위해 워크플로를 통해 등록을 라우팅할 수 있습니다. **과정** 페이지의 **일반** 빠른 탭에서 과정에 워크플로를 할당할 수 있습니다.







[!INCLUDE[footer-include](../includes/footer-banner.md)]
