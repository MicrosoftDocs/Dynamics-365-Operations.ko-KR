---
title: Dataverse 테이블
description: Microsoft Dynamics 365 Human Resources는 Dataverse를 사용하여 확장성 및 통합 시나리오를 지원합니다.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6774fad3543d80d04faacf5960c8037f1734f084
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452272"
---
# <a name="dataverse-tables"></a>Dataverse 테이블


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources는 Dataverse를 사용하여 확장성 및 통합 시나리오를 지원합니다.

> [!NOTE]
> Human Resources 엔터티는 Dataverse 테이블에 해당합니다. Dataverse(이전의 Common Data Service) 및 용어 업데이트에 대한 자세한 내용은 [Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)을 참조하세요.

다음과 같은 Dataverse 테이블을 Human Resources 엔터티 기반으로 사용할 수 있습니다.

## <a name="benefit-tables"></a>복리후생 테이블

| 이름 | 테이블 |
| --- | --- |
| 혜택 계산 빈도 | cdm_benefitcalculationfrequency |
| 혜택 계산 빈도 급여 기간 | cdm_benefitcalculationfrequencypayperiod |
| 혜택 계산 비율 | cdm_benefitcalculationrate |
| 혜택 계산 비율 세부 정보 | cdm_benefitcalculationratedetail |
| 혜택 옵션 | cdm_benefitoption |
| 혜택 계획 | cdm_benefitplan(사용자 지정 필드 지원용으로 활성화되지 않음) |
| 혜택 유형 | cdm_benefittype |

## <a name="business-process-tasks-tables"></a>비즈니스 프로세스 작업 테이블

| 이름 | 테이블 |
| --- | --- |
| 비즈니스 프로세스 캘린더 | cdm_businessprocesscalendar |
| 비즈니스 프로세스 그룹 할당 | cdm_businessprocessgroupassignment |
| 비즈니스 프로세스 라이브러리 작업 그룹 | cdm_businessprocesslibrarytaskgroup |
| 비즈니스 프로세스 단계 | cdm_businessprocessstage |
| 검사 목록 템플릿 헤더 | cdm_businessprocesstemplateheader |
| 검사 목록 템플릿 작업 | cdm_businessprocesstemplatetask |

## <a name="compensation-tables"></a>보상 테이블

| 이름 | 테이블 |
| --- | --- |
| 보상 고정 계획 | cdm_compensationfixedplan |
| 보상 그리드 | cdm_compensationgrid |
| 보상 수준 | cdm_compensationlevel |
| 보상 지급 빈도 | cdm_compensationpayfrequency |
| 보상 참조 지점 설정 | cdm_compensationreferencepointsetup |
| 보상 참조 지점 설정 라인 | cdm_compensationreferencepointsetupline |
| 보상 지역 | cdm_compensationregion |
| 보상 구조 | cdm_compensationstructure |
| 보상 가변 계획 | cdm_compensationvariableplan |
| 보상 가변 계획 수준 | cdm_compensationvariableplanlevel |
| 보상 가변 계획 유형 | cdm_compensationvariableplantype |
| 고정 보상 이벤트 | cdm_fixedcompensationevent |
| 귀속 확정 규칙 | cdm_vestingrule |
| 작업자 고정 보상 | cdm_workerfixedcompensation |

## <a name="organization-tables"></a>조직 테이블

| 이름 | 테이블 |
| --- | --- |
| 부서 | cdm_department |
| 고용 | cdm_employment |
| 회사 | cdm_company |
| 직무 | cdm_job |
| 직무 기능 | cdm_jobfunction |
| 직무 직위 | cdm_jobposition |
| 직위 유형 | cdm_positiontype |
| 직위 작업자 배정 | cdm_positionworkerassignmentmap |
| 직무 직위 차원 | cdm_jobpositiondimension|
| 직무 유형 | cdm_jobtype |
| 언어 | cdm_language |
| 제목 | cdm_title |

> [!NOTE]
> **직위 유형**, **직위 작업자 할당** 및 **고용** 에 대한 재무 차원은 Dataverse에 대한 단방향 통합을 제공합니다. 재무 차원 업데이트는 현재 Dataverse에서 Human Resources로 동기화할 수 없습니다. 

## <a name="leave-and-absence-tables"></a>휴가 및 휴직 테이블

| 이름 | 테이블 |
| --- | --- |
| 휴가 은행 거래 | cdm_leavebanktransaction |
| 휴가 등록 | cdm_leaveenrollment |
| 휴가 계획 | cdm_leaveplan |
| 휴직 요청 | cdm_leaverequest |
| 휴가 요청 세부 정보 | cdm_leaverequestdetail |
| 휴가 유형 | cdm_leavetype |
| 휴가 유형 이유 코드 | cdm_leavetypereasoncode |

## <a name="payroll-tables"></a>급여 테이블

| 이름 | 테이블 |
| --- | --- |
| 급여 주기 | cdm_paycycle |
| 급여 기간 | cdm_payperiod |
| 급여 소득 코드 | cdm_payrollearningcode |
| 은행 계좌 지급 | cdm_bankaccountdisbursement |
| 세금 지역 | cdm_taxregion |

## <a name="worker-tables"></a>작업자 테이블

| 이름 | 테이블 |
| --- | --- |
| 작업자 | cdm_worker |
| 작업자 주소 | cdm_workeraddress |
| 작업자 개인 세부 정보 | cdm_workerpersonaldetail |
| 작업자 개인 ID 번호 | cdm_workerpersonidentificationnumber |
| 작업자 개인 ID 유형 | cdm_workerpersonidentificationtype |
| 작업 캘린더 | cdm_workcalendar |
| 작업 캘린더 날짜 | cdm_workcalendarday |
| 작업 캘린더 공휴일 |cdm_workcalendarholiday |
| 작업 캘린더 공휴일 행 | cdm_workcalendarholidayline |
| 작업 캘린더 시간 간격 | cdm_workcalendartimeinterval(사용자 지정 필드 지원용으로 활성화되지 않음) |
| 작업자 은행 계좌 | cdm_workerbankaccount |

## <a name="worker-setup-tables"></a>작업자 설정 테이블

| 이름 | 테이블 |
| --- | --- |
| 베테랑 상태 | cdm_veteranstatus |
| 민족적 혈통 | cdm_ethnicorigin |
| 이유 코드 | cdm_reasoncode |
| 개인 ID 발급 기관 | cdm_personidentificationissuingagency |

## <a name="competency-tables"></a>역량 표

| 이름 | 테이블 |
| --- | --- |
| 기술 유형 | cdm_skilltype |

## <a name="table-relationship-models"></a>테이블 관계 모델

### <a name="worker"></a>작업자

![작업자.](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>직무 및 직무 직위

![직무 및 직무 직위.](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>복리후생

![복리후생.](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>보상

![보상.](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>휴가

![휴가.](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>작업 일정

![작업 일정.](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>참고 항목

[데이터 통합 기술 선택](hr-admin-integration-choose-technology.md)<br>
[Dataverse 통합 구성](hr-admin-integration-common-data-service.md)<br>
[Dataverse 가상 테이블 구성](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Human Resources 가상 테이블 FAQ](hr-admin-virtual-entity-faq.md)<br>
[Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)<br>
[용어 업데이트](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
