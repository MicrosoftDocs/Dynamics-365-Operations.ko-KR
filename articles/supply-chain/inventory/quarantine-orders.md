---
title: 격리 명령
description: 이번에는 격리 명령을 사용하여 재고를 차단하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5cf0ec8f9f4d862724cb8ab72b48771ed68eaf39
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448147"
---
# <a name="quarantine-orders"></a>격리 명령

[!include [banner](../includes/banner.md)]

이번에는 격리 명령을 사용하여 재고를 차단하는 방법에 대해 설명합니다.

격리 명령을 사용하면 재고를 차단할 수 있습니다. 예를 들어 품질 관리를 위해 품목을 격리할 수 있습니다. 격리된 재고는 격리 창고로 이전됩니다.

> [!NOTE]
> 고급 창고 관리 프로세스(창고 관리 내)를 사용하는 경우 격리 주문 처리는 반품 판매 주문에만 사용됩니다.

## <a name="quarantine-on-hand-inventory-items"></a>현 재고 품목 격리

품목을 격리할 때 격리 명령을 수동으로 생성하거나 인바운드 처리 중에 자동으로 생성하도록 시스템을 설정할 수 있습니다.

격리 명령을 자동으로 생성하도록 시스템을 설정하려면 다음 단계를 따르십시오.

1. **재고 관리 \> 설정 \> 재고 \> 품목 모델 그룹** 으로 이동합니다.
1. 목록 창에서 관련 모델 그룹을 선택하거나 새 모델 그룹을 생성합니다.
1. **재고 정책** 빠른 탭에서 **격리 관리** 확인란을 선택합니다.
1. 페이지를 닫습니다.
1. 입고 창고에 대한 **격리 창고** 필드에서 기본 격리 창고를 지정하세요.

창고에 입고된 것으로 등록된 품목이 **격리 관리** 확인란이 선택된 모델 그룹에 속하는 경우 격리 명령이 생성됩니다. 격리 명령은 근로자에게 물품을 격리 창고로 옮기도록 지시합니다.

**격리 주문** 페이지에서 격리 주문을 수동으로 생성하는 경우 관련 품목 모델 그룹에서 격리 관리를 위해 품목을 설정할 필요가 없습니다. 이 프로세스의 경우 격리해야 하는 현 재고와 사용해야 하는 격리 창고를 지정해야 합니다. 격리 명령 상태를 사용하여 프로세스를 계획할 수 있습니다.

## <a name="quarantine-order-statuses"></a>격리 명령 상태

격리 명령의 상태는 다음과 같습니다.

- 생성됨
- 시작됨
- 완료된 것으로 보고됨
- 종료됨

### <a name="created"></a>생성됨

격리 명령이 수동으로 생성되었지만 품목이 아직 격리 창고에 없는 경우 격리 명령은 **생성됨** 상태가 됩니다. 두 개의 재고 거래가 생성됩니다. 한 거래는 **주문 중**, **물리적으로 예약됨** 또는 **선택됨** 상태를 가질 수 있는 발행 거래입니다. 다른 거래는 격리 창고에서 **주문됨** 또는 **등록됨** 상태를 가질 수 있는 입고 거래입니다. 일반적인 프로세스를 사용하여 재고 업데이트를 예약, 선택 및 등록할 수 있습니다.

### <a name="started"></a>시작됨

격리 주문 상태가 **시작됨** 인 경우 재고가 일반 창고에서 격리 창고로 이전되고 두 개의 재고 거래가 생성됩니다. 한 거래는 **공제됨** 상태이고 다른 거래는 **수령됨** 상태입니다. 동시에 반품 전송을 처리하기 위해 두 개의 재고 거래가 생성됩니다. 이 거래는 날짜가 없습니다. 한 거래의 상태는 **물리적으로 예약됨** 이고 다른 거래의 상태는 **주문됨** 입니다.

### <a name="reported-as-finished"></a>완료된 것으로 보고됨

시작된 격리 주문을 완료된 것으로 보고하려면 주문을 열고 작업 창에서 **완료된 것으로 보고** 를 선택합니다. 품목이 격리 구역에서 해제되었지만 아직 일반 창고로 다시 이동되지 않았습니다. 정규 창고로의 복귀는 완제품으로 보고하는 동안 초기화될 수 있는 품목 도착 일지를 통해 처리될 수 있습니다.

### <a name="ended"></a>종료됨

격리 명령이 종료되면 격리 창고에서 일반 창고로 다시 이동합니다. 물품 거래 상태는 격리 창고에서 *판매됨*, 일반 창고에서 *구매됨* 으로 설정되어 있습니다.

## <a name="quarantine-order-scrap"></a>격리 주문 스크랩

격리 명령 프로세스의 일부로 재고를 폐기할 수 있습니다. 스크랩을 처리할 때 재고 상태는 격리 창고의 출고 거래에 의해 *판매됨* 으로 설정됩니다.

## <a name="additional-resources"></a>추가 리소스

- [재고 차단](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
