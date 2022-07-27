---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 2월 18일)
description: 이 항목에서는 2020년 2월 18일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 02/18/2020
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
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9cce93aab902a8ca269cf22e1999716fe49f3ed8
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452044"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 2월 18일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 문서에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.2903에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 LCS의 지원 번호를 나타냅니다.

## <a name="platform-update-32"></a>플랫폼 업데이트 32 

이제 플랫폼 업데이트 32를 사용할 수 있습니다. 자세한 내용은 [금융 및 운영 플랫폼 업데이트 32의 새로운 기능 또는 변경된 기능(2020년 2월)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md)을 참조하세요.

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a>간소화된 직원 양식에서 보기 옵션을 변경할 때 검색 값이 기억됨(383833)

새로운 **작업자** 양식은 이제 보기 옵션을 변경하고 변경 사항을 적용할 때 검색 값을 기억합니다.

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a>미리 보기 기능의 보상 관리 요약 타일이 잘못된 양식으로 리디렉션됨(401861)

고정 및 변동 보상 관리 타일이 이제 새로운 **작업자** 양식에 올바른 레코드를 표시합니다. 간소화된 직원 양식 미리 보기 기능에만 적용됩니다. **기능 관리** 에서 이 미리 보기 기능을 활성화할 수 있습니다. 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a>Dataverse의 일부 휴가 요청 레코드에 상태 필드가 비어 있음(414915)

이 변경으로 휴가 요청의 **상태** 필드가 **검토** 로 설정되었을 때 Dataverse의 문제가 해결됩니다. Dataverse는 이제 상태를 반영합니다.

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a>할당된 직무에 대해서만 기술 갭 분석이 가능함(411390)

이제 Human Resources에 정의된 모든 직무에 대해 기술 갭 분석을 수행할 수 있습니다.

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a>시스템 통화가 새 환경에서 Dataverse에서 Human Resources로 동기화되지 않음(418011)

이제 Dataverse의 시스템 통화를 Human Resources와 동기화할 수 있습니다.

## <a name="in-preview"></a>미리 보기

- [휴가 및 부재 미리 보기 기능](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [복리후생 관리 미리 보기 기능](hr-benefits-management-overview.md)

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

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]