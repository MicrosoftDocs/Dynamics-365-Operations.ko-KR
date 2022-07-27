---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 3월 10일)
description: 이 항목에서는 2020년 3월 10일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 03/10/2020
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
ms.search.validFrom: 2020-03-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c6e4d93f89721bd722de523fbba7adfd2ee3f786
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452005"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-10-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 3월 10일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 문서에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.2985에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 LCS의 지원 번호를 나타냅니다.

## <a name="cant-access-skill-gap-analysis-report-394460"></a>기술 갭 분석 보고서에 액세스할 수 없음(394460)

이 보고서는 Dynamics 365 Human Resources에서 지원되지 않습니다. SSRS 보고서를 인쇄하는 메뉴 항목이 제거되었습니다.

## <a name="incorrect-message-accessing-the-getting-started-page-417950"></a>시작 페이지에 액세스할 때 잘못된 메시지가 표시됨(417950)

이 변경으로 양식에 대한 액세스 권한이 없는 경우 보안 기능이 이 메뉴 항목을 숨깁니다.

## <a name="streamlined-task-maintenance-for-employees-380538"></a>직원을 위한 간소화된 작업 유지 관리(380538)

작업자 작업 유지 관리 양식에는 온보딩, 오프보딩, 전환 및 비즈니스 프로세스 전반에 걸쳐 직원의 모든 작업이 나열됩니다. 이제 작업을 삭제, 다시 할당하거나 상태를 업데이트할 수 있습니다.

예: Benjamin Martin은 복리후생 관리자입니다. 직원 온보딩 중에 Benjamin이 새 직원의 복리후생 선택을 검토할 작업이 생성됩니다. Benjamin은 완료한 과거 작업과 완료해야 하는 미래 작업이 있습니다. Benjamin은 회사를 떠나기로 했으므로 그의 작업은 다시 할당되거나 제거되어야 합니다. 작업 유지 관리 양식(**작업자** 양식의 작업 창에 있음)을 사용하면 Benjamin의 모든 작업을 다른 작업자에게 다시 할당하거나 제거할 수 있습니다.  

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
| 새로운 **직함** 엔터티 | <ul><li>**직함** 추가됨</li></ul> 새로운 **직함** 엔터티는 Dataverse에 포함되지만 현재 **직무 직위** 또는 **직무** 엔터티에서 참조되지 않습니다. |

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

다음 미리 보기 기능을 2020년 2월 3일에 사용할 수 있습니다.

- **휴가 및 부재 미리 보기 기능** - 자세한 내용은 [휴가 및 부재 미리 보기 기능](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)을 참조하세요.

- **복리후생 관리 미리 보기 기능** - 알려진 문제를 포함한 자세한 내용은 [복리후생 관리 개요](hr-benefits-management-overview.md)를 참조하세요.

## <a name="coming-soon"></a>업데이트 예정

### <a name="platform-update-33"></a>플랫폼 업데이트 33

- 전체 페이지 앱(미리 보기) - 저장된 보기 기능을 활성화해야 하는 이 미리 보기 기능을 사용하면 대시보드를 통해 Power Apps 및 타사 앱을 전체 페이지 환경으로 추가할 수 있습니다.

- 저장된 보기(미리 보기) - 이 미리 보기 기능을 사용하면 개인 설정 하위 시스템에 크게 향상된 저장된 보기가 활성화됩니다. 이 기능을 통해 사용자는 페이지당 여러 개의 명명된 개인 설정 집합을 가질 수 있습니다. 보안 역할에 보기를 게시할 수도 있습니다.

- 최적화된 "다음 중 하나" 필터링 환경 - 이 기능으로 여러 필터 값을 더 쉽게 입력할 수 있고, 개별 또는 모든 필터 값을 제거하는 더 간단한 메커니즘이 포함되며, 더 간결하고 직관적인 필터 값의 시각화를 지원하는 최적화된 "다음 중 하나" 필터링 환경을 사용할 수 있습니다.

- 권장 필드 - 사용자는 그리드나 페이지에 필드를 추가해야 할 때가 많습니다. 사용 가능한 필드가 너무 많으면 이 작업이 어려울 수 있습니다. 이 기능을 사용하면 많은 목록을 검색할 필요 없이 시스템에서 비슷한 시나리오에서 다른 사용자가 가장 자주 추가하는 항목을 기반으로 권장 필드 집합을 표시할 수 있습니다.

- 그리드의 기본 작업 고정 - 이 기능은 열이 이동되거나 숨겨져 있는지와 관계없이 그리드의 기본 작업이 그리드의 특정 열에 연결되도록 합니다.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]