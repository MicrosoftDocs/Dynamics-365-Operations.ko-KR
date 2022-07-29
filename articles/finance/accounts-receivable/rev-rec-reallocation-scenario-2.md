---
title: 수익 인정 재할당 - 시나리오 2
description: 이 항목에서는 판매 주문을 두 개 입력했고, 첫 번째 판매 주문이 청구된 후에 고객이 계약에 항목을 추가하는 재할당 시나리오를 살펴봅니다. 새 항목이 계약에 추가되면 새 판매 주문이나 기존 판매 주문에 이 항목을 추가할 수 있습니다.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1fe195f171e8e343e9ce01b2ca0d4980d193a6fd3d9aa6f95efed66a29aa7d6d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452827"
---
# <a name="revenue-recognition-reallocation--scenario-2"></a>수익 인정 재할당 - 시나리오 2

[!include [banner](../includes/banner.md)]

이 항목에서는 판매 주문을 두 개 입력했고, 첫 번째 판매 주문이 청구된 후에 고객이 계약에 항목을 추가하는 재할당 시나리오를 살펴봅니다. 새 항목이 계약에 추가되면 새 판매 주문이나 기존 판매 주문에 이 항목을 추가할 수 있습니다.

이 시나리오의 경우 **총계정원장 매개 변수** 페이지의 **수익 인정** 탭에서 **수취 계정에 송장 수정 게시** 옵션이 **아니요** 로 설정되어 있습니다(**수익 인정 \> 설정 \> 총계정원장 매개 변수**).

[![수취 계정에 송장 수정 게시 옵션이 아니요로 설정되어 있습니다.](./media/12_rev-rec-scenarios.png)](./media/12_rev-rec-scenarios.png)

고객 US\_SI\_0003에 대한 판매 주문이 생성됩니다. 고객이 노트북을 위한 설치 서비스(항목 번호 S0001) 및 지원 계획(항목 번호 S0008)을 구매하는 중에 아직까지 노트북을 선택하지 않았습니다. 설치 서비스에 대한 수익은 노트북을 구입한 날짜까지 이연됩니다. 지원 계획에 대한 수익은 계약의 날짜 범위에 정의된 대로 12개월 동안 이연되고 인정됩니다.

[![설치 서비스 및 지원 계획에 대한 판매 주문 라인](./media/13_rev-rec-scenarios.png)](./media/13_rev-rec-scenarios.png)

판매 주문이 확정됩니다. 두 항목 모두 수익 가격 할당이 설정되어 있기 때문에 판매 주문이 확정되면 수익 가격이 계산됩니다. **수익 가격 할당** 페이지에서 인정된 수익을 볼 수 있습니다(**판매 주문** 페이지, 작업 창, **관리** 탭, **수익 인정** 그룹에서 **수익 가격 할당** 선택). 설치 서비스에 대한 수익은 이연 수익 계정에 $250.00로 게시됩니다. 지원 계획에 대한 수익도 이연 수익에 $150.00로 게시됩니다. 수익 가격의 합은 수익 가격 할당($400.00)을 캡처하기 위해 설정한 라인의 합과 같아야 합니다.

[![수익 가격 재할당 페이지](./media/14_rev-rec-scenarios.png)](./media/14_rev-rec-scenarios.png)

판매 주문이 완전하게 확정됩니다. 다음 그림은 송장에 대해 게시된 회계 기입을 보여 줍니다.

[![100% 청구된 판매 주문에 대한 회계 기입](./media/15_rev-rec-scenarios.png)](./media/15_rev-rec-scenarios.png)

수익 인정 일정도 생성되지만 수익이 아직 인식되지 않습니다.

[![수익 인정 일정 페이지](./media/16_rev-rec-scenarios.png)](./media/16_rev-rec-scenarios.png)

며칠 후 고객이 노트북을 선택합니다. 고객에 대해 두 번째 판매 주문이 입력됩니다.

[![노트북에 대한 매도 주문 라인](./media/17_rev-rec-scenarios.png)](./media/17_rev-rec-scenarios.png)

두 번째 판매 주문이 확정됩니다. 이 판매 주문에 라인이 하나만 포함되어 있으므로 판매 주문이 확정되면 수익 가격 할당이 수행되지 않습니다. 수익 가격 할당은 고유 항목이 두 개 이상 있고 해당 항목이 수익 가격 할당을 위해 설정된 경우에만 발생합니다.

고객 계약에서 변경된 유일한 사항이 이 새 판매 주문이면 재할당 프로세스를 실행할 수 있습니다. 두 판매 주문 중 하나에서 **새 주문 라인으로 가격 재할당** 을 선택해 **새 주문 라인으로 가격 재할당** 페이지를 엽니다. 또는 **수익 인정 \> 정기 작업 \> 새 주문 라인으로 가격 재할당** 으로 이동합니다. 판매 주문 두 개와 해당 판매 주문 라인을 선택한 다음 **재할당 업데이트** 를 선택합니다. **재할당된 금액** 열에 각 판매 주문 라인에 대한 새로운 수익 가격이 표시됩니다.

