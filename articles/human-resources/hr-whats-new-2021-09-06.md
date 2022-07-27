---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 9월 6일)
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources(2021년 9월 6일)의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 09/06/2021
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
ms.search.validFrom: 2021-09-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2add53b4b014cb65caacff03bf175078d2b70d8f
ms.sourcegitcommit: a73df4ddc7f8ddc9e37269c0236dc1bb9b7c7966
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2021
ms.locfileid: "8451957"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-6-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 9월 6일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Microsoft Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4443에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
|---|---|---|
| 부재 관리자가 휴가를 관리할 수 있도록 활성화 | [부재 관리자가 휴가를 관리할 수 있도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | 이번 릴리스에서는 부재 관리자 작업 영역 보기를 업데이트하고 있습니다. 자세한 내용은 [부재 관리자 역할 구성](https://go.microsoft.com/fwlink/?linkid=2168107)을 참조하세요. |
| 휴가 유형별 첨부 파일 요구 사항 구성 | [휴가 유형별 첨부 파일 요구 사항 구성](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) | [휴가 및 휴직 유형 구성](https://go.microsoft.com/fwlink/?linkid=2168108) |
| 휴가 유형별 휴가 단위 구성 | [휴가 유형별 휴가 단위 구성](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) | [휴가 및 휴직 유형 구성](https://go.microsoft.com/fwlink/?linkid=2168215) |

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 | 설명 |
|---|---|---|
| 610128 | HcmDiscussionOverallCommentEntity를 사용할 때 데이터 게시 오류 | Excel 통합 문서에서 HcmDiscussionOverralCommentEntity 엔터티로 데이터를 게시하면 "HcmTopicOverrall 유형의 데이터 원본 레코드를 찾을 수 없습니다."라는 오류가 발생합니다. |
| 589073 | EEO-1 보고서가 "비특정" 및 값이 비어 있는 **성별** 필드를 "여성" 값으로 계산함. | **성별** 필드에 **남성** 이 지정되지 않은 경우 EEO-1 보고서는 기본값 **여성** 을 생성합니다. |
| 589617 | 사용자 역할이 특정 법인으로 제한된 경우 휴가 카드 잔액, 구매 가능 및 판매 가능 잔액이 표시되지 않음. | 사용자(직원 역할)가 특정 법인으로 제한된 경우 잔액이 **휴가 잔액** 카드와 **구매 가능** 및 **판매 가능** 필드에 잔액이 올바르게 표시되지 않습니다. |
| 604310 | 사용자에게 부재 계층이 할당되지 않은 경우 부재 관리자 탭을 숨겨야 함. | 지정된 법인에서 회사 간 매개 변수가 활성화되어 있고 하나 이상의 부재 계층 구조가 사용자와 연결되어 있지 않은 한 셀프 서비스 포털에서 **부재 관리자** 탭을 숨겨야 합니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 방법에 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
|---|---|---|
| 간소화된 급여 통합 활성화(급여 통합 API) | [급여 공급자와의 간소화된 통합 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [급여 통합 API](hr-admin-integration-payroll-api-introduction.md) |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 직원을 지불 준비됨으로 표시하도록 활성화 | [직원을 지불 준비됨으로 표시하도록 활성화](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [지불 준비됨](/dynamics365/human-resources/hr-compensation-payroll) |
| 자격의 사용자 지정 필드 |[자격 처리의 사용자 지정 필드 지원](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [자격 처리에 사용자 지정 필드 사용](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |

## <a name="coming-soon"></a>업데이트 예정

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

| 기능 | 세부 정보 |
|---|---|
| 플랫폼 업데이트 10.0.21(45) | 플랫폼 업데이트 10.0.21은 2021년 10월 4일 서비스 릴리스와 함께 출시될 예정입니다. 자세한 내용은 [금융 및 운영 앱 버전 10.0.21의 플랫폼 업데이트(2021년 10월)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21)를 참조하세요. |
| 복리후생 명세서 | 사원의 현재 복리후생 선택을 보기 위한 복리후생 명세서. 자세한 내용은 릴리스 웨이브 문서에서 [복리후생 명세서](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement)를 참조하세요. |

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 2 개요](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
