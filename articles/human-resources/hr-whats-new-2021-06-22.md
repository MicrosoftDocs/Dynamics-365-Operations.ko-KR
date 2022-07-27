---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 6월 22일)
description: 이 항목에서는 2021년 6월 22일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 897c25df96017c5be1ae789027d178ca6b3ccc0410b4f65c7d2557b39e840134
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451894"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-22-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 6월 22일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4258에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 고용되지 않은 작업자에게 알림 기능 - 고급 액세스가 켜져 있고 기능 관리에서 **고용되지 않은 모든 작업자 보기** 기능이 비활성화된 경우 고용되지 않은 작업자 양식에 배너가 표시됩니다. 배너는 사용자에게 **고용되지 않은 모든 작업자 보기** 기능을 켜도록 안내합니다. | 해당 없음| [고용되지 않은 작업자](/dynamics365/human-resources/hr-personnel-workers-without-employment)|
| 복리후생 관리 자격 규칙의 사용자 지정 필드 지원 | [자격 처리에 사용자 지정 필드 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[자격 규칙 구성](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| 휴가 적립 거래 감사 | 해당 없음 | [휴가 적립 거래 감사](hr-leave-and-absence-accrue.md)|
| 휴가 및 부재 워크플로 환경 개선 사항 | [휴가 및 부재 워크플로 환경 개선 사항](https://go.microsoft.com/fwlink/?linkid=2147528) | [휴가 요청](hr-employee-self-service-request-time-off.md)|

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 583052 | 피드백을 받는 사용자가 받은 피드백을 편집할 수 있음 | 성과 분개장에 피드백을 받는 직원이 **외부 링크 추가** 를 선택하면 양식이 편집 가능하게 되어 직원이 받은 성과 피드백을 편집할 수 있습니다. |
| 522281 | 보상 관리의 보상 구조 타일에서 직원 수를 선택하면 잘못된 결과가 나타남| 보상 작업 영역에서 보상 계획으로 드릴다운할 때 이제 직원 수가 정확하게 표시됩니다. |
| 580683 | 직원 및 관리자 역할에 할당된 사용자는 메모를 첨부하거나 성과 분개장을 업데이트할 수 없음 | 직원 및 관리자 역할에 할당된 사용자는 메모를 첨부하거나 성과 분개장을 업데이트할 수 없습니다. 사용자에게 "성과 분개장 항목(HcmPerfJournal)에 레코드를 생성할 수 없습니다. 보안 정책 권한이 거부되었습니다." 오류가 표시됩니다. |
| 583077 | 휴가 및 부재 회사 일정에 직원의 생일이 잘못된 날짜로 표시됨 | 사용자는 휴가 및 부재 회사 일정에서 직원의 정확한 생을 볼 수 있습니다. |
| 586996 | 회사 간 휴가 보기 기능으로 인해 액세스가 단일 회사로 제한될 때 잔액이 비어 있음 | 회사 간 휴가 보기가 활성화된 경우 사용자는 직원의 미래 휴가 잔액을 올바르게 볼 수 있습니다. |
| 581014 | 회사 간 휴가 및 부재 보기를 활성화하면 미래 잔액을 볼 때 오류가 발생함 | 회사 간 휴가 보기가 활성화된 상태에서 사용자가 미래의 휴가 잔액을 볼 때 오류가 수정되었습니다. |
| 509404 | 부서 인원 분석이 부서 간 직원 이동을 고려하지 않음. | 직원이 한 부서에서 다른 부서로 이동할 때 현재 연도에 직위 세부 정보가 만료된 경우 부서 인원 데이터에 직원이 전환된 이전 부서가 반영되지 않습니다. |
| 584851 | 복리후생 크레딧 비례 배분 규칙 "없음"이 크레딧을 제공하지 않음 |변동 크레딧 비례 배분 규칙 "없음"으로 인해 직원은 고용된 시기와 관계없이 복리후생 기간 0크레딧을 받았습니다. 직원이 복리후생 기간이 시작되기 전에 채용되면 전체 플렉스 크레딧을 받고 기간이 시작된 후 채용되면 크레딧을 전혀 받지 않도록 수정되었습니다. |
| 584897 | '기본 외부 기능 사용' 의무를 복제하면 오류가 발생함 | '기본 외부 기능 사용' 의무를 복제하려고 하면 사용자에게 "식별자가 UserDefinedAppHostDialogView인 개체를 찾을 수 없습니다."라는 오류가 표시됩니다. |
| 575692 | 보류 중인 작업자에 대해서는 휴가 및 부재 적립을 사용할 수 없음 | **간소화된 직원 입력** 이 활성화된 경우 미래 고용에 대해 휴가 및 부재 적립을 실행할 수 있습니다. |
| 580110 | 급여 통합에 회사를 추가하면 옵션이 프로젝트를 새로 고치지 않도록 설정된 경우에도 모든 엔터티를 사용하도록 통합이 재설정됨 | 고객이 급여 통합을 위해 엔터티를 제거했거나 데이터 프로젝트를 변경했으며 프로젝트 자동 새로 고침을 방지하도록 옵션이 설정된 경우 통합에 새 회사를 추가하면 설정이 무시되고 프로젝트가 새로 고쳐집니다.  |
| 584518 |복리후생 등록 처리 성능 문제 | 이 버그는 레거시 복리후생 등록 프로세스의 성능 문제를 해결했습니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 간소화된 급여 통합 활성화(급여 통합 API) | [급여 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [급여 통합 API](hr-admin-integration-payroll-api-introduction.md)|


## <a name="coming-soon"></a>업데이트 예정

| 기능 | 세부 정보 |
| --- | --- |
| 플랫폼 업데이트 10.0.19(43) | 플랫폼 업데이트 10.0.19는 2021년 6월 28일 서비스 릴리스와 함께 출시될 예정입니다. 자세한 내용은 [금융 및 운영 앱 버전 10.0.19의 플랫폼 업데이트(2021년 6월)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19)를 참조하세요. |
|  서비스 기간(연) 표시 토글 | 이 기능은 **간소화된 직원 입력** 양식과 **피플** 양식에 표시된 근속 기간을 계산하기 위해 다른 날짜를 사용하는 옵션을 제공합니다.  Human Resources 매개 변수에서 사용할 수 있습니다. |
|  부재 관리자가 휴가를 관리할 수 있도록 활성화 | [부재 관리자가 휴가를 관리할 수 있도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |
|  특정 휴가 유형에 대한 첨부 파일 강제 | 이 기능을 사용하면 관리자가 특정 휴가 유형에 대한 휴가 요청을 제출할 때 첨부 파일을 추가하도록 강제할 수 있습니다. |
|  휴가 유형별 휴가 단위 구성 | 이 기능으로 관리자는 각 휴가 유형에 대해 휴가 단위(시간 또는 일)를 구성할 수 있습니다.  |
| 직원을 지불 준비됨으로 표시하도록 활성화 | [직원을 지불 준비됨으로 표시하도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) |

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
