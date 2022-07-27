---
title: 고용되지 않은 작업자
description: 조직에서 미래, 활성 또는 과거 고용이 없는 근로자는 고용되지 않은 작업자 페이지에 표시됩니다.
author: twheeloc
ms.date: 11/03/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0b8fe7dd0818fa1c3cc4224e73035849f9dadfe
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452635"
---
# <a name="workers-without-employment"></a>고용되지 않은 작업자


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

조직에서 미래, 활성 또는 과거 고용이 없는 근로자는 **고용되지 않은 작업자** 페이지에 표시됩니다. 이 유형의 작업자는 고용 기록이 없는 작업자를 가져오거나 **작업자 \> 고용 이력** 을 통해 근로자의 고용을 삭제할 때 나타날 수 있습니다.

기본적으로 **고용되지 않은 작업자** 페이지는 다음 역할에 사용할 수 있습니다.

- Human Resources 보조원
- Human Resources 관리자
- 모집자
- 보상 및 복리후생 관리자
- 급여 운영자
- 급여 관리자
- 교육 관리자

**고용되지 않은 작업자** 목록에서 목록에 있는 개인을 삭제할 수 있습니다. 기본적으로 이 권한은 Human Resources 보조원 역할에 부여됩니다. 다음 단계에 따라 이 권한을 다른 역할에 부여할 수 있습니다.

1. **시스템 관리** 를 선택한 다음 **보안 구성** 을 선택합니다.

2. **권한** 탭에서 **권한** 목록을 **작업자 유지** 로 필터링합니다.

   [![권한 목록 필터링.](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)

3. **참조** 열에서 **메뉴 항목 표시** 를 선택합니다.

4. **메뉴 항목 표시** 에서 **HcmWorkersWithoutEmployment** 를 선택합니다.

   [![선택 양식.](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)

5. **삭제** 권한을 **부여** 로 설정합니다.

6. **게시되지 않은 개체** 탭을 선택합니다.

7. **모두 게시** 를 선택합니다.

   [![변경 게시.](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
