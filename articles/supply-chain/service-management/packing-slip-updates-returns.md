---
title: 반품을 위해 포장 전표 업데이트
description: 반품된 항목이 재고로 입고되기 전에 해당 항목이 속한 주문의 포장 전표를 업데이트해야 합니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f586537aa2d4cb47b0e55e76e401ea6852e1d60
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449302"
---
# <a name="packing-slip-updates-for-returns"></a>반품을 위해 포장 전표 업데이트  

[!include [banner](../includes/banner.md)]


반품된 항목이 재고로 입고되기 전에 해당 항목이 속한 주문의 포장 전표를 업데이트해야 합니다. 송장 업데이트 프로세스가 금융 거래의 업데이트인 것처럼 포장 전표 업데이트 프로세스는 재고 기록의 물리적 업데이트입니다. 즉, 재고에 대한 변경 사항을 커밋합니다. 반품의 경우 포장 전표 업데이트 중에 처리 작업에 할당된 단계가 구현됩니다.

포장 전표 업데이트는 항목 도착 일지 또는 반품 주문에서 처리할 수 있습니다.

포장 전표 전기 프로세스의 일부로 고객의 배송 문서에 있는 포장 전표 참조 번호를 주문 라인과 연결할 수 있습니다. 이 연결은 선택 사항이며 참조용입니다. 트랜잭션 업데이트를 생성하지 않습니다.

예상 반품 항목이 모두 도착하지 않은 경우 포장 전표 업데이트에 받은 수량만 포함해야 합니다. 나머지 반품 배송물이 도착할 때까지 주문에 남아 있는 항목을 그대로 두십시오.

검역관이 재고의 항목을 어디에 보관해야 하는지 모르는 경우와 같이 항목이 검역소에서 배송 및 입고 부서로 반송되는 경우 해당 포장 전표를 업데이트하여 올바르게 등록하고 검역 결과로 지정된 처분 코드에 따라 조치를 취해야 합니다.

판매 계약에서 반환된 항목에 대한 포장 전표를 업데이트하면 해당 항목에 대한 판매 계약 약정이 수량 또는 금액의 변경 사항을 반영하도록 자동으로 업데이트됩니다. 

## <a name="see-also"></a>참고 항목

[반품에 대한 송장 업데이트 수행](perform-invoice-updates-for-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]