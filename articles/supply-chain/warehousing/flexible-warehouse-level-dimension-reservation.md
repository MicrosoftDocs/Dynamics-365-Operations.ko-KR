---
title: 유연한 창고 수준 차원 예약 정책
description: 이 토픽에서는 제품과 연결된 예약 계층이 특정 배치의 예약을 허용하지 않는 경우에도 배치 추적 제품을 판매하고 WMS 지원 작업으로 물류를 실행하는 기업이 고객 판매 주문에 대해 특정 배치를 예약할 수 있도록 하는 재고 예약 정책에 대해 설명합니다.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReservationHierarchy, WHSWorkTrans, WHSWorkInventTrans, WHSInventTableReservationHierarchy, WHSReservationHierarchyCreate, WHSInventTableReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 0fe4b377ec80601f616f81f71222129256dfd448
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2021
ms.locfileid: "8447541"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a>유연한 창고 수준 차원 예약 정책

[!include [banner](../includes/banner.md)]

*Batch-below\[위치\]* 유형의 재고 예약 계층이 제품과 연관되는 경우, 배치 추적 제품을 판매하고 Microsoft Dynamics 365 WMS(Warehouse Management System)에 대해 활성화된 운영으로 물류를 실행하는 기업은 고객 판매 주문을 위해 해당 제품의 특정 배치를 예약할 수 없습니다.

비슷한 방식으로 특정 번호판은 판매 주문의 제품이 기본 예약 계층 구조와 연결되어 있는 경우 해당 제품에 대해 예약할 수 없습니다.

이 토픽에서는 제품이 *Batch-below\[위치\]* 예약 계층과 연결된 경우에도 이러한 기업이 특정 배치 또는 번호판을 예약할 수 있도록 하는 재고 예약 정책에 대해 설명합니다.

## <a name="inventory-reservation-hierarchy"></a>재고 예약 계층 구조

이 섹션에서는 기존 재고 예약 계층 구조를 요약합니다.

재고 예약 계층 구조는 재고 규모와 관련하여 수요 주문이 사이트, 창고 및 재고 상태의 필수 차원을 전달하도록 지시합니다. 즉, 필수 차원은 예약 계층에서 위치 차원 위의 모든 차원이며 창고 논리는 요청된 수량에 위치를 할당하고 위치를 예약하는 역할을 합니다. 수요 주문과 창고 작업 간의 상호 작용에서 수요 주문은 주문을 배송해야 하는 위치(즉, 사이트 및 창고)를 나타낼 것으로 예상됩니다. 그런 다음 창고는 논리에 따라 창고 구내에서 필요한 수량을 찾습니다.

그러나 비즈니스의 운영 모델을 반영하기 위해 추적 규모(배치 및 일련 번호)가 더 유연합니다. 재고 예약 계층은 다음 조건이 적용되는 시나리오를 수용할 수 있습니다.

- 이 비즈니스는 창고 운영에 의존하여 창고 보관 공간에서 수량을 찾은 *이후* 배치 또는 일련 번호가 있는 수량의 피킹을 관리합니다. 이 모델을 *Batch-below\[위치\]* 또는 *Serial-below\[위치\]* 라고 합니다. 일반적으로 제품의 배치 또는 일련 번호 식별이 판매 회사에 요구하는 고객에게 중요하지 않을 때 사용됩니다.
- 이 비즈니스는 창고 운영에 의존하여 창고 보관 공간에서 수량을 찾은 *이전* 배치 또는 일련 번호가 있는 수량의 피킹을 관리합니다. 배치 또는 일련 번호가 고객 주문 사양의 일부로 필요한 경우 수요 주문에 기록되며 창고에서 수량을 찾는 창고 작업에서는 이를 변경할 수 없습니다. 이 모델을 *Batch-above\[위치\]* 또는 *Serial-above\[위치\]* 라고 합니다. 위치 위의 차원은 충족되어야 하는 요구 사항에 대한 특정 요구 사항이므로 창고 논리에서 할당하지 않습니다. 이러한 규모는 항상 수요 주문 또는 관련 예약에 **지정되어야 합니다.**

이러한 시나리오에서 문제는 출시된 각 제품에 하나의 재고 예약 계층 구조만 할당할 수 있다는 것입니다. 따라서 WMS가 추적 품목을 처리하기 위해 계층 지정 후 배치 또는 일련번호를 예약해야 하는 시기(수요 주문이 접수될 때 또는 창고 피킹 작업 중일 때)를 결정하고 나면 이 타이밍을 임시로 변경할 수 없습니다.

## <a name="flexible-reservation-for-batch-tracked-items"></a>일괄 추적 항목에 대한 유연한 예약

### <a name="business-scenario"></a>비즈니스 시나리오

이 시나리오에서 회사는 완제품이 배치 번호로 추적되는 재고 전략을 사용합니다. 이 회사는 또한 WMS 워크로드를 사용합니다. 이 워크로드에는 배치 지원 항목에 대한 창고 피킹 및 배송 작업을 계획하고 실행하기 위한 잘 갖추어진 논리가 있기 때문에 대부분의 완제품 품목은 *Batch-below\[위치\]* 재고 예약 계층 구조와 연결됩니다. 이러한 유형의 운영 설정의 장점은 어떤 배치를 선택하고 창고에 넣을 위치에 대한 결정(실제로는 예약 결정)이 창고 피킹 작업이 시작될 때까지 연기된다는 것입니다. 고객의 주문과 동시에 만들어지지 않습니다.

*Batch-below\[위치\]* 예약 계층 구조가 회사의 비즈니스 목표에 잘 부합하지만 회사의 많은 기존 고객은 제품을 재주문할 때 이전에 구매한 것과 동일한 배치를 필요로 합니다. 따라서 회사는 일괄 예약 규칙이 처리되는 방식의 유연성을 찾고 있으므로 동일한 품목에 대한 고객의 요구에 따라 다음과 같은 동작이 발생합니다.

- 배치 번호는 판매 프로세서가 주문을 받을 때 기록 및 예약할 수 있으며 창고 운영 중 및/또는 다른 수요로 인해 변경될 수 없습니다. 이 동작은 주문한 배치 번호가 고객에게 배송되도록 보장하는 데 도움이 됩니다.
- 고객에게 배치 번호가 중요하지 않은 경우 창고 운영은 판매 주문 등록 및 예약이 완료된 후 피킹 작업 중에 배치 번호를 결정할 수 있습니다.

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a>판매 주문의 특정 배치 예약 허용

*Batch-below\[위치\]* 재고 예약 계층 구조와 연결된 항목에 대한 일괄 예약 동작의 원하는 유연성을 수용하려면 재고 관리자는 **재고 예약 계층 구조** 페이지에서 **배치 번호** 수준에 대해 **주문형 예약 허용** 확인란을 선택해야 합니다.

![재고 예약 계층 구조를 유연하게 만듭니다.](media/Flexible-inventory-reservation-hierarchy.png)

계층 구조에서 **배치 번호** 수준을 선택하면 해당 수준 이상에서 **위치** 수준까지의 모든 차원이 자동으로 선택됩니다. (기본적으로 **위치** 수준 이상의 모든 차원이 미리 선택되어 있습니다.) 이 동작은 주문 라인에서 특정 배치 번호를 예약한 후 배치 번호와 위치 사이의 범위에 있는 모든 차원도 자동으로 예약되는 논리를 반영합니다.

> [!NOTE]
> **주문형 주문 예약 허용** 확인란은 창고 위치 차원 아래에 있는 예약 계층 구조 수준에만 적용됩니다.
>
> **배치 번호** 와 **번호판** 은 탄력적 예약 정책에 대해 열려 있는 계층 구조의 유일한 수준입니다. 즉, **위치** 또는 **일련 번호** 수준에 대해 **주문형 예약 허용** 확인란을 선택할 수 없습니다.
>
> 예약 계층에 일련 번호 차원(항상 **배치 번호** 수준 아래에 있어야 함)이 포함되어 있고 배치 번호에 대해 배치별 예약을 켠 경우 시스템은 *Serial-below\[위치\]* 예약 정책에 적용되는 규칙에 따라 일련 번호 예약 및 피킹 작업을 계속 처리합니다.

