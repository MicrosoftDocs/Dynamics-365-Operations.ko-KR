---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 7월 12일)
description: 이 항목에서는 2021년 7월 12일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
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
ms.search.validFrom: 2021-07-12
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4ebe5a6ae19d00b94247381c700ff21d31910fcac1968ab4f8a673f89ddd2f0f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451927"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-12-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 7월 12일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4353에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
|  서비스 기간(연) 표시 토글 | |이 기능은 **간소화된 직원 입력** 페이지와 **피플** 페이지에 표시된 근속 기간을 계산하기 위해 다른 날짜를 사용하는 옵션을 제공합니다.  [Human Resources 매개 변수](/dynamics365/human-resources/hr-setup-parameters)에서 사용할 수 있게 됩니다. |


### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 595871 | Human Resources의 정보 창에 잘못된 Dataverse 용어가 있음 | Common Data Service에서 Dataverse로 브랜드가 변경됨에 따라 Microsoft Dynamics 365 Human Resources 정보 창(**도움말 및 지원 > 정보**)에 용어가 업데이트되었습니다. |
| 598676 | 간소화된 직원 입력 양식 재정의 작업을 저장된 보기와 함께 사용하면 오류가 발생할 수 있음| **작업자** 페이지에 '간소화된 직원 입력' 기능이 켜져 있는 경우 저장된 보기에 **항상 편집용으로 열기** 가 설정되면 애플리케이션이 충돌할 수 있습니다. |
| 592344 |직위의 작업자 보상 섹션은 복리후생 관리가 활성화된 경우 읽기 전용이 됨 | 작업자 보상 정보는 레거시 복리후생 기능을 사용하여 생성됩니다.  복리후생 관리가 활성화되면 필드는 읽기 전용입니다. 복리후생 관리가 켜져 있고 HR 공유 매개 변수에서 **기존 복리후생 양식 숨기기** 가 **예** 로 설정되어 있으면 **작업자 보상** 탭이 숨겨집니다. |
| 598617 | 개인 설정을 적용하면 **HcmDiscussion** 양식 활성화 탭에서 무한 루프 발생 | 그리드 및 세부 정보 보기에 **항상 편집용으로 열기** 가 켜져 있으면 재정의된 작업 메서드에서 탭을 활성화하는 코드가 포커스를 가져야 하는 컨트롤에 대한 개인 설정과 충돌하고 무한 루프가 발생합니다. |
| 593553 | 성과 분개장의 분개장 날짜 필드가 UTC로 표시됨 | 성과 분개장의 **분개장 날짜** 필드는 시스템 날짜 설정에 정의된 시간대가 아닌 UTC 시간대로 표시되므로 일부 시간대의 경우 날짜가 정확하지 않을 수 있습니다. |
| 586930 | 성과 목표를 위한 활동을 열면 완전히 다른 기록이 열림 | 기능 관리에서 '성과 분개장 확장 보고서 보기' 기능이 활성화된 경우 **직원 셀프 서비스** 의 **내 팀** 탭에서 확장 부하 직원의 성과 목표를 선택하면 선택한 직원 대신 다른 직원의 목표가 열립니다. |
| 569959 |  HcmPositionWorkerAssignmentV2 엔터티가 작업자를 직위에 할당하지 않음 | 사용자에게 엔터티를 통한 직위 할당 레코드 추가와 게시 실패 오류가 표시됩니다. |
| 582259 | VETS 4212 보고서가 2020 양식 대신 2017 양식을 사용함 | 2020 형식으로 업데이트되었습니다.  새 형식을 로드하려면 **보고서 구성** 으로 이동하여 왼쪽 열에서 VETS-4212 보고서를 삭제하세요. **전자 보고 - 리포지토리- HR 리소스** 로 이동하고 **열기** 를 선택합니다.  **VETS-4212 PDF 인쇄물** 을 선택하고 **가져오기** 를 선택합니다.|


## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 간소화된 급여 통합 활성화(급여 통합 API) | [급여 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [급여 통합 API](hr-admin-integration-payroll-api-introduction.md)|
|  부재 관리자가 휴가를 관리할 수 있도록 활성화 | [부재 관리자가 휴가를 관리할 수 있도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | [부재 관리자 역할 구성](https://go.microsoft.com/fwlink/?linkid=2168107)|
|  휴가 유형별 첨부 파일 요구 사항 구성 | [휴가 유형별 첨부 파일 요구 사항 구성](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[휴가 및 휴직 유형 구성](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  휴가 유형별 휴가 단위 구성 | [휴가 유형별 휴가 단위 구성](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[휴가 및 휴직 유형 구성](https://go.microsoft.com/fwlink/?linkid=2168215)|
| 직원을 지불 준비됨으로 표시하도록 활성화 | [직원을 지불 준비됨으로 표시하도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [지불 준비됨](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>업데이트 예정

| 기능 | 세부 정보 |
| --- | --- |
| 플랫폼 업데이트 10.0.20(44) | 플랫폼 업데이트 10.0.20은 2021년 7월 26일 서비스 릴리스와 함께 출시될 예정입니다. 자세한 내용은 [금융 및 운영 앱 버전 10.0.20의 플랫폼 업데이트(2021년 8월)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20)를 참조하세요. |

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
