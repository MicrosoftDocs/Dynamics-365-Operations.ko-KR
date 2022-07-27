---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 2월 7일)
description: 이 항목에서는 2020년 2월 7일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 02/07/2020
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
ms.search.validFrom: 2020-02-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 70acaaf2218c8b5c0239b968a29a927ac23080f0
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451993"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-7-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 2월 7일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 문서에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.2835에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 Microsoft Dynamics Lifecycle Services(LCS)의 지원 번호를 나타냅니다.

## <a name="learning-analytics-doesnt-show-the-course-if-the-classroom-is-blank-388289"></a>강의실이 비어 있는 경우 학습 분석에 과정이 표시되지 않음(388289)

이제 강의실이 비어 있는 경우 학습 분석 페이지에 과정이 표시됩니다.

## <a name="position-lookup-doesnt-take-the-time-zone-into-account-405344"></a>직위 조회가 표준 시간대를 고려하지 않음(405344)

이제 열린 직위에 대한 조회에서 직위가 열려 있는지 확인할 때 표준 시간대를 고려합니다.

## <a name="current-balance-analysis-view-doesnt-update-with-the-correct-current-leave-balance-after-submitting-time-off-requests-409756"></a>현재 잔액 분석 보기가 휴가 요청을 제출한 후 올바른 현재 휴가 잔액으로 업데이트되지 않음(409756)

이제 현재 잔액에 제출된 휴가 요청이 포함됩니다.

## <a name="in-preview"></a>미리 보기

다음 미리 보기 기능을 2020년 2월 3일에 사용할 수 있습니다.

- **휴가 및 부재 미리 보기 기능** - 자세한 내용은 [휴가 및 부재 미리 보기 기능](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)을 참조하세요.

- **복리후생 관리 미리 보기 기능** - 알려진 문제를 포함한 자세한 내용은 [복리후생 관리 개요](hr-benefits-management-overview.md)를 참조하세요.

## <a name="coming-soon"></a>업데이트 예정

### <a name="platform-update-32"></a>플랫폼 업데이트 32 

플랫폼 업데이트 32가 곧 제공됩니다. [플랫폼 업데이트 32에 관한 자세한 내용은 여기에서 확인하세요](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md).

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