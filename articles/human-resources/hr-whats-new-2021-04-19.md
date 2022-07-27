---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 4월 19일)
description: 이 항목에서는 2021년 4월 19일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 04/19/2021
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
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fadad34be31f6522654bc3af47a4f71695dcc5fea7f0b3e760ff26d79d88eb4c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451882"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-19-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 4월 19일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4113에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 플랫폼 업데이트 10.0.17(41) | -- | [금융 및 운영 앱 버전 10.0.17의 플랫폼 업데이트(2021년 4월)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md) |
| 복리후생 관리 양식의 사용자 지정 필드 지원 | [복리후생 관리의 사용자 지정 필드 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management)| [혜택 관리 개요](hr-benefits-management-overview.md)|

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 552164 | **직원 셀프 서비스 > 열린 과정** 의 **저장된 보기** 가 의제가 포함된 과정에서 작동하지 않음 | 저장된 보기가 열린 과정(ESS)에서 사용되고 과정 중 하나에 의제가 첨부된 경우 보기에 해당 과정에 대한 여러 줄이 더는 표시되지 않습니다 |
| 560614 | **복리후생 > 생활 이벤트 옵션** 도구 설명 설명서와 코드 동작이 불일치를 보여줌. | 올바른 동작을 보여주도록 **생활 이벤트 옵션** 의 도구 설명을 업데이트했습니다. |
| 560616 | 작업자 복리후생 계획에서 **복리후생 > 생활 이벤트 옵션** 을 편집할 수 있지만 변경이 영향을 받지 않음. | 도구 설명 설명서에 따라 종속 옵션을 기반으로 활성화 또는 비활성화하도록 생활 이벤트 옵션 스위치의 동작이 업데이트되었습니다. |
| 565054 | **고급 액세스** 가 켜져 있으면 **고용되지 않은 근로자** 목록 내용을 볼 수 없음. | 이 릴리스는 **고급 액세스** 가 켜져 있을 때 시스템 관리자만 **고용되지 않은 작업자** 목록의 내용을 볼 수 있는 문제를 수정합니다. 이 수정 사항은 보안 변경 사항이므로 기능 관리에서 선택해야 합니다. 기능이 켜져 있으면 고급 액세스가 켜져 있어도 양식에 액세스할 수 있는 역할에 콘텐츠가 표시됩니다. 자세한 내용은 [고용되지 않은 작업자](hr-personnel-workers-without-employment.md)를 참조하세요. |
| 570586 | 모든 휴가 계획에서 해당 작업자에 대한 최신 거래 전에 고용이 종료되면 휴가 요청 유효성 검사가 실패함. | 고용 종료 후 직원 휴가 거래 기반의 휴가 요청 유효성 검사가 실패하지 않습니다.|
| 570783 | Human Resources 공유 매개 변수에서 회사 간 휴가를 활성화 및 비활성화하면 단일 회사에 고용된 직원이 휴가 요청에서 보는 내용이 변경됨. | 단일 회사에 고용된 직원은 매개 변수가 활성화 또는 비활성화된 경우 휴가 요청에 변경 사항이 없습니다. |
| 572343 | 회사 간 휴가 보기 기능이 활성화된 경우 필수 사유 코드가 표시되지 않음. | 회사 간 휴가 보기 기능이 활성화된 경우 이제 사유 코드가 제대로 표시됩니다. |
| 573676 | **복리후생 관리 > 연결 > 복리후생 계획** 에 **기간** 을 추가할 수 없음. | 기존 **복리후생** 양식에 **기간** 을 추가하거나 업데이트할 수 없는 버그를 수정했습니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 휴가 및 부재 워크플로 환경 개선 사항 | [휴가 및 부재 워크플로 환경 개선 사항](https://go.microsoft.com/fwlink/?linkid=2147528) | [휴가 요청](hr-employee-self-service-request-time-off.md)|
| 간소화된 급여 통합 활성화(급여 통합 API) | [급여 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [급여 통합 API](hr-admin-integration-payroll-api-introduction.md)|

## <a name="coming-soon"></a>업데이트 예정

| 기능 | 세부 정보 |
| --- | --- |
| 관리자가 직원을 위해 입력한 기술은 워크플로에서 자동 승인될 수 있음 | 업데이트 예정. |
| 플랫폼 업데이트 10.0.18(42) | 플랫폼 업데이트 10.0.18은 2021년 5월 17일 서비스 릴리스와 함께 출시될 예정입니다. 자세한 내용은 [금융 및 운영 앱 버전 10.0.18의 플랫폼 업데이트(2021년 5월)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18)를 참조하세요. |
| 복리후생 관리 자격 규칙의 사용자 지정 필드 지원  | [자격 처리에 사용자 지정 필드 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
