---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 8월 6일)
description: 이 항목에서는 2020년 8월 6일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 08/06/2020
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
ms.search.validFrom: 2020-08-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dbcf854330b7c5ba6ca812a5aed384584c05ce8d
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452029"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-06-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 8월 6일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3444에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 LCS의 지원 번호를 나타냅니다.

## <a name="platform-update-1001236-is-now-available"></a>이제 플랫폼 업데이트 10.0.12(36)를 사용할 수 있습니다

자세한 내용은 [금융 및 운영 앱 버전 10.0.12의 플랫폼 업데이트(2020년 8월)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-10-0-12.md)를 참조하세요.

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>복리후생 관리를 위한 DMF(Data Management Framework) 엔터티
 
복리후생 관리 엔터티가 릴리스되고 있습니다. DMF 엔터티를 사용하면 데이터 가져오기 및 내보내기로 복리후생 관리를 쉽게 구성할 수 있습니다. 데이터를 이동하기 위한 복리후생 관리 템플릿이 제공됩니다. 템플릿은 데이터 종속성을 존중하기 위해 순차적으로 데이터를 내보내고 가져옵니다. 자세한 내용은 다음을 참조하세요.

- Dynamics 365 2020 릴리스 웨이브 1 계획의 [DMF 엔터티 지원](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/dmf-entity-support)
- [데이터 관리 개요](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)


## <a name="claire-creates-a-workflow-for-buying-and-selling-leave-requests-446557"></a>Claire가 휴가 요청 구매 및 판매를 위한 워크플로를 만듦(446557)

자세한 내용은 다음을 참조하세요.

