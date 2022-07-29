---
title: 이중 쓰기의 잠재 현금화
description: 이번에는 이중 쓰기의 잠재 고객 대 현금에 대한 정보를 제공합니다.
author: RamaKrishnamoorthy
ms.date: 01/07/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 7c53bcd1084d89b59d0f6b2674a85d7c3481a9bf
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8460655"
---
# <a name="prospect-to-cash-in-dual-write"></a>이중 쓰기의 잠재 현금화

[!include [banner](../../includes/banner.md)]

대부분의 비즈니스의 중요한 목표는 잠재 고객을 고객으로 전환한 다음 해당 고객과 지속적인 비즈니스 관계를 유지하는 것입니다. Microsoft Dynamics 365 앱에서 잠재 고객에서 현금으로의 프로세스는 견적 또는 주문 처리 워크플로를 통해 발생하며 재무가 조정되고 인식됩니다. 잠재 고객 대 현금을 이중 쓰기와 통합하면 Dynamics 365 Sales 또는 Dynamics 365 Supply Chain Management에서 시작된 견적과 주문을 받는 워크플로가 만들어지고 두 앱에서 견적과 주문을 사용할 수 있습니다.

앱 인터페이스에서 실시간으로 처리 상태 및 송장 정보에 액세스할 수 있습니다. 따라서 견적 및 주문을 다시 생성하지 않고도 Supply Chain Management에서 제품 재고, 재고 처리 및 이행과 같은 함수를 보다 쉽게 관리할 수 있습니다.

![잠재 고객 대 현금의 이중 쓰기 데이터 흐름.](../dual-write/media/dual-write-prospect-to-cash[1].png)

고객 및 연락처 통합에 대한 정보는 [통합 고객 마스터](customer-mapping.md)를 참조하십시오. 제품 통합에 대한 자세한 내용은 [통합 제품 경험](product-mapping.md)을 참조하십시오.

> [!NOTE]
> Dynamics 365 Sales에서 **잠재 고객** 과 **고객** 은 모두 **관계 유형** 열이 잠재 고객 또는 고객인 **계정** 테이블의 기록을 참조합니다. 비즈니스 논리에 **계정** 기록이 생성되고 먼저 잠재 고객으로 자격이 부여된 다음 고객 자격이 부여되는 **계정** 자격 프로세스가 포함된 경우 해당 기록은 고객(`RelationshipType=Customer`)인 경우에만 재무 및 운영 앱과 동기화됩니다. **계정** 행을 잠재 고객으로 동기화하려면 잠재 고객 데이터를 통합하기 위한 사용자 지정 맵이 필요합니다.

## <a name="prerequisites-and-mapping-setup"></a>전제 조건 및 매핑 설정

판매 견적을 동기화하려면 먼저 다음 설정을 업데이트해야 합니다.

### <a name="setup-in-sales"></a>판매 설정

영업에서 **설정 \> 관리 \> 시스템 설정 \> 영업** 으로 이동하여 다음 설정이 사용되는지 확인합니다.

- **시스템 가격 계산 시스템 사용** 옵션이 **예** 로 설정되어 있습니다.
- **할인 계산 방법** 열이 **항목** 으로 설정됩니다.

### <a name="sites-and-warehouses"></a>사이트 및 창고

Supply Chain Management에서 **사이트** 및 **창고** 열은 견적 라인 및 주문 라인에 필요합니다. 사이트 및 창고를 기본 주문 설정으로 설정하면 견적 라인이나 주문 라인에 제품을 추가할 때 해당 열이 자동으로 설정됩니다. 

### <a name="number-sequences-for-quotations-and-orders"></a>견적 및 주문에 대한 번호 시퀀스

견적 및 주문이 Sales and Supply Chain Management에서 생성 및 동기화될 때 Supply Chain Management 및 Sales의 번호 시퀀스는 연결되지 않습니다. Sales에서 생성된 판매 주문이 Supply Chain Management와 동기화된 경우 Supply Chain Management에서 동일한 판매 주문 번호를 가집니다. 판매 주문 번호가 중복되지 않도록 하려면 두 앱에서 서로 다른 번호 시퀀스 시스템을 사용해야 합니다.

예를 들어 Supply Chain Management의 번호 시퀀스는 **1, 2, 3, 4, 5, ...** 이고 Sales의 번호 시퀀스는 **100, 99, 98, ...** 입니다. Sales에서 100개의 판매 주문을 생성하면 결국 Supply Chain Management에 이미 존재하는 주문 번호가 생성됩니다. 즉, Supply Chain Management 및 Sales에서 판매 주문이 생성됨에 따라 두 개의 숫자 시퀀스가 결국 겹칩니다. 대신 Supply Chain Management에서는 **F1, F2, F3, ...** 와 같은 숫자 시퀀스를 사용하고 Sales에서는 **C1, C2, C3, ...** 와 같은 숫자 시퀀스를 사용할 수 있습니다. 이러한 번호 시퀀스는 중복 판매 주문 번호를 생성하지 않습니다.

