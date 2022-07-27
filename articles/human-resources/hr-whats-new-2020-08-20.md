---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 8월 20일)
description: 이 항목에서는 2020년 8월 20일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a97997212a090f141c7280f7e48fd116a1f31481
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452026"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 8월 20일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3478에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 Lifecycle Services(LCS) 지원 번호를 나타냅니다.

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a>피플 작업 영역의 카드에 예정된 휴가 및 보류 중인 휴가 정보 표시

보류 중인 휴가 요청과 예정된 휴가 요청 옵션은 이제 **피플** 작업 영역의 휴가 및 부재 카드에서 사용할 수 있습니다.

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a>직원 셀프 서비스의 직원 역할에 대한 비공개 필드가 기본적으로 예가 아님(477106)

직원이 직원 셀프 서비스의 **개인 정보** 페이지를 통해 새 주소 기록을 추가할 때 **비공개** 필드가 이제 기본적으로 **예** 로 설정됩니다. 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a>인사 관리의 채용할 후보자 빠른 탭에 후보자 수가 잘못 표시됨(470110)

이제 **인사 관리** 페이지에 채용할 후보자 수가 정확하게 표시됩니다. 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a>적립이 0으로 설정된 경우 해고된 직원의 병가를 입력할 수 없음(446195)

이제 미래에 해고되고 적립이 0으로 설정된 직원에 대해서도 휴가 거래가 허용됩니다. 휴가 거래는 직원의 퇴직 날짜까지 입력할 수 있습니다. 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a>새 작업자 양식에 사용자 지정 필드를 추가하면 휴가 관리를 위한 작업 창의 필드가 비활성화됨(473314)

사용자 지정 필드가 새 **작업자** 양식에 추가된 경우 **휴가 관리** 의 새 **작업자** 양식의 작업 창 옵션이 더는 비활성화되지 않습니다.

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a>코멘트 남기기 필드를 필수로 설정해도 코멘트를 입력하지 않고 휴가 요청을 제출할 수 있음(473543)

코멘트 필드는 이제 필수 항목이 될 수 있으며 휴가 요청이 이 설정을 준수합니다. 필수 필드는 미리 보기 기능입니다.

### <a name="dmf-entity-available-for-accrual-suspensions"></a>DMF 엔터티를 적립 일시 중단에 사용할 수 있음

이제 DMF 엔터티를 적립 일시 중단에 사용할 수 있습니다.

## <a name="in-preview"></a>미리 보기

### <a name="mandatory-fields"></a>필수 필드

Human Resources 개인 설정 기능을 사용하여 필드를 필수 항목으로 만들 수 있습니다. 이 기능에는 **저장된 보기** 가 필요합니다. 저장된 보기에 대한 자세한 내용은 다음을 참조하세요.

- Dynamics 365 2020 릴리스 웨이브 2 계획의 [저장된 보기 - 일반 공급](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)
- [저장된 보기를 완전히 활용하는 양식 작성](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Teams의 Human Resources 애플리케이션

직원은 Microsoft Teams 내에서 휴가를 보고 요청할 수 있습니다. 봇과 상호 작용하여 휴가 요청을 만들 수 있습니다. 자세한 내용은 다음을 참조하세요.

- Dynamics 365 2020 릴리스 웨이브 1 계획의 [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams)
- [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)

## <a name="coming-soon"></a>업데이트 예정

### <a name="human-resources-app-in-teams-preview-features"></a>Teams의 Human Resources 미리 보기 기능
 
-  **알림**: 휴가 요청의 제출자 및 승인자는 Teams의 Human Resources 앱에서 알림을 받습니다. 승인자는 휴가 요청을 승인하거나 거부할 수 있으며 요청이 승인 또는 거부되면 제출자에게 통지됩니다.
 
- **관리자 휴가 일정**: 관리자는 일정 보기에서 직속 부하 직원의 승인된 휴가와 보류 중인 휴가를 볼 수 있게 됩니다. 이 보기를 사용하면 팀 구성원이 언제 자리를 비우는지 쉽게 이해할 수 있습니다.

### <a name="checklist-entities-included-in-dataverse"></a>Dataverse에 포함된 검사 목록 엔터티

온보딩, 오프보딩, 전환 및 비즈니스 프로세스에 대한 검사 목록 엔터티는 Dataverse에서 곧 사용할 수 있습니다.

## <a name="known-issues"></a>알려진 문제

**기능 관리** 작업 영역이 정식으로 제공되는 기능을 미리 보기 기능으로 비활성화하여 표시할 수 있습니다. 다음은 정식으로 제공되는 기능 중 잘못된 상태로 표시되는 기능의 목록입니다. 

- 복리후생 관리
- 사례 관리
- 데이터베이스 로깅(감사)
- 단일 회사 또는 단일 계획의 휴가 적립
- 휴가 및 부재 적립 일시 중지
- 잔액 조정 사유 코드 및 설명
- 휴가 구매 및 판매
- 휴가 및 부재 일정
- 휴가 이월 규칙
- 휴가 적립 감사
- 휴가 적립 삭제
- 휴가 적립 반올림
- 단일 휴가 계획에 여러 휴가 유형 구성
- 휴가 업데이트 개선 사항
- 적립에 직원의 FTE 사용
- 회사 간 보상 보기
- 성과 검토 인쇄
- 휴가 적립 공휴일 수정

### <a name="benefit-plan-employee-entity"></a>복리후생 계획 직원 엔터티 

최근에 **BenefitsPlanEmployee** 엔터티에 관한 두 가지 문제를 발견했습니다. 작업자 등록을 가져올 때 **보장 코드** 및 **계획 유형 코드** 가 잘못 설정됩니다. 이 문제로 인해 직원 복리후생 계획이 직원 셀프 서비스의 **근로자 복리후생 계획** 양식과 **공개 등록** 양식에 잘못 표시됩니다. 이 문제는 직원 셀프 서비스에서 계획을 선택하는 데도 영향을 줄 수 있습니다. 현재는 해결 방법이 없습니다. 이 문제를 우선 순위가 높은 수정으로 처리하고 다음 릴리스에서 수정을 출시할 예정입니다.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]