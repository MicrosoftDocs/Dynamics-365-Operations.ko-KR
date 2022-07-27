---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 3월 8일)
description: 이 항목에서는 2021년 3월 8일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 03/08/2021
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
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 133cfffadabade8f7770b4853e14b769c5b961370546e3104d6db26bc0c6331a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451876"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-08-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 3월 8일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4017에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 관리자의 휴가에 대한 회사 간 보기 | [관리자의 직원 휴가에 대한 회사 간 보기](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [휴가 및 휴직 매개 변수 구성](./hr-leave-and-absence-parameters.md) |

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 486611 | **모든 일정에서 휴가 비활성화** 를 활성화해도 휴가 일정에 휴가가 표시됨 | **모든 일정에서 휴가 비활성화** 가 활성화된 경우 휴가 및 부재 일정 개선 기능이 활성화되면 휴가 정보가 더는 표시되지 않습니다.|
| 508972 | 휴가 및 부재 은행 거래 엔터티에 등록 유효성 검사가 누락됨 | 휴가 및 부재 은행 거래 엔터티를 사용할 때 계획에 등록되지 않은 직원은 더는 가져올 수 없습니다. |
| 554854 | 사용자 옵션의 기본 법인이 다른 경우 고용 엔터티의 일정을 업데이트하면 오류가 발생함 | 고용 엔터티를 사용하여 직원의 달력을 업데이트할 때 사용자 옵션의 기본 법인이 다른 경우 더는 오류가 발생하지 않습니다. |
| 558347 | 시작 페이지를 로드할 때 "양식 구성(FormRunConfiguration)에서 기록을 생성할 수 없습니다" 오류가 표시됨. | 개인 설정으로 인해 시작 페이지를 로드할 때 "양식 구성(FormRunConfiguration)에서 기록을 생성할 수 없습니다" 오류가 표시됩니다. |
| 557327 | 복리후생 관리 작업 영역: 그리드 위에 간격이 있음. | 복리후생 작업 영역의 테이블 그리드 테두리에 의도하지 않은 간격이 나타나는 사용자 환경 문제를 수정했습니다. |
| 557334 | 복리후생 관리 작업 영역: **기간** 선택 드롭다운 상자는 **요약** 탭에만 표시되어야 함 | 복리후생 **기간** 선택 드롭다운은 이제 **요약** 탭이 **처리 결과** 및 **연결** 섹션이 아닌 복리후생 작업 영역에서 활성화된 경우에만 나타납니다. |
| 557336 | 복리후생 관리 작업 영역: 타일 보기에서 **체크아웃된 계획이 있는 공개 등록** 텍스트가 잘림 | 필요한 컨텍스트가 잘리지 않도록 타일 보기의 텍스트를 **체크아웃된 계획...공개 등록** 으로 변경했습니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 직원이 비즈니스 연락처 세부 정보를 편집하지 못하도록 제한 | [직원이 비즈니스 연락처 세부 정보를 편집하지 못하도록 제한](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [개인 정보 편집 제한](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>업데이트 예정

| 기능 | 세부 정보 |
| --- | --- |
| 관리자가 직원을 위해 입력한 기술은 워크플로에서 자동 승인될 수 있음 | 업데이트 예정. |

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]