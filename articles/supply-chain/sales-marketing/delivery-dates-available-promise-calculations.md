---
title: 주문 약속
description: 이 토픽에서는 주문 약속에 대한 정보를 제공합니다. 주문 약속은 고객에게 배송 날짜를 확실하게 약속하는 데 도움이 되며 해당 날짜를 맞출 수 있도록 유연성을 제공합니다.
author: Henrikan
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesATP, SalesAvailableDlvDates, SalesCarrier
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193933
ms.assetid: 676fc53a-fa25-4688-9f26-1005316763b8
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f7535ba28358fef21784956da38cd334a4aebe7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448540"
---
# <a name="order-promising"></a>주문 약속

[!include [banner](../includes/banner.md)]

이 토픽에서는 주문 약속에 대한 정보를 제공합니다. 주문 약속은 고객에게 배송 날짜를 확실하게 약속하는 데 도움이 되며 해당 날짜를 맞출 수 있도록 유연성을 제공합니다.

주문 약속은 가장 빠른 출고 일자와 입고 일자를 산정하며, 배송 일자 관리 방식과 운송 일자를 기준으로 합니다. 네 가지 배달 날짜 제어 방법 중에서 선택할 수 있습니다.

-   **판매 리드 타임** – 판매 리드 타임은 판매 주문 생성과 항목 배송 사이의 시간입니다. 배달 날짜 계산은 기본 일수를 기반으로 하며 재고 가용성, 알려진 수요 또는 계획된 공급을 고려하지 않습니다.
-   **ATP(약속 가능 재고)** – ATP는 사용 가능하고 특정 날짜에 고객에게 약속할 수 있는 항목의 수량입니다. ATP 계산에는 미약정 재고, 리드 타임, 계획 입고 및 출고가 포함됩니다.
-   **ATP + 발행 마진** – 배송 날짜는 ATP 날짜에 품목의 발행 마진을 더한 날짜와 같습니다. 발행 마진은 선적을 위해 품목을 준비하는 데 필요한 시간입니다.
-   **CTP(주문 이행 가능)** – 가용성은 폭발을 통해 계산됩니다.

> [!NOTE]
> 판매 주문이 업데이트되면 다음 예와 같이 기존 주문 약속 날짜를 이행할 수 없는 경우에만 주문 약속 정보가 업데이트됩니다.
> 
> - **예시 1**: 현재 주문 예정일은 7월 20일이지만, 수량 증가로 인해 7월 25일까지 배송이 되지 않습니다. 현재 날짜를 더 이상 맞출 수 없기 때문에 주문 약속이 트리거됩니다.
> -  **예시 2**: 현재 주문 예정일은 7월 20일이지만, 수량 감소로 인해 7월 15일에 배송이 가능합니다. 그러나 현재 날짜가 아직 이행될 수 있으므로 주문 약속이 실행되지 않으며 7월 20일이 주문 약속 날짜로 남아 있습니다.

## <a name="atp-calculations"></a>ATP 계산
ATP 수량은 "예측이 포함된 누적 ATP" 방법을 사용하여 계산됩니다. 이 ATP 계산 방법의 주요 이점은 입고 간의 출고 합계가 최신 입고보다 많은 경우(예: 요구사항을 충족하기 위해 이전 입고의 수량을 사용해야 하는 경우)를 처리할 수 있다는 것입니다. "예측이 있는 누적 ATP" 계산 방법은 입고할 누적 수량이 출고할 누적 수량을 초과할 때까지 모든 출고를 포함합니다. 따라서 이 ATP 계산 방법은 이전 기간의 수량 중 일부를 이후 기간에 사용할 수 있는지 여부를 평가합니다.  

ATP 수량은 첫 번째 기간의 미약정 재고 잔액입니다. 일반적으로 영수증이 예약된 각 기간에 대해 계산됩니다. 프로그램은 ATP 기간을 일 단위로 계산하고 현재 일자를 ATP 수량의 첫 번째 일자로 계산합니다. 첫 번째 기간에서 ATP에는 현재고에서 납기 및 기한이 지난 고객 주문을 뺀 값이 포함됩니다.  

ATP는 다음 공식을 사용하여 계산됩니다.  

