---
title: Field Service의 작업 주문을 Supply Chain Management의 판매 주문과 동기화
description: 이 토픽에서는 Field Service의 작업 주문을 Supply Chain Management의 판매 주문과 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
author: Henrikan
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b7b311701aff12d58392fc036d0f1174678b7dc3
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449815"
---
# <a name="synchronize-work-orders-in-field-service-to-sales-orders-in-supply-chain-management"></a>Field Service의 작업 주문을 Supply Chain Management의 판매 주문과 동기화

[!include[banner](../includes/banner.md)]



이 토픽에서는 Dynamics 365 Field Service의 작업 주문을 Dynamics 365 Supply Chain Management의 판매 주문과 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

[![Supply Chain Management와 Field Service 간의 비즈니스 프로세스 동기화.](./media/field-service-integration.png)](./media/field-service-integration.png)


## <a name="templates-and-tasks"></a>템플릿 및 작업

다음 템플릿 및 기본 작업은 Field Service의 작업 주문을 Supply Chain Management의 판매 주문과 동기화하는 데 사용됩니다.

### <a name="names-of-the-templates-in-data-integration"></a>데이터 통합의 템플릿 이름

**작업 주문에서 판매 주문으로(Field Service에서 Supply Chain Management로)** 템플릿은 동기화를 실행하는 데 사용됩니다.

### <a name="names-of-the-tasks-in-the-data-integration-project"></a>데이터 통합 프로젝트의 작업 이름

- WorkOrderHeader
- WorkOrderServiceLineEstimate
- WorkOrderServiceLineUsed
- WorkOrderProductLineEstimate
- WorkOrderProductLineUsed

판매 주문 헤더 및 라인을 동기화하려면 다음 동기화 태스크가 필요합니다.

- Field Service 제품(Supply Chain Management에서 Field Service로)
- 제품(Sales에서 Supply Chain Management로) - 직접

## <a name="entity-set"></a>엔터티 세트

| **Field Service** | **Supply Chain Management** |
|-------------------------|-------------------------|
| msdyn_workorders        | Dataverse 판매 주문 헤더 |
| msdyn_workorderservices | Dataverse 판매 주문 라인   |
| msdyn_workorderproducts | Dataverse 판매 주문 라인   |

## <a name="entity-flow"></a>엔터티 흐름

작업 주문은 Field Service에서 생성됩니다. 작업 주문이 외부에서 유지 관리되는 제품만 포함하고 **작업 주문 상태** 값이 **시작됨-예정 없음** 및 **마감 – 취소** 와 다른 경우 작업 주문은 Microsoft Dataverse 데이터 통합 프로젝트를 통해 Supply Chain Management에 동기화될 수 있습니다. 작업 주문에 대한 업데이트는 Supply Chain Management에서 판매 주문으로 동기화됩니다. 이러한 업데이트에는 원본 유형 및 상태에 대한 정보가 포함됩니다.

## <a name="estimated-versus-used"></a>예상 값 및 사용 값 비교

Field Service에서 작업 주문의 제품 및 서비스에는 수량 및 금액에 대한 **예상** 값과 **사용** 값이 모두 있습니다. 그러나 Supply Chain Management에서 판매 주문에는 **예상** 값과 **사용** 값의 개념이 동일하지 않습니다. Supply Chain Management에서 판매 주문의 예상 수량을 사용하는 제품 할당을 지원하지만 소비 및 송장을 발행해야 하는 사용 수량을 유지하기 위해 두 작업 세트가 작업 주문에서 제품과 서비스를 동기화합니다. 작업 세트 중 하나는 **예상** 값에 대한 것이고 다른 작업 세트는 **사용** 값에 대한 것입니다.

이 동작은 예상 값이 Supply Chain Management의 할당 또는 예약에 사용되는 반면 사용된 값은 소비 및 송장 발행에 사용되는 시나리오를 가능하게 합니다.

### <a name="estimated"></a>예상

제품 라인 동기화의 경우 **예상** 값은 **라인 상태** 값이 **예상**, **할당** 옵션이 **예** 로 설정되어 있고 **시스템 상태** 값이 **마감됨 – 전기** 가 아닐 때 사용됩니다.

