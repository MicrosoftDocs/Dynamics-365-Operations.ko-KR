---
title: 연기
description: 이 토픽에서는 기준 계획의 연기 날짜에 대한 정보를 제공합니다. 연기 날짜는 기준 계획에서 계산하는 가장 빠른 주문 이행 날짜가 요청 날짜보다 늦은 경우 트랜잭션이 받는 현실적인 만기 날짜입니다.
author: ChristianRytt
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e89830feea12b4f5703e0eda622729887dd9bf46
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448651"
---
# <a name="delays"></a>연기

[!include [banner](../includes/banner.md)]

이 토픽에서는 기준 계획의 연기 날짜에 대한 정보를 제공합니다. 연기 날짜는 기준 계획에서 계산하는 가장 빠른 주문 이행 날짜가 요청 날짜보다 늦은 경우 트랜잭션이 받는 현실적인 만기 날짜입니다.

기준 계획은 리드 타임, 자재 가용성, 용량 가용성 및 다양한 계획 매개 변수를 기반으로 트랜잭션의 가장 빠른 주문 이행 날짜를 계산할 수 있습니다. 

기준 계획에서 현재 날짜보다 앞선 주문 날짜를 계산하면 주문을 제시간에 이행할 수 없습니다. 따라서 주문이 연기됩니다. 이 경우 기준 계획은 현재 일자부터 주문을 앞으로 계획하고 리드 타임을 포함합니다. 이러한 리드 타임은 하위 수준 구성 요소 항목에서 시작됩니다. 그러면 주문이 연기된 날짜를 받습니다. 연기된 날짜는 현재 데이터를 기반으로 하는 실제 기한입니다. 기준 계획에서는 연기 일수도 계산합니다. 

사용자가 대체 배달 모드를 선택하여 리드 타임을 단축할 수 있다는 것을 알고 있는 경우와 같은 일부 상황에서는 연기를 계산하지 않도록 선택할 수 있습니다. 

서비스 그룹에 대해 연기를 계산하는 방법을 구성할 수 있습니다. 그런 다음 나중에 항목에 적용 범위 그룹을 연결할 수 있습니다. 

**기준 계획 매개 변수** 페이지에서 연기 계산을 위한 시작 시간을 설정할 수 있습니다. 이 시간 이후에 주문이 완료되면 주문의 연기 날짜에 하루의 연기가 추가됩니다. 

> [!NOTE]
> 이전 버전에서는 계산된 연기를 *선물 메시지*, 연기된 날짜를 *선물 날짜*, 연기된 트랜잭션을 *미래에 설정된 트랜잭션* 이라고 했습니다.

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a>여러 BOM 수준으로 생산 설정 연기 제한
여러 BOM 수준이 있는 생산 설정에서 연기로 작업하는 경우 연기를 유발하는 항목(BOM 구조에서) 바로 위에 있는 항목만 기준 계획 실행의 일부로 연기로 업데이트된다는 점에 유의하는 것이 중요합니다. BOM 구조의 다른 항목은 최상위 수준에 대한 계획 주문이 승인되거나 확정되는 첫 번째 기준 계획 실행까지 연기가 적용되지 않습니다. 

이 알려진 제한 사항을 해결하기 위해 연기가 있는 BOM 구조의 맨 위에 있는 생산 주문은 다음 기준 계획 실행 전에 승인(또는 확정)될 수 있습니다. 이렇게 하면 연기된 승인된 계획 생산 오더의 연기가 유지되고 이에 따라 모든 기본 구성 요소가 업데이트됩니다.
BOM 구조의 다른 연기로 인해 나중 날짜로 이동할 수 있는 계획 주문을 식별하는 데 작업 메시지를 사용할 수도 있습니다.

## <a name="desired-date"></a>원하는 날짜

**계획된 주문** 페이지의 **연기** 탭 아래에는 계획된 주문의 **원하는 날짜** 가 있습니다. 계획 주문의 원하는 날짜는 연기에 대한 기준 날짜이며, 이는 **순 소요량** 에서 계산된 **요청 날짜** 와 동일한 계산 날짜입니다. 계획 주문이 BOM 라인, 생산 라인 또는 칸반 라인인 경우 원하는 날짜는 **요구 사항 날짜** 를 기준으로 하며 원하는 날짜는 **계획된 주문** 페이지에 표시되지 않습니다.

## <a name="additional-resources"></a>추가 리소스

[적용 범위 설정](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]