- Dynamics 365 2020 릴리스 웨이브 2 계획에서 [직원이 휴가를 구매 및 판매할 수 있도록 허용](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave)
- [휴가 구매 및 판매 정책 관리](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [휴가 구매 및 판매](./hr-employee-self-service-buy-sell-leave.md)


## <a name="worker-postal-addresses-v2-entity-has-access-across-legal-entities-with-restricted-access-459126"></a>작업자 우편 주소 V2 엔터티가 액세스가 제한된 법인 전체에 액세스할 수 있음(459126)

이번 변경으로 **작업자 우편 주소 V2** 엔터티는 사용자에게 부여된 법인 액세스 권한을 기반으로 제한합니다.

## <a name="workflow-email-hyperlink-fails-to-open-relevant-reviews-437398"></a>워크플로 이메일 하이퍼링크가 관련 검토를 열지 못함(437398)

자리 표시자를 사용하여 검토 워크플로에서 성과 검토를 열면 이제 이메일에 생성된 하이퍼링크가 선택한 레코드를 엽니다.

## <a name="new-entities-for-buying-and-selling-leave-473180"></a>휴가 구매 및 판매를 위한 신규 엔터티(473180)

이제 휴가를 사고파는 데 Data Management Framework 엔터티를 사용할 수 있습니다. 자세한 내용은 [데이터 관리 개요](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)를 참조하세요.

## <a name="when-viewing-record-information-and-using-advanced-filters-a-user-could-gain-access-to-other-employees-records-472490"></a>기록 정보를 보고 고급 필터를 사용할 때 사용자가 다른 직원의 기록에 액세스할 수 있음(472490)

이 변경으로 직원 셀프 서비스 사용자는 직원 셀프 서비스를 사용하는 동안 자신의 기록만에 액세스할 수 있습니다. 필터링 옵션을 변경하는 동안 기록 정보를 볼 때 더는 추가 데이터가 노출되지 않습니다.

## <a name="personnel-management-analytics-include-exited-worker-records-382893"></a>인사 관리 분석에 퇴사한 직원 기록이 포함됨(382893)

이 릴리스로 이제 인사 관리 분석에 활성 작업자만 포함됩니다. 
 
## <a name="unable-to-process-a-merit-increase-for-an-employee-473125"></a>직원의 성과급 인상을 처리할 수 없음(473125)

이 변경으로 새 성과급 인상에 대한 적용 날짜를 변경할 때 성과급 인상을 입력할 수 있습니다.

## <a name="review-workflow-can-be-started-more-than-once-467541"></a>검토 워크플로를 두 번 이상 시작할 수 있음(467541)

이 변경으로 성과 검토 워크플로를 한 번만 시작할 수 있습니다. 관리자의 상태에 더는 검토 시작 옵션이 표시되지 않습니다.

## <a name="leave-request-work-flow-ends-in-error-when-canceling-an-approved-leave-request-472063"></a>승인된 휴가 요청을 취소하면 휴가 요청 워크플로가 오류로 종료됨(472063)

이 릴리스에서는 승인된 휴가 요청을 취소하면 요청 상태가 더는 승인된 상태로 유지되지 않고 워크플로가 계속됩니다.

## <a name="system-suggests-exited-workers-when-creating-a-new-review-form-the-template-460624"></a>템플릿에서 새 검토를 작성할 때 시스템에서 퇴사한 작업자를 제안함(460624)

이 변경으로 템플릿에서 새 검토를 작성할 때 더는 퇴사한 작업자를 사용할 수 없습니다. 고용 날짜가 지난 직원에 대해서는 검토를 작성할 수 없습니다.

## <a name="position-hierarchy-circular-reference-detection-415879"></a>직위 계층 순환 참조 감지(415879)

이 변경으로 직위 계층 순환 참조 감지가 단일 시점으로 제한됩니다. 보고 구조에 순환 참조가 없는지 확인하기 위해 다른 날짜에 대해 순환 참조 검색을 실행할 수 있습니다.

## <a name="buy-and-sell-leave"></a>휴가 구매 및 판매 

일부 조직에서는 직원이 휴가를 구매하거나 판매할 수 있는 복리후생을 제공합니다. 이 프로세스는 종종 수동으로 관리됩니다. 이 기능은 HR 부서의 정책 및 요청 관리를 자동화합니다. 휴가 관리 프로세스를 간소화하고 실수를 제거하는 데 도움이 됩니다. 자세한 내용은 다음을 참조하세요.

- Dynamics 365 2020 릴리스 웨이브 2 계획에서 [직원이 휴가를 구매 및 판매할 수 있도록 허용](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave)
- [휴가 구매 및 판매 정책 관리](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [휴가 구매 및 판매](./hr-employee-self-service-buy-sell-leave.md)

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

## <a name="in-preview"></a>미리 보기

### <a name="mandatory-fields"></a>필수 필드

Human Resources 개인 설정 기능을 사용하여 필드를 필수 항목으로 만들 수 있습니다. 이 기능에는 **저장된 보기** 가 필요합니다. 저장된 보기에 대한 자세한 내용은 다음을 참조하세요.

- Dynamics 365 2020 릴리스 웨이브 2 계획의 [저장된 보기 - 일반 공급](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)
- [저장된 보기를 완전히 활용하는 양식 작성](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Teams의 Human Resources 애플리케이션

직원은 Microsoft Teams 내에서 휴가를 보고 요청할 수 있습니다. 봇과 상호 작용하여 휴가 요청을 만들 수 있습니다. 자세한 내용은 다음을 참조하세요.

- Dynamics 365 2020 릴리스 웨이브 1 계획의 [Microsoft Teams의 직원 휴가 및 부재 환경](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams)
- [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)

### <a name="dmf-entity-available-for-accrual-suspensions"></a>DMF 엔터티를 적립 일시 중단에 사용할 수 있음

이제 DMF 엔터티를 적립 일시 중단에 사용할 수 있습니다.

## <a name="coming-soon"></a>업데이트 예정

## <a name="checklist-entities-included-in-dataverse"></a>Dataverse에 포함된 검사 목록 엔터티

온보딩, 오프보딩, 전환 및 비즈니스 프로세스에 대한 검사 목록 엔터티는 Dataverse에서 곧 사용할 수 있습니다.

## <a name="known-issues"></a>알려진 문제

**기능 관리** 작업 영역이 정식으로 제공되는 기능을 미리 보기 기능으로 비활성화하여 표시할 수 있습니다. 다음은 정식으로 제공되는 기능 중 잘못된 상태로 표시되는 기능의 목록입니다. 

1.  복리후생 관리
2.  사례 관리
3.  데이터베이스 로깅(감사)
4.  단일 회사 또는 단일 계획의 휴가 적립
5.  휴가 및 부재 적립 일시 중지
6.  잔액 조정 사유 코드 및 설명
7.  휴가 구매 및 판매
8.  휴가 및 부재 일정
9.  휴가 이월 규칙
10. 휴가 적립 감사
11. 휴가 적립 삭제
12. 휴가 적립 반올림
13. 단일 휴가 계획에 여러 휴가 유형 구성
14. 휴가 업데이트 개선 사항
15. 적립에 직원의 FTE 사용
16. 회사 간 보상 보기
17. 성과 검토 인쇄
18. 휴가 적립 공휴일 수정

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]