서비스 라인 동기화의 경우 **예상** 값은 **라인 상태** 값이 **예상** 이고 **시스템 상태** 값이 **마감 – 전기** 가 아닐 때 사용됩니다.

### <a name="used"></a>사용

**사용** 값은 소비 및 송장 발행에 사용됩니다. 이러한 경우 **사용** 값이 동기화됩니다.

다음 테이블을 제품군의 다양한 조합에 대한 개요를 제공합니다.

| 시스템 상태 <br>(Field Service) | 라인 상태 <br>(Field Service) | 할당 <br>(Field Service) |동기화 값 <br>(Supply Chain Management) |
|--------------------|-------------|-----------|---------------------------------|
| 시작됨 - 예약됨   | 예상   | 예       | 예상                       |
| 시작됨 -예약됨   | 예상   | 아니요        | 사용                            |
| 시작됨 -예약됨   | 사용        | 예       | 사용                            |
| 시작됨 -예약됨   | 사용        | 아니요        | 사용                            |
| 시작됨 -진행 중 | 예상   | 예       | 예상                       |
| 시작됨 -진행 중 | 예상   | 아니요        | 사용                            |
| 시작됨 -진행 중 | 사용        | 예       | 사용                            |
| 시작됨 -진행 중 | 사용        | 아니요        | 사용                            |
| 시작됨 -완료됨   | 예상   | 예       | 예상                       |
| 시작됨 -완료됨   | 예상   | 아니요        | 사용                            |
| 시작됨 -완료됨   | 사용        | 예       | 사용                            |
| 시작됨 -완료됨   | 사용        | 아니요        | 사용                            |
| 마감 - 전기    | 예상   | 예       | 사용                            |
| 마감 - 전기    | 예상   | 아니요        | 사용                            |
| 마감 - 전기    | 사용        | 예       | 사용                            |
| 마감 - 전기    | 사용        | 아니요        | 사용                            |

다음 테이블을 서비스 라인의 다양한 조합에 대한 개요를 제공합니다.

| 시스템 상태 <br>(Field Service) | 라인 상태 <br>(Field Service) | 동기화 값 <br>(Supply Chain Management) |
|--------------------|-------------|-----------|
| 시작됨 -예약됨   | 예상   | 예상 |
| 시작됨 -예약됨   | 사용        | 사용      |
| 시작됨 -진행 중 | 예상   | 예상 |
| 시작됨 -진행 중 | 사용        | 사용      |
| 시작됨 -완료됨   | 예상   | 예상 |
| 시작됨 -완료됨   | 사용        | 사용      |
| 마감 - 전기    | 예상   | 사용      |
| 마감 - 전기    | 사용        | 사용      |

**예상** 값과 **사용** 값의 동기화는 제품 라인과 서비스 라인에 대한 두 가지 작업 세트를 통해 관리됩니다. 사전 정의된 필터는 올바른 작업을 트리거하고 기본 매핑은 **예상** 대 **사용** 에 대한 올바른 값이 동기화되도록 보장하는 데 도움이 됩니다.

### <a name="example"></a>예

1. Field Service에서 작업 주문이 생성되고 예약됩니다.

    **시스템 상태** 값은 **미결 – 예약됨** 입니다.

    - **제품 라인:** 예상 수량 = 5개, 사용 수량 = 0개, 라인 상태 = 예상, 할당됨 = 아니요
    - **서비스 라인:** 예상 수량 = 2시간, 사용 수량 = 0시간, 라인 상태 = 예상

    이 예에서 제품의 **사용 수량** 값 **0** 과 서비스의 **예상 수량** 값 **2시간** 이 Supply Chain Management와 동기화됩니다.

2. 제품은 Field Service에 할당됩니다.

    **시스템 상태** 값은 **미결 – 예약됨** 입니다.

    - **제품 라인:** 예상 수량 = 5개, 사용 수량 = 0개, 라인 상태 = 예상, 할당됨 = 예
    - **서비스 라인:** 예상 수량 = 2시간, 사용 수량 = 0시간, 라인 상태 = 예상

    이 예에서 제품의 **예상 수량** 값 **5개** 와 서비스의 **예상 수량** 값 **2시간** 이 Supply Chain Management와 동기화됩니다.

