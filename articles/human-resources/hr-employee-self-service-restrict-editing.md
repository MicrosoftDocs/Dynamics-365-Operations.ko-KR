---
title: 개인 정보 편집 제한
description: Dynamics 365 Human Resources에서 직원에 연락처 세부 정보를 편집하지 못하도록 제한합니다.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e10db35996d31dc6c40a4253a324139c346be8c9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452662"
---
# <a name="restrict-editing-of-personal-information"></a>개인 정보 편집 제한


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

이 항목에서는 직원이 Dynamics 365 Human Resources에서 연락처 세부 정보를 편집하지 못하도록 제한하는 방법을 설명합니다. 직원이 회사 위치 또는 이메일 주소와 같은 특정 연락처 세부 정보를 편집하지 못하도록 할 수 있습니다.

> [!NOTE]
> 이 기능을 사용하려면 먼저 기능 관리에서 **직원이 특정 목적으로 주소 및 연락처 정보를 추가하거나 편집하지 못하도록 제한(미리 보기)** 을 활성화해야 합니다. 미리 보기 기능의 활성화에 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.<br><br>![미리 보기 기능 활성화.](./media/hr-employee-self-service-restrict-enable.png)

## <a name="choose-the-information-an-employee-can-add-or-edit"></a>직원이 추가하거나 편집할 수 있는 정보 선택

1. Human Resources에서 **인사 관리**, **연결** 을 선택한 다음 **인적 자원 매개 변수** 를 선택합니다.

   ![Human Resources 매개 변수로 이동합니다.](./media/hr-employee-self-service-human-resources-parameters.png)

2. **인적 자원 매개 변수** 페이지에서 **직원 셀프 서비스** 탭을 선택합니다.

   ![직원 셀프 서비스 선택.](./media/hr-employee-self-service-tab.png)

3. **직원 셀프 서비스** 탭의 **주소 및 연락처 정보** 섹션에서 직원이 추가하거나 편집하지 못하도록 하려는 모든 정보를 선택 취소합니다. 이 예에서는 **비즈니스** 연락처 정보의 선택을 취소했습니다.

   ![비즈니스 연락처 정보에 대한 편집 제한](./media/hr-employee-self-service-restrict-business.png)

4. **저장** 을 선택합니다.

   ![변경 내용 저장.](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a>직원 환경

직원이 연락처 세부 정보를 추가하거나 편집하지 못하도록 제한하면 직원은 정보를 볼 수 있지만 변경할 수는 없습니다.

이 예에서 직원은 **비즈니스** 연락처 세부 정보를 편집할 수 없지만 **직원 셀프 서비스** 에서 정보를 계속 볼 수 있습니다.

![비즈니스 연락처 세부 정보 보기.](./media/hr-employee-self-service-restrict-view.png)

그러나 비즈니스 연락처 세부 정보를 선택하면 **주소 편집** 창이 읽기 전용으로 표시되고 필드를 변경할 수 없습니다.

![읽기 전용으로 표시되는 비즈니스 연락처 세부 정보.](./media/hr-employee-self-service-restrict-read-only.png)

또한 **추가** 를 선택하여 새 주소를 추가할 때 **목적** 드롭다운 상자에서 **비즈니스** 를 선택할 수 없습니다.

![직원은 비즈니스 주소를 추가할 수 없습니다.](./media/hr-employee-self-service-restrict-add.png)

직원은 **개인 정보** 페이지에서 **연락처 세부 정보** 를 선택하고 새 주소를 추가할 때도 같은 경험을 하게 됩니다. **목적** 드롭다운 상자에 추가할 수 있는 정보 유형만 표시됩니다. 

![직원은 목적 드롭다운에서 비즈니스를 선택할 수 없습니다.](./media/hr-employee-self-service-restrict-purpose.png)

이제 **연락처 세부 정보** 의 그리드에 **목적** 이 표시됩니다.

![연락처 세부 정보 그리드에 목적이 표시됩니다.](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a>참고 항목

[직원 및 관리자 셀프 서비스 개요](hr-employee-manager-self-service-overview.md)<br>
[인적 자원 매개 변수 구성](hr-setup-parameters.md)<br>
[개인 정보 편집](hr-employee-manager-self-service-edit-personal-information.md)