ATP = 이전 기간에 대한 ATP + 현재 기간에 대한 입고 – 현재 기간에 대한 출고 – 미래 기간을 포함하여 미래 기간까지의 모든 미래 기간에 대한 입고 합계가 초과하는 기간까지 각 미래 기간에 대한 순 출고 수량 미래 기간을 포함한 문제의 합계.  

ATP 계산에는 시스템이 어떤 수량을 약속할 수 있을 때 예상하는 ATP 타임펜스 이후 및 만료 날짜에 대한 정보가 포함되지 않습니다.

더 이상 고려할 출고 또는 입고가 없는 경우 다음 일자의 ATP 수량은 가장 최근에 계산된 ATP 수량과 동일합니다.  

ATP 확인이 완료될 때 품목에 사용된 모든 차원이 제공되지 않은 경우에도 출고 및 입고에 지정할 수 있습니다. 이 경우 ATP 계산에서 입고 및 출고를 기존 차원으로 집계하여 ATP 계산에 사용되는 입고 및 출고 라인 수를 줄여야 합니다.  

표시되는 ATP 수량은 항상 0(영)보다 크거나 같습니다. 계산에서 음수 ATP 수량을 반환하는 경우(예: 이전에 약속한 수량이 가용 수량을 초과하는 경우) 수량은 자동으로 0으로 설정됩니다.

### <a name="example"></a>예

**ATP 후방 수요 타임 펜스** 필드는 지연된 수요 주문 또는 재고 문제를 찾기 위해 시간을 얼마나 거슬러 올라가야 하는지를 제어합니다. **ATP 후방 공급 타임 펜스** 필드는 지연된 공급 주문 또는 재고 입고를 찾기 위해 시간을 얼마나 거슬러 올라가야 하는지를 제어합니다. 예를 들어, 지연된 수요와 공급이 내일 ATP 계산에서 고려되어야 하는 경우 두 필드를 모두 **7** 로 설정해야 합니다.  

**ATP 연기된 수요 상쇄 시간** 및 **ATP 연기된 공급 상쇄 시간** 필드는 연기된 수요 또는 공급이 ATP 계산에서 고려되는 시기를 제어합니다. 예를 들어, 지연된 수요와 공급이 내일 ATP 계산에서 고려되어야 하는 경우 두 필드를 모두 **2** 로 설정해야 합니다. 값 **2** 는 ATP 계산에서 고려해야 하는 지연된 구매 주문의 항목 수량이 현재 날짜로부터 2일 후에 사용 가능한 것으로 표시됨을 의미합니다.  

다음 예의 경우 **ATP 후방 수요 타임펜스** 및 **ATP 후방 공급 타임펜스** 필드에 **7** 이 입력되고 **ATP 연기 수요 상쇄 시간** 및 **ATP 연기 공급 상쇄 시간** 필드에 **1** 이 입력됩니다.  

3일 전에 받았어야 하는 제품 200개 구매 주문이 아직 받지 못했습니다. 따라서 어제 출하되어야 하는 동일한 제품의 75개 품목에 대한 판매 주문 라인이 출하되지 않았습니다.  

고객이 전화를 걸어 동일한 제품 150개를 주문하려고 합니다. 제품의 가용성을 확인하면 제품 100개에 대한 다른 구매 주문이 10일 후에 배달된다는 것을 알게 됩니다.  

제품에 대한 판매 주문 라인을 생성하고 수량으로 **150** 을 입력합니다.  

납품 일자 관리 방법이 ATP이므로 ATP 데이터는 가능한 가장 빠른 출하 일자를 찾기 위해 계산됩니다. 설정에 따라 연기된 구매 오더 및 판매 오더가 고려되고 현재 일자에 대한 결과 ATP 수량이 0입니다. 내일 연기된 구매 주문이 입고될 것으로 예상되는 경우 ATP 수량은 0 이상으로 계산됩니다(이 경우 125로 계산). 단, 지금부터 10일 후 100개 추가 구매 주문 예정인 경우 ATP 수량이 150개 이상이 됩니다.  

따라서 출고일은 ATP 계산에 따라 지금부터 10일로 설정됩니다. 따라서 고객에게 지금부터 10일 이내에 요청한 수량을 배송할 수 있다고 말합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]