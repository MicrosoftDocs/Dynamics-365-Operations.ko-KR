---
title: 재고 규모당 실행 평균 비용 추적
description: 재고 규모 그룹은 모든 재고 항목에 연결됩니다. 따라서 항목의 실행 평균 비용 가격은 재정적으로 추적 중인 선택한 재고 규모를 기반으로 계산됩니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ed1ced17eb25bdc10994b1e9e74c90a1d4ec95227bb1ddb072bae88e9255c0d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447328"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a>재고 규모당 실행 평균 비용 추적

[!include [banner](../includes/banner.md)]

재고 규모 그룹은 모든 재고 항목에 연결됩니다. 따라서 항목의 실행 평균 비용 가격은 재정적으로 추적 중인 선택한 재고 규모를 기반으로 계산됩니다.

재고 규모에는 제품, 보관 및 추적의 세 가지 유형이 있습니다. 제품 치수에는 구성, 크기 및 색상이 포함됩니다. 제품 치수는 항상 재정적으로 추적됩니다. 보관 및 추적 규모에는 사이트, 창고, 위치, 재고 상태, 번호판, 배치 번호 및 일련 번호가 포함됩니다. 재정적으로 추적할 스토리지 및 추적 규모를 결정할 수 있습니다. 

**예시 1** 

항목에 연결된 재고 규모 그룹이 창고별로 재무적으로 추적되는 경우 창고별로 실행 평균 비용 가격이 계산됩니다. 다음 구매 주문이 청구되었습니다.

-   USD 10.00의 비용 가격으로 수량 2에 대한 구매 주문이 창고 GW에 대해 청구되었습니다.
-   USD 12.00의 비용 가격으로 수량 3에 대한 구매 주문이 창고 GW에 대해 청구되었습니다.
-   USD 15.00의 비용 가격으로 수량 5에 대한 구매 주문이 창고 MW에 대해 청구되었습니다.

창고 GW의 실행 평균 비용 가격은 USD 11.20이고 창고 MW의 실행 평균 비용 가격은 USD 15.00입니다. 창고 GW에 대한 판매 주문 송장이 전기됩니다. 재고 가치 및 판매 제품 원가(재고 마감이 실행되기 전 및 표시 없음)는 USD 11.20입니다. 창고 MW에 대한 또 다른 판매 주문이 전기됩니다. 재고 가치 및 판매 제품 원가(재고 마감이 실행되기 전 및 표시 없음)는 USD 15.00입니다. 

**예시 2** 항목에 연결된 재고 규모 그룹이 창고별로 재정적으로 추적되고 추적 규모 그룹이 배치 번호로 재정적으로 추적되는 경우 각 배치에 대해 실행 평균 비용 가격이 계산됩니다. 

**참고:** 추적 중인 모든 재무 차원에 대한 비용 가격을 항상 확인하는 것이 좋습니다. 다음 구매 주문이 청구되었습니다.

-   USD 10.00의 비용 가격으로 수량 2에 대한 구매 주문이 창고 GW 및 배치 AAA에 대해 청구되었습니다.
-   USD 12.00의 비용 가격으로 수량 3에 대한 구매 주문이 창고 GW 및 배치 AAA에 대해 청구되었습니다.
-   USD 15.00의 비용 가격으로 수량 2에 대한 구매 주문이 창고 GW 및 배치 BBB에 대해 청구되었습니다.

창고 GW 및 배치 AAA의 실행 평균 비용 가격은 USD 11.20이고 창고 GW 및 배치 BBB의 실행 평균 비용 가격은 USD 15.00입니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]