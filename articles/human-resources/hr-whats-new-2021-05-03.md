---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 5월 3일)
description: 이 항목에서는 2021년 5월 3일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 05/03/2021
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
ms.search.validFrom: 2021-05-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1bfbfabc8ba9c41dfd02c205755042f82387f5e09c88722e2503316bc1cf5feb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451903"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-3-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 5월 3일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4140에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 생활 이벤트가 생성될 때 정보 표시줄을 추가합니다. | - | 생활 이벤트를 만들면 정보 표시줄에 만든 생활 이벤트의 유형을 나타내는 메시지가 표시됩니다.

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 559312 |  직원에 대한 고정 보상 계획을 만들 때 수준이 표시되지 않음. |  사용자의 표준 시간대와 회사의 표준 시간대가 일치하지 않는 경우 해당 직무에 대한 보상 수준을 읽을 수 없습니다. 쿼리가 UTC 시간을 기준으로 검색하도록 업데이트되었습니다. |
| 573676  | **복리후생 계획** 양식에 새 기간을 추가할 수 없음. | **복리후생 계획** 의 **기간** 빠른 탭에 **새로 만들기** 버튼이 활성화되도록 양식을 업데이트했습니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 휴가 및 부재 워크플로 환경 개선 사항 | [휴가 및 부재 워크플로 환경 개선 사항](https://go.microsoft.com/fwlink/?linkid=2147528) | [휴가 요청](hr-employee-self-service-request-time-off.md)|
| 간소화된 급여 통합 활성화(급여 통합 API) | [급여 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [급여 통합 API](hr-admin-integration-payroll-api-introduction.md)|
| 휴가 적립 거래 감사 | - | [휴가 적립 거래 감사](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>업데이트 예정

| 기능 | 세부 정보 |
| --- | --- |
| 플랫폼 업데이트 10.0.18(42) | 플랫폼 업데이트 10.0.18은 2021년 5월 17일 서비스 릴리스와 함께 출시될 예정입니다. 자세한 내용은 [금융 및 운영 앱 버전 10.0.18의 플랫폼 업데이트(2021년 5월)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18)를 참조하세요. |
| 복리후생 관리 자격 규칙의 사용자 지정 필드 지원  | [자격 처리에 사용자 지정 필드 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