3. 서비스 기술자는 작업 지시에 대한 작업을 시작하고 자재 사용량을 6으로 등록합니다.

    **시스템 상태** 값은 **미결 – 진행 중** 입니다.

    - **제품 라인:** 예상 수량 = 5개, 사용 수량 = 6개, 라인 상태 = 사용, 할당됨 = 예
    - **서비스 라인:** 예상 수량 = 2시간, 사용 수량 = 0시간, 라인 상태 = 예상

    이 예에서 제품의 **사용 수량** 값 **6** 과 서비스의 **예상 수량** 값 **2시간** 이 Supply Chain Management와 동기화됩니다.

4. 서비스 기술자는 작업 주문을 완료하고 1.5시간의 사용 시간을 등록합니다.

    **시스템 상태** 값은 **미결 – 완료** 입니다.

    - **제품 라인:** 예상 수량 = 5개, 사용 수량 = 6개, 라인 상태 = 사용, 할당됨 = 예
    - **서비스 라인:** 예상 수량 = 2시간, 사용 수량 = 1.5시간, 라인 상태 = 사용

    이 예에서 제품의 **사용 수량** 값 **6** 과 서비스의 **사용 수량** 값 **1.5시간** 이 Supply Chain Management와 동기화됩니다.

## <a name="sales-order-origin-and-status"></a>판매 주문 원산지 및 상태

### <a name="sales-origin"></a>판매 출처

작업 주문에서 시작된 판매 주문을 추적하기 위해 **출처 유형 할당** 옵션이 **예** 로 설정되고 **판매 출처 유형** 필드가 **작업 주문 통합** 으로 설정된 판매 출처를 생성할 수 있습니다.

기본적으로 매핑은 작업 주문에서 생성된 모든 판매 주문의 **작업 주문 통합** 판매 출처 유형에 대한 판매 출처를 선택합니다. 이 동작은 Supply Chain Management에서 판매 주문으로 작업할 때 유용할 수 있습니다. 작업 주문에서 시작된 판매 주문이 작업 주문으로 Field Service에 다시 동기화되지 않도록 해야 합니다.

Supply Chain Management에서 올바른 판매 출처 설정을 생성하는 방법에 대한 자세한 내용은 이 항목의 "사전 조건 및 매핑 설정" 섹션을 참조하세요.

### <a name="status"></a>상태

판매 주문이 작업 주문에서 시작되면 **외부 작업 주문 상태** 필드가 판매 주문 헤더의 **설정** 탭에 나타납니다. 이 필드는 Field Service의 작업 주문 시스템 상태를 표시하여 Supply Chain Management에서 판매 주문의 동기화된 작업 주문 상태를 추적하는 데 도움이 됩니다. 이 필드는 또한 사용자가 판매 주문을 배송하거나 송장을 발행해야 하는 시기를 결정하는 데 도움이 될 수 있습니다.

**외부 작업 주문 상태** 필드는 다음 값을 가질 수 있습니다.

- 시작됨 -예약됨
- 시작됨 -진행 중
- 시작됨 -완료됨
- 마감 - 전기

## <a name="field-service-crm-solution"></a>Field Service CRM 솔루션

Field Service와 Supply Chain Management 간의 통합을 지원하려면 Field Service CRM 솔루션의 추가 기능이 필요합니다. 솔루션에는 다음 변경 사항이 포함됩니다.

### <a name="work-order-entity"></a>작업 주문 엔터티

**외부에서 유지 관리되는 제품만 있음** 필드가 **작업 주문** 엔터티에 추가되어 페이지에 나타납니다. 작업 주문이 전적으로 외부에서 유지 관리되는 제품으로 구성되어 있는지 여부를 일관되게 추적하는 데 사용됩니다. 모든 관련 제품이 Supply Chain Management에서 유지 관리되는 경우 작업 주문은 전적으로 외부에서 유지 관리되는 제품으로 구성됩니다. 이 필드는 사용자가 알 수 없는 제품이 있는 작업 주문을 동기화하지 않도록 합니다.

