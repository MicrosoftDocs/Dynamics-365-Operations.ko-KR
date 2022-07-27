---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 5월 28일)
description: 이 항목에서는 2020년 5월 28일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 05/28/2020
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 624201841b512b01daf94d13e3d9fe7c381f5c11b328d57e22fbd73e1066bf88
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451900"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 5월 28일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3287에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 LCS의 지원 번호를 나타냅니다.

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a>휴가 계획당 여러 유형을 활성화하면 LeaveRequest 엔터티가 작동하지 않음(447498)

이 변경으로 이제 여러 휴가 유형을 활성화할 때 발생하는 오류를 수정하는 데 **LeaveEnrollmentV2Entity** 를 사용할 수 있습니다.

## <a name="batch-contention-reduction-feature-preview-446619"></a>일괄 경합 감소 기능(미리 보기)(446619)

이 기능을 활성화하면 작업을 선택하고 작업을 완료하는 동안 일괄 처리 프레임워크 테이블에서 차단이 감소합니다.

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a>작업자를 저장하는 동안 업데이트 충돌 때문에 피플에서 레코드를 편집할 수 없음(427915)

이 변경은 새 작업자 추가, 주소 정보 업데이트 및 언어 기본 설정 변경 시 오류를 수정합니다. 이 고유한 시나리오에서는 레코드를 업데이트할 수 없다는 오류가 표시됩니다. 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a>승인된 휴가 요청에 첨부 파일을 추가하여 다시 제출할 수 없음(425407)

이 변경으로 승인된 휴가 요청에 첨부할 수 있습니다.

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a>사용자는 직원에 대한 보상을 다른 법인 양식으로 입력할 수 있음(409529)

이 변경은 보상 옵션을 비활성화하여 잘못된 법인에 실수로 보상 레코드를 입력하지 않도록 합니다.

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a>직원을 이전할 때 작업자 직위 할당 날짜가 직위 기간 이전인 경우 오류가 발생함(429402)

이 시나리오에서 직원을 전환할 때 발생하는 오류 메시지가 문제를 수정하는 데 필요한 변경을 더 잘 설명하도록 업데이트되었습니다.

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a>직원 셀프 서비스 복리후생 등록의 첨부 파일 기능
 
이제 직원이 등록하는 각 계획에 복리후생 등록 프로세스 중에 첨부 파일을 추가할 수 있습니다. 그런 다음 **작업자 등록 복리후생** 양식에서 첨부 파일을 볼 수 있습니다.

## <a name="in-preview"></a>미리 보기

## <a name="human-resources-application-in-teams"></a>Teams의 Human Resources 애플리케이션

직원은 Microsoft Teams 내에서 휴가를 보고 요청할 수 있습니다. 봇과 상호 작용하여 휴가 요청을 만들 수 있습니다. 자세한 내용은 [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)을 참조하세요. 

## <a name="leave-suspension"></a>휴가 일시 중단

Human Resources에서 직원의 휴가 및 부재를 일시 중단할 수 있습니다. 휴가를 일시 중단하면 선택한 휴가 유형에 대한 휴가 적립이 중지됩니다. 휴가 적립이 처리된 후 일시 중단이 발생한 경우 휴가를 일시 중단하면 직원의 휴가 잔액에 비례하여 조정됩니다. 자세한 내용은 [휴가 일시 중단](hr-leave-and-absence-suspend-leave.md)을 참조하세요.

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>적립 일시 중단을 표시하도록 사용자 환경 업데이트(429550)

이제 사용자 환경에 계획에 대한 적립 일시 중단이 표시됩니다.

## <a name="coming-soon"></a>업데이트 예정

## <a name="database-logging-in-preview-in-june"></a>데이터베이스 로깅(6월 미리 보기)

데이터베이스 로깅 기능을 사용하면 모니터링할 테이블과 필드를 결정할 수 있습니다. 또한 변경 추적을 트리거할 이벤트를 결정할 수 있습니다. 조회 기능으로 시간 경과에 따른 이러한 변경 사항을 확인할 수 있습니다.

## <a name="buy-and-sell-leave-in-preview-june-1"></a>휴가 구매 및 판매(6월 1일 미리 보기)

일부 조직에서는 직원이 휴가를 구매하거나 판매할 수 있는 복리후생을 제공합니다. 이 프로세스는 종종 수동으로 관리됩니다. 이 기능은 HR 부서의 정책과 요청을 관리하는 더 자동화된 방법을 제공하고 휴가 관리 프로세스를 간소화하면서 실수를 제거하는 데 도움이 됩니다. 자세한 내용은 다음을 참조하세요.

- [휴가 구매 및 판매 정책 관리](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [휴가 구매 및 판매](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>복리후생 관리를 위한 DMF(Data Management Framework) 엔터티
 
복리후생 관리 엔터티가 릴리스되고 있습니다. DMF 엔터티를 사용하면 데이터 가져오기 및 내보내기로 복리후생 관리를 쉽게 구성할 수 있습니다. 데이터를 이동하기 위한 복리후생 관리 템플릿도 제공됩니다. 템플릿은 데이터 종속성을 존중하기 위해 순차적인 방식으로 데이터를 내보내고 가져옵니다.

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a>적립 일시 중단에 사유 코드 추가(6월 1일)

적립 일시 중단에 사유 코드가 추가되었습니다.

## <a name="carry-forward-rules-june-1"></a>이월 규칙(6월 1일)

이월 조정이 이전되는 이월 잔액에 대해 이월 휴가 유형을 지정할 수 있습니다. 예를 들어 직원이 10일을 이월한 경우 해당 10일에 대해 다른 휴가 유형을 선택할 수 있습니다. 자세한 내용은 [휴가 및 부재 매개 유형 구성](hr-leave-and-absence-types.md)을 참조하세요.

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a>지정된 휴가 유형에 대한 휴가 적립 일시 중단(6월 1일)

이 릴리스에서 HR은 무급 휴가를 위한 입력한 휴가 요청이 있는 직원의 휴가 적립을 일시 중단하는 규칙을 만들 수 있습니다. 무급 휴가는 한 유형일 수 있지만 반드시 그래야 하는 것은 아닙니다. 다른 휴가 유형에 따라 휴가를 일시 중단할 수 있습니다.

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a>DMF 엔터티를 적립 일시 중단에 사용할 수 있음(6월 1일)

이제 DMF 엔터티를 적립 일시 중단에 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]