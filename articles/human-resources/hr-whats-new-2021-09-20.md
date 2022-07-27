---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 9월 20일)
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources(2021년 9월 20일)의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 09/20/2021
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
ms.search.validFrom: 2021-09-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3f4fc4768f8c96678b216709f78af6d3ddfd4132
ms.sourcegitcommit: ba8ca42e43e1a5251cbbd6ddb292566164d735dd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2021
ms.locfileid: "8451960"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-20-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 9월 20일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Microsoft Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4464에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
|---|---|---|
| 간소화된 급여 통합 활성화(급여 통합 API) | [급여 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [급여 통합 API](hr-admin-integration-payroll-api-introduction.md) |
| 직원을 지불 준비됨으로 표시하도록 활성화 | [직원을 지불 준비됨으로 표시하도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [지불 준비됨](/dynamics365/human-resources/hr-compensation-payroll) |

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 | 설명 |
|---|---|---|
| 619774 | 주소 설명 편집이 Dataverse와 실시간으로 동기화되지 않음. | 작업자 주소에 대한 설명을 편집할 때 업데이트된 설명이 Dataverse와 실시간으로 동기화되지 않습니다. 업데이트를 보내기 위해 **물류 위치** 테이블의 구독이 업데이트되었습니다. |
| 614603| **작업자 인사 조치** 매개 변수가 선택되지 않은 경우 **작업자** 페이지에 오류가 발생함. | 새 직원을 채용하거나 **직원** 페이지로 이동할 때 **인사 조치** 가 꺼져 있어도 "**인사 조치 유형** 필드를 입력해야 합니다."라는 오류가 표시됩니다. |
| 615367 | **승인된 휴가** 탭에 경고가 표시되고 잘못 표시됨. | **휴가 유형별 휴가 단위 구성** 기능을 활성화하기 전에 휴가 단위가 **일** 로 설정된 경우 **승인된 휴가** 탭에 잘못된 경고와 잘못된 열이 표시됩니다. |


## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 방법에 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
|---|---|---|
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 자격의 사용자 지정 필드 |[자격 처리의 사용자 지정 필드 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [자격 처리에 사용자 지정 필드 사용](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |
| 복리후생 명세서 |[복리후생 명세서](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) | [복리후생 명세서](hr-benefits-statement.md) |

### <a name="benefits-statement-known-issues"></a>복리후생 명세서 알려진 문제

| 문제 | 설명 |
|---|---|
| 복리후생 명세서에 대한 **직원 셀프 서비스** 의 **보고서 매개 변수** 페이지가 잘못됨. | **직원 셀프 서비스** 의 **복리후생 명세서** 로 이동하면 **보고서 매개 변수** 페이지에 **포함할 레코드** 및 **백그라운드에서 실행** 빠른 탭이 표시됩니다.  이러한 항목은 제거해야 합니다. |
| 마감 및 미래 기간은 복리후생 명세서의 **보고서 매개 변수** 페이지에 표시됩니다. | **복리후생 명세서 보고서** 대상 페이지로 이동할 때 사용자는 마감되었거나 미래 날짜인 복리후생 계획 기간을 선택할 수 있으며 그 결과 빈 페이지가 표시됩니다. 현재 복리후생 계획 기간만 목록에 표시돼야 합니다. |
|GER 보고 대상을 사용하여 보고서를 이메일로 보낼 때 오류가 발생함. | 복리후생 명세서는 **GER 보고 대상** 페이지 내에서 이메일 매개 변수를 사용하도록 설정할 수 있습니다. 설정을 완료하고 보고서를 인쇄하면 사용자에게 서식 오류가 표시되고 복리후생 명세서가 전송되지 않습니다.|


## <a name="coming-soon"></a>업데이트 예정

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

| 기능 | 세부 정보 |
|---|---|
| 플랫폼 업데이트 10.0.21(45) | 플랫폼 업데이트 10.0.21은 2021년 10월 4일 서비스 릴리스와 함께 출시될 예정입니다. 자세한 내용은 [금융 및 운영 앱 버전 10.0.21의 플랫폼 업데이트(2021년 10월)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21)를 참조하세요. |
|성과 분개장 확장 부하 직원 보기 | 이 기능은 다음 롤아웃에서 기본적으로 활성화됩니다. |


## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
