---
title: 직급 계층 구조에서 텍스트 잘림 방지 및 Visio로 내보내기
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources에서 개인 및 직급 계층의 이름이 잘리는 문제를 해결하는 방법에 대해 설명합니다.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7b11bd0247634290c8dc43c2ae2291a485449627
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452443"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>직급 계층 구조에서 텍스트 잘림 방지 및 Visio로 내보내기


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**문제**

고객이 Microsoft Dynamics 365 Human Resources에서 직급 계층을 보면 개인 및 직급 이름이 잘립니다. 따라서 스크린샷을 찍거나 계층을 인쇄 및 배포하는 것이 어려울 수 있습니다.

![직급 계층.](media/position-h.png)

**원인**

이 동작은 의도적으로 설계된 것입니다.

**해결**

안타깝게도, 사용자는 텍스트 크기를 쉽게 변경할 수 없습니다. 그러나 직급 계층을 Human Resources에서 내보낸 다음 Microsoft Visio로 가져올 수 있습니다. 다음 문서는 Microsoft Dynamics AX 2012를 위해 생성되었지만, 이 프로세스는 Human Resources에도 적용됩니다. [Microsoft Visio로 직급 계층 내보내기](/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio)

다음 단계에 따라 Visio로 내보냅니다.

1. Human Resources에서 **직급** 목록 페이지를 엽니다.

    조직 구조 다이어그램에 자세한 정보를 포함하려면 이 절차의 뒷부분에 있는 **조직도 마법사** 를 사용할 때 사용할 수 있도록 **위치** 목록에 필드를 추가하십시오.

2. 작업 창에서 **Microsoft Office에서 열기** 버튼을 선택한 다음 **Excel로 내보내기** 아래에서 **직급** 을 선택합니다. 또는 Ctrl+T를 누릅니다.

    ![직급 목록 페이지를 Excel로 내보냅니다.](media/org-admin.png)

3. 내보낸 Excel 파일을 저장합니다.

    ![Excel로 내보내기 대화 상자.](media/export-excel.png)

4. Visio에서 **Visio - 새로 만들기** 를 선택하고 비즈니스 **템플릿** 범주를 선택합니다.

    ![새로운 다이어그램.](media/new.png)

5. **조직도 마법사** 를 선택한 다음 **만들기** 를 선택합니다.

    ![조직도 마법사 대화 상자.](media/orgchart-wizard.png)

6. **파일 또는 데이터베이스에 이미 저장된 정보** 를 선택한 후 **다음** 을 선택합니다.

    ![조직도 마법사 1.](media/orgchart-wizard7.png)

7. **텍스트, Org Plus(\*.txt) 또는 Excel 파일** 을 선택한 후 **다음** 을 선택합니다.

    ![조직도 마법사 2.](media/orgchart-wizard3.png)

8. 직급 계층이 들어 있는 내보낸 Excel 파일을 찾아 선택한 후 **다음** 을 선택합니다.

    ![조직도 마법사 3.](media/orgchart-wizard2.png)

9. **이름** 필드를 **직급** 으로 설정하고 **보고 대상** 필드를 **직급 보고서** 로 설정한 후 **다음** 을 선택합니다.

    ![조직도 마법사 4.](media/orgchart-wizard1.png)

10. 각 노드에 표시할 필드를 선택한 후 **다음** 을 선택합니다.

    ![조직도 마법사 5.](media/orgchart-wizard5.png)

11. **직급** 열을 **모양 데이터 필드** 목록에 추가하고 **다음** 을 선택합니다.

    ![조직도 마법사 6.](media/orgchart-wizard6.png)

12. 사진은 현재 사용할 수 없습니다. 따라서 다음 페이지에서 **다음** 을 선택합니다.
13. **마법사가 내 조직 차트를 여러 페이지에 걸쳐 자동으로 분할하도록 합니다** 를 선택합니다.

    ![조직도 마법사 7.](media/orgchart-wizard4.png)

14. **완료** 를 선택합니다.

    구조에 없는 직급이 있으면 다이어그램에 포함시켜야 합니다.

Visio에서 생성된 다이어그램은 각 관리자를 별도의 워크시트에 표시합니다.

다이어그램에 포함하도록 선택한 필드를 기반으로 각 노드는 Visio 파일이 생성될 때 적절한 정보를 표시합니다.

![계층 다이어그램.](media/hierarchy.png)

**추가 옵션**

Human Resources에서 **사람** 작업 영역을 사용하여 일부 계층 관련 정보를 볼 수도 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