### <a name="work-order-product-entity"></a>작업 주문 제품 엔터티

- **주문이 외부에서 유지 관리되는 제품만 있음** 필드가 **작업 주문 제품** 엔터티에 추가되고 페이지에 나타납니다. 작업 주문 제품이 Supply Chain Management에서 유지 관리되는지 여부를 일관되게 추적하는 데 사용됩니다. 이 필드는 사용자가 Supply Chain Management에 알려지지 않은 작업 주문 제품을 동기화하지 않도록 하는 데 도움이 됩니다.
- **헤더 시스템 상태** 필드가 **작업 주문 제품** 엔터티에 추가되었으며 페이지에 나타납니다. 작업 주문의 시스템 상태를 일관되게 추적하는 데 사용되며 작업 주문 제품이 Supply Chain Management와 동기화될 때 올바른 필터링을 보장하는 데 도움이 됩니다. 통합 작업에 필터가 설정되면 **헤더 시스템 상태** 정보를 사용하여 예상 값 또는 사용 값을 동기화해야 하는지 여부도 결정합니다.
- **청구된 단위 금액** 필드에는 사용된 실제 단위당 청구된 금액이 표시됩니다. 값은 **총 금액** 값을 **실제 수량** 값으로 나눈 값으로 계산됩니다. 이 필드는 사용 수량과 청구 수량에 대해 다른 값을 지원하지 않는 시스템에 통합하는 데 사용됩니다. 이 필드는 사용자 인터페이스(UI)에 표시되지 않습니다. 
- **청구된 할인 금액** 필드는 **할인 금액** 값에 **청구된 단위 금액** 계산의 반올림을 더한 값으로 계산됩니다. 이 필드는 통합에 사용되며 UI에 표시되지 않습니다.
- **소수점 수량** 필드는 **수량** 필드의 값을 십진수로 저장합니다. 이 필드는 통합에 사용되며 UI에 표시되지 않습니다. 
- 작업 주문 제품의 **라인 상태** 값이 **사용** 에서 **예상** 으로 변경된 경우 **사용** 필드의 값은 **0**(영)으로 재설정됩니다. 이 변경은 **라인 상태** 값이 **예상** 이고 **할당** 옵션이 **아니요** 로 설정된 경우 잘못 입력된 사용 수량을 동기화에 사용하는 상황을 방지하는 데 도움이 됩니다.

### <a name="work-order-service-entity"></a>작업 주문 서비스 엔터티