## <a name="sales-quotations"></a>판매 견적

판매 견적은 판매 또는 Supply Chain Management에서 생성할 수 있습니다. Sales에서 견적을 생성하면 실시간으로 Supply Chain Management와 동기화됩니다. 마찬가지로 Supply Chain Management에서 견적을 생성하면 실시간으로 Sales와 동기화됩니다. 다음 사항에 유의하십시오.

+ 견적서에 제품에 할인을 추가할 수 있습니다. 이 경우 할인은 Supply Chain Management와 동기화됩니다. 헤더의 **할인**, **비용** 및 **세금** 열은 Supply Chain Management의 설정에 의해 제어됩니다. 이 설정은 통합 매핑을 지원하지 않습니다. 대신 **가격**, **할인**, **요금** 및 **세금** 열이 Supply Chain Management에서 유지 관리되고 처리됩니다.
+ 판매 견적 헤더의 **할인 %**, **할인** 및 **운임** 열은 읽기 전용 열입니다.
+ **운송 조건**, **배송 조건**, **배송 방법** 및 **배송 모드** 열은 기본 매핑의 일부가 아닙니다. 이러한 열을 매핑하려면 테이블이 동기화되는 조직의 데이터와 관련된 값 매핑을 설정해야 합니다.

Field Service 솔루션도 사용 중인 경우 **견적 라인 빠른 생성** 매개 변수를 다시 활성화해야 합니다. 매개 변수를 다시 활성화하면 빠른 생성 함수를 사용하여 견적 라인을 계속 생성할 수 있습니다.

1. Dynamics 365 Sales 애플리케이션으로 이동합니다.
2. 상단 탐색 모음에서 설정 아이콘을 선택합니다.
3. **고급 설정** 을 선택합니다.
4. **시스템 사용자 지정** 옵션을 선택하십시오.
5. **견적 라인** 메뉴 항목을 선택합니다.
6. **데이터 서비스** 섹션으로 이동하여 **빠른 생성 허용** 확인란을 선택합니다.

## <a name="sales-orders"></a>판매 주문

판매 주문은 판매 또는 Supply Chain Management에서 생성할 수 있습니다. Sales에서 판매 주문을 생성하면 실시간으로 Supply Chain Management와 동기화됩니다. 마찬가지로 Supply Chain Management에서 판매 주문을 생성하면 실시간으로 판매와 동기화됩니다. 다음 사항에 유의하십시오.

+ Dynamics 365 Sales의 기입 제품은 Dynamics 365 Supply Chain Management의 제품 범주로 나타납니다.
+ 할인 계산 및 반올림:

    - Sales의 할인 계산 모델은 Supply Chain Management의 할인 계산 모델과 다릅니다. Supply Chain Management에서 판매 라인의 최종 할인 금액은 할인 금액과 할인 비율을 조합한 결과일 수 있습니다. 이 최종 할인 금액을 라인의 수량으로 나누면 반올림이 발생할 수 있습니다. 그러나 반올림된 단위당 할인 금액이 Sales와 동기화된 경우 이 반올림은 고려되지 않습니다. Supply Chain Management에서 판매 라인의 전체 할인 금액이 판매와 올바르게 동기화되도록 하려면 라인 수량으로 나누지 않고 전체 금액을 동기화해야 합니다. 따라서 Sales에서 **Line item** 으로 할인 계산 방식을 정의해야 합니다.
    - 판매 주문 라인이 Sales에서 Supply Chain Management로 동기화되면 전체 라인 할인 금액이 사용됩니다. Supply Chain Management에는 라인에 대한 전체 할인 금액을 저장할 수 있는 열이 없기 때문에 금액을 수량으로 나누어 **라인 할인** 열에 저장합니다. 이 분할 중에 발생하는 모든 반올림은 판매 라인의 **판매 비용** 열에 저장됩니다.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>예:, 판매에서 Supply Chain Management로 동기화

다음 판매 주문이 있습니다.

+ **매상** 수량 = 3, 라인당 할인 = $10.00
+ **Supply Chain Management:** 수량 = 3, 라인 할인 금액 = $3.33, 판매 수수료 = –$0.01

Supply Chain Management에서 Sales로 동기화하면 다음 결과를 얻습니다.

