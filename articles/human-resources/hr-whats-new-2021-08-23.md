---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 8월 23일)
description: 이 항목에서는 2021년 8월 23일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 08/23/2021
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
ms.search.validFrom: 2021-08-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 21c9ee0206bd77a8a2ec42501d64e83077baef09
ms.sourcegitcommit: 696796ca5635863850ae9ef16fc1fb0fc46ce8f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/28/2021
ms.locfileid: "8451951"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-23-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 8월 23일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Microsoft Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4419에 적용된 변경 사항.

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 | 설명 |
| --- | --- | --- |
| 594066 | 연락처 정보를 삭제할 수 없음 | 직원의 연락처 정보 레코드 삭제를 선택하면 선택한 레코드 이외의 연락처 정보 레코드가 대신 삭제됩니다. |
| 611339 | 개인 설정을 추가하면 은행 계좌가 필터를 무시하고 첫 번째 레코드를 가져옴 | 개인 설정을 추가하면 데이터 원본 쿼리가 실행된 후 은행 계좌 목록이 개인 설정 쿼리를 실행하여 세부 정보를 보고 있는 작업자와 관계없이 쿼리가 최상위 레코드를 가져옵니다. |
| 591806 | 온보딩 기한 작업이 잘못 계산됨 | 생성된 검사 목록이 확장된 시간 범위(예: 2005년에서 2050년)의 일정을 사용하고 사용자의 기본 설정은 중부 표준시 이외의 표준 시간대를 사용하는 경우 기한이 잘못 계산됩니다. |   
| 592749 | **직원 셀프 서비스** 에 휴가 잔액이 잘못됨 | 직원이 둘 이상의 법인에 고용되어 있고 회사 간 휴가 보기가 활성화된 경우 휴가 잔액이 올바르지 않을 수 있습니다. |
| 603133 | 휴가를 요청할 때 예기치 않은 경고 | 휴가를 요청할 때 **금액** 필드보다 **반일** 필드를 먼저 채우면 예기치 않은 경고가 발생합니다. |
| 606546 | 승인된 휴가에 선택 필드가 표시되지 않음 | 승인된 휴가 요청을 여러 개 선택하는 확인란이 표시되지 않았습니다. |
| 597059 | **휴가 및 부재 회사 일정** 에 작업자가 표시되지 않음 | 적용 날짜 범위에 휴가 요청이 거부된 날짜가 포함된 경우 **휴가 및 부재 회사 달력** 에 작업자가 표시되지 않습니다. |


## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 방법에 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 간소화된 급여 통합 활성화(급여 통합 API) | [급여 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [급여 통합 API](hr-admin-integration-payroll-api-introduction.md)|
| 부재 관리자가 휴가를 관리할 수 있도록 활성화 | [부재 관리자가 휴가를 관리할 수 있도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | 이번 릴리스에서는 부재 관리자 작업 영역 보기를 업데이트하고 있습니다. 자세한 내용은 [부재 관리자 역할 구성](https://go.microsoft.com/fwlink/?linkid=2168107)을 참조하세요. |
| 휴가 유형별 첨부 파일 요구 사항 구성 | [휴가 유형별 첨부 파일 요구 사항 구성](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[휴가 및 휴직 유형 구성](https://go.microsoft.com/fwlink/?linkid=2168108)|
| 휴가 유형별 휴가 단위 구성 | [휴가 유형별 휴가 단위 구성](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[휴가 및 휴직 유형 구성](https://go.microsoft.com/fwlink/?linkid=2168215)|
| 직원을 지불 준비됨으로 표시하도록 활성화 | [직원을 지불 준비됨으로 표시하도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [지불 준비됨](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>업데이트 예정

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

| 기능 | 세부 정보 |
| --- | --- |
| 플랫폼 업데이트 10.0.21(45) | 플랫폼 업데이트 10.0.21은 2021년 10월 4일 서비스 릴리스와 함께 출시될 예정입니다. 자세한 내용은 [금융 및 운영 앱 버전 10.0.21의 플랫폼 업데이트(2021년 10월)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21)를 참조하세요. |

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
