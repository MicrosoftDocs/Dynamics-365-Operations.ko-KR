---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 6월 11일)
description: 이 항목에서는 2020년 6월 11일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 06/16/2020
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
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f7e8f2b158f3d3274fee87f94c69c599380f2e2c06cf0bd2284f963d46d81c02
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451915"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 6월 11일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 문서에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3316에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 LCS의 지원 번호를 나타냅니다.

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a>간소화된 직원 양식 때문에 하위 양식 닫기(X) 버튼이 작동을 멈춤(442369)

새 **작업자** 양식이 활성화되면 자식 양식의 닫기(**X**) 버튼이 때때로 작동하지 않았습니다. 이 문제는 간헐적이었습니다. 양식을 나갔다가 다시 돌아오면 양식을 닫을 수 있습니다. 예를 들어 왼쪽에서 메뉴 항목을 선택하고 **작업자** 양식으로 다시 이동하면 닫을 수 있습니다. 이번 주 릴리스는 이 문제를 수정합니다. 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a>작업자 개인 연락처 엔터티가 부모 관계 유형의 개인 연락처를 내보내지 않음

이번 릴리스에서 **작업자 개인 연락처 사람** 엔터티는 모든 관계 유형을 내보냅니다.

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a>HcmPositionWorkerAssignmentV2Entity는 기본적으로 Ceridian 급여 통합 패키지의 일부여야 함(448506)

이 변경으로 **HcmPositionWorkerAssignmentV2Entity** 가 Ceridian 급여 통합 패키지에 포함됩니다.

## <a name="in-preview"></a>미리 보기

## <a name="database-logging"></a>데이터베이스 로깅

데이터베이스 로깅 기능을 사용하면 모니터링할 테이블과 필드를 결정할 수 있습니다. 또한 변경 추적을 트리거할 이벤트를 결정할 수 있습니다. 데이터베이스 로깅 기능을 사용하여 시간 경과에 따른 이러한 변경을 확인합니다. 자세한 내용은 [데이터베이스 로깅 구성 및 관리](hr-admin-database-logging.md)를 참조하세요.

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

## <a name="new-platform-capabilities"></a>새 플랫폼 기능 

개인 설정을 사용하여 필드를 필수 항목으로 만들 수 있습니다. 이 기능을 사용하려면 **저장된 보기** 를 활성화해야 합니다.

## <a name="configure-the-name-of-employee-self-service"></a>직원 셀프 서비스의 이름 구성

Human Resources 매개 변수에서 직원 셀프 서비스 작업 영역의 이름을 셀프 서비스로 업데이트하는 새 옵션을 사용할 수 있습니다. 

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]