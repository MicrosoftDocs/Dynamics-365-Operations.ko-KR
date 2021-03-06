---
title: 창고 작업자 관리
description: 이 문서에서는 Warehouse Management 모바일 앱을 사용하여 창고 직원이 수행하는 작업을 제어하고 모니터링하는 방법에 대해 설명합니다.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, InventLocation, WHSLaborStandards, WHSWorker, WHSWorkTable, WHSWorkTableListPage, WHSResetUserPassword
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72891
ms.assetid: feaa6f15-49d2-41f5-9b87-453463c52e4e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a3261571f7ba43a79ee42afd8cdfe9b69cb83c01de3e4b2b89d2b0aae668ea2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447088"
---
# <a name="manage-warehouse-workers"></a>창고 작업자 관리

[!include [banner](../includes/banner.md)]

이 문서에서는 Warehouse Management 모바일 앱을 사용하여 창고 직원이 수행하는 작업을 제어하고 모니터링하는 방법에 대해 설명합니다.

창고 관리의 기능을 사용하는 경우 모든 창고 작업자 작업을 *작업* 이라고 합니다. 피킹, 이동, 보유 재고 계산과 같은 작업은 모바일 디바이스를 사용하여 기록됩니다. 창고 작업자가 작업을 수행하려면 먼저 인적 자원의 작업자와 연결되어야 합니다. 각 **작업자** 계정에는 연결된 여러 창고 작업 사용자가 있을 수 있습니다. 이러한 작업 사용자는 다른 창고에서 작업할 수 있으며 다양한 모바일 디바이스 메뉴에 대한 액세스 수준이 다를 수 있습니다. 창고 작업 사용자를 선택한 작업자에 대한 다중 로그온으로 생각할 수 있습니다. 각 작업 사용자에게는 기본 창고가 있으며 특정 워크플로는 해당 작업 사용자가 사용할 수 있는 메뉴 항목에 의해 표시됩니다. 

새 직장 사용자를 만들려면 **작업자** 페이지의 **일반** 탭에 있는 **창고** 섹션에서 **작업자** 를 클릭합니다. 사용자 ID, 사용자 이름, 기본 웨어하우스 및 메뉴 이름을 지정해야 합니다. 이 메뉴는 사용자가 Warehouse 모바일 디바이스 포털에 로그인할 때 로드되며 사용자가 액세스할 수 있는 메뉴 항목을 정의할 수 있습니다. 

각 작업 사용자에 대한 설정의 일부로 특정 프로세스 워크플로를 정의할 수도 있습니다. 예를 들어 **주기 실사 감독자임** 필드를 사용하여 사용자가 실사 작업 중 주기 실사 불일치에 대한 조정을 처리할 수 있는지 여부 또는 이러한 조정을 다른 사람이 먼저 검토해야 하는지 여부를 지정할 수 있습니다.

## <a name="defining-labor-standards"></a>노동 기준 정의
**노동 표준** 페이지에서는 시스템이 특정 유형의 작업에 필요한 예상 시간을 계산하는 데 사용하는 계산 방법을 정의할 수 있습니다. 이 정의는 일반 수준 또는 특정 수준에서 설정할 수 있습니다. 예를 들어, 특정 피킹 프로세스가 사용될 때 특정 단위 정의에 대한 중량당 판매 주문 피킹을 처리하는 데 필요한 시간을 정의할 수 있습니다. 동시에 피킹된 현재고의 풋 작업에 대해 다른 계산 방법에 따라 시간을 기록할 수 있습니다. 

정의한 노동 기준을 활성화하려면 노동 기준이 사용될 각 창고에 대해 **노동 기준 허용** 옵션을 선택해야 합니다.

## <a name="monitoring-and-controlling-warehouse-work"></a>창고 작업 모니터링 및 제어
**모든 작업** 페이지에서는 계획, 진행 및 완료된 모든 작업을 모니터링하고 유지 관리할 수 있습니다. 이 페이지에서 창고 작업 사용자 할당 및 작업 우선 순위와 같은 다양한 프로세스를 업데이트할 수 있습니다. 또한 작업 헤더 및 작업 라인과 관련된 세부 정보를 드릴다운하여 예상되거나 완료된 작업 프로세스를 이해할 수 있습니다. 

**근로기준법** 을 활성화하면 해당 작업에 대해 계산된 예상 시간을 확인할 수 있습니다. 그러면 작업이 처리되면 각 작업 작업에 대한 실제 시간도 표시됩니다. 이러한 방식으로 예상 시간 계산을 실제 시간과 비교할 수 있습니다. 

또한 작업 생성 중 작업을 자동으로 분할하는 규칙에서 예상 시간을 사용할 수 있습니다. 이러한 방식으로 작업을 완료하는 데 예상되는 시간을 기준으로 작업 부하를 분산할 수 있습니다. 

작업 항목을 처리하는 데 사용되는 시간을 분석하면 창고 작업자의 효율성을 개선하는 데 도움이 될 수 있습니다. 이 분석에 도움이 되는 보고서는 다음과 같습니다.

-   **사용자별 노동** – 이 보고서는 예상 시간 대비 실제 시간을 기준으로 작업자 생산성을 보여줍니다.
-   **업무 트랜잭션 유형별 노무** – 이 보고서를 사용하여 특정 창고 프로세스의 비효율성을 조사할 수 있습니다. 예를 들어, 이전 주문에 대한 선택이 이전 주보다 이번 주에 더 오래 걸린다는 것을 알 수 있습니다. 그런 다음 추가 조사를 위해 이 정보를 사용할 수 있습니다.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]