언제든지 배포에서 기존 *Batch-below\[위치\]* 예약 계층에 대한 일괄 예약을 허용할 수 있습니다. 이 변경 사항은 변경 사항이 발생하기 전에 생성된 예약 및 오픈 창고 작업에는 영향을 미치지 않습니다. 그러나 **예약된 주문**, **예약된 물리적** 또는 **주문된** 발행 유형의 재고 트랜잭션이 해당 예약 계층 구조와 연결된 하나 이상의 항목에 대해 존재하는 경우 **주문형 주문 예약 허용** 확인란의 선택을 취소할 수 없습니다.

> [!NOTE]
> 항목의 기존 예약 계층 구조가 주문에 대한 배치 지정을 허용하지 않는 경우 계층 수준 구조가 두 계층에서 동일하다면 배치 지정을 허용하는 예약 계층에 이를 재할당할 수 있습니다. **항목에 대한 예약 계층 변경** 기능을 사용하여 재할당을 수행합니다. 이 변경은 일괄 추적 항목의 하위 집합에 대해 유연한 일괄 예약을 방지하지만 나머지 제품 포트폴리오에는 허용하려는 경우에 적합할 수 있습니다.

**주문형 예약 허용** 확인란을 선택했는지 여부에 관계없이 주문 라인의 항목에 대한 특정 배치 번호를 예약하지 않으려면 *Batch-below\[위치\]* 예약에 유효한 기본 창고 작업 논리 계층 구조가 계속 적용됩니다

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a>고객 주문에 대한 특정 배치 번호 예약

배치 추적 항목의 *Batch-below\[위치\]* 재고 예약 계층이 판매 주문에 대한 특정 배치 번호의 예약을 허용하도록 설정된 후 판매 주문 프로세서는 고객의 요청에 따라 다음 방법 중 하나로 동일한 항목에 대한 고객 주문을 받을 수 있습니다.

- **배치 번호를 지정하지 않고 주문 세부 정보 입력** – 이 접근 방식은 제품의 배치 사양이 고객에게 중요하지 않을 때 사용해야 합니다. 이 유형의 주문 처리와 관련된 모든 기존 프로세스는 변경되지 않은 상태로 유지됩니다. 사용자 측에서는 추가 고려 사항이 필요하지 않습니다.
- **주문 세부 정보를 입력하고 특정 배치 번호를 예약합니다** – 이 접근 방식은 고객이 특정 배치를 요청할 때 사용해야 합니다. 일반적으로 고객은 이전에 구매한 제품을 재주문할 때 특정 배치를 요청합니다. 이러한 유형의 배치별 예약을 *주문 확약 예약* 이라고 합니다.

다음 규칙 집합은 수량이 처리되고 배치 번호가 특정 주문에 커밋될 때 유효합니다.

- *Batch-below\[위치\]* 예약 정책에 따라 항목에 대한 특정 배치 번호의 예약을 허용하려면 시스템이 모든 차원을 위치까지 예약해야 합니다. 이 범위에는 일반적으로 번호판 치수가 포함됩니다.
- 주문 약정 배치 예약을 사용하는 판매 라인에 대한 피킹 작업이 생성될 때 위치 지시문이 사용되지 않습니다.
- 주문이 확정된 배치에 대한 작업을 창고에서 처리하는 동안 사용자와 시스템 모두 배치 번호를 변경할 수 없습니다. (이 처리에는 예외 처리가 포함됩니다.)

다음 예는 엔드투엔드 흐름을 보여줍니다.

## <a name="example-scenario-batch-number-allocation"></a>예시 시나리오: 배치 번호 할당

이 예에서는 데모 데이터가 설치되어 있어야 하며 **USMF** 데모 데이터 회사를 사용해야 합니다.

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a><a name="Example-batch-allocation"></a>배치별 예약을 허용하도록 재고 예약 계층을 설정합니다.

1. **Warehouse Management** \> **설정** \> **재고 \> 예약 계층** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **이름** 필드에 이름을 입력합니다(예: **BatchFlex**).
4. **설명** 필드에 설명을 입력합니다(예: **유연 아래에 배치**).
5. **선택됨** 필드에서 **일련 번호** 및 **담당자** 를 선택한 다음 왼쪽 화살표 버튼을 선택하여 **사용 가능** 필드로 이동합니다.
6. **확인** 을 선택합니다.
7. **배치 번호** 차원 수준 행에서 **주문형 예약 허용** 확인란을 선택합니다. **번호판** 및 **위치** 수준은 자동으로 선택되며 해당 확인란의 선택을 취소할 수 없습니다.
8. **저장** 을 선택합니다.

### <a name="create-a-new-released-product"></a>새로 출시된 제품 생성

1. 다음 값을 사용하여 제품의 세 가지 마스터 데이터 매개 변수를 설정합니다.

    - **재고 규모 그룹** 필드에서 **창고** 를 선택합니다.
    - **추적 규모 그룹** 필드에서 **배치-실제** 를 선택합니다.
    - **예약 계층** 필드에서 **BatchFlex** 를 선택합니다.

2. **B11** 및 **B22** 와 같은 두 개의 배치 번호를 생성합니다.
3. 다음 값을 사용하여 현재고에 품목 수량을 추가합니다.

    | 창고 | 배치 번호 | 위치 | 번호판 | 수량 |
    |-----------|--------------|----------|---------------|----------|
    | 24        | B11          | BULK-001 | 없음          | 10       |
    | 24        | B11          | FL-001   | LP11          | 10       |
    | 24        | B22          | FL-002   | LP22          | 10       |

### <a name="enter-sales-order-details"></a><a name="sales-order-details"></a>판매 주문 세부 정보 입력

1. **영업 및 마케팅** \> **판매 주문** \> **모든 판매 주문** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. 판매 주문 헤더의 **고객 계정** 필드에 **US-003** 을 입력합니다.
4. 새 항목에 대한 라인을 추가하고 수량으로 **10** 을 입력합니다. **창고** 필드가 **24** 로 설정되어 있는지 확인합니다.
5. **판매 주문 라인** 빠른 탭에서 **재고** 를 선택한 다음 **유지 관리** 그룹에서 **배치 예약** 을 선택합니다. **배치 예약** 페이지에는 주문 라인에 대해 예약 가능한 배치 목록이 표시됩니다. 이 예에서는 배치 번호 **B11** 에 대해 수량 **20** 을 표시하고 배치 번호 **B22** 에 대해 수량 **10** 을 표시합니다. 배치별 예약을 허용하도록 설정되어 있지 않으면 해당 라인의 항목이 *Batch-below\[위치\]* 예약 계층과 연결된 경우 해당 라인에서 **배치 예약** 페이지에 액세스할 수 없습니다.

    > [!NOTE]
    > 판매 주문에 대한 특정 배치를 예약하려면 **배치 예약** 페이지를 사용해야 합니다.
    >
    > 판매 주문 라인에 배치 번호를 직접 입력하는 경우 시스템은 *Batch-below\[위치\]* 예약 정책이 적용되는 품목에 대해 특정 배치 값을 입력한 것처럼 작동합니다. 라인을 저장하면 경고 메시지가 표시됩니다. 배치 번호를 주문 라인에 직접 지정해야 함을 확인하면 해당 라인은 일반 창고 관리 논리에서 처리되지 않습니다.
    >
    > **예약** 페이지에서 수량을 예약하면 특정 배치가 예약되지 않으며 라인에 대한 창고 작업 실행은 *Batch-below\[위치\]* 예약 정책에 따라 적용되는 규칙을 따릅니다.

    일반적으로 이 페이지는 *Batch-above\[위치\]* 유형의 연결된 예약 계층이 있는 항목에 대해 동일한 방식으로 작동하고 상호 작용합니다. 그러나 다음 예외가 적용됩니다.

    - **소스 라인에 커밋된 배치 번호** 빠른 탭은 주문 라인에 대해 예약된 배치 번호를 표시합니다. 그리드의 배치 값은 창고 처리 단계를 포함하여 주문 라인의 이행 주기 전체에 걸쳐 표시됩니다. 반면에 **개요** 빠른 탭에서는 일반 주문 라인 예약(즉, **위치** 수준 이상의 차원에 대해 수행된 예약)이 창고 작업이 생성되는 시점까지 그리드에 표시됩니다. 그러면 작업 엔터티가 회선 예약을 인수하고 회선 예약이 페이지에 더 이상 표시되지 않습니다. **소스 라인에 커밋된 배치 번호** 빠른 탭은 판매 주문 프로세서가 송장 발행까지 수명 주기 중 어느 시점에서든 고객의 주문에 커밋된 배치 번호를 볼 수 있도록 보장합니다.
    - 특정 배치를 예약하는 것 외에도 사용자는 시스템이 자동으로 선택하도록 하는 대신 배치의 특정 위치와 번호판을 수동으로 선택할 수 있습니다. 이 기능은 주문 확정 배치 예약 메커니즘의 설계와 관련이 있습니다. 앞에서 언급했듯이 *Batch-below\[위치\]* 예약 정책에 따라 항목에 대한 특정 배치 번호의 예약을 허용하려면 시스템이 모든 차원을 위치까지 예약해야 합니다. 따라서 창고 작업은 주문에 대해 작업한 사용자가 예약한 것과 동일한 재고 규모를 수행하며 피킹 작업에 편리하거나 심지어 가능한 항목 저장 배치를 나타내지 않을 수도 있습니다. 주문 처리자가 창고 제약 조건을 알고 있는 경우 배치를 예약할 때 특정 위치와 번호판을 수동으로 선택하기를 원할 수 있습니다. 이 경우 사용자는 페이지 머리글에서 **규모 표시** 기능을 사용해야 하며 **개요** 빠른 탭의 그리드에 위치와 번호판을 추가해야 합니다.