- **주문이 외부에서 유지 관리되는 제품만 있음** 필드가 **작업 주문 서비스** 엔터티에 추가되고 페이지에 나타납니다. 작업 주문 서비스가 Supply Chain Management에서 유지 관리되는지 여부를 일관되게 추적하는 데 사용됩니다. 이 필드는 사용자가 Supply Chain Management에 알려지지 않은 작업 주문 서비스를 동기화하지 않도록 하는 데 도움이 됩니다.
- **헤더 시스템 상태** 필드가 **작업 주문 서비스** 엔터티에 추가되었으며 페이지에 나타납니다. 작업 주문의 시스템 상태를 일관되게 추적하는 데 사용되며 작업 주문 서비스가 Supply Chain Management와 동기화될 때 올바른 필터링을 보장하는 데 도움이 됩니다. 통합 작업에 필터가 설정되면 **헤더 시스템 상태** 정보를 사용하여 예상 값 또는 사용 값을 동기화해야 하는지 여부도 결정합니다.
- **기간(시간)** 필드는 해당 값이 분에서 시간으로 변환된 후 **기간** 필드의 값을 저장합니다. 이 필드는 통합에 사용되며 UI에 표시되지 않습니다.
- **예상 기간(시간)** 필드는 해당 값이 분에서 시간으로 변환된 후 **예상 기간** 필드의 값을 저장합니다. 이 필드는 통합에 사용되며 UI에 표시되지 않습니다.
- **청구된 단위 금액** 필드에는 사용된 실제 단위당 청구된 금액이 저장됩니다. 값은 **총 금액** 값을 **실제 수량** 값으로 나눈 값으로 계산됩니다. 이 필드는 사용 수량과 청구 수량에 대해 다른 값을 지원하지 않는 시스템에 통합하는 데 사용됩니다. 이 필드는 UI에 표시되지 않습니다.
- **청구된 할인 금액** 필드는 **할인 금액** 값에 **청구된 단위 금액** 계산의 반올림을 더한 값으로 계산됩니다. 이 필드는 통합에 사용되며 UI에 표시되지 않습니다.
- **외부 라인 주문** 필드는 작업 주문 제품과 서비스 라인이 결합된 외부 시스템에서 사용할 수 있는 계산된 음수 라인 주문 번호입니다. 이 필드를 사용하면 삽입된 작업 주문 제품이 양수 라인 번호를 갖고 작업 주문 서비스가 음수 라인 번호를 가질 수 있습니다. 이 필드의 값은 **라인 주문** 값에 -1을 곱한 값으로 계산됩니다. 이 필드는 UI에 표시되지 않습니다.
- 어떤 이유로 작업 주문 서비스의 **라인 상태** 값이 **사용** 에서 **예상** 으로 변경된 경우 **사용** 필드의 값은 **0**(영)으로 재설정됩니다. 이 변경은 **라인 상태** 값이 **예상** 이고 **헤더 시스템 상태** 값이 **마감 – 전기** 일 때 잘못 입력된 사용 수량이 동기화에 사용되는 상황을 방지하는 데 도움이 됩니다.

## <a name="preconditions-and-mapping-setup"></a>전제 조건 및 매핑 설정

작업 주문을 동기화하기 전에 시스템에서 다음 설정을 업데이트하는 것이 중요합니다.

### <a name="setup-in-field-service"></a>Field Service에서 설정

- Field Service의 작업 주문에 사용되는 번호 시리즈가 Supply Chain Management의 판매 주문에 사용되는 번호 시퀀스와 겹치지 않는지 확인합니다. 그렇지 않으면 Field Service 또는 Supply Chain Management에서 기존 판매 주문이 잘못 업데이트될 수 있습니다.
- 송장이 Supply Chain Management에서 수행되기 때문에 **작업 주문 송장 생성** 필드를 **절대 안 함** 으로 설정해야 합니다. **Field Service** \> **설정** \> **관리** \> **Field Service 설정** 으로 이동한 후 **작업 주문 송장 생성** 필드가 **절대 안 함** 으로 설정되어 있는지 확인합니다.

### <a name="setup-in-supply-chain-management"></a>Supply Chain Management 설정

작업 주문 통합을 위해서는 판매 출처를 설정해야 합니다. 판매 출처는 Field Service의 작업 주문에서 생성된 Supply Chain Management의 판매 주문을 구별하는 데 사용됩니다. 판매 주문에 **작업 주문 통합** 유형의 판매 출처가 있는 경우 **외부 작업 주문 상태** 필드가 판매 주문 헤더에 나타납니다. 또한 판매 출처는 Field Service의 작업 주문에서 생성된 판매 주문이 Supply Chain Management에서 Field Service로 판매 주문 동기화 중에 필터링되도록 보장하는 데 도움이 됩니다.

1. **영업 및 마케팅** \> **설정** \> **판매 주문** \> **판매 출처** 로 이동합니다.
2. **새로 만들기** 를 선택하여 판매 출처를 만듭니다.
3. **판매 출처** 필드에 **WorkOrder** 와 같은 판매 출처의 이름을 입력합니다.
4. **설명** 필드에 **Field Service 작업 주문** 과 같은 설명을 입력합니다.
5. **출처 유형 할당** 확인란을 선택합니다.
6. **판매 출처 유형** 필드를 **작업 주문 통합** 으로 설정합니다.
7. **저장** 을 선택합니다.


### <a name="setup-in-data-integration"></a>데이터 통합에서 설정

