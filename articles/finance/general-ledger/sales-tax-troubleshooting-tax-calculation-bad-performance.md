---
title: 세금 계산 성능이 거래에 영향을 미침
description: 이 항목에서는 세금 계산 성능 및 거래에 대한 영향과 관련된 문제 해결 정보를 제공합니다.
author: shtao
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: da19a83945450c2d35f95be2241b84e407860fe7808ff83934686ca2e00859bc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450517"
---
# <a name="tax-calculation-performance-affects-transactions"></a>세금 계산 성능이 거래에 영향을 미침

[!include [banner](../includes/banner.md)]

때때로 거래가 세금 계산 시 발생하는 성능 문제의 영향을 받습니다. 이 문제를 해결하려면 필요에 따라 다음 섹션의 단계를 따르세요.

## <a name="review-the-transaction-line-count"></a>거래 라인 수 검토

거래에 많은 수의 라인(예: 수백 개 이상)이 있는지 확인합니다. 그렇지 않으면 다음 섹션으로 이동합니다. 거래에 수백 개의 라인이 있으면 세금 계산을 연기합니다. 자세한 내용은 [분개에서 세금 계산 지연 활성화](enable-delayed-tax-calculation.md)를 참조하세요. 

다음은 다음 조건 중 하나라도 해당하는지 확인할 수 있습니다.

- 대용량 파일에서 가져오기 트랜잭션이 있습니다.
- 여러 세션에서 동일한 거래세 계산을 동시에 처리합니다.
- 거래에는 여러 라인이 있으며 보기가 실시간으로 업데이트됩니다. 예를 들어 **일반 분개장** 페이지의 **계산된 판매세 금액** 필드는 라인의 필드가 변경되면 실시간으로 업데이트됩니다.

   [![분개장 전표 페이지의 계산된 판매세 금액 필드.](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)

이러한 조건 중 하나라도 충족되면 세금 계산을 연기하세요.

## <a name="review-the-call-stack"></a>호출 스택 검토

호출 스택을 검토하여 세금 계산이 여러 번 호출되었는지 확인합니다. 그렇지 않으면 다음 섹션으로 이동합니다. 호출 스택이 여러 번 호출되는 경우 다음 단계에 따라 세금 계산 시간을 단축합니다.

1. 분개장이 거래를 고려했다면 세금 계산을 연기합니다. 자세한 내용은 [분개에서 세금 계산 지연 활성화](enable-delayed-tax-calculation.md)를 참조하세요.
2. 거래가 구매 주문이고 애플리케이션 버전이 10.0.15 이후인 경우 **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch** 에 대한 플라이팅을 활성화하여 최종 계산까지 세금 계산을 연기할 수 있습니다.

## <a name="review-the-call-stack-timeline"></a>호출 스택 타임라인 검토

호출 스택 타임라인을 검토하여 다음 문제가 있는지 확인합니다. 그렇다면 **TaxUncommittedDoIsolateScopeFlighting** 의 플라이팅을 활성화하여 문제를 해결합니다.

- 트랜잭션으로 인해 세션이 끝날 때까지 시스템이 응답을 중지합니다. 따라서 트랜잭션이 세금 결과를 계산할 수 없습니다. 다음 그림은 받는 "세션이 종료됨" 메시지 상자를 보여줍니다.

    [![세션 종료 메시지.](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)

- **TaxUncommitted** 메서드가 다른 메서드보다 시간이 오래 걸립니다. 예를 들어 다음 그림에서 **TaxUncommitted::updateTaxUncommitted()** 메서드는 43,347.42초가 걸리지만 다른 메서드는 0.09초가 걸립니다.

    [![메서드 실행 시간.](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)

## <a name="customizing-and-calling-tax-calculation"></a>세금 계산 사용자 지정 및 호출

사용자 지정할 때 각 라인에 **insert()** 또는 **update()** 메서드에서 세금 계산을 호출하지 마세요. 세금 계산은 거래 수준에서 호출해야 합니다.

## <a name="determine-whether-customization-exists"></a>사용자 지정이 있는지 확인

이전 섹션의 단계를 완료했지만 문제가 발견되지 않는 경우 사용자 지정이 있는지 확인하세요. 사용자 지정이 없으면 Microsoft 서비스 요청을 작성하여 추가 지원을 받으세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
