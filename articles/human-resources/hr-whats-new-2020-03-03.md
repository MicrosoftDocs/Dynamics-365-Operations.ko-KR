---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 3월 3일)
description: 이 항목에서는 2020년 3월 3일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 03/03/2020
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
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2fea153f7d532b25d7866f852875453ca3e4fc49
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452008"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-3-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 3월 3일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 문서에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.2955에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 LCS의 지원 번호를 나타냅니다.

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>이제 Dataverse 솔루션에서 다음 변경 사항을 사용할 수 있습니다.

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

3.  업그레이드하려는 환경을 찾습니다. 환경은 Human Resources의 **정보** 양식에 있는 **Common Data Service 정보** 섹션의 **환경 이름** 과 일치해야 합니다.

4.  환경 세부 정보를 보려면 환경을 선택합니다.

5.  상단의 작업 표시줄에서 **솔루션 관리** 를 선택합니다. 새 브라우저 창이 열리고 환경의 컨텍스트에서 **Dynamics 365 관리 센터** 로 이동합니다.

6.  **솔루션** 목록에서 **Dynamics 365 Human Resources 앵커** 를 선택합니다.

7.  **업그레이드** 를 선택하여 최신 솔루션을 적용합니다.

## <a name="import-issues-with-the-leave-enrollment-data-entity-406082"></a>휴가 등록 데이터 엔터티의 가져오기 문제(406082)

이제 새 등록 날짜가 이전 계획의 만료된 등록 날짜보다 늦은 경우 같은 유형의 새 휴가 계획에 직원을 등록할 수 있습니다.

## <a name="issue-with-exporting-contribution-rates-in-the-401k-payrollworkerenrolledbenefitdetail-entity-in-dmf-420700"></a>DMF의 401k payrollWorkerEnrolledBenefitDetail 엔터티에서 기여 비율 내보내기 문제(420700)

이 변경은 고용주 기여에 대한 현재 값을 반영하도록 **payrollWorkerEnrolledBenefitDetail** 엔터티의 내보내기 기능을 수정합니다.

## <a name="searching-in-the-streamlined-worker-form-causes-message-saying-person-field-must-be-filled-in-402525"></a>간소화된 작업자 양식에서 검색하면 사람 필드를 채워야 한다는 메시지가 표시됨(402525)

직원을 검색할 때 **사람** 필드를 채워야 한다는 메시지가 더는 표시되지 않습니다.

## <a name="note-field-value-doesnt-render-on-the-add-more-skills-form-380134"></a>기술 추가 양식에서 메모 필드 값이 렌더링되지 않음(380134)

이 변경은 직원 셀프 서비스에서 **기술 추가** 양식을 개인 설정할 때 발생하는 문제를 수정합니다.

## <a name="multiple-fixed-compensation-plans-dont-expire-when-transferring-employees-389466"></a>직원을 전환할 때 여러 고정 보상 계획이 만료되지 않음(389466)

이 변경으로 이전 직위에 대한 모든 활성 고정 보상 기록이 전환 날짜에 만료됩니다.

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