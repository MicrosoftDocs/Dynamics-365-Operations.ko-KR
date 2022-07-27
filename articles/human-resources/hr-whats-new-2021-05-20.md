---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 5월 20일)
description: 이 항목에서는 2021년 5월 20일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 05/20/2021
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
ms.search.validFrom: 2021-05-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4519e90e19d0652f855999d1a73ca64777b53b53465d6065987afc1cf2494187
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451885"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-20-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 5월 20일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4189에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 플랫폼 업데이트 10.0.18(42) | -- | [금융 및 운영 앱 버전 10.0.18의 플랫폼 업데이트(2021년 5월)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18) |
| Microsoft Teams용 Human Resources 앱은 이제 반일 지정 및 날짜 분할 기능을 지원합니다 | -- | [Teams에서 휴가 요청 관리](/dynamics365/human-resources/hr-teams-leave-app#create-a-new-request) |

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 583776 | 직원을 휴가 계획에 대량 등록하면 중복 레코드 오류가 발생함 | 이 버그는 최신 릴리스로 수정되었으며 대량 휴가 계획 등록이 정상적으로 처리될 것입니다. |
| 582263 | 한 번에 모든 작업자에 대해 생활 이벤트 처리를 실행할 수 없음 | 생활 이벤트 처리에서 **작업자** 필드를 비워 두면 모든 작업자가 처리됩니다. |
| 558383 | 기본 수혜자가 선택되지 않은 경우 기본 수혜자가 100%로 표시되지 않음 | 버그가 수정되어 사용자가 기본 수혜자 토글만 선택하면 됩니다.|
| 509404 | 부서 인원 분석이 부서 간 직원 이동을 고려하지 않음 |부서 간 직원 이동을 포함하도록 분석이 업데이트되었습니다|
| 579420 | 그리드의 열 고정 기능을 아직 사용할 수 없어야 함 | Human Resources에서 사용할 수 없는 **그리드의 열 고정** 기능이 기능 관리에서 사용 가능한 것으로 나열되었습니다. 해당 기능이 활성화할 기능 목록에서 제거되었습니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 복리후생 관리 자격 규칙의 사용자 지정 필드 지원 | [자격 처리에 사용자 지정 필드 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[자격 규칙 구성](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 휴가 및 부재 워크플로 환경 개선 사항 | [휴가 및 부재 워크플로 환경 개선 사항](https://go.microsoft.com/fwlink/?linkid=2147528) | [휴가 요청](hr-employee-self-service-request-time-off.md)|
| 간소화된 급여 통합 활성화(급여 통합 API) | [급여 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [급여 통합 API](hr-admin-integration-payroll-api-introduction.md)|
| 휴가 적립 거래 감사 | - | [휴가 적립 거래 감사](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>업데이트 예정

| 기능 | 세부 정보 |
| --- | --- |
|  부재 관리자가 휴가를 관리할 수 있도록 활성화 | [부재 관리자가 휴가를 관리할 수 있도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
