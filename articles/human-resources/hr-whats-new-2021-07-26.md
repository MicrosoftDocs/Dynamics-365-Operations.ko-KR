---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 7월 26일)
description: 이 항목에서는 2021년 7월 26일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 07/12/2021
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
ms.search.validFrom: 2021-07-26
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 810511c42cd690579d8c8b6ebcc17b0cf7fcb9eb2b999822dc2226fabd127cc6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451906"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-26-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 7월 26일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4384에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 플랫폼 업데이트 10.0.20 | -- | [금융 및 운영 앱 버전 10.0.20의 플랫폼 업데이트(2021년 8월)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20) |

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 600422 | 지불 준비를 위한 급여 주소 확인에 실패함. | 유효성 검사가 업데이트되어 '급여 거주지 위치' 유형의 주소와 '급여 근무 위치' 유형의 주소가 하나만 필요합니다. |
| 601226 | 데이터 통합 문제: 급여 통합 내보내기 프로젝트에 전체 푸시 옵션이 없음 | Ceridian DayForce에 대한 급여 통합에 전체 푸시 대신 증분 푸시를 수행했습니다. Ceridian은 항상 전체 새로 고침이 필요합니다. 이 문제는 이제 수정되었으며 데이터 내보내기 프로젝트의 엔터티가 더는 증분 푸시로 전환되지 않습니다. |
| 602272 | 직원 셀프 서비스 작업 영역에 추가된 타일이 이제 없으며 더는 타일을 추가할 수 없음 | 직원 셀프 서비스의 개인 설정 문제를 수정했습니다. 보기에 새 타일을 추가할 수 있으며 기존 개인 설정이 사용자에게 표시됩니다 |
| 600711 | 하루 전체 휴가 요청에 대해 반일 지정 선택 필드가 활성화됨 | 이 문제는 이제 수정되었으며 직원이 반일 지정이 활성화된 휴가 유형을 선택하고 금액 값으로 반일을 선택한 경우에만 반일 지정 필드가 활성화됩니다 |
| 602208 | 적립 비율 단위에 일이 아닌 시간이 표시됨 | 이 문제는 이제 수정되었습니다. **휴가** 양식은 **적립 비율** 열에 정확한 휴가 단위(시간 또는 일)를 표시합니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 간소화된 급여 통합 활성화(급여 통합 API) | [급여 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [급여 통합 API](hr-admin-integration-payroll-api-introduction.md)|
|  부재 관리자가 휴가를 관리할 수 있도록 활성화 | [부재 관리자가 휴가를 관리할 수 있도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | 이번 릴리스에서는 부재 관리자 작업 영역 보기를 업데이트하고 있습니다. 자세한 내용은 [부재 관리자 역할 구성](https://go.microsoft.com/fwlink/?linkid=2168107)을 참조하세요.|
|  휴가 유형별 첨부 파일 요구 사항 구성 | [휴가 유형별 첨부 파일 요구 사항 구성](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[휴가 및 휴직 유형 구성](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  휴가 유형별 휴가 단위 구성 | [휴가 유형별 휴가 단위 구성](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[휴가 및 휴직 유형 구성](https://go.microsoft.com/fwlink/?linkid=2168215)|
| 직원을 지불 준비됨으로 표시하도록 활성화 | [직원을 지불 준비됨으로 표시하도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [지불 준비됨](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>업데이트 예정

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
