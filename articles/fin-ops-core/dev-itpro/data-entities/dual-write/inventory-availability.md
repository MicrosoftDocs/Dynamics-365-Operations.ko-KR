---
title: 이중 쓰기의 인벤토리 가용성
description: 이 항목에서는 이중 쓰기에서 인벤토리 가용성을 확인하는 방법에 대한 정보를 제공합니다.
author: RamaKrishnamoorthy
ms.date: 05/26/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 989ba6cd26d6e48c24db856fa9bb0bd5d2bae80e
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460940"
---
# <a name="inventory-availability-in-dual-write"></a>이중 쓰기의 인벤토리 가용성

[!include [banner](../../includes/banner.md)]

재고 가용성을 사용하여 Microsoft Dynamics 365 Sales의 **견적**, **주문** 또는 **송장** 페이지에 제품을 추가하기 전에 재고를 확인할 수 있습니다. 예를 들어 재고를 확인하고 이행 날짜를 [잠재 현금](dual-write-prospect-to-cash.md) 프로세스의 하나의 핵심 작업으로 결정합니다.

재고가 충분하지 않은 경우 예상 재고 입고 및 출고를 기반으로 배송 날짜를 예측할 수 있습니다. 사전 정의된 타임펜스에서 ATP 수량을 찾을 수 있는 제품의 ATP(수주 가능량) 정보를 확인할 수도 있습니다.

## <a name="on-hand-inventory"></a>보유 인벤토리

Dynamics 365 Sales에서 새로운 **현재고** 버튼이 **견적**, **주문** 및 **송장** 페이지 헤더에 추가되었습니다 이 버튼을 선택하면 현재고를 확인할 회사와 제품을 지정할 수 있는 대화 상자가 나타납니다. 이 대화 상자에는 [보유 재고](../../../../supply-chain/inventory/tasks/check-availability-stock.md)와 동일한 정보가 표시됩니다.

대화 상자에서 Dynamics 365 Supply Chain Management의 인벤토리 정보를 반환합니다. 이 정보에는 다음 수량이 포함됩니다.

- 현재고 수량
- 예약된 현재고 수량
- 사용 가능 현재고 수량
- 주문 수량
- 주문 시 수량
- 예약된 주문 수량
- 총 사용 가능 수량

## <a name="atp-information"></a>ATP 정보

Sales에는 새로운 **ATP 정보** 버튼이 **견적**, **주문** 및 **송장** 페이지의 광고 항목에 추가되었습니다. 이 버튼을 선택하면 회사, 제품, 재고 사이트, 재고 창고, 주문 수량을 지정할 수 있는 대화 상자가 나타납니다. 이 대화 상자에는 [주문 예상](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations)에 설명된 것과 동일한 설정이 있습니다.

대화 상자는 Supply Chain Management에서 ATP 정보를 반환합니다. 이 정보에는 다음 수량이 포함됩니다.

- ATP 수량
- 영수증 수량
- 발행 수량
- 현재고 수량

## <a name="how-it-works"></a>작동 원리

**견적**, **주문** 또는 **송장** 페이지에서 **현재고** 버튼을 선택하면 라이브 이중 쓰기 호출이 **현재고** API에 적용됩니다. API는 주어진 제품에 대한 현재고를 계산합니다. 결과는 **InventCDSInventoryOnHandRequestEntity** 및 **InventCDSInventoryOnHandEntryEntity** 테이블에 저장되고 Dataverse에 이중 쓰기로 작성됩니다. 이 기능을 사용하려면 다음 이중 쓰기 맵을 실행해야 합니다. 맵을 실행할 때 초기 동기화를 건너뜁니다.

- CDS 재고 현재고 항목(msdyn_inventoryonhandentries)
- CDS 재고 보유 요청(msdyn_inventoryonhandrequests)

## <a name="templates"></a>템플릿

현재고 데이터를 표시하는 데 사용할 수 있는 템플릿은 다음과 같습니다.

금융 및 운영 앱 | Customer Engagement 앱     | 설명
---|---|---
[CDS 인벤토리 보유 항목](mapping-reference.md#145) | msdyn_inventoryonhandentries |
[CDS 인벤토리 보유 요청](mapping-reference.md#147) | msdyn_inventoryonhandrequests |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
