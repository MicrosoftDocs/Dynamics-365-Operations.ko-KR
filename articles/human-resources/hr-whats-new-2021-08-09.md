---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 8월 9일)
description: 이 항목에서는 2021년 8월 9일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 08/09/2021
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
ms.search.validFrom: 2021-08-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f515b614aedce3d58994bf21104ada25702a71e
ms.sourcegitcommit: fc19ee0aba2a6174fef305d151f1eb23ca6c0346
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2021
ms.locfileid: "8451933"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-9-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 8월 9일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Microsoft Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4393에 적용된 변경 사항.

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 | 설명 |
| --- | --- | --- |
| 558385 | 기본 피지명자에 대해 **피지명자 자동 선택** 옵션이 켜져 있으면 기본 피지명자가 선택되지 않음. | 이 문제는 이제 수정되었습니다. **Human Resources 공유 매개 변수** 페이지의 **피지명자 자동 선택** 옵션이 켜져 있는 경우 적격 계획에서 여러 기본 피지명자가 자동으로 선택됩니다. |
| 589617 | **휴가** 페이지에서 특정 회사에 대한 접근이 제한된 경우 **구매 가능** 및 **판매 가능** 잔액이 비어 있음. | 이 문제는 이제 수정되었습니다. **휴가** 페이지에서 특정 회사에 대한 접근이 제한된 경우 **구매 가능** 및 **판매 가능** 잔액이 올바르게 표시됩니다. |

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
