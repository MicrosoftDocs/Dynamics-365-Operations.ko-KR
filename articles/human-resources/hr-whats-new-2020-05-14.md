---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 5월 14일)
description: 이 항목에서는 2020년 5월 14일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 05/14/2020
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
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb4693f3c856e7abcc39cbd658183d01ec98a066
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452065"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 5월 14일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3244에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 Lifecycle Services(LCS) 지원 번호를 나타냅니다.

## <a name="platform-changes"></a>플랫폼 변경

이번 주 릴리스에는 플랫폼 변경 사항이 포함되어 있습니다. 자세한 내용은 [금융 및 운영 앱 버전 10.0.10의 플랫폼 업데이트(2020년 5월)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34.md)를 참조하세요. 이 릴리스에는 버그 수정과 저장된 보기 변경 사항이 포함되어 있습니다.
 
## <a name="ensure-dataverse-picklists-are-consistent-with-leave-enums-436343"></a>Dataverse 선택 목록이 휴가 열거형과 일치함(436343)

이제 Dataverse 선택 목록이 휴가 열거형과 일치합니다.

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a>사용자가 요청 금액에 따라 휴가 요청 워크플로를 구성할 수 있도록 허용(300044)

사용자는 요청 금액에 따라 휴가 요청 워크플로를 구성할 수 있습니다.
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a>고급 보안이 활성화된 경우 새 작업자 양식이 보기 메뉴를 통해 데이터를 노출함(403185)

이 릴리스는 고급 액세스가 활성화되고 다른 회사의 작업자가 액세스할 수 있는 경우 법인 전체의 작업자 보기 기능을 수정합니다.

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a>계획 또는 회사에 대한 휴가 적립 운영 허용(318844)

이 변경으로 회사 또는 계획에 대한 휴가 적립을 운영할 수 있습니다.
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a>등록된 작업자 양식에 직위의 정규직 상응(FTE) 표시(414658)

작업자 직위의 FTE 값은 휴가 유형에서 FTE 옵션이 활성화된 경우 작업자의 적립 비율을 결정합니다. 이 필드는 이제 **등록된 작업자** 양식과 **대량 등록** 대화 상자에 포함됩니다.

## <a name="add-leave-balance-expiration-batch-job-431266"></a>휴가 잔액 만료 일괄 작업 추가(431266)

이제 매일 실행되는 새 일괄 작업을 사용할 수 있습니다. 이 일괄 작업은 만료 날짜가 최신이 되면 남은 휴가 잔액을 줄입니다.

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a>작업자 개인 연락처 사람 엔터티를 사용하여 직원의 개인 연락처를 내보내면 부모 관계 유형이 있는 개인 연락처를 내보내지 않음(345893)

DMF의 **작업자 개인 연락처 차람** 데이터 엔터티(DMF의 **HcmPersonalContactPersonEntity** 및 OData의 **PersonalContactPerson**)는 **부모** 관계 유형이 있는 개인 연락처를 내보내지 못합니다. 이 변경 후에 생성된 개인 연락처에 대해서는 이 문제가 수정되었습니다. 기존의 **부모** 유형 개인 연락처는 이후 릴리스에서 수정됩니다.

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a>휴가 및 부재로 표시되고 간소화된 직원 양식이 활성화된 경우 사유 코드가 다양한 시나리오에 표시됨(434163)

이 변경은 간소화된 직원 입력을 활성화할 때 사유 코드를 휴가 및 부재 코드로만 제한합니다.

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a>미리 보기 기능인 직원에게 미래의 휴가 계획을 할당하면 오류가 표시됨(433555)

이 변경은 휴가 계획에 두 가지 휴가 유형이 할당되어 있고 직원을 할당하려고 할 때 오류를 수정합니다.

## <a name="getting-started-banner-appears-for-all-users-441731"></a>모든 사용자에게 시작 배너가 나타남(441731)

이 변경으로 시스템 관리자 또는 데이터 관리 관리자가 아닌 사용자에게는 시작 배너가 숨겨집니다. 

## <a name="the-dataverse-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a>Dataverse 작업자 주소 엔터티가 Human Resources의 날짜 시간 유효 날짜와 다르게 작동함(425071)

이 변경은 주소 날짜를 기준으로 특정 시나리오에서 주소 정보를 일치된 상태로 유지합니다.

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a>승인된 휴가 요청에 첨부 파일을 추가할 수 없음(425407)

이번 주 릴리스에서는 휴가 요청을 변경하지 않고 승인된 휴가 요청에 첨부 파일을 추가할 수 있습니다.

## <a name="in-preview"></a>미리 보기

## <a name="leave-suspension"></a>휴가 일시 중단

Human Resources에서 직원의 휴가 및 부재를 일시 중단할 수 있습니다. 휴가를 일시 중단하면 선택한 휴가 유형에 대한 휴가 적립이 중지됩니다. 휴가 적립이 처리된 후 일시 중단이 발생한 경우 휴가를 일시 중단하면 직원의 휴가 잔액에 비례하여 조정됩니다. 자세한 내용은 [휴가 일시 중단](hr-leave-and-absence-suspend-leave.md)을 참조하세요.

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>적립 일시 중단을 표시하도록 사용자 환경 업데이트(429550)

이제 사용자 환경에 계획에 대한 적립 일시 중단이 표시됩니다.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>지정된 휴가 유형에 대한 휴가 적립 일시 중단(272447)

이 릴리스에서 HR은 무급 휴가를 위한 입력한 휴가 요청이 있는 직원의 휴가 적립을 일시 중단하는 규칙을 만들 수 있습니다. 무급 휴가는 한 유형일 수 있지만 반드시 그래야 하는 것은 아닙니다. 다른 휴가 유형에 따라 휴가를 일시 중단할 수 있습니다.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>DMF 엔터티를 적립 일시 중단에 사용할 수 있음(429549)

이제 DMF 엔터티를 적립 일시 중단에 사용할 수 있습니다.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>적립 일시 중단에 사유 코드 추가(429547)

적립 일시 중단에 사유 코드가 추가되었습니다.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Human Resources 매개 변수에서 휴가 및 부재 매개 변수로 전환 시작

이 릴리스에서는 Human Resources 매개 변수를 휴가 및 부재 매개 변수와 결합하기 시작합니다.

## <a name="carry-forward-rules"></a>이월 규칙

이월 조정이 이전되는 이월 잔액에 대해 이월 휴가 유형을 지정할 수 있습니다. 예를 들어 직원이 10일을 이월한 경우 해당 10일에 대해 다른 휴가 유형을 선택할 수 있습니다. 자세한 내용은 [휴가 및 부재 매개 유형 구성](hr-leave-and-absence-types.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]