6. **배치 예약** 페이지에서 배치 **B11** 에 대한 라인을 선택한 다음 **라인 예약** 을 선택합니다. 자동 예약시 위치와 번호판을 할당하는 로직은 따로 없습니다. **예약** 필드에 수량을 수동으로 입력할 수 있습니다. **소스 라인에 커밋된 배치 번호** 빠른 탭에서 배치 **B11** 이 **커밋됨** 으로 표시됩니다.

    ![배치 예약 페이지의 판매 주문 라인에 특정 배치 번호를 커밋합니다.](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > 판매 주문 라인의 수량 예약은 여러 배치에 걸쳐 수행할 수 있습니다. 마찬가지로 여러 위치 및 번호판에 대해 동일한 배치를 예약할 수 있습니다(위치에 번호판이 활성화된 경우).
    >
    > 판매 주문 라인의 수량에 대한 특정 배치 예약도 부분적일 수 있습니다. 예를 들어 총 수량 100개를 예약하여 특정 배치가 20개로 약정되는 반면 80개는 사용 가능한 배치에 대해 현장 및 창고 레벨에서 예약할 수 있습니다. 이 경우 WMS는 두 개의 개별 작업 라인을 사용하여 피킹 작업을 처리합니다.

7. **제품 정보 관리** \> **제품** \> **출시 제품** 으로 이동합니다. 항목을 선택한 다음 **재고 관리** \> **보기** \> **트랜잭션** 을 선택합니다.

    ![재고 트랜잭션 유형으로 주문 커밋된 예약입니다.](media/Inventory-transactions-for-order-committed-reservation.png)

8. 판매 주문 라인 예약과 관련된 품목의 재고 트랜잭션을 검토합니다.

    - **참조** 필드가 **판매 주문** 으로 설정되고 **발행** 필드가 **실제 예약됨** 으로 설정된 트랜잭션은 **위치** 수준 위의 재고 차원에 대한 주문 라인 예약을 나타냅니다. 항목의 재고 예약 계층에 따라 해당 차원은 사이트, 창고 및 재고 상태입니다.
    - **참조** 필드가 **주문 확정 예약** 으로 설정되고 **발행** 필드가 **실제 예약됨** 으로 설정된 트랜잭션은 특정 배치 및 그 위의 모든 재고 차원에 대한 주문 라인 예약을 나타냅니다. 항목의 재고 예약 계층 구조에 따라 해당 차원은 배치 번호와 위치입니다. 이 예에서 위치는 **Bulk-001** 입니다.

9. 판매 주문 헤더에서 **창고** \> **조치** \> **창고로 출고** 를 선택합니다. 이제 주문 라인이 흔들리고 부하와 작업이 생성됩니다.

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a>주문 완료 배치 번호가 있는 창고 작업 검토 및 처리

1. **판매 주문 라인** 빠른 탭에서 **창고** \> **작업 세부 정보** 를 선택합니다.

    판매 주문 라인에 약정된 배치 수량에 대한 피킹 작업을 처리하는 작업은 다음과 같은 특징이 있습니다.

    - 작업을 생성하기 위해 시스템은 작업 템플릿을 사용하지만 위치 지시문은 사용하지 않습니다. 최대 선택 라인 수 또는 특정 측정 단위와 같이 작업 템플릿에 대해 정의된 모든 표준 설정은 새 작업을 생성해야 하는 시기를 결정하는 데 적용됩니다. 그러나 주문 확정 예약이 이미 모든 재고 차원을 지정하기 때문에 피킹 위치를 식별하기 위한 위치 지시문과 연결된 규칙은 고려되지 않습니다. 이러한 재고 차원에는 창고 저장 수준의 차원이 포함됩니다. 따라서 작업은 위치 지시문을 참조하지 않고도 해당 차원을 상속합니다.
    - *Batch-above\[위치\]* 예약 계층이 연결된 항목에 대해 생성된 작업 라인의 경우와 같이 배치 번호는 선택 라인에 표시되지 않습니다. 대신 "시작" 배치 번호 및 기타 모든 저장 차원이 연관된 재고 트랜잭션에서 참조되는 작업 라인의 작업 재고 트랜잭션에 표시됩니다.

        ![주문 확정 예약에서 시작된 작업에 대한 창고 재고 트랜잭션입니다.](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - 작업이 생성되면 **참조** 필드가 **주문 확정 예약** 으로 설정된 항목의 재고 트랜잭션이 제거됩니다. **참조** 필드가 **작업** 으로 설정된 재고 트랜잭션은 이제 모든 수량의 재고 차원에 대한 실제 예약을 보유합니다.

        창고 작업은 일반적인 방식으로 작업 실행을 처리하도록 진행할 수 있습니다. 그러나 모바일 디바이스의 지침은 작업자에게 특정 배치 번호를 선택하도록 지시합니다. 위치가 번호판으로 제어되는 창고 환경에서는 작업자가 여러 번호판에 동일한 배치를 저장하는 위치에 도달한 후 아직 예약되지 않은 번호판에서 선택할 수 있습니다(예: 다른 주문 커밋 예약 또는 해당 유형의 예약에서 비롯된 작업)

        작업 라인에 지정된 위치에서 피킹하는 것이 비현실적인 것으로 판명되면 창고 운영자는 다음 조치 중 하나를 사용하여 보다 편리한 위치에서 특정 배치의 피킹을 리디렉션할 수 있습니다.

        - 모바일 디바이스의 표준 **위치 대체** 조치(창고 작업자의 **피킹 위치 대체 허용** 설정이 활성화된 경우)
        - **작업 목록 세부 정보** 페이지에서 **위치 변경** 작업입니다. 

2. 모바일 디바이스에서 작업을 선택하고 퍼팅을 완료합니다.

    이제 판매 주문 라인에 대해 배치 번호 **B11** 의 수량 **10** 이 선택되어 **베이도어** 위치에 배치됩니다. 이 시점에서 트럭에 싣고 고객의 주소로 배송할 준비가 되었습니다.

## <a name="flexible-license-plate-reservation"></a>유연한 번호판 예약

### <a name="business-scenario"></a>비즈니스 시나리오

이 시나리오에서 회사는 Warehouse Management 및 작업 처리를 사용하고 작업이 생성되기 전에 Supply Chain Management 외부의 개별 팔레트/컨테이너 수준에서 로드 계획을 처리합니다. 이러한 컨테이너는 재고 차원에서 번호판으로 표시됩니다. 따라서 이 접근 방식의 경우 피킹 작업이 완료되기 전에 특정 번호판을 판매 주문 라인에 미리 할당해야 합니다. 회사는 다음과 같은 동작이 발생하도록 번호판 예약 규칙을 처리하는 방식의 유연성을 찾고 있습니다.

- 번호판은 판매 프로세서가 주문을 받을 때 기록 및 예약할 수 있으며 다른 요구에 의해 가져갈 수 없습니다. 이 동작은 계획된 번호판이 고객에게 배송되도록 보장하는 데 도움이 됩니다.
- 번호판이 판매 오더 라인에 지정되지 않은 경우 창고 직원은 판매 오더 등록 및 예약이 완료된 후 피킹 작업 중에 번호판을 선택할 수 있습니다.

### <a name="turn-on-flexible-license-plate-reservation"></a>유연한 번호판 예약 켜기

유연한 번호판 예약을 사용하려면 시스템에서 두 가지 기능을 켜야 합니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 설정을 사용하여 기능의 상태를 확인하고 필요한 경우 켤 수 있습니다. 다음 순서로 기능을 켜야 합니다.

1. **기능 이름:** *유연한 창고 수준 차원 예약*
1. **기능 이름:** *유연한 주문 커밋된 번호판 예약*

### <a name="reserve-a-specific-license-plate-on-the-sales-order"></a>판매 주문에서 특정 번호판 예약

주문에 대한 번호판 예약을 활성화하려면 관련 항목과 연결된 계층 구조의 **재고 예약 계층** 페이지에서 **번호판** 수준에 대한 **주문형 예약 허용** 확인란을 선택해야 합니다.

![유연한 번호판 예약 계층 구조를 위한 재고 예약 계층 구조 페이지.](media/Flexible-LP-reservation-hierarchy.png)

배포의 어느 시점에서든 주문에 대해 번호판 예약을 활성화할 수 있습니다. 이 변경 사항은 변경 사항이 발생하기 전에 생성된 예약 또는 오픈 창고 작업에는 영향을 미치지 않습니다. 그러나 해당 예약 계층 구조와 연결된 하나 이상의 항목에 대해 문제 상태가 *주문 시*, *주문 예약됨* 또는 *실제 예약됨* 인 미결 아웃바운드 재고 트랜잭션이 있는 경우 **주문형 주문 예약 허용** 확인란의 선택을 취소할 수 없습니다.

**번호판** 수준에서 **주문형 예약 허용** 확인란을 선택하더라도 주문에 특정 번호판을 예약하지 *않을* 수 있습니다. 이 경우 예약 계층에 유효한 기본 창고 운영 논리가 적용됩니다.

특정 번호판을 예약하려면 [OData(Open Data Protocol)](../../fin-ops-core/dev-itpro/data-entities/odata.md) 프로세스를 사용해야 합니다. 애플리케이션에서 **Excel에서 열기** 명령의 **번호판별 주문 커밋 예약** 옵션을 사용하여 판매 주문에서 직접 이 예약을 수행할 수 있습니다. Excel 추가 기능에서 열리는 엔터티 데이터에서 다음 예약 관련 데이터를 입력한 다음 **게시** 를 선택하여 데이터를 다시 Supply Chain Management로 보내야 합니다.

- 참조(*판매 주문* 값만 지원됩니다.)
- 주문 번호(값은 로트에서 파생될 수 있습니다.)
- 로트 ID
- 번호판
- 수량

배치 추적 항목에 대해 특정 번호판을 예약해야 하는 경우 [판매 주문 세부 정보 입력](#sales-order-details) 섹션에 설명된 대로 **배치 예약** 페이지를 사용하세요.

주문 확정된 번호판 예약을 사용하는 판매 주문 라인이 창고 작업에서 처리되는 경우 위치 지시문이 사용되지 않습니다.

창고 작업 항목이 전체 팔레트와 같고 번호판 커밋된 수량을 가진 라인으로 구성된 경우 **번호판으로 처리** 옵션이 *예* 로 설정된 모바일 디바이스 메뉴 항목을 사용하여 피킹 프로세스를 최적화할 수 있습니다. 그러면 창고 작업자는 작업에서 항목을 하나씩 스캔할 필요 없이 번호판을 스캔하여 선택을 완료할 수 있습니다.

![번호판으로 처리 옵션이 예로 설정된 모바일 디바이스 메뉴 항목.](media/Handle-by-LP-menu-item.png)

**번호판으로 처리** 기능은 여러 팔레트를 다루는 작업을 지원하지 않으므로 다른 번호판에 대해 별도의 작업 항목을 갖는 것이 좋습니다. 이 접근 방식을 사용하려면 **작업 템플릿** 페이지에서 **주문 커밋된 번호판 ID** 필드를 작업 헤더 나누기로 추가합니다.

> [!NOTE]
> 주문 커밋 작업 생성 프로세스의 경우 "주문 커밋 재고 차원" 값이 피킹 작업 라인에 할당되며 번호판 값을 직접 볼 수 없습니다. 모바일 디바이스 메뉴 항목을 설정할 때 *사용자 지정* 프로세스만 지원됩니다.

## <a name="example-scenario-set-up-and-process-an-order-committed-license-plate-reservation"></a>예시 시나리오: 주문 완료 번호판 예약 설정 및 처리

이 시나리오는 주문 확정 번호판 예약을 설정하고 처리하는 방법을 보여줍니다.

### <a name="make-demo-data-available"></a>데모 데이터 사용 가능

이 시나리오는 Supply Chain Management를 위해 제공되는 표준 데모 데이터에 포함된 값과 레코드를 나타냅니다. 여기에 제공된 값을 사용하여 시나리오를 진행하려면 데모 데이터가 설치된 환경에서 작업해야 합니다. 또한 시작하기 전에 법인을 **USMF** 로 설정합니다.

### <a name="create-an-inventory-reservation-hierarchy-that-allows-for-license-plate-reservation"></a>번호판 예약을 허용하는 인벤토리 예약 계층 생성

1. **Warehouse Management \> 설정 \> 재고 \> 예약 계층** 으로 이동합니다.
1. **새로 만들기** 를 선택합니다.
1. **이름** 필드에 값(예: *FlexibleLP*)을 입력합니다.
1. **설명** 필드에 값(예: *Flexible LP 예약*)을 입력합니다.
1. **선택** 목록에서 **배치 번호**, **일련 번호** 및 **담당자** 를 선택합니다.
1. **제거** 단추 ![뒤로 화살표](media/backward-button.png)를 선택하여 선택한 레코드를 **사용 가능** 목록으로 이동합니다.
1. **확인** 을 선택합니다.
1. **번호판** 차원 수준 행에서 **주문형 예약 허용** 확인란을 선택합니다. **위치** 수준은 자동으로 선택되며 해당 확인란의 선택을 취소할 수 없습니다.
1. **저장** 을 선택합니다.

### <a name="create-two-released-products"></a>2개의 출시된 제품 만들기

1. **제품 정보 관리 \> 제품 \> 릴리스된 제품** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **새로 출시된 제품** 대화 상자에서 다음 값을 설정합니다.

    - **제품 번호:** *Item1*
    - **품목 번호:** *Item1*
    - **항목 모델 그룹:** *FIFO*
    - **항목 그룹:** *오디오*
    - **재고 규모 그룹:** *창고*
    - **추적 규모 그룹:** *없음*
    - **예약 계층:** *FlexibleLP*

1. **확인** 을 선택하여 제품을 생성하고 대화 상자를 닫습니다.
1. 새 프로젝트가 열려 있습니다. **창고** 빠른 탭에서 **단위 시퀀스 그룹 ID** 필드를 *개수* 로 설정합니다.
1. 이전 단계를 반복하여 동일한 설정을 가진 두 번째 제품을 생성하되 **제품 번호** 및 **품목 번호** 필드를 *Item2* 로 설정합니다.
1. 작업 창의 **재고 관리** 탭에 있는 **보기** 그룹에서 **현재고** 를 선택합니다. 그런 다음 **수량 조정** 을 선택합니다.
1. 다음 테이블에 지정된 대로 신규 품목의 현재고를 조정합니다.

    | 항목  | 창고 | 위치 | 번호판 | 수량 |
    |-------|-----------|----------|---------------|----------|
    | Item1 | 24        | FL-010   | LP01          | 10       |
    | Item1 | 24        | FL-011   | LP02          | 10       |
    | Item2 | 24        | FL-010   | LP01          | 5        |
    | Item2 | 24        | FL-011   | LP02          | 5        |

    > [!NOTE]
    > 두 개의 번호판을 생성하고 *FL-010* 및 *FL-011* 과 같이 혼합 품목을 허용하는 위치를 사용해야 합니다.

### <a name="create-a-sales-order-and-reserve-a-specific-license-plate"></a>판매 주문 생성 및 특정 번호판 예약

1. **영업 및 마케팅 \> 판매 주문 \> 모든 판매 주문** 으로 이동합니다.
1. **새로 만들기** 를 선택합니다.
1. **판매 주문 만들기** 대화 상자에서 다음 값을 설정합니다.

    - **고객 계정** *US-001*
    - **창고:** *24*

1. **확인** 을 선택하여 **판매 주문 생성** 대화 상자를 닫고 새 판매 주문을 엽니다.
1. **판매 주문 라인** 빠른 탭에서 다음 설정이 있는 줄을 추가합니다.

    - **품목 번호:** *Item1*
    - **수량:** *10*

1. 다음 설정이 있는 두 번째 판매 주문 라인을 추가합니다.

    - **품목 번호:** *Item2*
    - **수량:** *5*

1. **저장** 을 선택합니다.
1. **라인 세부 정보** 빠른 탭의 **설정** 탭에서 각 라인의 **로트 ID** 값을 기록해 둡니다. 이 값은 특정 번호판을 예약할 때 필요합니다.

    > [!NOTE]
    > 특정 번호판을 예약하려면 **번호판별로 주문 커밋 예약** 데이터 엔터티를 사용해야 합니다. 특정 번호판에서 배치 추적 항목을 예약하려면 [판매 주문 세부 정보 입력](#sales-order-details) 섹션에 설명된 대로 **배치 예약** 페이지를 사용할 수도 있습니다.
    >
    > 판매 주문 라인에 직접 번호판을 입력하여 시스템에 확인을 하면 해당 라인은 창고관리 처리가 되지 않습니다.

1. **Microsoft Office에서 열기** 를 선택하고 **번호판별 주문 약정 예약** 을 선택하고 파일을 다운로드합니다.
1. Excel에서 다운로드한 파일을 열고 **편집 사용** 을 선택하여 Excel 추가 기능을 실행할 수 있도록 합니다.
1. Excel 추가 기능을 처음 실행하는 경우 **이 추가 기능 신뢰** 를 선택합니다.
1. **로그인** 하라는 메시지가 표시되면 로그인을 선택한 다음 Supply Chain Management에 로그인할 때 사용한 것과 동일한 자격 증명을 사용하여 로그인합니다.
1. 특정 번호판의 항목을 예약하려면 Excel 추가 기능에서 **새로 만들기** 를 선택하여 예약 라인을 추가하고 다음 값을 설정합니다.

    - **로트 ID**: *Item1* 의 판매 주문 라인에 대해 찾은 **로트 ID** 값을 입력합니다.
    - **번호판:** *LP02*
    - **ReservedInventoryQuantity:** *10*

1. **새로 만들기** 를 선택하여 다른 라인을 추가하고 다음 값을 설정합니다.

    - **로트 ID**: *Item2* 의 판매 주문 라인에 대해 찾은 **로트 ID** 값을 입력합니다.
    - **번호판:** *LP02*
    - **ReservedInventoryQuantity:** *5*

1. Excel 추가 기능에서 **게시** 를 선택하여 데이터를 다시 Supply Chain Management로 보냅니다.

    > [!NOTE]
    > 예약 라인은 오류 없이 퍼블리싱이 완료된 경우에만 시스템에 나타납니다.

1. Supply Chain Management으로 돌아갑니다. 
1. 항목의 예약을 검토하려면 **판매 주문 라인** 빠른 탭의 **재고** 메뉴에서 **유지 관리 \> 예약** 을 선택합니다. *Item1* 에 대한 판매 주문 라인에 대해 *10* 의 재고가 예약되고 *Item2* 에 대한 판매 주문 라인에 대해 *5* 의 재고가 예약됩니다.
1. 판매 주문 라인 예약과 관련된 재고 트랜잭션을 검토하려면 **판매 주문 라인** 빠른 탭의 **재고** 메뉴에서 **보기 \> 트랜잭션** 을 선택합니다. 예약과 관련된 두 가지 트랜잭션이 있습니다. 하나는 **참조** 필드가 *판매 주문* 으로 설정되고 다른 하나는 **참조** 필드가 *주문 확정 예약* 으로 설정됩니다.

    > [!NOTE]
    > **참조** 필드가 *판매 주문* 으로 설정된 트랜잭션은 **위치** 수준(현장, 창고 및 재고 상태) 위에 있는 재고 차원에 대한 주문 라인 예약을 나타냅니다. **참조** 필드가 *주문 확정 예약* 으로 설정된 트랜잭션은 특정 번호판 및 위치에 대한 주문 라인 예약을 나타냅니다.

1. 판매 주문을 출고하려면 작업 창의 **창고** 탭에 있는 **작업** 그룹에서 **창고로 출고** 를 선택합니다.

### <a name="review-and-process-warehouse-work-with-order-committed-license-plates-assigned"></a>주문 완료 번호판이 할당된 창고 작업 검토 및 처리

1. **판매 주문 라인** 빠른 탭의 **창고** 메뉴에서 **작업 세부 정보** 를 선택합니다.

    특정 배치에 대한 예약이 완료되면 시스템은 번호판 예약을 사용하는 판매 주문에 대한 작업을 생성할 때 위치 지시를 사용하지 않습니다. 주문 확정 예약은 위치를 포함한 모든 재고 차원을 지정하기 때문에 위치 지시문을 사용할 필요가 없습니다. 해당 재고 차원이 작업에 입력되기 때문입니다. **작업 재고 트랜잭션** 페이지의 **재고 차원에서** 섹션에 표시됩니다.

    > [!NOTE]
    > 작업이 생성되면 **참조** 필드가 *주문 확정 예약* 으로 설정된 항목의 재고 트랜잭션이 제거됩니다. **참조** 필드가 *작업* 으로 설정된 재고 트랜잭션은 이제 모든 수량의 재고 차원에 대한 실제 예약을 보유합니다.

1. 모바일 디바이스에서 **번호판으로 처리** 확인란이 선택된 메뉴 항목을 이용하여 작품의 픽킹과 퍼팅을 마칩니다.

    > [!NOTE]
    > **번호판으로 처리** 기능은 전체 번호판을 처리하는 데 도움이 됩니다. 번호판의 일부를 처리해야 하는 경우 이 기능을 사용할 수 없습니다.
    >
    > 각 번호판에 대해 별도의 작업을 생성하는 것이 좋습니다. 이 결과를 얻으려면 **작업 템플릿** 페이지에서 **작업 헤더 나누기** 기능을 사용합니다.

    이제 판매 주문 라인에 대해 번호판 *LP02* 가 선택되어 *베이도어* 위치에 배치됩니다. 이 시점에서 로드 및 고객에게 발송할 준비가 되었습니다.

## <a name="exception-handling-of-warehouse-work-that-has-order-committed-batch-numbers"></a>주문 완료 배치 번호가 있는 창고 작업의 예외 처리

주문이 확정된 배치 번호를 피킹하기 위한 창고 작업은 일반 작업과 동일한 표준 창고 예외 처리 및 조치가 적용됩니다. 일반적으로 열려 있는 작업이나 작업 라인은 취소할 수 있고, 사용자 위치가 만차로 인해 중단될 수 있으며, 짤막하게 뽑힐 수 있으며, 이동으로 인해 업데이트될 수 있습니다. 마찬가지로 이미 완료된 작업의 선택 수량을 줄이거나 작업을 되돌릴 수 있습니다.

다음 주요 규칙은 이러한 모든 예외 처리 작업에 적용됩니다. 고객을 위해 예약된 배치 번호는 다른 배치 번호로 대체될 수 없지만, 저장 치수(위치 및 번호판)는 사용자에 의한 수동 업데이트 또는 시스템에 의한 자동 업데이트를 통해 변경할 수 있습니다. 자동 업데이트는 특정 배치가 자동으로 예약되었지만 스토리지 차원이 지정되지 않았을 때 적용된 동일한 무작위 스토리지 차원 할당을 기반으로 합니다.

### <a name="example-scenario"></a>예시 시나리오

이 시나리오의 예는 **피킹 수량 감소** 기능을 사용하여 이전에 완료된 작업이 피킹 해제되는 상황입니다. 이 예에서는 [예 시나리오: 배치 번호 할당](#Example-batch-allocation)에 설명된 단계를 이미 완료했다고 가정합니다. 예에서 계속됩니다.

1. **Warehouse Management** \> **부하** \> **활성 부하** 로 이동합니다.
2. 판매 주문 배송과 관련하여 생성된 로드를 선택합니다.
3. **주문 라인 로드** 빠른 탭에서 **피킹 수량 줄이기** 를 선택합니다.
4. **피킹 수량 줄이기** 페이지의 **위치로 이동** 필드에서 **FL-001** 을 선택합니다.
5. **번호판으로 이동** 필드에서 **LP33** 을 선택합니다.
6. 그리드의 **선택 해제할 재고 수량** 필드에 **10** 을 입력합니다.
7. **확인** 을 선택합니다.

다음은 선택 해제 작업의 결과입니다.

- 이전에 마감된 작업의 상태는 **취소됨** 으로 설정됩니다.
- **재고 이동** 유형의 신규 작업은 배치 번호 **B11** 에 대해 피킹되지 않은 수량 **10** 개에 대해 생성됩니다. 이 작업은 **베이도어** 위치에서 **FL-001** 위치의 번호판 **LP33** 으로의 이동을 나타냅니다. 상태가 **닫힘** 으로 설정됩니다.
- 시스템은 원래 주문한 배치 번호를 다시 예약하고 위치와 번호판 ID를 할당합니다. (이 프로세스는 지정된 배치 번호의 주문 라인에 대해 **라인 예약** 기능을 실행하는 것과 같습니다.) 결과적으로 **배치 예약** 페이지의 **소스 라인에 커밋된 배치 번호** 빠른 탭에서 배치 **B11** 이 커밋된 것으로 표시되며 **예약** 필드에는 **B11** 에 대한 수량 **10** 이 포함됩니다. 또한 **위치** 필드는 **FL-001** 로 설정되고 **번호판** 필드는 **LP11** 로 설정됩니다. (이러한 필드가 표시되지 않는 경우 그리드에 추가할 수 있습니다.)

다음 테이블은 시스템이 특정 창고 작업에 대한 주문 약정 배치 예약을 처리하는 방법을 보여주는 개요를 제공합니다. 테이블의 내용을 해석하려면 각 창고 조치가 주문 확정 배치 예약에서 시작된 기존 창고 작업의 컨텍스트에서 실행되거나 각 창고 조치의 실행이 해당 유형의 작업에 영향을 미친다고 가정합니다.

> [!NOTE]
> 이 테이블에서 "배치 수량 사용 가능" 열은 현재 주문 약정 예약에 대해 이미 예약되었거나 해당 유형의 예약에서 시작된 창고 작업에 의해 이미 예약된 수량 외에 배치 수량을 사용할 수 있는지 여부를 나타냅니다.

#### <a name="override-the-pick-location-on-the-open-work"></a>미결 작업에서 선택 위치 재정의

<table>
<thead>
<tr>
<th>키 설정 매개 변수</th>
<th>배치 수량 사용 가능</th>
<th>주요 사용자 단계</th>
<th>창고 작업</th>
<th>주문 확정 배치 예약</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>작업자에서 <strong>선택 위치 재정의 허용</strong> 옵션이 활성화됩니다.</td>
<td>예</td>
<td>
<ol>
<li>피킹 작업을 시작할 때 Warehouse Management 모바일 앱에서 <strong>위치 재정의</strong> 메뉴 항목을 선택합니다.</li>
<li><strong>제안</strong>을 선택합니다.</li>
<li>배치 수량 가용성을 기반으로 제안된 새 위치를 확인합니다.</li>
</ol>
</td>
<td>현재 작업에서 다음 작업이 발생합니다.
<ul>
<li>선택 라인의 위치가 새 위치로 업데이트됩니다. (위치가 번호판으로 제어되는 경우 작업 인벤토리 트랜잭션에 임의의 번호판이 할당되고 작업자는 사용 가능한 수량이 있는 번호판에서 선택할 수 있습니다.)</li>
<li>새 위치의 두 개 이상의 번호판에서 수량을 찾은 경우 원래 선택 라인은 각 번호판과 일치하도록 여러 라인으로 분할됩니다.</li>
</ul>
</td>
<td>해당 없음</td>
</tr>
<tr>
<td>아니요</td>
<td>
<ol>
<li>피킹 작업을 시작할 때 Warehouse Management 모바일 앱에서 <strong>위치 재정의</strong> 메뉴 항목을 선택합니다.</li>
<li>위치를 수동으로 입력합니다.</li>
</ol>
</td>
<td><strong>위치 재정의</strong> 작업은 불가능합니다. 실패하고 오류가 발생합니다.</td>
<td>해당 없음</td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a>전체 단추 – 사용자 위치의 오버플로로 인해 작업 라인 분할

<table>
<thead>
<tr>
<th>키 설정 매개 변수</th>
<th>배치 수량 사용 가능</th>
<th>주요 사용자 단계</th>
<th>창고 작업</th>
<th>주문 확정 배치 예약</th>
</tr>
</thead>
<tbody>
<tr>
<td>모바일 디바이스 메뉴 항목에서 <strong>작업 분할 허용</strong> 옵션이 활성화됩니다.</td>
<td>해당 없음</td>
<td>
<ol>
<li>피킹 작업을 처리할 때 Warehouse Management 모바일 앱에서 <strong>전체</strong> 메뉴 항목을 선택합니다.</li>
<li><strong>피킹 수량</strong> 필드에 전체 용량을 나타내기 위해 필요한 피킹의 부분 수량을 입력합니다.</li>
</ol>
</td>
<td>
<ul>
<li>현재 작업에서 수량이 피킹되어야 하는 나머지 수량으로 업데이트됩니다.</li>
<li>피킹된 수량에 대한 신규 작업이 생성되고 마감됩니다.</li>
</ul></td>
<td>해당 없음</td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a>(부하에서) 완료된 작업의 선택 수량을 줄입니다.

<table>
<thead>
<tr>
<th>키 설정 매개 변수</th>
<th>배치 수량 사용 가능</th>
<th>주요 사용자 단계</th>
<th>창고 작업</th>
<th>주문 확정 배치 예약</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>해당 없음</td>
<td>예</td>
<td>
<ol>
<li>로드 라인에서 <strong>피킹 수량 줄이기</strong> 페이지를 엽니다.</li>
<li>선택 해제할 전체 수량을 입력합니다.</li>
<li>"이동" 위치/번호판을 선택합니다.</li>
</ol>
</td>
<td>
<ul> 
<li>로드 라인과 관련된 작업이 취소됩니다.</li>
<li>재고 이동을 위한 새 작업이 생성되고 마감됩니다.</li>
</ul>
</td>
<td>수량은 동일한 배치에 대해 다시 예약됩니다. 시스템은 수량을 사용할 수 있는 위치와 번호판(위치가 번호판으로 제어되는 경우)을 무작위로 할당합니다.</td>
</tr>
<tr>
<td>아니요</td>
<td>이전 행을 참조하세요.</td>
<td>이전 행을 참조하세요.</td>
<td>수량은 동일한 배치 및 언피킹 중에 입력된 동일한 위치 및 번호판(위치가 번호판으로 제어되는 경우)에 대해 다시 예약됩니다.</td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a>창고 내에서 항목 이동

> [!NOTE]
> 이 창고 조치는 템플릿에 의한 이동이 아닌 **작업 생성 프로세스** 유형의 이동에만 적용됩니다.

<table>
<thead>
<tr>
<th>키 설정 매개 변수</th>
<th>배치 수량 사용 가능</th>
<th>주요 사용자 단계</th>
<th>창고 작업</th>
<th>주문 확정 배치 예약</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>작업자에서 <strong>연결된 작업과 함께 재고 이동 허용</strong> 옵션이 활성화됩니다.</td>
<td>예</td>
<td>
<ol>
<li>Warehouse Management 모바일 앱에서 이동을 시작합니다.</li>
<li>"시작" 및 "도착" 위치를 입력합니다.</li>
</ol></td>
<td>
<ul>
<li>이동의 영향을 받는 모든 기존 작업에서 선택 위치가 새 "도착" 위치로 업데이트됩니다.</li>
<li>재고 이동을 위한 새 작업이 생성되고 마감됩니다.</li>
</ul>
</td>
<td>지정된 위치에서 수량 이동의 영향을 받는 모든 기존 예약은 동일한 배치에 대해 다시 예약됩니다. 시스템은 수량을 사용할 수 있는 위치와 번호판(위치가 번호판으로 제어되는 경우)을 무작위로 할당합니다.</td>
</tr>
<tr>
<td>아니요</td>
<td>이전 행을 참조하세요.</td>
<td>이전 행을 참조하세요.</td>
<td>지정된 위치에서 수량 이동의 영향을 받는 모든 기존 예약은 동일한 배치와 새 "도착" 위치 및 번호판(위치가 번호판으로 제어되는 경우)에 대해 다시 예약됩니다.</td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a>완료된 작업의 선택된 수량을 취소합니다(부하 또는 웨이브에서).

<table>
<thead>
<tr>
<th>키 설정 매개 변수</th>
<th>배치 수량 사용 가능</th>
<th>주요 사용자 단계</th>
<th>창고 작업</th>
<th>주문 확정 배치 예약</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'>해당 없음</td>
<td>예</td>
<td>
<ol>
<li><strong>리버스 작업</strong> 페이지를 엽니다.</li>
<li>요청 페이지에서 <strong>현재 위치에 항목 유지</strong> 옵션을 선택합니다.</li>
</ol>
</td>
<td>로드와 관련된 모든 작업이 취소됩니다.</td>
<td>수량은 동일한 배치에 대해 다시 예약됩니다. 시스템은 수량을 사용할 수 있는 위치와 번호판(위치가 번호판으로 제어되는 경우)을 무작위로 할당합니다.</td>
</tr>
<tr>
<td>아니요</td>
<td>이전 행을 참조하세요.</td>
<td>이전 행을 참조하세요.</td>
<td>수량은 동일한 배치에 대해, 그리고 취소 시 수량이 남아 있던 위치 및 번호판에 대해 재예약됩니다.</td>
</tr>
<tr>
<td>예</td>
<td>
<ol>
<li><strong>리버스 작업</strong> 페이지를 엽니다.</li>
<li>요청 페이지에서 <strong>이 위치에 항목 할당</strong> 옵션을 선택합니다.</li>
</ol>
</td>
<td>
<ul>
<li>현재 작업이 취소되었습니다.</li>
<li>재고 이동을 위한 새 작업이 생성되고 마감됩니다.</li>
</ul>
</td>
<td>수량은 동일한 배치에 대해 다시 예약됩니다. 시스템은 수량을 사용할 수 있는 위치와 번호판(위치가 번호판으로 제어되는 경우)을 무작위로 할당합니다.</td>
</tr>
<tr>
<td>아니요</td>
<td>이전 행을 참조하세요.</td>
<td>이전 행을 참조하세요.</td>
<td>수량은 동일한 배치에 대해, 그리고 취소 시 수량에 할당된 위치 및 번호판에 대해 다시 예약됩니다.</td>
</tr>
<tr>
<td>예/아니요</td>
<td>
<ol>
<li><strong>리버스 작업</strong> 페이지를 엽니다.</li>
<li>요청 페이지에서 <strong>이 위치로 항목 이동</strong> 옵션을 선택합니다.</li>
</ol>
</td>
<td>반전은 지원되지 않습니다.</td>
<td>해당 없음</td>
</tr>
<tr>
<td>예/아니요</td>
<td>
<ol>
<li><strong>리버스 작업</strong> 페이지를 엽니다.</li>
<li>요청 페이지에서 <strong>위치 지시에 따라 항목 이동</strong> 옵션을 선택합니다.</li>
</ol>
</td>
<td>반전은 지원되지 않습니다. </td>
<td>해당 없음</td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a>수량 단기 선택 – 피킹 작업 시 현장/번호판에 물리적으로 발견되지 않는 수량으로 등록

<table>
<thead>
<tr>
<th>키 설정 매개 변수</th>
<th>배치 수량 사용 가능</th>
<th>주요 사용자 단계</th>
<th>창고 작업</th>
<th>주문 확정 배치 예약</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><strong>항목 재할당</strong> = <strong>없음</strong>, <strong>재고 조정</strong> = <strong>예</strong>, <strong>예약 제거</strong> = <strong>아니요</strong>인 <strong>단기 선택</strong> 유형의 작업 예외가 설정됩니다.</td>
<td>예</td>
<td>
<ol>
<li>피킹 작업 실행 시 Warehouse Management 모바일 앱에서 단기 <strong>선택 메뉴</strong> 항목을 선택하세요.</li>
<li><strong>피킹 수량</strong> 필드에 <strong>0</strong>(영)을 입력합니다.</li>
<li><strong>이유</strong> 필드에 <strong>재할당 없음</strong>을 입력합니다.</li>
</ol>
</td>
<td>
<ul>
<li>현재 작업이 마감되었으며 피킹된 수량은 0(영)입니다.</li>
<li>조정을 나타내기 위해 <strong>실사</strong> 유형 및 <strong>판매</strong> 발행 유형의 재고 트랜잭션이 생성됩니다.</li>
</ul>
</td>
<td>수량은 동일한 배치에 대해 다시 예약됩니다. 시스템은 수량을 사용할 수 있는 위치와 번호판(위치가 번호판으로 제어되는 경우)을 무작위로 할당합니다.</td>
</tr>
<tr>
<td>아니요</td>
<td>이전 행을 참조하세요.</td>
<td>
<ul>
<li>단기 선택 작업이 실패하고 오류가 발생합니다.</li>
<li>현재 작업은 열려 있습니다.</li>
</ul>
</td>
<td>해당 없음</td>
</tr>
<tr>
<td rowspan='2'><strong>항목 재할당</strong> = <strong>없음</strong>, <strong>재고 조정</strong> = <strong>예</strong>, <strong>예약 제거</strong> = <strong>예</strong>인 <strong>단기 선택</strong> 유형의 작업 예외가 설정됩니다.</td>
<td>예</td>
<td>
<ol>
<li>피킹 작업 실행 시 Warehouse Management 모바일 앱에서 단기 <strong>선택 메뉴</strong> 항목을 선택하세요.</li>
<li><strong>피킹 수량</strong> 필드에 <strong>0</strong>(영)을 입력합니다.</li>
<li><strong>이유</strong> 필드에 <strong>재할당 없음</strong>을 입력합니다.</li>
</ol>
</td>
<td>
<ul>
<li>현재 작업이 마감되었으며 피킹된 수량은 0(영)입니다.</li>
<li>조정을 나타내기 위해 <strong>실사</strong> 유형 및 <strong>판매</strong> 발행 유형의 재고 트랜잭션이 생성됩니다.</li>
</ul>
</td>
<td>단기 선택 위치에서 수량 조정의 영향을 받는 모든 기존 예약은 동일한 배치에 대해 다시 예약됩니다. 시스템은 수량을 사용할 수 있는 위치와 번호판(위치가 번호판으로 제어되는 경우)을 무작위로 할당합니다.</td>
</tr>
<tr>
<td>아니요</td>
<td>이전 행을 참조하세요.</td>
<td>이전 행을 참조하세요.</td>
<td>단기 선택 위치에서 수량 조정의 영향을 받는 모든 기존 예약이 제거됩니다.</td>
</tr>
<tr>
<td><strong>항목 재할당</strong> = <strong>수동</strong>, <strong>재고 조정</strong> = <strong>예</strong>, <strong>예약 제거</strong> = <strong>아니요/예</strong>인 <strong>단기 선택</strong> 유형의 작업 예외가 설정됩니다. 또한 작업자에서 <strong>수동 항목 재할당 허용</strong> 옵션이 활성화됩니다.</td>
<td>예</td>
<td>
<ol>
<li>피킹 작업 실행 시 Warehouse Management 모바일 앱에서 단기 <strong>선택 메뉴</strong> 항목을 선택하세요.</li>
<li><strong>수량 단기 선택</strong> 필드에 <strong>0</strong>(영)을 입력합니다.</li>
<li><strong>이유</strong> 필드에서 <strong>수동 재할당으로 단기 선택</strong>을 선택합니다.</li>
<li>목록에서 위치/번호판을 선택합니다.</li>
</ol>
</td>
<td>
<ul>
<li>현재 작업에서 다음 작업이 발생합니다.
<ul>
<li>피킹 라인이 닫혀 있고 피킹 수량이 0(영)입니다.</li>
<li>풋 라인이 취소됩니다.</li>
<li>새 피킹 라인이 생성됩니다. 사용자가 선택한 위치/번호판을 사용합니다.</li>
<li>새 픗 라인이 생성됩니다.</li>
</ul>
</li>
<li>조정을 나타내기 위해 <strong>실사</strong> 유형 및 <strong>판매</strong> 발행 유형의 재고 트랜잭션이 생성됩니다.</li>
</ul>
</td>
<td>해당 없음</td>
</tr>
<tr>
<td><strong>항목 재할당</strong> = <strong>수동</strong>, <strong>재고 조정</strong> = <strong>예</strong>, <strong>예약 제거</strong> = <strong>아니요</strong>인 <strong>단기 선택</strong> 유형의 작업 예외가 설정됩니다. 또한 작업자에서 <strong>수동 항목 재할당 허용</strong> 옵션이 활성화됩니다.</td>
<td>아니요</td>
<td>
<ol>
<li>피킹 작업 실행 시 Warehouse Management 모바일 앱에서 단기 <strong>선택 메뉴</strong> 항목을 선택하세요.</li>
<li><strong>수량 단기 선택</strong> 필드에 <strong>0</strong>(영)을 입력합니다.</li>
<li><strong>이유</strong> 필드에서 <strong>수동 재할당으로 단기 선택</strong>을 선택합니다.</li>
</ol>
</td>
<td>단기 선택 작업이 실패하고 오류가 발생합니다.</td>
<td>해당 없음</td>
</tr>
<tr>
<td><strong>항목 재할당</strong> = <strong>수동</strong>, <strong>재고 조정</strong> = <strong>예</strong>, <strong>예약 제거</strong> = <strong>예</strong>인 <strong>단기 선택</strong> 유형의 작업 예외가 설정됩니다. 또한 작업자에서 <strong>수동 항목 재할당 허용</strong> 옵션이 활성화됩니다.</td>
<td>아니요</td>
<td>
<ol>
<li>피킹 작업 실행 시 Warehouse Management 모바일 앱에서 단기 <strong>선택 메뉴</strong> 항목을 선택하세요.</li>
<li><strong>수량 단기 선택</strong> 필드에 <strong>0</strong>(영)을 입력합니다.</li>
<li><strong>이유</strong> 필드에서 <strong>수동 재할당으로 단기 선택</strong>을 선택합니다.</li>
<li>목록에서 위치/번호판을 선택합니다.</li>
</ol>
</td>
<td>
<ul>
<li>현재 작업에서 다음 작업이 발생합니다.
<ul>
<li>피킹 라인이 닫혀 있고 피킹 수량이 0(영)입니다.</li>
<li>풋 라인이 취소됩니다.</li>
</ul>
</li>
<li>조정을 나타내기 위해 <strong>실사</strong> 유형 및 <strong>판매</strong> 발행 유형의 재고 트랜잭션이 생성됩니다.</li>
</ul>
</td>
<td>단기 선택 위치/번호판에서 수량 조정의 영향을 받는 모든 기존 예약이 제거됩니다.</td>
</tr>
<tr>
<td><strong>항목 재할당</strong> = <strong>자동</strong>, <strong>재고 조정</strong> = <strong>예/아니요</strong>, <strong>예약 제거</strong> = <strong>예/아니요</strong>인 <strong>단기 선택</strong> 유형의 작업 예외가 설정됩니다.</td>
<td>해당 없음</td>
<td>
<ol>
<li>피킹 작업 실행 시 Warehouse Management 모바일 앱에서 단기 <strong>선택 메뉴</strong> 항목을 선택하세요.</li>
<li><strong>수량 단기 선택</strong> 필드에 <strong>0</strong>(영)을 입력합니다.</li>
<li><strong>이유</strong> 필드에서 <strong>자동 재할당으로 단기 선택</strong>을 선택합니다.</li>
</ol>
</td>
<td>자동 재할당을 포함하는 단기 선택은 지원되지 않습니다.</td>
<td>자동 재할당을 포함하는 단기 선택은 지원되지 않습니다.</td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a>재고 상태 변경

> [!NOTE]
> 이 창고 조치는 여러 진입점에서 수행할 수 있습니다. 여기에 표시된 예는 **위치별 현재고** 페이지에서 **재고 상태 변경** 조치를 사용합니다.

<table>
<thead>
<tr>
<th>키 설정 매개 변수</th>
<th>배치 수량 사용 가능</th>
<th>주요 사용자 단계</th>
<th>창고 작업</th>
<th>주문 확정 배치 예약</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'><strong>창고</strong> 탭의 <strong>창고</strong> 레코드에서 <strong>예약 및 표시 제거</strong> 필드가 <strong>예약</strong> 또는 <strong>표시 및 예약</strong>으로 설정됩니다.</td>
<td>예</td>
<td>
<ol>
<li>특정 위치를 선택합니다.</li>
<li>특정 항목, 위치 및 번호판이 있는 라인을 선택합니다(위치가 번호판으로 제어되는 경우).</li>
<li><strong>재고 상태 변경</strong>을 선택합니다.</li>
<li><strong>재고 상태</strong> 필드를 <strong>차단</strong>으로 설정합니다.</li>
</ol>
</td>
<td>작업용으로 예약된 수량에 대해서는 재고 상태 변경이 허용되지 않습니다.</td>
<td>
<ul>
<li>수량은 동일한 배치에 대해 다시 예약됩니다. 시스템은 수량을 사용할 수 있는 위치와 번호판(위치가 번호판으로 제어되는 경우)을 무작위로 할당합니다.</li>
<li>재고 상태 차원의 변경을 나타내기 위해 <strong>재고 상태 변경</strong> 유형의 두 가지 재고 트랜잭션이 생성됩니다.</li>
<li><strong>재고 차단</strong> 유형 및 <strong>예약된 물리적</strong> 출고 유형의 재고 트랜잭션이 차단 수량의 예약을 나타내기 위해 생성됩니다.</li>
</ul>
</td>
</tr>
<tr>
<td>아니요</td>
<td>이전 행을 참조하세요.</td>
<td>작업용으로 예약된 수량에 대해서는 재고 상태 변경이 허용되지 않습니다.</td>
<td>
<ul>
<li>예약이 삭제됩니다.</li>
<li>재고 상태 차원의 변경을 나타내기 위해 <strong>재고 상태 변경</strong> 유형의 두 가지 재고 트랜잭션이 생성됩니다.</li>
<li><strong>재고 차단</strong> 유형 및 <strong>예약된 물리적</strong> 출고 유형의 재고 트랜잭션이 차단 수량의 예약을 나타내기 위해 생성됩니다.</li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'><strong>창고</strong> 탭의 <strong>창고</strong> 레코드에서 <strong>예약 및 표시 제거</strong> 필드가 <strong>아니요</strong>로 설정됩니다.</td>
<td>예</td>
<td>
<ol>
<li>특정 위치를 선택합니다.</li>
<li>특정 항목, 위치 및 번호판이 있는 라인을 선택합니다(위치가 번호판으로 제어되는 경우).</li>
<li><strong>재고 상태 변경</strong>을 선택합니다.</li>
<li><strong>재고 상태</strong> 필드를 <strong>차단</strong>으로 설정합니다.</li>
</ol>
</td>
<td>작업용으로 예약된 수량에 대해서는 재고 상태 변경이 허용되지 않습니다.</td>
<td>수량은 동일한 배치에 대해 다시 예약됩니다. 시스템은 수량을 사용할 수 있는 위치와 번호판(위치가 번호판으로 제어되는 경우)을 무작위로 할당합니다.</td>
</tr>
<tr>
<td>아니요</td>
<td>이전 행을 참조하세요.</td>
<td>작업용으로 예약된 수량에 대해서는 재고 상태 변경이 허용되지 않습니다.</td>
<td>재고 상태 변경은 허용되지 않습니다.</td>
</tr>
</tbody>
</table>

## <a name="limitations"></a>제한 사항

- 유연한 창고 수준 차원 예약 기능은 다음 기능을 지원하지 않습니다.

    - 공칭 무게 관리
    - 실제 마이너스 재고
    - 주문 공급에 대한 예약
    - 이전 주문 및 원자재 피킹

- 지시 단위별 포장에 대한 컨테이너 통합 규칙에는 제한이 있습니다. 주문 확정 예약의 경우 **지시문 단위별 포장** 필드가 활성화된 컨테이너 빌드 템플릿을 사용하지 않는 것이 좋습니다. 현재 디자인에서는 창고 작업이 생성될 때 위치 지시문이 사용되지 않습니다. 따라서 컨테이너화 웨이브 단계에서는 단위 시퀀스 그룹의 가장 낮은 단위(재고 단위)만 적용됩니다.

## <a name="see-also"></a>참고 항목

- [Warehouse Management의 배치 번호](/dynamicsax-2012/appuser-itpro/batch-numbers-in-warehouse-management)
- [판매 주문에 대해 동일한 배치 예약](../sales-marketing/reserve-same-batch-sales-order.md)
- [모바일 디바이스에서 가장 오래된 배치 선택](pick-oldest-batch.md)
- [배치 및 번호판 확인](batch-and-license-plate-confirmation.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]