---
title: 기술 입력
description: 작업자와 관리자는 Dynamics 365 Human Resources에서 기술을 입력할 수 있습니다.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c2a35079f43b92b5ff6d68aa7068f3e1f68ce8c2c32d23cdd22798f95c9a0ff4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451891"
---
# <a name="enter-skills"></a>기술 입력

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources에서 작업자, 지원자 또는 연락처의 목표 기술 또는 실제 기술을 입력할 수 있습니다. 목표 기술은 사람이 달성하려고 계획하는 기술입니다. 실제 기술은 사람이 현재 가지고 있는 기술입니다.

## <a name="create-a-workflow-to-auto-approve-skills"></a>기술을 자동 승인하는 워크플로 만들기

승인 없이 기술을 입력하려면 기술을 자동 승인하는 워크플로를 만들어야 합니다.

> [!NOTE]
> 작업자가 입력한 기술에는 항상 관리자의 승인이 필요합니다. 이 워크플로는 작업자 대신 관리자가 입력한 기술만 자동 승인합니다.

1. **인사 관리** 작업 영역에서 **연결** 을 선택합니다.

2. **설정** 에서 **인적 자원 워크플로** 를 선택합니다.

3. **새로 만들기** 를 선택합니다.

4. **워크플로 만들기** 창에서 **작업자 기술** 을 선택합니다.

   [![작업자 기술 워크플로 선택.](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)

5. **이 파일을 여시겠습니까?** 대화 상자에서 **열기** 를 선택합니다. 메시지가 표시되면 자격 증명을 입력합니다.

6. 워크플로 편집기에서 **기술 승인** 워크플로 요소를 선택하고 캔버스로 끌어서 놓습니다.

   [![기술 워크플로 요소 승인 선택.](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)

7. **시작** 요소를 **기술 1 승인** 요소에 연결한 후 **기술 1 승인** 요소를 **종료** 요소에 연결합니다. **종료** 요소를 보려면 아래로 스크롤해야 할 수 있습니다. 다른 요소에 더 가깝게 끌어서 올 수 있습니다.

   [![워크플로 요소 연결.](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)

8. **기술 1 요소** 워크플로 요소를 두 번 클릭하고 **1단계** 요소를 오른쪽 버튼으로 클릭합니다. **1단계** 요소를 마우스 오른쪽 버튼으로 클릭한 다음 **속성** 을 선택합니다.

9. **속성** 창의 왼쪽 탐색 모음에서 **조건** 을 선택합니다.

10. **다음 조건이 충족되는 경우에만 이 단계 실행** 을 선택합니다.

11. **조건 추가** 를 선택합니다. **조건** 다음에 **직원 셀프 서비스 기술** 을 선택한 다음 **직원 셀프 서비스 기술.사람** 을 선택합니다. **일치함** 다음에 **필드** 를 선택한 다음 **사용자와 사람의 관계.사람**.

    [![조건 지정.](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)

12. 왼쪽 탐색 모음에서 **할당** 을 선택합니다.

13. **할당 유형** 탭에서 **계층** 을 선택합니다.

14. **계층 선택** 탭의 **계층 유형:** 필드에서 **관리 계층** 을 선택합니다.

    [![관리 계층 지정.](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)

15. **닫기** 를 선택하고 캔버스 이동 경로의 **워크플로** 를 선택한 다음 **저장 및 닫기** 를 선택합니다.

워크플로 만들기에 대한 자세한 내용은 [워크플로 시스템 개요](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json)를 참조하세요.

## <a name="enter-skills-for-a-worker"></a>작업자의 기술 입력

1. 작업자를 선택합니다.

2. **작업자** 페이지의 작업 표시줄에서 **사람** 을 선택한 다음 **기술** 을 선택합니다.

3. **기술** 페이지에서 각 기술에 대해 다음 필드를 완료합니다.

   - **기술**: 기술을 선택합니다.
   - **수준 유형**: 작업자가 이미 가지고 있는 기술에 **실제** 를 선택하거나 작업자가 작업 중인 기술에 대해 **대상** 을 선택합니다.
   - **수준**: 작업자의 기술 수준을 선택합니다.
   - **수준 날짜**: 일정 도구에서 날짜를 선택합니다.
   - **심사관**: 해당하는 경우 목록에서 심사관을 선택합니다. 검색을 필터링할 수 있습니다.
   - **경험 기간(년)**: 경험 기간(년)을 입력합니다.
   - **확인됨**: 기술이 확인된 경우 확인란을 선택합니다.
   - **확인한 사람**: 확인한 사람의 이름을 입력합니다.

4. 기술 입력이 완료되면 **저장** 을 선택합니다.

## <a name="see-also"></a>참고 항목

[기술 구성](hr-develop-skills.md)<br>
[기술 매핑](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]