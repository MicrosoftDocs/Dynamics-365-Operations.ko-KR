---
title: 수익 인정 재할당 - 시나리오 1
description: 이 항목에서는 판매 주문을 두 개 입력했지만 하나만 확인되는 재할당 시나리오를 살펴봅니다. 세 개 이상의 판매 주문이 확인된 상태인 경우에 동일한 시나리오에서 유사한 결과가 생성됩니다.
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
ms.openlocfilehash: d63082553f8625a9953b0a85d59a4949a37c92770ce2a41a43d78cf0266f3b85
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452830"
---
# <a name="revenue-recognition-reallocation--scenario-1"></a>수익 인정 재할당 - 시나리오 1

[!include [banner](../includes/banner.md)]

이 항목에서는 판매 주문을 두 개 입력했지만 하나만 확인되는 재할당 시나리오를 살펴봅니다. 세 개 이상의 판매 주문이 확인된 상태인 경우에 동일한 시나리오에서 유사한 결과가 생성됩니다.

이 시나리오의 경우 **총계정원장 매개 변수** 페이지의 **수익 인정** 탭에서 **수취 계정에 송장 수정 게시** 옵션이 **아니요** 로 설정되어 있습니다(**수익 인정 \> 설정 \> 총계정원장 매개 변수**).

[![수취 계정에 송장 수정 게시 옵션이 아니요로 설정되어 있습니다.](./media/06_rev-rec-scenarios.png)](./media/06_rev-rec-scenarios.png)

고객 US\_SI\_0003에 대한 판매 주문이 생성됩니다. 고객이 노트북(항목 번호 S0012), 이에 대한 지원 계획(항목 번호 S0008, '지속적인 엔지니어링 서비스')을 구매합니다. 노트북에 대한 수익은 즉시 인정됩니다(수익 인정 일정이 없음). 지원 계획에 대한 수익은 계약의 날짜 범위에 정의된 대로 12개월 동안 이연되고 인정됩니다.

[![노트북 및 지원 계획에 대한 판매 주문 라인](./media/07_rev-rec-scenarios.png)](./media/07_rev-rec-scenarios.png)

판매 주문이 확정됩니다. 두 항목 모두 수익 가격 할당이 설정되어 있기 때문에 판매 주문이 확정되면 수익 가격이 계산됩니다. **수익 가격 할당** 페이지에서 인정된 수익을 볼 수 있습니다(**판매 주문** 페이지, 작업 창, **관리** 탭, **수익 인정** 그룹에서 **수익 가격 할당** 선택). 노트북에 대한 수익은 수익 계정에 $1,008.01로 게시됩니다. 지원 계획에 대한 수익은 이연 수익 계정에 $190.99로 게시됩니다. 수익 가격의 합은 수익 가격 할당($1,199.00)을 캡처하기 위해 설정한 라인의 합과 같아야 합니다.

[![수익 가격 재할당 페이지](./media/08_rev-rec-scenarios.png)](./media/08_rev-rec-scenarios.png)

고객이 판매 당시 설치 서비스(항목 번호 S0001)를 구매하지 않기로 했다가 나중에 마음을 바꾸었습니다. 따라서 동일한 고객에 대해 두 번째 판매 주문이 입력됩니다.

[![설치 서비스에 대한 판매 주문 라인](./media/09_rev-rec-scenarios.png)](./media/09_rev-rec-scenarios.png)

두 번째 판매 주문이 확정됩니다. 이 판매 주문에 라인이 하나만 포함되어 있으므로 판매 주문이 확정되면 수익 가격 할당이 수행되지 않습니다. 수익 가격 할당은 고유 항목이 두 개 이상 있고 해당 항목이 수익 가격 할당을 위해 설정된 경우에만 발생합니다.

고객 계약에서 변경된 유일한 사항이 이 새 판매 주문이면 재할당 프로세스를 실행할 수 있습니다. 두 판매 주문 중 하나에서 **새 주문 라인으로 가격 재할당** 을 선택해 **새 주문 라인으로 가격 재할당** 페이지를 엽니다. 또는 **수익 인정 \> 정기 작업 \> 새 주문 라인으로 가격 재할당** 으로 이동합니다. 판매 주문 두 개와 해당 판매 주문 라인을 선택한 다음 **재할당 업데이트** 를 선택합니다. **재할당된 금액** 열에 각 판매 주문 라인에 대한 새로운 수익 가격이 표시됩니다.

[![새 주문 라인으로 가격 재할당 페이지의 새 수익 가격](./media/10_rev-rec-scenarios.png)](./media/10_rev-rec-scenarios.png)

**예상 쿠폰** 을 선택하면 게시된 송장이 없기 때문에 아무것도 표시되지 않습니다.

재할당을 완료하려면 **처리** 를 선택합니다. 아무것도 게시되지 않은 경우에도 게시 날짜를 묻는 메시지가 표시됩니다. 재배치 완료 후 각 판매 주문의 **수익 가격 할당** 페이지에는 두 판매 주문의 모든 항목에 대한 가격 할당이 표시됩니다. 다시 말해 각 판매 주문의 **수익 가격 할당** 페이지가 동일한 계약의 일부이지만 다른 판매 주문에 있기 때문에 해당 판매 주문에 존재하지 않는 항목이 포함됩니다.

> [!TIP]
> 이러한 추가 항목이 표시되는 이유에 대한 컨텍스트를 제공하기 위해 **재할당 ID** 및 **판매 주문** 같은 다른 열을 그리드에 추가할 수 있습니다.
> 
> [![수익 가격 재할당 페이지의 추가 열](./media/11_rev-rec-scenarios.png)](./media/11_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]