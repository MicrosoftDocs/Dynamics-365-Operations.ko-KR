---
title: 유지 관리 검사 목록
description: 이 토픽에서는 자산 관리의 유지 관리 체크리스트에 대해 설명합니다.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderChecklist, EntAssetMobileWorkOrderLineChecklistDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9ece9abcbaed0a1881f6b6a0d1b2357bc87ef181636a37564709f62c6aa38475
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447127"
---
# <a name="maintenance-checklists"></a>유지 관리 검사 목록

[!include [banner](../../includes/banner.md)]



유지 관리 체크리스트는 유지 관리 작업 유형에 대해 설정됩니다. 작업 주문 완료 프로세스의 일부로 유지 관리 체크리스트를 작성합니다. **유지 관리 작업 유형 기본값** 페이지에서 [유지 관리 작업 유형에 대한 유지 관리 체크리스트](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)를 설정하는 방법에 대한 자세한 내용은 유지 관리 작업 유형 범주 및 유지 관리 작업 유형, 유지 관리 작업 유형 변형, 유지 관리 작업 거래 및 유지 관리 체크리스트를 참조하세요.

작업 주문에 대한 유지 관리 체크리스트로 작업할 때 유지 관리 작업 유형과 관련된 미리 정의된 유지 관리 체크리스트를 채울 수 있습니다. 유지 관리 체크리스트를 더 추가할 수도 있습니다.


## <a name="fill-in-a-maintenance-checklist"></a>유지 관리 체크리스트 작성

1. **자산 관리** > **공통** > **작업 주문** > **모든 작업 주문** 또는 **활성 작업 주문** 을 클릭합니다.

2. **작업 주문** 을 선택한 다음 작업 창의 작업 주문 탭에 있는 **라인** 그룹에서 **유지 관리 체크리스트** 를 선택합니다.

3. **작업 주문 유지 관리 작업 체크리스트** 는 모든 작업 주문 작업에 대한 체크리스트를 보여줍니다. 작업 주문 작업의 유지 관리 작업 유형이 다른 경우 유지 관리 체크리스트는 각 작업 주문 작업마다 다를 수 있습니다. 관련 유지 관리 체크리스트로 작업할 작업 주문 작업을 선택합니다. 선택된 유지 관리 체크리스트 라인의 세부 사항은 **라인 세부 사항** 빠른 탭에 표시됩니다.

4. 모든 유지 관리 체크리스트 라인을 나타나는 순서대로 한 번에 하나씩 완료하세요. **라인 세부 정보** 빠른 탭의 필드를 작성하여 유지 관리 체크리스트 라인을 완료합니다. 라인을 완성하는 데 필요한 정보는 라인 유형에 따라 다를 수 있습니다. 예를 들어, **텍스트** 유형의 행에 검사 결과를 설명하는 메모를 추가합니다. **측정** 유형의 라인에는 장비에서 읽은 카운터 값을 입력하고 필요에 따라 메모를 추가할 수도 있습니다. **헤더** 유형의 유지 관리 체크리스트 라인은 그 아래에 나타나는 유지 관리 체크리스트 행을 그룹화하기 위한 제목으로 사용됩니다. 헤더를 입력할 필요가 없습니다. 다른 모든 유형의 유지 관리 체크리스트 라인의 경우 **헤더** 유형의 라인에 메모를 추가할 수 있습니다.

5. 지침이 유지 관리 체크리스트 라인과 관련된 경우 **지침** 확인란이 선택됩니다. **라인 세부 정보** 빠른 탭의 **지침** 필드에서 선택한 유지 관리 체크리스트 라인에 대한 지침을 읽으세요.

6. 유지 관리 체크리스트 라인을 완료했으면 해당 라인에서 **체크됨** 확인란을 선택하여 완료된 것으로 표시합니다. 작업 지시 작업과 관련이 없기 때문에 유지 관리 체크리스트 라인을 삭제하려면 해당 라인에서 **N/A** 확인란을 선택합니다. 유지 관리 체크리스트 라인에서 **필수** 확인란이 선택된 경우 **체크됨** 확인란 또는 **N/A** 체크박스를 선택해야 합니다.

>[!NOTE]
>작업 주문이 [활성](../setup-for-work-orders/work-order-lifecycle-states.md) 수명 주기 상태인 경우에만 유지 관리 체크리스트 등록을 업데이트할 수 있습니다.  


