---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 7월 8일)
description: 이 항목에서는 2020년 7월 8일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 07/08/2020
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
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8a574436bc7762fbee722af8be2f923d18d01e5b
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451990"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 7월 8일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3382에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 LCS의 지원 번호를 나타냅니다.

## <a name="database-logging"></a>데이터베이스 로깅

데이터베이스 로깅을 사용하면 모니터링할 테이블과 필드를 결정할 수 있습니다. 또한 변경 추적을 트리거할 이벤트를 결정할 수 있습니다. 데이터베이스 로깅 기능을 사용하여 시간 경과에 따른 이러한 변경을 확인합니다. 자세한 내용은 [데이터베이스 로깅 구성 및 관리](hr-admin-database-logging.md)를 참조하세요.

## <a name="configure-the-name-of-employee-self-service"></a>직원 셀프 서비스의 이름 구성

이제 **Human Resources 매개 변수** 에서 **직원 셀프 서비스** 작업 영역의 이름을 **셀프 서비스** 로 변경할 수 있습니다. 자세한 내용은 [직원 셀프 서비스 작업 영역 이름 변경](hr-employee-self-service-workspace-name.md)을 참조하세요

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a>복리후생 관리 기간 외 공개 등록

이 릴리스에서는 직원이 등록 기간 외에 또는 생활 이벤트 없이 복리후생 공개 등록에 액세스할 수 있는 버그를 수정합니다. 따라서 직원 셀프 서비스에서 공개 등록을 시연해야 하는 경우 공개 등록 날짜를 오늘(또는 그 이전)로 조정하여 액세스할 수 있도록 해야 합니다. **복리후생 관리 > 규칙 및 옵션 기간** 에서 이 설정을 변경할 수 있습니다.

## <a name="email-employee-enrollment-confirmation"></a>직원 등록 확인 이메일

이제 직원이 복리후생 선택을 완료한 후 직원에게 이메일을 보낼 수 있습니다. 기본 메시지를 보내거나 조직 이메일 템플릿을 사용할 수 있습니다. 이러한 설정은 **Human Resource 매개 변수 > 복리후생 관리** 에 있습니다.

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a>취소된 휴가가 피플 작업 영역에 예정된 휴가로 계속 표시됨(441358)

취소된 휴가는 더는 **피플** 작업 영역의 휴가 카드에 예정된 휴가로 표시되지 않습니다.

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a>PositionV2 엔터티에서 부서 엔터티 속성을 사용할 수 없음(456486)

이제 중복 관계를 만들지 않고 부서를 추가할 수 있습니다.

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a>PayrollWorkerEnrolledBenefitDetailEntity는 퇴직 계획을 위해 계산된 필드만 사용해야 함(459779)

**PayrollWorkerEnrolledBenefitDetailEntity** 엔터티를 내보낼 때 비율 테이블을 기반으로 계산된 필드를 사용해야 하는지 또는 지원 테이블의 **ContributionAmountCur** 필드를 사용해야 하는지를 결정합니다. 데이터 엔터티에서 사용하는 논리는 애플리케이션이 일반적으로 사용하지 않는 상황에 비율 테이블을 사용합니다. 계산 비율 테이블이 없고 제품에서 고객이 이를 지정하도록 허용하지 않기 때문에 이 논리로 인해 엔터티 내보내기가 이 열에 대해 0 값을 반환합니다.
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a>인사 관리 및 직원 셀프 서비스에서 체코어 번역 혼동(400276)

이 릴리스에서 **회사 디렉터리**, **다음 등록한 과정**, **직무** 및 **직위** 의 번역이 수정되었습니다.
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a>WorkCalendarEmployment 테이블에 생성 및 수정된 시스템 필드가 활성화되어 있지 않음(460171)

생성 및 수정된 시스템 필드는 이제 Human Resources의 **WorkCalendarEmployment** 테이블에서 활성화됩니다.
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a>채용에 대한 Null 참조 예외와 미래 직원에 대한 세부 정보 추가(455475)

이 릴리스에서는 **채용 및 세부 정보 추가** 옵션을 사용하여 직원을 고용할 때 간소화된 직원 입력의 오류(null 참조)를 수정합니다.

## <a name="changes-made-in-the-dataverse-worker-entity-dont-reflect-in-human-resources-455652"></a>Dataverse 작업자 엔터티의 변경이 Human Resources에 반영되지 않음(455652)

Dataverse의 **작업자** 엔터티의 다음 필드에 대한 변경 사항이 이제 Human Resources에 나타납니다.

