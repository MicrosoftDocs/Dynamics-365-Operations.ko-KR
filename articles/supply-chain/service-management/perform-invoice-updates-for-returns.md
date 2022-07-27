---
title: 반품에 대한 송장 업데이트 수행
description: 이 기능은 반품 주문과 판매 주문이 동시에 같은 사람에 의해 청구되도록 선택한 조직의 비즈니스 프로세스를 지원합니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 736496a0499e70987f80f3d4687414371606cd8c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449140"
---
# <a name="perform-invoice-updates-for-returns"></a>반품에 대한 송장 업데이트 수행 

[!include [banner](../includes/banner.md)]


반품 주문은 반품된 주문으로 표시된 판매 주문 유형입니다. 따라서 **모든 판매 주문** 목록 페이지는 **반품 주문** 대신 반품 주문에 대한 송장을 생성하는 데 사용됩니다. 이 기능은 반품 주문과 판매 주문이 동시에 같은 사람에 의해 청구되도록 선택한 조직의 비즈니스 프로세스를 지원합니다.

반품된 품목에 대한 송장은 음수 금액에 대한 것이므로 대변표라고 합니다.

일괄 처리를 위해 송장 업데이트를 설정할 때 유형 **반품된 주문** 의 판매 주문은 반품 라인 상태는 **수신됨** 이어야 합니다. 이는 주문의 포장 전표가 업데이트되었음을 나타냅니다.

## <a name="post-an-invoice-for-a-return-order"></a>반품 주문에 대한 송장 전기

1.  **수취 계정** \> **공통** \> **판매 주문** \> **모든 판매 주문** 을 클릭합니다.

2.  **반품된 주문** 이 **주문 유형** 필드에 표시되는 판매 주문을 선택합니다.

3.  작업 창의 **송장** 탭에 있는 **생성** 그룹에서 **송장** 을 클릭합니다.

4.  **매개 변수** 탭에서 **전기** 확인란을 선택합니다.

5.  양식의 정보를 검토하고 필요한 경우 변경합니다.

6.  **확인** 을 클릭합니다. 대변표가 전기됩니다.

## <a name="see-also"></a>참고 항목

[반품을 위해 포장 전표 업데이트](packing-slip-updates-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]