## <a name="add-a-maintenance-checklist-line"></a>유지 관리 체크리스트 라인 추가

유지 관리 체크리스트는 유지 관리 작업 유형 기본값에 대한 정의에서 생성되고 작업 주문 작업으로 전송됩니다. 필요에 따라 작업 주문 작업에 유지 관리 체크리스트 라인을 추가할 수 있습니다. 수동으로 추가한 유지 관리 체크리스트 라인은 **수동** 참조를 얻습니다.

1. **작업 주문 유지 관리 작업 체크리스트** 페이지에서 유지 관리 체크리스트를 추가할 작업 주문 작업을 선택합니다.

2. **유지 관리 체크리스트 라인** 빠른 탭에서 새로 만들기를 선택하여 유지 관리 체크리스트 라인을 추가합니다. 그런 다음 선택한 줄 뒤에 새 줄을 삽입하려면 **아래쪽 화살표** 키를 누릅니다. 순서의 다음 번호는 **라인 번호** 필드에 자동으로 입력됩니다. 선택한 줄 앞에 새 라인을 삽입하려면 **라인 추가** 를 선택합니다. 

3. **이름** 필드에 유지 관리 체크리스트 라인의 이름을 입력합니다.

4. **유형** 필드에서 유지 관리 체크리스트 라인의 유형을 선택합니다. **라인 세부 정보** 빠른 탭에는 각 유지 관리 체크리스트 유형에 대한 관련 필드가 포함되어 있습니다.
    - **텍스트** - 이 유형을 사용하여 수행해야 할 작업을 설명하는 텍스트가 있는 유지 관리 체크리스트 행을 추가합니다. 예를 들어 작업자가 무언가를 확인하거나 검사하기를 원하지만 특정(측정 가능한) 결과를 기대하지 않는 경우 이 유형을 사용할 수 있습니다. 이 유형을 선택한 후 **라인 세부 정보** 빠른 탭의 **지침** 필드에 수행해야 할 작업을 설명하는 텍스트를 입력합니다.
    - **헤더** - 유형의 유지 관리 체크리스트 라인은 그 아래에 나타나는 유지 관리 체크리스트 행을 그룹화하기 위한 제목으로 사용됩니다. 이 유형은 특정 영역으로 나눌 수 있는 여러 유지 관리 체크리스트 행이 있는 경우에 유용합니다. 이 유형을 선택한 후 **이름** 필드에 설명이 포함된 이름을 입력합니다.
    - **템플릿** - 이 유형은 작업 주문 작업에 유지 관리 체크리스트 라인을 수동으로 추가하는 경우 적용할 수 없습니다.  
    - **변수** - 이 유형을 사용하여 유지 관리 체크리스트 라인의 범위에서 가능한 결과를 정의합니다. 유지 관리 체크리스트 변수를 설정하는 방법에 대한 정보는 [유지 관리 작업 유형 범주 및 유지 관리 작업 유형, 유지 관리 작업 유형 변형, 유지 관리 작업 거래 및 유지 관리 체크리스트](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)를 참조하세요. 이 유형을 선택한 후 **이름** 필드에 변수를 설명하는 이름을 입력합니다. **라인 세부 정보** 빠른 탭의 **변수** 필드에서 변수를 선택합니다. **지침** 필드에 수행해야 할 작업을 설명하는 텍스트를 입력합니다.
    - **측정** - 이 유형을 사용하여 유지보수 체크리스트 라인에 특정 측정을 기록합니다. 이 유형을 선택한 후 **이름** 필드에 측정 이름을 입력합니다. **라인 세부 정보** 빠른 탭의 **카운터** 및 **단위** 필드에서 적절한 값을 선택합니다. **지침** 필드에 수행해야 할 작업을 설명하는 텍스트를 입력합니다.

5. 유지 관리 체크리스트 행을 수동으로 추가했으면 위의 **유지 관리 체크리스트 작성** 섹션에 설명된 대로 행을 채우십시오.

>[!NOTE]
>**작업 주문 유지 관리 작업 체크리스트** 페이지에서 **작업 유형** 참조가 있는 유지 관리 체크리스트 라인을 삭제할 수 없습니다. 귀하 또는 다른 유지 관리 작업자가 수동으로 생성하고 **수동** 참조가 있는 유지 관리 체크리스트 라인만 삭제할 수 있습니다.

아래 그림은 오류 등록의 예를 보여줍니다.

![자료 1.](media/14-work-orders.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]