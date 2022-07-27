---
title: 철회 칸반으로 보충
description: 이 항목에서는 제조 활동을 위한 자재 보충에 철회 칸반이 사용되는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob, KanbanFlow, KanbanRules, WHSKanbanWaveTable, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b90e4699c440d0dd753cd16ff17cf958507e7872138a7f2c2c84f645f713d3db
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446911"
---
# <a name="replenishment-with-withdrawal-kanbans"></a>철회 칸반으로 보충

[!include [banner](../includes/banner.md)]

이 항목에서는 제조 활동을 위한 자재 보충에 철회 칸반이 사용되는 방법에 대해 설명합니다.

## <a name="workflow-for-material-replenishment-that-uses-the-withdrawal-kanban"></a>철회 칸반을 사용하는 자재 보충 워크플로

철회 칸반은 단일 항목의 칸반을 창고와 자재가 소비되는 생산 위치 간에 이동하는 데 사용할 수 있습니다. 철회 칸반은 자재 보충을 위한 풀 기반 솔루션을 지원하며, 특정 수요에 대한 공급을 트리거하기 위해 풀 신호가 필요합니다. 

다음 시나리오는 풀 신호가 생산 프로세스를 위한 자재를 보충하기 위해 칸반 생성을 트리거하는 풀 기반 보충 시스템을 보여줍니다. 

[![풀 신호는 칸반 생성을 트리거하여 생산 공정을 위한 자재를 보충합니다.](./media/material-replenishment-with-withdrawal-kanban.png)](./media/material-replenishment-with-withdrawal-kanban.png)

1.  철회 칸반
2.  칸반 "시작" 위치 및 창고 작업 위치 지정
3.  칸반 "종료" 위치 및 생산 입력 위치
4.  제조 공정
5.  칸반 피킹 창고 작업
6.  원자재 창고 위치
7.  자재 창고
8.  제조 창고

이 시나리오에서 제조 프로세스(4)는 제조 창고(8)의 생산 입력 위치(3)에서 자재를 소비합니다. 자재(칸반)의 취급 단위가 소모되면 비어있는 것으로 등록됩니다. 항목 원산지에 대한 보충 신호가 생성되고 새 칸반(1)이 생성됩니다. 이 경우 항목 출처는 자재 창고(7)의 위치로 구성됩니다. 칸반의 자재가 선택되어 동일한 창고의 위치(2)에 배치됩니다. 자재가 피킹되면 위치 2에서 제조 창고(8)의 생산 입력 위치(3)로 이동할 준비가 됩니다.

## <a name="configure-warehouse-work-for-kanban-picking-for-the-withdrawal-kanban"></a>철회 칸반에 대한 간판 피킹을 위한 창고 작업 구성

철회 칸반에 대한 원자재 피킹을 활성화하려면 **칸반 피킹** 작업 주문 유형에 대해 웨이브 템플릿, 작업 템플릿 및 위치 지시문을 구성합니다. 이 작업 주문 유형은 철회 칸반에 대한 피킹 프로세스만 지원하지 않습니다. 또한 제조 간판의 피킹 프로세스를 지원합니다. 그러나 웨이브 템플릿, 작업 템플릿 및 위치 지시문을 분리하여 각 칸반 유형에 대해 별도의 선택 프로세스를 구성할 수 있습니다. 웨이브 템플릿, 작업 템플릿 및 위치 지시문을 분리하려면 해당 엔터티에 대한 쿼리에서 활동 유형(**프로세스** 또는 **전송**)에 대한 기준을 설정합니다.

## <a name="configure-the-withdrawal-kanban"></a>철회 칸반 구성

철회 칸반에 사용되는 이전 활동은 린 생산 흐름에서 활성화된 활동 계획의 일부로 구성됩니다. 전송 활동 구성의 일부로 전송에 대한 "시작" 및 "종료" 위치를 지정합니다. 전송 활동을 구성한 후에는 이를 **철회** 유형의 칸반 규칙에 할당할 수 있습니다. 칸반 규칙은 철회 칸반에 대한 정책 및 구성을 설정합니다. 칸반 수량은 이전 프로세스 동안 칸반이 운반하는 처리 단위의 단위 수를 정의합니다. 고정 간판 수량은 고정 보충 전략이 선택될 때 사용됩니다. 이 수량은 재고를 방지하거나 수요 소스에서 재고가 소진되는 것을 방지하기 위해 필요한 칸반 수를 정의합니다. 고정 수량은 실제 수요, 과거 수요 및 서비스 수준을 기반으로 계산할 수 있습니다. 다음 두 시나리오는 철회 칸반을 사용하는 자재 보충을 관리하는 방법을 설명합니다.