**msdyn_workorders** 에 대한 **통합 키** 가 있는지 확인합니다.
1. 데이터 통합으로 이동
2. **연결 세트** 탭 선택
3. 작업 주문 동기화에 사용되는 연결 집합 선택
4. **통합 키** 탭 선택
5. msdyn_workorders를 찾아 **msdyn_name(작업 주문 번호)** 키가 추가되었는지 확인합니다. 표시되지 않으면 **키 추가** 를 클릭하여 추가하고 페이지 상단의 **저장** 을 클릭합니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

다음 그림은 데이터 통합에서 템플릿 매핑을 보여줍니다.

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderheader"></a>작업 주문에서 판매 주문으로(Field Service에서 Supply Chain Management로): WorkOrderHeader

필터: (msdyn_systemstatus ne 690970005) 및 (msdyn_systemstatus ne 690970000) 및 (msdynce_hasexternallymaintainedproductsonly eq true)

[![작업 주문 대 판매 주문(Field Service에서 Supply Chain Management로)에 대한 데이터 통합의 템플릿 매핑: WorkOrderHeader.](./media/FSWorkOrder1.png )](./media/FSWorkOrder1.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderservicelineestimate"></a>작업 주문에서 판매 주문으로(Field Service에서 Supply Chain Management로): WorkOrderServiceLineEstimate

필터: (msdynce_headersystemstatus ne 690970005) 및 (msdynce_headersystemstatus ne 690970000) 및 (msdynce_orderhasexternalmaintainedproductsonly eq true) 및 (msdyn_linestatus eq 690970000) 및 (msdynce_headersystemstatus ne 690970004)

[![작업 주문 대 판매 주문(Field Service에서 Supply Chain Management로)에 대한 데이터 통합의 템플릿 매핑: WorkOrderServiceLineEstimate.](./media/FSWorkOrder2.png )](./media/FSWorkOrder2.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderservicelineused"></a>작업 주문에서 판매 주문으로(Field Service에서 Supply Chain Management로): WorkOrderServiceLineUsed

필터: (msdynce_headersystemstatus ne 690970005) 및 (msdynce_headersystemstatus ne 690970000) 및 (msdynce_orderhasexternalmaintainedproductsonly eq true) 및 ((msdyn_linestatus eq 690970001) 또는 (msdynce_headersystemstatus eq 690970004))

[![작업 주문 대 판매 주문(Field Service에서 Supply Chain Management로)에 대한 데이터 통합의 템플릿 매핑: WorkOrderServiceLineUsed.](./media/FSWorkOrder3.png )](./media/FSWorkOrder3.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderproductlineestimate"></a>작업 주문에서 판매 주문으로(Field Service에서 Supply Chain Management로): WorkOrderProductLineEstimate

필터: (msdynce_headersystemstatus ne 690970005) 및 (msdynce_headersystemstatus ne 690970000) 및 (msdynce_orderhasexternalmaintainedproductsonly eq true) 및 (msdyn_linestatus eq 690970000) 및 (msdynce_headersystemstatus ne 690970004) 및 (msdyn_allocated eq true)

[![작업 주문 대 판매 주문(Field Service에서 Supply Chain Management로)에 대한 데이터 통합의 템플릿 매핑: WorkOrderProductLineEstimate.](./media/FSWorkOrder4.png )](./media/FSWorkOrder4.png)

### <a name="work-orders-to-sales-orders-field-service-to-supply-chain-management-workorderproductlineused"></a>작업 주문에서 판매 주문으로(Field Service에서 Supply Chain Management로): WorkOrderProductLineUsed

필터: (msdynce_headersystemstatus ne 690970005) 및 (msdynce_headersystemstatus ne 690970000) 및 (msdynce_orderhasexternalmaintainedproductsonly eq true) 및 ((msdyn_linestatus eq 690970001) 또는 (msdynce_headersystemstatus eq 690970004) 또는 (msdyn_allocated ne true))

[![작업 주문 대 판매 주문(Field Service에서 Supply Chain Management로)에 대한 데이터 통합의 템플릿 매핑: WorkOrderProductLineUsed.](./media/FSWorkOrder5.png )](./media/FSWorkOrder5.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]