+ **Supply Chain Management:** 수량 = 3, 라인 할인 금액 = $3.33, 판매 수수료 = –$0.01
+ **매상** 수량 = 3, 라인당 할인 = (3 × $3.33) + $0.01 = $10.00

## <a name="dual-write-solution-for-sales"></a>영업을 위한 이중 쓰기 솔루션

새 열이 **주문** 테이블에 추가되고 페이지에 나타납니다. 이러한 열의 대부분은 Sales의 **통합** 탭에 표시됩니다. 상태 열이 매핑되는 방법에 대한 자세한 내용은 [판매 주문 상태 열에 대한 매핑 설정](sales-status-map.md)을 참조하십시오.

+ **판매 주문** 페이지의 **송장 생성** 및 **주문 취소** 버튼은 판매에 숨겨져 있습니다.
+ **판매 주문 상태** 값은 **활성** 상태로 유지되어 Supply Chain Management의 변경 사항이 판매의 판매 주문으로 흘러갈 수 있도록 합니다. 이 동작을 제어하려면 기본 **Statecode \[상태\]** 값을 **활성** 으로 설정하십시오.

## <a name="invoices"></a>'송장',

판매 송장은 Supply Chain Management에서 생성되고 판매와 동기화됩니다. 다음 사항에 유의하십시오.

+ **송장 번호** 열이 **송장** 테이블에 추가되어 페이지에 나타납니다.
+ 송장이 Supply Chain Management에서 생성되고 Sales와 동기화되기 때문에 **판매 주문** 페이지의 **송장 생성** 버튼은 숨겨져 있습니다. **송장** 이 Supply Chain Management에서 동기화되므로 송장 페이지를 편집할 수 없습니다.
+ Supply Chain Management의 관련 송장이 판매와 동기화되면 **판매 주문 상태** 값이 자동으로 **송장 발행** 으로 변경됩니다. 또한 송장이 생성된 판매 주문의 소유자가 송장의 소유자로 지정됩니다. 따라서 판매 오더의 소유자는 송장을 볼 수 있습니다.
+ **운송 조건**, **배송 조건** 및 **배송 모드** 열은 기본 매핑에 포함되지 않습니다. 이러한 열을 매핑하려면 테이블이 동기화되는 조직의 데이터와 관련된 값 매핑을 설정해야 합니다.

## <a name="templates"></a>템플릿

Prospect-to-cash에는 다음 표와 같이 데이터 상호 작용 중에 함께 작동하는 핵심 테이블 맵 모음이 포함됩니다.

| 금융 및 운영 앱 | 고객 참여 앱 | 설명 |
|-----------------------------|-----------------------------------|-------------|
[모든 제품](mapping-reference.md#138) | msdyn_globalproducts | |
[고객 V3](mapping-reference.md#101) | 계정 | |
[고객 V3](mapping-reference.md#116) | 다음 담당자에게 연락해 주십시오. | |
[연락처 V2](mapping-reference.md#221) | msdyn_contactforparty | |
[CDS 판매 주문 헤더](mapping-reference.md#217) | 판매 주문 | |
[CDS 판매 주문 라인](mapping-reference.md#216) | salesorderdetails | |
[CDS 판매 견적 헤더](mapping-reference.md#215) | 견적 | |
[CDS 판매 견적 라인](mapping-reference.md#214) | 견적 세부 사항 | |
[출시된 제품 V2](mapping-reference.md#189) | msdyn_shared제품 세부 정보 | |
[판매 송장 헤더 V2](mapping-reference.md#118) | 송장 | 재무 및 운영 앱의 판매 송장 헤더 V2 테이블에는 판매 주문에 대한 송장 및 자유 텍스트 송장이 포함됩니다. 자유 텍스트 송장 문서를 걸러내는 Dataverse 이중 쓰기에 필터가 적용됩니다. |
[판매 송장 라인 V2](mapping-reference.md#117) | 송장 세부 정보 | |
[판매 주문 출처 코드](mapping-reference.md#186) | msdyn_salesorderorigins | |

가격 목록에 대한 자세한 내용은 [통합 제품 환경](product-mapping.md)을 참조하십시오.

## <a name="limitations"></a>한계

- 반품 주문은 지원되지 않습니다.
- 신용 메모는 지원되지 않습니다.
- 마스터 데이터(예: 고객 및 공급 업체)에 대해 재무 차원을 설정해야 합니다. 고객이 견적 또는 판매 주문에 추가되면 고객 기록와 연결된 재무 차원이 자동으로 주문으로 이동합니다. 현재 이중 쓰기에는 마스터 데이터에 대한 재무 차원 데이터가 포함되지 않습니다.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