## <a name="scenario-1-replenish-a-production-input-location-by-using-a-fixed-withdrawal-kanban"></a>시나리오 1: 고정 철회 칸반을 사용하여 생산 입력 위치 보충

제조 프로세스는 생산 창고에 있는 생산 입력 위치에서 구매한 원자재를 소비합니다. 공급업체로부터 원자재를 받으면 자재 창고의 위치에 저장됩니다. 자재에 대한 수요가 일정 기간 동안 안정적인 것으로 간주되기 때문에 고정 수량 칸반 흐름으로 생산을 공급하도록 설정되었습니다. 생산 입력 위치에서 칸반이 소비되면 빈 신호가 등록되고 동일한 유형의 새 칸반이 흐름에 추가됩니다. 

칸반이 완료되면 빈 신호가 자동으로 발생하도록 구성할 수 있습니다. 또는 빈 신호를 칸반 전송 보드 또는 휴대용 디바이스의 메뉴에서 제공되는 수동 상호 작용으로 설정할 수 있습니다. 칸반 전송 보드는 칸반 수명 주기의 모든 활동이 관리되는 작업 공간입니다. 

칸반이 생성되면 원자재에 대한 웨이브 라인이 자재 창고에 대한 칸반 웨이브에 추가됩니다. 칸반 전송 보드의 불출 목록 섹션에서는, 웨이브 생성부터 작업 생성에 이르기까지 자재나 관련 창고 공정의 상황을 감시할 수 있어 자재가 "전송 시작" 위치에 현재고로 있어 생산 입력 위치로 이송할 수 있는 상태가 됩니다. 칸반은 칸반 전송 보드나 휴대용 디바이스의 메뉴에서 완료할 수 있습니다. 

이 시나리오에서 자재 창고의 피킹 작업은 하나의 활동으로 처리됩니다. 자재 창고와 생산 창고 간의 이전 활동은 별도의 활동으로 처리됩니다. 이 접근 방식은 예를 들어 두 창고 사이에 물리적 거리가 먼 경우에 유용할 수 있습니다. 이 경우 칸반 이전 활동은 트럭 적재를 나타낼 수 있습니다. 

창고 위치와 생산 입력 위치 사이의 거리가 작은 경우 피킹 프로세스에 이전 활동을 포함하는 것이 더 효율적일 수 있습니다. 그런 다음 자재를 피킹한 후 생산 입력 위치에 직접 넣을 수 있습니다. 이 프로세스를 지원하기 위해 철회 칸반의 선택 작업이 처리될 때 자동으로 완료되도록 이전 활동을 구성합니다.

## <a name="scenario-2-automatically-complete-the-transfer-activity-when-kanban-picking-work-is-processed"></a>시나리오 2: 칸반 피킹 작업이 처리될 때 이전 활동을 자동으로 완료합니다.

다음 시나리오에서 철회 칸반의 이전 활동은 동일한 창고의 두 위치 간에 이전하도록 구성됩니다. 철회 칸반의 전송 활동은 자동으로 완료되도록 설정됩니다. 

[![칸반 피킹 작업이 처리되면 전송 작업이 자동으로 완료됩니다.](./media/transfer-activities-when-processing-kanban-picking.png)](./media/transfer-activities-when-processing-kanban-picking.png)

1.  원자재 및 생산을 위한 공유 창고
2.  원자재 창고 위치
3.  칸반 "시작" 위치 및 창고 작업 위치 지정
4.  철회 칸반
5.  생산 입력 위치
6.  제조 공정

생산 입력 위치에서 칸반을 소비하면 칸반이 비어 있다고 보고되고 흐름에 새로운 칸반이 추가됩니다. 칸반이 생성되면 칸반 웨이브에 물결선이 추가됩니다. 칸반 웨이브가 처리되면 칸반 피킹을 위한 창고 작업이 생성됩니다. 창고 작업자는 칸반 피킹 작업을 처리하고 작업의 지시를 받아 창고 위치에서 칸반에 대한 자재를 피킹합니다. 이 창고 작업자가 피킹을 확인하면 칸반이 자동으로 완료되고 창고 작업자가 자재를 생산 입력 위치로 투입하도록 안내합니다.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]