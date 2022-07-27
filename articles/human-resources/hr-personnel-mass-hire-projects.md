---
title: 대량 채용 프로젝트
description: 이 항목에서는 인사 전문가가 여러 직위를 만들고 해당 직위에 작업자를 효율적으로 채용할 수 있는 대량 채용 프로젝트에 관해 설명합니다.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMMassHireProject, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fcfc973dc9acea624336f059d68562fa5eb41353
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452611"
---
# <a name="mass-hire-projects"></a>대량 채용 프로젝트


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



인사 전문가가 대량 채용 프로젝트로 여러 직위를 만들고 해당 직위에 작업자를 효율적으로 채용할 수 있습니다.

## <a name="overview"></a>개요

계절적 수요를 맞추기 위해 채용할 때와 같이 한 번에 많은 작업자를 채용할 때는 대량 채용 프로젝트를 사용합니다. 대량 채용 프로젝트를 만들면 직위 레코드, 작업자 레코드 및 직위에 대한 작업자 할당을 동시에 만들 수 있으므로 유용합니다. 대량 채용 프로젝트에 대한 직위를 만들 때 다음 정보를 지정할 수 있습니다.

- 만들 직위 수
- 해당 직위에 채용할 사람들의 작업자 유형
- 직위와 관련된 부서 및 직무
- 직위의 정규직 상응 값

## <a name="example"></a>예

여름에는 일반적으로 15~20명의 시간제 대학생을 고용하여 회사의 인턴십 인원을 채웁니다. 올해는 회계사 5명, 주문 처리사 5명, 계산원 5명을 고용하려고 합니다. 각 직위 기록과 작업자 기록을 별도로 만드는 대신 "여름 인턴"이라는 대량 채용 프로젝트를 하나 만듭니다. 프로젝트 시작 및 종료 날짜는 대량 채용 프로젝트를 위해 만든 직위에 대한 직위 기간 시작 날짜와 종료 날짜에 연관됩니다.

**대량 채용 프로젝트** 페이지에서 **여름 인턴** 프로젝트를 선택하고 **프로젝트 열기** 를 선택합니다. 열린 대량 채용 프로젝트에서 **직위 만들기** 를 선택하고 회계사 직위에 대한 정보를 입력합니다. 5개의 회계사 직위를 만들고 각각에 대해 동일한 정보를 사용하도록 지정할 수 있습니다. 그런 다음 **확인** 을 선택합니다. 주문 처리자와 계산원 직위에 대해 이 프로세스를 반복합니다.

인턴십 직위에 채용할 학생을 선택한 후 채용하려는 직위의 직위 세부 정보에 각 학생의 정보를 입력합니다. 모든 직위 세부 정보를 입력했으면 **대량 채용 프로젝트** 페이지에서 직위를 선택하고 **채용** 을 선택합니다. 각 직위에 대한 직위 레코드가 생성되고 작업자 레코드가 생성되어 채용한 각 사람의 올바른 직위에 할당됩니다.

## <a name="mass-hire-project-statuses"></a>대량 채용 프로젝트 상태

대량 채용 프로젝트는 다음 상태를 가질 수 있습니다.

- 생성됨
- 열림
- 닫힘

대량 채용 프로젝트의 상태를 변경하려면 **대량 채용 프로젝트** 페이지에서 **프로젝트 열기** 또는 **프로젝트 닫기** 를 선택합니다. 다음 표에는 상태에 따라 프로젝트로 수행할 수 있는 작업이 설명됩니다.

<table>
<thead>
<tr>
<th>상태</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr>
<td>생성됨</td>
<td>정보를 생성하고 수정할 수 있지만 프로젝트에 직위를 만들 수는 없습니다. 이것은 새 프로젝트의 기본 상태입니다.</td>
</tr>
<tr>
<td>열림</td>
<td>프로젝트 세부 정보를 수정하고 대량 채용 프로젝트에 직위를 만들고 해당 직위에 인력을 채용할 수 있습니다. 이것은 프로젝트의 활성 상태입니다.</td>
</tr>
<tr>
<td>닫힘</td>
<td><p>프로젝트에 직위를 추가할 수 없습니다. 대량 채용 프로젝트에 직위를 추가하려면 프로젝트를 다시 열어야 합니다. 이것은 완료된 프로젝트의 상태입니다.</p>
<p><strong>참고:</strong> 대량 채용 프로젝트를 마감하려면 프로젝트의 모든 직위 상태가 <b>생성됨</b> 또는 <b>닫힘</b>이어야 합니다.</p>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
