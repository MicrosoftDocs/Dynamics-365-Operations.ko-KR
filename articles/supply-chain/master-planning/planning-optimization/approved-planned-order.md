---
title: 계획 주문 보기, 관리 및 승인
description: 이 항목에서는 Planning Optimization에서 계획 주문을 보고, 관리하고, 승인하는 방법에 대한 정보를 제공합니다.
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 2d7daac5a33c77e1b49f689061a8dbcf17c3a1d3501461cf3abc0e9cac5121ba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446635"
---
# <a name="view-manage-and-approve-planned-orders"></a>계획 주문 보기, 관리 및 승인

[!include [banner](../../includes/banner.md)]

이 항목에서는 Planning Optimization에서 계획 주문을 보고, 관리하고, 승인하는 방법에 대한 정보를 제공합니다.

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a>계획 주문 보기 및 관리

계획 주문 목록 페이지에서 계획 주문을 보고 관리할 수 있습니다. 작업하려는 계획 주문 유형에 따라 다음 위치 중 하나로 이동합니다.

- 마스터 플래닝 \> 작업 영역 \> 마스터 플래닝
- 마스터 플래닝 \> 마스터 플래닝 \> 계획 주문
- 생산 관리 \> 생산 주문 \> 계획된 생산 주문
- 조달 및 소싱 \> 구매 주문 \> 계획된 구매 주문
- 재고 관리 \> 인바운드 주문 \> 계획된 전송
- 재고 관리 \> 아웃바운드 주문 \> 계획된 전송

## <a name="view-and-edit-the-status-of-planned-orders"></a>계획 주문 상태 보기 및 편집

각 계획된 주문의 **상태** 필드를 사용하여 진행 상황을 추적하거나 계획 주문이 처리되는 방식을 변경할 수 있습니다. 다음과 같은 **상태** 값을 사용할 수 있습니다.

- **미처리** – 기준 계획에서 계획 주문을 생성할 때 이 상태가 제공됩니다. 이 상태의 계획 주문은 다음 계획 실행 중에 삭제됩니다.
- **완료됨** – 이 상태는 계획 주문이 완료되었음을 나타냅니다. 계획 주문을 확정하지 않기로 결정한 경우 수동으로 상태를 *완료됨* 으로 변경할 수 있습니다. 시스템은 *미처리* 와 *완료됨* 상태를 같은 방식으로 처리합니다.
- **승인됨** – 이 상태는 계획 주문이 확정 승인되었음을 나타냅니다. 계획 주문을 확정하려는 경우 상태를 *승인됨* 으로 변경할 수 있습니다. 계획 주문에 대한 편집 내용을 유지하거나 계획 주문을 확정하려는 경우 상태를 *승인됨* 으로 변경합니다. 상태가 *승인됨* 인 계획 주문은 기준 계획에 의해 고정되고 예상되는 공급으로 간주됩니다. 따라서 이후 기준 계획 실행 중에 수정되거나 삭제되지 않습니다. 이 동작을 수행하기 위해 계획 논리는 상태가 *승인됨* 인 계획 주문을 기준 계획 중에 이전 계획 버전에서 새 계획 버전으로 복사합니다. 상태가 *승인됨* 인 계획 주문은 특정 기준 계획 내에만 공급하는 것으로 간주됩니다.

단일 계획 주문의 상태를 변경하려면 [계획 주문 목록 페이지를 열고](#view-planned-orders), 주문을 연 후 다음 단계 중 하나를 따르세요.

- **일반** 빠른 탭에서 **상태** 필드의 값을 변경합니다.
- 작업 창의 **계획 주문** 탭에서 **프로세스** 그룹에 있는 **상태 변경** 을 선택합니다.
- 작업 창에서 **승인** 을 선택하여 주문을 승인됨으로 표시합니다.

여러 계획 주문의 상태를 동시에 변경하려면 [계획 주문 목록 페이지를 열고](#view-planned-orders), 변경하려는 각 주문의 확인란을 선택한 후 다음 단계 중 하나를 따릅니다.

- 작업 창의 **계획 주문** 탭에서 **프로세스** 그룹에 있는 **상태 변경** 을 선택합니다.
- 작업 창에서 **승인** 을 선택하여 주문을 승인됨으로 표시합니다.

## <a name="approve-planned-orders"></a>계획 주문 승인

계획 주문 승인은 계획 주문에서 확정 주문을 생성하는 프로세스의 선택적 단계입니다.

다음 그림은 승인 워크플로를 구현하기 위해 각 계획 주문에 할당된 **상태** 값을 사용하는 방법을 보여줍니다. 승인 프로세스를 구현하려면 이전 섹션에서 설명한 대로 각 계획 주문의 **상태** 값을 수동으로 조정합니다.

![계획된 주문 흐름.](media/approved-planned-orders-1.png)

> [!TIP]
> 수정된 계획 주문을 승인하는 것이 좋습니다. 그렇지 않으면 편집 내용이 무시되고 다음 계획 실행에서 덮어씁니다.

## <a name="additional-resources"></a>추가 리소스

- [확정 계획 주문](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