[![새 주문 라인으로 가격 재할당 페이지의 새 수익 가격](./media/18_rev-rec-scenarios.png)](./media/18_rev-rec-scenarios.png)

다음으로 **예상 쿠폰** 을 선택해 총계정원장에만 게시될 회계 기입을 봅니다. **총계정원장 매개 변수** 페이지에서 **수취 계정에 송장 수정 게시** 옵션이 **아니요** 로 설정되어 있기 때문에 재할당을 처리해도 수취 계정에서 아무것도 변경되지 않습니다.

[![예상 쿠폰 페이지의 회계 기입](./media/19_rev-rec-scenarios.png)](./media/19_rev-rec-scenarios.png)

**예상 쿠폰** 페이지에서 마지막 세 줄은 게시된 송장의 원래 회계 기입을 반전합니다. 첫 네 줄은 송장에 대해 게시된 새로운 회계 기입을 구성합니다. 고객에게 새 송장이 제공되지 않는다는 점을 이해해야 합니다. 재할당 후에도 고객이 여전히 $426.00를 빚지고 있습니다. 이 금액은 수취 계정의 새 회계 기입에 게시해야 합니다. 상계 세금과 이연 수익은 $188.69 + $314.48 + $26.00 = $529.17입니다. 재할당으로 인해 이연 수익 금액이 변경되었습니다. $103.17의 차액은 부분 송장 수익 정산 계정에 게시됩니다. 이 잔액은 재할당에 포함된 두 번째 판매 주문에 대한 송장이 게시될 때 반제됩니다.

재할당을 완료하려면 **처리** 를 선택합니다. 아무것도 게시되지 않은 경우에도 게시 날짜를 묻는 메시지가 표시됩니다. 재배치 완료 후 각 판매 주문의 **수익 가격 할당** 페이지에는 두 판매 주문의 모든 항목에 대한 가격 할당이 표시됩니다. 다시 말해 각 판매 주문의 **수익 가격 할당** 페이지가 동일한 계약의 일부이지만 다른 판매 주문에 있기 때문에 해당 판매 주문에 존재하지 않는 항목이 포함됩니다.

> [!TIP]
> 이러한 추가 항목이 표시되는 이유에 대한 컨텍스트를 제공하기 위해 **재할당 ID** 및 **판매 주문** 같은 다른 열을 그리드에 추가할 수 있습니다.
> 
> [![수익 가격 재할당 페이지의 추가 열](./media/20_rev-rec-scenarios.png)](./media/20_rev-rec-scenarios.png)

판매 주문 00036에서 새 수익 재할당 가격을 기반으로 수익 인정 일정도 업데이트되었습니다. 이 판매 주문에서 **수익 인정 일정** 페이지를 엽니다. 이전에는 항목 S0008에 대해 13개의 라인이 있었습니다(12개월 일정이 이 항목에 할당됨). 지금은 원래 일정 라인 13개, 역일정 라인 13개, 새 수익 가격을 기반으로 하는 라인 13개로 이루어진 39개의 라인이 있습니다.

[![항목 S0008의 경우 39개의 라인으로 수익 인정 일정 페이지가 업데이트되었습니다.](./media/21_rev-rec-scenarios.png)](./media/21_rev-rec-scenarios.png)

마찬가지로 이전에는 항목 S0001에 라인이 두 개 있었지만 지금은 6개가 있습니다.

[![항목 S0001의 경우 6개의 라인으로 수익 인정 일정 페이지가 업데이트되었습니다.](./media/22_rev-rec-scenarios.png)](./media/22_rev-rec-scenarios.png)

판매 주문 000036에서 **쿠폰** 을 선택하면 송장 분개장에 원래 회계 기입이 표시됩니다. 판매 주문에서 반전 기입과 새 회계 기입을 보려면 작업 창에서 **수익 조정** 을 선택한 후 **쿠폰** 을 선택합니다.

[![판매 주문 000036](./media/23_rev-rec-scenarios.png)](./media/23_rev-rec-scenarios.png)

다음으로 **모든 고객** 페이지(**수취 계정 \> 고객 \> 모든 고객**)를 열고 고객 **US\_SI\_0003** 울 선택한 다음 **거래** 를 선택합니다. 판매 주문 000036의 미결 송장이 표시됩니다. 쿠폰을 선택하면 재할당의 새 회계 항목이 아닌 원래 회계 기입이 표시됩니다. 반대 기입과 새 회계 기입은 수취 계정에서 볼 수 없습니다.

이제 두 번째 판매 주문이 확정됩니다. 고객에게 제공되는 전체 송장은 $1,099.00 + $71.44 tax = $1,170.44입니다. 다음 그림은 게시된 회계 기입을 보여 줍니다.

[![게시된 회계 기입이 있는 쿠폰 거래 페이지](./media/24_rev-rec-scenarios.png)](./media/24_rev-rec-scenarios.png)

수익과 매출의 합이 $1,170.44보다 크므로 -$130.17에 대한 차액이 게시됩니다. 이 금액은 부분 송장 수익 정산 계정에서 잔액을 정산합니다. 잔액은 재할당 후 새 회계 기입에서 게시됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]