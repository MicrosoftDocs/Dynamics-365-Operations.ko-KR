---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 11월 19일)
description: 이 항목에서는 독립 실행형 Microsoft Dynamics 365 Human Resources(2021년 11월 19일)의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 12/03/2021
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
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 618d90f95637002f444b334e16d3fef466dda65e
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2022
ms.locfileid: "8452692"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-november-19-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 11월 19일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Microsoft Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다. 빌드 번호 8.1.4591에 적용된 변경 사항.

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 | 설명 |
|---|---|---|
| 626178 | **관리자 셀프 서비스** 의 작업자 타일에 탐색이 누락됨 | 이 문제는 이제 수정되었습니다. **관리자 셀프 서비스** 에서 탐색으로 보고서 세부 정보를 볼 수 있습니다. |
| 632573 | **과정** 을 저장할 때 유효성 검사 오류가 없음 | 이 문제는 이제 수정되었습니다. **최소 참가자 수** 가 0보다 큰 과정을 만들 때 **최대 참가자 수** 가 0인 경우에도 여전히 저장이 허용되었습니다. |
| 615955 | 새 모집 요청 위치를 만들 때 "**목적** 필드에 입력해야 합니다" 오류가 발생함. | 새 모집 요청 위치를 위한 주소를 만들 때 "목적 필드에 입력해야 합니다" 오류가 발생합니다. 하지만 이 페이지에는 **목적** 필드가 없습니다. |
| 620797 | **성별** 필드 비워 두기 오류에 오해의 소지가 있음 | 개인 연락처에 성별을 입력하지 않으면 보고서에 '텍스트를 입력하려면 여기를 클릭하거나 탭하세요'가 표시되지만 필드에 아무것도 입력할 수 없으므로 오해의 소지가 있습니다. |
| 620800 | 복리후생 명세서 링크가 숨겨져 있음 | 복리후생 명세서는 기본적으로 **직원 셀프 서비스** 에서 볼 수 없습니다.  **직원 셀프 서비스** 오른쪽의 **링크** 섹션에 링크가 추가되었습니다 |
| 629778 | CDS 통합의 성능 문제. | 권한 부여 관련 요청으로 인해 성능 문제가 발생했습니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 방법에 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
|---|---|---|
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |


## <a name="coming-soon"></a>업데이트 예정
계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 및 업계 클라우드: 2021 릴리스 웨이브 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)를 참조하세요.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
