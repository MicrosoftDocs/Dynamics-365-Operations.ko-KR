---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 4월 3일)
description: 이 항목에서는 2020년 4월 3일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 04/03/2020
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
ms.search.validFrom: 2020-04-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f5f52b2e6bf646f6dd53acfd2928682e84e78fb
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452059"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-3-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 4월 3일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 문서에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3111에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 Lifecycle Services(LCS) 지원 번호를 나타냅니다.

## <a name="features-that-are-generally-available-the-week-of-april-6"></a>4월 6일 주간에 정식으로 제공될 기능

- **휴가 및 부재 기능** - 자세한 내용은 [휴가 및 부재 개요](hr-leave-and-absence-overview.md)를 참조하세요.

- **복리후생 관리 기능** - 자세한 내용은 [복리후생 관리 개요](hr-benefits-management-overview.md)를 참조하세요.

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>Human Resources 환경 제한은 이제 업데이트된 라이선스를 기반으로 함(394595)

LCS의 프로젝트당 환경 수 제한이 변경되었습니다. 이전 제한은 두 개의 환경이었습니다. LCS에서 Human Resources에 대해 생성할 수 있는 프로덕션 및 샌드박스 환경의 수 제한은 이제 업데이트된 라이선스에 기반을 둡니다. 이제 구매한 라이선스 수에 따라 LCS 프로젝트별로 필요한 만큼 많은 환경을 만들 수 있습니다. 고객은 2020년 2월 1일에 업데이트된 새로운 라이선스로 추가 환경을 구매할 수 있습니다. 추가 환경을 위한 라이선스 요구 사항에 대한 자세한 내용은 [Dynamics 365 라이선스 가이드](https://dynamics.microsoft.com/pricing/#HumanResources)를 참조하세요.
 
## <a name="error-when-trying-to-delete-a-questionnaire-428603"></a>설문지를 삭제하는 동안 오류가 발생함(428603)

이번 주 업데이트는 설문지를 삭제하려고 할 때 다음 오류가 표시되는 문제를 수정합니다.

불균형한 X++ TTSBEGIN/TTSCOMMIT 쌍이 감지되었습니다.

## <a name="performance-journal-and-professional-certificates-security-issue-428499"></a>실적 분개장 및 전문 자격증 보안 문제(428499)

이 변경으로 인해 액세스 권한이 있는 회사를 바탕으로 성과 분개장과 전문 자격증의 가시성이 제한됩니다. 

## <a name="the-abbreviation-for-quebec-and-manitoba-387510"></a>퀘벡 및 매니토바의 약어(387510)

매니토바 및 퀘벡에 올바른 약어를 반영하도록 시작 데이터가 업데이트되었습니다.

## <a name="new-entities-available-in-data-management-framework"></a>Data Management Framework에서 사용할 수 있는 새 엔터티

이제 다음 엔터티를 사용할 수 있습니다. 엔터티 목록에 이러한 엔터티가 표시되지 않으면 **프레임워크 매개 변수 > 엔터티 설정 > 엔터티 목록 새로 고침** 의 **엔터티 새로 고침** 을 사용하세요.

 - 휴가 및 부재 거래 V2
 - 휴가 및 부재 등록 V2
 - 휴가 및 부재 계획 계층 V2
 - 휴가 및 부재 계획 V2

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>이제 Dataverse 솔루션에서 다음 변경 사항을 사용할 수 있습니다.

| 설명 | 변경 |
| --- | --- |
| **직무/직위** 엔터티 변경됨 | <ul><li>**보상 지역** 추가됨</li>|
| **직무 직위 차원** 엔터티 추가됨 | <ul><li>**재무 차원** 추가됨</li>
| **작업자** 엔터티 변경됨 | <ul><li>**이름 시퀀스** 추가됨</li><li>**재택 근무** 추가됨</li><li>**언어** 추가됨</li><li>**선임 날짜** 추가됨</li><li>**기념일** 추가됨</li><li>**원래 채용 날짜** 추가됨</li></ul> |
| **고용** 엔터티 변경됨 | <ul><li>**재무 차원** 추가됨</li><li>**해고 사유** 추가됨</li><li>**전환 날짜** 에서 **해고 날짜** 로 이름이 변경됨</li><li>**수습 날짜** 추가됨</li></ul> |
| **작업자 주소** 엔터티 변경됨 | <ul><li>**나머지 주소** 추가됨</li><li>**주소란 1**, **주소란 2** 및 **주소란 3** 이 지원 중단으로 표시됨</li></ul> |
| 새로운 변동 보상 설정 엔터티 | <ul><li>**보상 변동 계획 유형**</li><li>**보상 변동 계획**</li><li>**귀속 확정 규칙**</li><li>**보상 가변 계획 수준**</li></ul> |
| 새 **작업자 일정 고용** 엔터티 | <ul><li>**작업 일정 엔터티** 추가됨</li></ul> |
| 새 **급여 직위 세부 정보** 엔터티 | <ul><li>**급여 직위 세부 정보** 추가됨</li></ul> |
| 새로운 **직함** 엔터티 | <ul><li>**직함** 추가됨</li></ul>새로운 **직함** 엔터티는 Dataverse에 포함되지만 현재 **직무 직위** 또는 **직무** 엔터티에서 참조되지 않습니다. |

> [!NOTE]
> 직위와 고용 모두에 대한 재무 차원은 Human Resources에서 Dataverse로의 업데이트를 위한 일방향 통합을 제공합니다. 재무 차원 업데이트는 현재 Dataverse에서 Human Resources로 동기화할 수 없습니다.

앞으로 몇 주 동안 이러한 엔터티 변경 사항을 모든 환경에서 사용할 수 있습니다. Human Resources를 위한 최신 Dataverse 솔루션을 수동으로 설치하려면 다음을 수행하세요.

1.  [Power Platform 관리 센터](https://admin.powerplatform.microsoft.com)로 이동합니다.

2.  **환경** 을 선택합니다.

3.  업그레이드하려는 환경을 찾습니다. 환경은 Human Resources의 **정보** 양식에 있는 **Dataverse 정보** 섹션의 **환경 이름** 과 일치해야 합니다.

4.  환경 세부 정보를 보려면 환경을 선택합니다.

5.  상단의 작업 표시줄에서 **솔루션 관리** 를 선택합니다. 새 브라우저 창이 열리고 환경의 컨텍스트에서 **Dynamics 365 관리 센터** 로 이동합니다.

6.  **솔루션** 목록에서 **Dynamics 365 Human Resources 앵커** 를 선택합니다.

7.  **업그레이드** 를 선택하여 최신 솔루션을 적용합니다.

## <a name="in-preview"></a>미리 보기

## <a name="leave-suspension"></a>휴가 일시 중단

Human Resources에서 직원의 휴가 및 부재를 일시 중단할 수 있습니다. 휴가를 일시 중단하면 선택한 휴가 유형에 대한 휴가 적립이 중지됩니다. 휴가 적립이 처리된 후 일시 중단이 발생한 경우 휴가를 일시 중단하면 직원의 휴가 잔액에 비례하여 조정됩니다. 자세한 내용은 [휴가 일시 중단](hr-leave-and-absence-suspend-leave.md)을 참조하세요.

## <a name="carry-forward-rules"></a>이월 규칙

이월 조정이 이전되는 이월 잔액에 대해 이월 휴가 유형을 지정할 수 있습니다. 예를 들어 직원이 10일을 이월한 경우 해당 10일에 대해 다른 휴가 유형을 선택할 수 있습니다. 자세한 내용은 [휴가 및 부재 매개 유형 구성](hr-leave-and-absence-types.md)을 참조하세요.

## <a name="coming-soon"></a>업데이트 예정

## <a name="new-production-release-cadence"></a>새로운 프로덕션 릴리스 주기

4월부터 Human Resources의 릴리스 주기가 주간 업데이트에서 격주 업데이트로 변경됩니다. 안전한 배포 관행을 유지하고 높은 수준의 서비스 안정성과 신뢰성을 유지하기 위해 모든 지역에 서비스 업데이트를 배포하는 프로세스는 2주 동안 롤아웃됩니다. 프로세스의 각 단계에서 성공적인 배포를 확인하기 위해 추가 테스트와 모니터링이 배치됩니다. 릴리스 주기에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

## <a name="known-issues"></a>알려진 문제

## <a name="employment-detail-entity"></a>고용 세부 정보 엔터티

**고용 세부 정보** 엔터티가 **지급 빈도**, **고용 범주 ID**, **고용 유형**, **고용 유형 ID** 및 **복리후생 고용 상태** 필드를 포함하도록 업데이트되었습니다. 이 필드의 설정 데이터는 기능 관리에서 활성화된 복리후생 관리에 의존합니다. 가져오는 동안 오류가 발생하므로 **고용 세부 정보** 엔터티에서 이러한 필드를 채우거나 업데이트하면 안 됩니다.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>일부 환경에서 SharePoint 미리 보기가 작동하지 않음

SharePoint에 저장된 문서의 문서 미리 보기가 작동하지 않는 경우 다음 절차를 시도하세요.

1. 관리 사용자 계정에 사용자 레코드와 연결된 이메일이 있는지 확인합니다. 이 정보는 **사용자** 페이지에서 볼 수 있습니다. 이메일이 설정되지 않은 경우 OData Excel 추가 기능으로 이메일 및 공급자를 추가해야 합니다. 기본적으로 이메일 주소는 Excel 디자인에 표시되지 않습니다. Excel 디자인을 편집하고 모든 필드를 추가하고 적용하고 새로 고쳐야 합니다. 이러한 단계를 완료하면 관리자 계정을 업데이트할 수 있습니다.

2. 관리자 계정에 이메일 계정을 연결한 후에는 관리자 자격 증명으로 Human Resources에 로그인합니다.

3. 문서 미리 보기를 시작하려면 SharePoint의 첨부 파일에 액세스합니다.

4. 첨부 파일에 대한 액세스 권한이 있는 다른 사용자 계정으로 로그인하고 미리 보기가 정상적으로 작동하는지 확인합니다.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]