---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 2월 25일)
description: 이 항목에서는 2020년 2월 25일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 02/25/2020
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
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6f8a8795b1af59339e920281ffc46139fb9c45e2
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452011"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 2월 25일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 문서에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.2927에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 LCS의 지원 번호를 나타냅니다.

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a>사례 관리 탐색 및 DMF(Data Management Framework) 엔터티 활성화(414754)

이 미리 보기 기능을 사용하면 사례 관리 사례를 추가로 탐색할 수 있습니다. **기능 관리** 작업 영역에서 이 미리 보기 기능을 활성화할 수 있습니다. 이러한 메뉴 항목은 Dynamics 365 Human Resources의 **규정 준수** 작업 영역에 나타납니다. 이 변경으로 Human Resources는 다음에 액세스할 수 있습니다.

- 모든 사례
- 내 사례
- 내 열린 사례
- 내 지연된 사례
- 워크플로를 통해 나에게 할당된 사례

사례에 대한 이러한 새로운 보기와 함께 **사례 세부 정보** DMF 엔터티도 사용할 수 있습니다.

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a>전체 주소록에서 관계 정의 활성화(414762)

이제 전체 주소록에서 관계를 사용할 수 있습니다. 이번 주 릴리스 이전에는 **관계** 팩트 상자에 시스템 정의 관계가 표시되었습니다. 이제 전체 주소록 페이지 내에서 이러한 관계를 정의할 수 있습니다.

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a>직위에 대한 활성 보상 레코드가 있는 경우 직위를 제거할 수 있음(414568)

이 변경으로 직위를 삭제하려고 할 때 작업자가 같은 직위에 대해 활성 보상 기록이 있으면 경고가 나타납니다. 이 경우 직위를 제거하기 전에 직원 고정 보상 레코드를 업데이트해야 합니다.

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a>성과 검토 워크플로가 때때로 프로세스에 참여하지 않은 사람들의 승인을 추가함(414171)

이 변경 사항은 추가 승인 참가자가 성과 검토에 추가되는 문제를 수정합니다.

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a>새 작업자 대화 상자에서 선택하면 Dataverse에서 작업자 직위 할당이 생성되지 않음(413479)

이 변경은 새 작업자를 채용하고 신입사원을 **새 작업자** 대화 상자를 통해 직위에 할당할 때 발생하는 문제를 수정합니다. 이제 직위 할당이 Dataverse에 반영됩니다.

## <a name="coming-soon"></a>업데이트 예정

### <a name="updated-dataverse-solution"></a>업데이트된 Dataverse 솔루션

새로운 Dataverse 솔루션이 다음 변경 사항과 함께 곧 제공될 예정입니다.

| 설명 | 변경 |
| ----------------------------------------- | --- |
| **직무/직위** 엔터티 변경됨 | **보상 지역** 추가됨</br>**재무 차원** 추가됨 |
| **작업자** 엔터티 변경됨 | **이름 시퀀스** 추가됨</br>**재택 근무** 추가됨</br>**언어** 추가됨</br>**선임 날짜** 추가됨</br>**기념일** 추가됨</br>**원래 채용 날짜** 추가됨 |
| **고용** 엔터티 변경됨 | **재무 차원** 추가됨</br>**해고 사유** 추가됨</br>**전환 날짜** 에서 **해고 날짜** 로 이름이 변경됨</br>**수습 날짜** 추가됨 |
| **작업자 주소** 엔터티 변경됨 | **나머지 주소** 추가됨</br>**주소란 1**, **주소란 2** 및 **주소란 3** 이 지원 중단으로 표시됨 |
| 새로운 변동 보상 설정 엔터티 | **보상 변동 계획 유형**</br>**보상 변동 계획**</br>**귀속 확정 규칙**</br>**보상 가변 계획 수준** |
| 새 **작업자 일정 고용** 엔터티 | **작업 일정 엔터티** 추가됨 |
| 새 **급여 직위 세부 정보** 엔터티 | **급여 직위 세부 정보** 추가됨 |
| 새로운 **직함** 엔터티 | **직함** 추가됨. 새 **직함** 엔터티가 Human Resources와 Dataverse 간의 동기화 프로세스에 포함됩니다. **직무 직위** 또는 **직무** 엔터티에서 처음에 참조되지 않습니다. |

앞으로 몇 주 동안 이러한 엔터티 변경 사항을 모든 환경에서 사용할 수 있습니다. Human Resources를 위한 최신 Dataverse 솔루션을 수동으로 설치하려면 다음을 수행하세요.

1.  [Power Platform 관리 센터](https://admin.powerplatform.microsoft.com)로 이동합니다.

2.  **환경** 을 선택합니다.

3.  업그레이드하려는 환경을 찾습니다. 이는 Human Resources의 **정보** 양식에 있는 **Common Data Service 정보** 섹션의 **환경 이름** 과 일치해야 합니다.

4.  환경 세부 정보를 보려면 환경을 선택합니다.

5.  상단의 작업 표시줄에서 **솔루션 관리** 를 선택합니다. 새 브라우저 창이 열리고 환경의 컨텍스트에서 **Dynamics 365 관리 센터** 로 이동합니다.

6.  **솔루션** 목록에서 **Dynamics 365 Human Resources 앵커** 를 선택합니다.

7.  **업그레이드** 를 선택하여 최신 솔루션을 적용합니다.

## <a name="in-preview"></a>미리 보기

다음 미리 보기 기능을 2020년 2월 3일에 사용할 수 있습니다.

- **휴가 및 부재 미리 보기 기능** - 자세한 내용은 [휴가 및 부재 미리 보기 기능](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)을 참조하세요.

- **복리후생 관리 미리 보기 기능** - 알려진 문제를 포함한 자세한 내용은 [복리후생 관리 개요](hr-benefits-management-overview.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]