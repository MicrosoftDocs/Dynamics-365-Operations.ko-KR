---
title: 생산 주문을 완료된 것으로 보고
description: 생산 단계를 완료된 것으로 보고 이 단계에서 완제품이 보고되고 생산 주문에서 재고로 이동됩니다.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d509f0f732c1255a87bf810ab9a3bba3f61e2061f9a761ee0797b3fec45e45a3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446668"
---
# <a name="report-production-orders-as-finished"></a>생산 주문을 완료된 것으로 보고

[!include [banner](../includes/banner.md)]

생산 단계를 완료된 것으로 보고 이 단계에서 완제품이 보고되고 생산 주문에서 재고로 이동됩니다.

완제품의 수량이 생산 주문에서 완료된 것으로 보고되면 재고에서 현재고로 업데이트됩니다. 원래 계획된 주문 수량의 일부 수량은 완료로 보고될 수 있습니다. 수량을 완료된 것으로 보고할 때 연관된 오류 이유와 함께 오류 수량을 보고하는 것도 가능합니다. 생산 주문이 완료로 보고된 단계에 도달하면 생산 주문에서 더 이상 수량이 보고되지 않음을 나타냅니다.
다음 특성은 **완료로 보고됨** 프로세스와도 연관됩니다.
-   보고된 수량에 비례하여 원료의 소모량과 시간을 설정할 수 있습니다(백플러싱).
-   창고 프로세스에 사용할 수 있는 품목에 대해 보관 작업을 생성할 수 있습니다.
-   완제품의 계획 또는 표준 원가 값은 원장 계정에 보고되도록 설정할 수 있습니다.
-   품질 연관 설정에 따라 보고된 수량에 대해 품질 주문을 생성할 수 있습니다.

수량은 출력 위치에 보고됩니다. 그런 다음 창고 작업이 생성되어 출력 위치에서 보관 작업에 대한 위치 지시문에 의해 정의된 최종 목적지로 수량을 이동합니다.

-   품질 연관이 설정된 경우 생산 주문이 완료된 것으로 보고되면 품질 주문을 생성할 수 있습니다.

## <a name="set-a-production-order-to-reporting-as-finished"></a>생산 주문에 완료된 것으로 보고 설정
표준 생산 주문 업데이트 기능, 경로 및 작업 카드 분개장 또는 분개장 **완료로 보고** 를 통해 생산 주문을 **완료로 보고** 하도록 설정할 수 있습니다. 또한 생산 주문의 마지막 작업에 대해 보고할 때 작업 카드 터미널 및 작업 카드 디바이스 페이지를 통해 **완료로 보고** 단계를 업데이트할 수 있습니다. 마지막으로, 휴대용 창고 디바이스 솔루션에 대한 프로세스로 **완료로 보고** 옵션을 사용 설정할 수 있습니다.  





[!INCLUDE[footer-include](../../includes/footer-banner.md)]