- **재택 근무**
- **선임 날짜**
- **기념일**
- **원래 채용 날짜**

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a>직위에 할당된 작업에 따라 올바른 보상 수준이 기본값으로 설정되지 않음(394136)

이 변경으로 **직위 세부 정보** 의 **적용 날짜** 와 **보상 계획 할당** 의 **시작 날짜** 레코드를 기반으로 올바른 보상 수준이 기본값으로 설정됩니다.

## <a name="in-preview"></a>미리 보기

## <a name="mandatory-fields"></a>필수 필드 

이제 Human Resources 개인 설정 기능을 사용하여 필드를 필수 항목으로 만들 수 있습니다. 이 기능에는 **저장된 보기** 가 필요합니다.

## <a name="human-resources-application-in-teams"></a>Teams의 Human Resources 애플리케이션

직원은 Microsoft Teams 내에서 휴가를 보고 요청할 수 있습니다. 봇과 상호 작용하여 휴가 요청을 만들 수 있습니다. 자세한 내용은 [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)을 참조하세요. 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>복리후생 관리를 위한 DMF(Data Management Framework) 엔터티
 
복리후생 관리 엔터티가 릴리스되고 있습니다. DMF 엔터티를 사용하면 데이터 가져오기 및 내보내기로 복리후생 관리를 쉽게 구성할 수 있습니다. 데이터를 이동하기 위한 복리후생 관리 템플릿이 제공됩니다. 템플릿은 데이터 종속성을 존중하기 위해 순차적으로 데이터를 내보내고 가져옵니다.

## <a name="buy-and-sell-leave"></a>휴가 구매 및 판매 

일부 조직에서는 직원이 휴가를 구매하거나 판매할 수 있는 복리후생을 제공합니다. 이 프로세스는 종종 수동으로 관리됩니다. 이 기능은 HR 부서의 정책 및 요청 관리를 자동화합니다. 휴가 관리 프로세스를 간소화하고 실수를 제거하는 데 도움이 됩니다. 자세한 내용은 다음을 참조하세요.

- [휴가 구매 및 판매 정책 관리](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [휴가 구매 및 판매](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>단일 회사 또는 단일 계획의 휴가 적립

고객은 단일 회사 또는 단일 휴가 및 부재 계획의 적립을 처리할 수 있습니다. 이 기능은 휴가 연도 또는 휴가 적립 정책이 다른 고객을 위해 적립 프로세스를 명확하게 제공합니다. 자세한 내용은 [회사 또는 휴가 계획별 휴가 적립](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>휴가 요청에 첨부 파일 추가

승인된 휴가 요청에 첨부 파일을 추가하는 기능은 현재 COVID-19 환경에서 매우 중요합니다. 직원은 이제 이러한 첨부 파일을 추가할 수 있습니다. 또한 휴가 요청이 업데이트되는 방법에 대해 더 많은 통찰력을 얻을 수 있습니다. 자세한 내용은 [기존 요청에 첨부 파일 추가](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request)를 참조하세요.

## <a name="add-reason-code-to-accrual-suspensions"></a>적립 일시 중단에 사유 코드 추가 

적립 일시 중단에 사유 코드가 추가되었습니다.

## <a name="carry-forward-rules"></a>이월 규칙 

이월 조정이 이전되는 이월 잔액에 대해 이월 휴가 유형을 지정할 수 있습니다. 예를 들어 직원이 10일을 이월한 경우 해당 10일에 대해 다른 휴가 유형을 선택할 수 있습니다. 자세한 내용은 [휴가 및 부재 매개 유형 구성](hr-leave-and-absence-types.md)을 참조하세요.

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>지정된 휴가 유형에 대한 휴가 적립 일시 중단

무급 휴가를 위한 입력한 휴가 요청이 있는 직원의 휴가 적립을 일시 중단하는 규칙을 만들 수 있습니다. 무급 휴가는 한 유형일 수 있지만 반드시 그래야 하는 것은 아닙니다. 다른 휴가 유형에 따라 휴가를 일시 중단할 수 있습니다.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>DMF 엔터티를 적립 일시 중단에 사용할 수 있음 

이제 DMF 엔터티를 적립 일시 중단에 사용할 수 있습니다.

## <a name="coming-soon"></a>업데이트 예정

## <a name="checklist-entities-included-in-dataverse"></a>Dataverse에 포함된 검사 목록 엔터티

온보딩, 오프보딩, 전환 및 비즈니스 프로세스에 대한 검사 목록 엔터티는 Dataverse에서 곧 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]