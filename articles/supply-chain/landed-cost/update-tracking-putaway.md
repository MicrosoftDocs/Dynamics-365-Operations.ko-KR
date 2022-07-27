---
title: 보관 추적 업데이트
description: 이 토픽에서는 정기적인 작업에 대한 업데이트 추적을 설정하고 실행하는 방법에 대해 설명합니다.
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: d8e2a42d8e12a5a9cf18e876b6f9e45ecb877881
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2021
ms.locfileid: "8447703"
---
# <a name="update-tracking-for-put-away"></a>보관 추적 업데이트

[!include [banner](../includes/banner.md)]

*보관 추적 업데이트* 정기 작업은 야간 반복 배치로 실행되도록 설계되었습니다. 모든 인벤토리 트랜잭션을 수신한 항해와 실제 종료 날짜에 대한 값이 없는 항해를 식별합니다. 그런 다음 실제 종료 날짜를 필요에 따라 현재 날짜로 설정합니다.

*컨테이너 활동* 은 각 *운송 컨테이너* 에 대한 여정의 각 *구간* 에 대해 생성됩니다. 이러한 값은 항해가 생성될 때 선택되는 여정 템플릿에 의해 정의됩니다. 각 컨테이너 활동 레코드에 대해 **시작 날짜**, **예상 종료 날짜** 및 **실제 종료 날짜** 필드에 대한 값을 설정할 수 있습니다. 이 필드는 구간이 시작되었거나 완료되었다는 확인을 받으면 업데이트할 수 있습니다.

일반적으로 확인된 날짜와 관련된 정보는 Microsoft Dynamics 365 Supply Chain Management 외부에서 유지 관리되기 때문에 화물 운송업체와 같은 제3자가 제공합니다. 그러나 여정 구간에서 창고로의 상품 도착을 추적하기 위해 제3자의 정보가 필요하지 않습니다(상품 보관으로 표시됨). 따라서 Dynamics 365 Supply Chain Management의 정보를 기반으로 추적 여부를 판단할 수 있습니다.

*보관 추적 업데이트* 정기 작업을 설정하고 실행하려면 다음 단계를 따르세요.

1. **상륙 비용 \> 정기 작업 \> 보관 추적 업데이트** 로 이동합니다.
1. **보관 추적 업데이트** 대화 상자의 **매개 변수** 섹션에서 다음 필드를 설정합니다.

    - **구간** – 추적을 업데이트하려는 여정 부분의 고유 식별 이름/번호를 선택합니다. 선택한 값은 창고에 항해가 도착했음을 나타내야 합니다.
    - **활동** – 선택한 구간에서 수행한 활동을 선택합니다. 이러한 값은 추적 제어 센터의 여정 템플릿 라인별로 할당됩니다.

1. 업데이트에 포함해야 하는 레코드 집합을 제한하려면 **포함할 레코드** 빠른 탭에서 **필터** 단추를 선택합니다. 선택 기준, 정렬 기준 및 조인을 정의할 수 있는 표준 쿼리 대화 상자가 나타납니다. 필드는 Supply Chain Management의 다른 유형의 쿼리에 대해 작동하는 것처럼 작동합니다. 여기의 필드는 읽기 전용이며 쿼리와 관련된 값을 표시합니다.
1. **백그라운드에서 실행** 빠른 탭에서 Supply Chain Management의 다른 작업 유형과 마찬가지로 필요에 따라 일괄 처리 및 일정 옵션을 설정합니다.
1. **확인** 을 선택하여 설정을 적용하고 업데이트를 실행하거나 예약합니다.
