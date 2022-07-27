---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 6월 25일)
description: 이 항목에서는 2020년 6월 23일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a89c0febbe2e4adca1508f106ffa7b84b5f14e2c
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452002"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 6월 23일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3347에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 LCS의 지원 번호를 나타냅니다.

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a>해고된 사원의 등록이 만료되면 휴가 등록 양식에서 휴가 유형, 잔액, 금액이 모두 지워짐(444867)

**휴가 유형**, **잔액** 및 **금액** 의 값은 이제 이 선택할 때 지워지지 않고 유지됩니다.

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a>새 기능(단일 회사 또는 단일 계획에 대한 휴가 적립)이 활성화된 경우 예상 잔액이 잘못됨(456553)

이제 단일 회사 또는 단일 계획에 대한 휴가 적립이 활성화된 경우 올바른 예상 잔액이 이제 표시됩니다.

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a>관계가 있는 엔터티 때문에 탐색 속성이 중복됨(456486)

이 릴리스는 여러 엔터티의 탐색 속성(관계) 문제를 수정합니다. 중복 관계가 감지되었습니다. 이러한 시나리오는 모두 수정되었습니다.
 
## <a name="cross-company-comments-on-performance-review-455536"></a>성과 검토에 대한 회사 간 코멘트(455536)

이 수정으로 이제 성과 검토에서 회사 간 코멘트를 볼 수 있습니다. 이 변경은 같은 성과 검토에 대해 다른 회사에 입력된 검토자 코멘트 보기를 수정합니다.
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a>보상 관리 데이터 표시 불일치(432562)

이제 관리자 셀프 서비스에서 보상 데이터의 일관된 보기가 유지됩니다. 작업자의 **보상 세부 정보** 로 이동하는 방법에 따라 이제 보상 데이터가 관리자에게 일관되게 표시됩니다.
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a>고정 보상 계획의 적용 날짜가 기본적으로 오늘 날짜로 설정됨(411994)

이제 보상 시작 날짜는 직원에게 할당된 직위의 시작 날짜를 기준으로 합니다.

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a>휴가 및 부재 양식 반일 지정 활성화가 양식이 열릴 때 비활성화됨(452607)

이 변경으로 **반일 지정 활성화** 는 새로운 휴가 거래가 있을 때까지 활성화됩니다. 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a>Excel을 통해 HcmDiscussionEntity에 게시할 수 없고 TotalRatingScore 필드 오류가 발생함(453899)

이제 Excel 통합 문서 디자이너에서 **HCMDiscussionEntity** 를 사용하여 **TotalRatingScore** 필드를 업데이트할 수 있습니다.

## <a name="in-preview"></a>미리 보기

## <a name="database-logging"></a>데이터베이스 로깅

데이터베이스 로깅을 사용하면 모니터링할 테이블과 필드를 결정할 수 있습니다. 또한 변경 추적을 트리거할 이벤트를 결정할 수 있습니다. 데이터베이스 로깅 기능을 사용하여 시간 경과에 따른 이러한 변경을 확인합니다. 자세한 내용은 [데이터베이스 로깅 구성 및 관리](hr-admin-database-logging.md)를 참조하세요.

## <a name="mandatory-fields"></a>필수 필드 

이제 Human Resources 개인 설정 기능을 사용하여 필드를 필수 항목으로 만들 수 있습니다. 이 기능에는 **저장된 보기** 가 필요합니다.

## <a name="human-resources-application-in-teams"></a>Teams의 Human Resources 애플리케이션

직원은 Microsoft Teams 내에서 휴가를 보고 요청할 수 있습니다. 봇과 상호 작용하여 휴가 요청을 만들 수 있습니다. 자세한 내용은 [Teams의 Human Resources 앱](./hr-admin-teams-leave-app.md)을 참조하세요. 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>복리후생 관리를 위한 DMF(Data Management Framework) 엔터티
 
복리후생 관리 엔터티가 릴리스되고 있습니다. DMF 엔터티를 사용하면 데이터 가져오기 및 내보내기로 복리후생 관리를 쉽게 구성할 수 있습니다. 데이터를 이동하기 위한 복리후생 관리 템플릿이 제공됩니다. 템플릿은 데이터 종속성을 존중하기 위해 순차적으로 데이터를 내보내고 가져옵니다.

## <a name="buy-and-sell-leave"></a>휴가 구매 및 판매 

일부 조직에서는 직원이 휴가를 구매하거나 판매할 수 있는 복리후생을 제공합니다. 이 프로세스는 종종 수동으로 관리됩니다. 이 기능은 HR 부서의 정책 및 요청 관리를 자동화합니다. 휴가 관리 프로세스를 간소화하고 실수를 제거하는 데 도움이 됩니다. 자세한 내용은 다음을 참조하세요.

- [휴가 구매 및 판매 정책 관리](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [휴가 구매 및 판매](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>단일 회사 또는 단일 계획의 휴가 적립

고객은 단일 회사 또는 단일 휴가 및 부재 계획의 적립을 처리할 수 있습니다. 이 기능은 휴가 연도 또는 휴가 적립 정책이 다른 고객을 위해 적립 프로세스를 명확하게 제공합니다. 자세한 내용은 [회사 또는 휴가 계획별 휴가 적립](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>휴가 요청에 첨부 파일 추가

승인된 휴가 요청에 첨부 파일을 추가하는 기능은 현재 COVID-19 환경에서 매우 중요합니다. 직원은 이제 이러한 첨부 파일을 추가할 수 있습니다. 또한 휴가 요청이 업데이트되는 방법에 대해 더 많은 통찰력을 얻을 수 있습니다. 자세한 내용은 [기존 요청에 첨부 파일 추가](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request)를 참조하세요.

## <a name="add-reason-code-to-accrual-suspensions"></a>적립 일시 중단에 사유 코드 추가 

적립 일시 중단에 사유 코드가 추가되었습니다.

## <a name="carry-forward-rules"></a>이월 규칙 

이월 조정이 이전되는 이월 잔액에 대해 이월 휴가 유형을 지정할 수 있습니다. 예를 들어 직원이 10일을 이월한 경우 해당 10일에 대해 다른 휴가 유형을 선택할 수 있습니다. 자세한 내용은 [휴가 및 부재 매개 유형 구성](hr-leave-and-absence-types.md)을 참조하세요.

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>지정된 휴가 유형에 대한 휴가 적립 일시 중단

무급 휴가를 위한 입력한 휴가 요청이 있는 직원의 휴가 적립을 일시 중단하는 규칙을 만들 수 있습니다. 무급 휴가는 한 유형일 수 있지만 반드시 그래야 하는 것은 아닙니다. 다른 휴가 유형에 따라 휴가를 일시 중단할 수 있습니다.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>DMF 엔터티를 적립 일시 중단에 사용할 수 있음 

이제 DMF 엔터티를 적립 일시 중단에 사용할 수 있습니다.

## <a name="coming-soon"></a>업데이트 예정

## <a name="configure-the-name-of-employee-self-service"></a>직원 셀프 서비스의 이름 구성

**Human Resources 매개 변수** 에서 직원 셀프 서비스 작업 영역의 이름을 셀프 서비스로 업데이트하는 새 옵션을 사용할 수 있습니다.

## <a name="checklist-entities-included-in-dataverse"></a>Dataverse에 포함된 검사 목록 엔터티

온보딩, 오프보딩, 전환 및 비즈니스 프로세스에 대한 검사 목록 엔터티는 Dataverse 내에서 곧 사용할 수 있습니다.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]