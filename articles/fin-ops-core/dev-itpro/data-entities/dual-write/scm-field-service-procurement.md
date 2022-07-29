---
title: Supply Chain Management와 Field Service 간의 구매 통합
description: 이 항목에서는 이중 쓰기 통합이 Supply Chain Management 및 Field Service 모두에서 구매 주문 생성 및 업데이트를 지원하는 방법에 대해 설명합니다.
author: RamaKrishnamoorthy
ms.date: 11/11/2020
ms.topic: article
audience: Application User
ms.reviewer: tfehr
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ab251ee60bf3c831b0139beb9557c6b3faaf9f66
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8461001"
---
# <a name="integrate-procurement-between-supply-chain-management-and-field-service"></a>Supply Chain Management와 Field Service 간의 구매 통합

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Microsoft Dynamics 365 Supply Chain Management는 강력한 조달 기능을 제공합니다. Dynamics 365 Field Service는 서비스 프로세스와 관련된 구매 프로세스를 지원하는 유사한 기능을 제공합니다. 이 두 앱의 기능은 이중 쓰기를 통해 통합되며 결과적인 교차 기능 사용 사례는 테이블 매핑, 솔루션 논리, 보기 및 양식을 통해 활성화됩니다.

이 통합은 구매 주문 생성 및 대부분의 경우 두 앱의 업데이트를 지원합니다. 그러나 Supply Chain Management는 가격 책정, 주소 및 제품 수령을 제어합니다. Field Service와 Supply Chain Management를 모두 사용하는 조직에서는 여러 가지 강력한 기능 간 사용 사례를 사용할 수 있습니다. 이러한 사용 사례를 통해 두 시스템에서 조달을 시작하고 추적할 수 있습니다.

다음 그림은 두 시스템의 테이블과 테이블이 서로 매핑되는 방식을 보여줍니다. Field Service의 구매 주문은 *계정* 행을 참조하는 반면 Supply Chain Management의 구매 주문은 *공급업체* 열을 참조합니다. 통합을 해결하기 위해 이중 쓰기는 *공급업체* 행과 *계정* 행의 링크에 대한 참조를 사용합니다. 자세한 내용은 [통합 공급업체 마스터](vendor-mapping.md)를 참조하세요.

![조달을 위한 매핑.](media/scm-field-service-tables.png)

## <a name="prerequisites"></a>전제 조건

Supply Chain Management를 Field Service와 통합하려면 다음 구성 요소를 설치해야 합니다.

- 종합적인 구매 주문 통합을 위한 Field Service 버전 8.8.31.60 이상
- Supply Chain Management 버전 10.0.14 이상
- OneFSSCM 솔루션을 실행하기 위한 이중 쓰기

## <a name="installation-guidelines"></a>설치 지침

### <a name="prerequisites"></a>전제 조건

- **이중 쓰기** - 자세한 내용은 [이중 쓰기 홈페이지](dual-write-home-page.md#dual-write-setup)를 참조하세요.
- **Dynamics 365 Field Service** - 자세한 내용은 [Dynamics 365 Field Service 설치 방법](/dynamics365/field-service/install-field-service#step-1-install-dynamics-365-field-service)을 참조하세요.

Microsoft Dataverse에서 활성화되면 이중 쓰기 및 Field Service는 새로운 메타데이터, 양식, 보기 및 논리로 환경을 확장하는 여러 솔루션 계층을 도입합니다. 이러한 솔루션은 어떤 순서로든 활성화할 수 있지만 일반적으로 여기에 제공된 순서대로 설치합니다.

1. **Field Service Common** – Field Service Common은 Field Service가 환경에 설치될 때 설치됩니다.
2. **Field Service(Anchor)** – Field Service(Anchor)는 Field Service가 환경에 설치될 때 설치됩니다. 
3. **Supply Chain Management 확장** – 환경에서 이중 쓰기가 활성화되면 Supply Chain Management Extended가 자동으로 설치됩니다. 
4. **OneFSSCM 솔루션** – OneFSSCM은 마지막으로 설치된 솔루션(Field Service 또는 Supply Chain Management)에 의해 자동으로 설치됩니다.

    - Field Service가 환경에 이미 설치되어 있고 Supply Chain Management Extended를 설치하는 이중 쓰기를 활성화하면 OneFSSCM이 설치됩니다.
    - Supply Chain Management 확장이 환경에 이미 설치되어 있고 Field Service를 설치하면 OneFSSCM이 설치됩니다.

## <a name="initial-synchronization"></a>초기 동기화

새 구매 주문을 생성하고 기존 구매 주문으로 작업하려면 Supply Chain Management와 Dataverse 간의 참조 데이터를 동기화해야 합니다. 초기 쓰기 기능을 사용하여 테이블 관계를 감지하고 지정된 맵에 대해 활성화해야 하는 테이블을 찾습니다.

다음 테이블을 동기화해야 합니다.

- 제품 템플릿

    초기 쓰기를 실행하면 필요한 테이블의 전체 목록이 표시됩니다. 다음은 이러한 템플릿의 몇 가지 예입니다.

    - 모든 제품
    - 출시된 제품 V2
    - Dataverse 릴리스 고유 제품

- 사이트
- 창고
- 조달 카테고리 템플릿

    다음은 이러한 템플릿의 몇 가지 예입니다.

    - 조달 범주
    - Pro
    - 제품 범주 계층
    - 제품 범주 할당

- 공급업체 V2와 같은 공급업체 템플릿
- 담당자 템플릿, 예: Dataverse 연락처 V2
- 작업자와 같은 작업자 템플릿

테이블을 동기화하면 Supply Chain Management의 모든 문서(구매 주문서 및 제품 영수증)를 Dataverse에서 사용할 수 있습니다.

### <a name="account-and-vendor-tables"></a>계정 및 공급업체 테이블

Field Service의 구매 주문은 계정 테이블을 사용하여 공급업체를 추적합니다. 따라서 구매 주문의 Dataverse 테이블은 계정을 사용하여 공급업체를 추적합니다. 이러한 주요 차이점을 수용하려면 계정과 공급업체를 동기화된 상태로 유지하기 위해 다음 네 가지 워크플로를 활성화해야 합니다. 

- 계정 테이블에 공급업체 생성
- 공급업체 테이블에 공급업체 생성
- 계정 테이블에 공급업체 업데이트
- 공급업체 테이블에 공급업체 업데이트

OneFSSCM이 설치된 경우 Field Service와 Supply Chain Management Extended가 모두 설치되어 있으므로 이러한 워크플로가 자동으로 활성화됩니다. Field Service가 설치되어 있지 않지만 구매 주문 테이블을 Dataverse와 통합하려는 경우, 이러한 워크플로를 활성화해야 합니다. 두 경우 모두 처음부터 시작하지 않는 한 구매 주문을 생성하기 전에 Dataverse에서 모든 공급업체가 계정으로 생성되었는지 확인해야 할 수 있습니다. 그러지 않으면 오류가 발생할 수 있습니다.

### <a name="initial-synchronization"></a>초기 동기화

모든 전제 조건이 갖추어진 후 기존 구매 주문 및 제품 영수증을 두 시스템에서 모두 사용할 수 있게 하려면 다음 템플릿의 초기 동기화를 수행해야 합니다.

- 구매 주문 헤더 V2
- CDS 구매 주문 라인
- CDS 구매 발주 라인 일시 삭제
- 구매 주문 영수증
- 구매 주문 영수증 제품

## <a name="mappings-with-logic"></a>논리가 있는 매핑

조달 통합은 다음 로직으로 제품 매핑을 확장하여 **Field Service 제품 유형** 열이 Dataverse의 제품 테이블에 올바르게 설정되었는지 확인합니다.

- **상품 유형** 이 *제품* 으로 설정되고 **품목 모델군, 재고품** 이 *진실* 로 설정되면 **Field Service 제품 유형** 이 *목록* 으로 설정됩니다.
- **상품 유형** 이 *제품* 으로 설정되고 **품목 모델군, 재고품** 이 *False* 로 설정되면 **Field Service 제품 유형** 이 *비인벤토리* 로 설정됩니다.
- **상품 유형** 이 *서비스* 로 설정되면 **Field Service 제품 유형** 이 *서비스* 로 설정됩니다.

또한 Dataverse에는 공급업체를 관련 계정과 매핑하는 논리가 포함됩니다. 이 논리는 기본 송장 공급업체 계정을 설정합니다. 생성 시 서버 측 플러그인 논리는 계정과 관련된 공급업체의 기본 송장 공급업체 계정을 설정합니다. 공급업체에는 이 값을 설정하는 데 사용되는 송장 계정에 대한 참조가 있습니다.

## <a name="supported-scenarios"></a>지원되는 시나리오

- 구매 주문은 Dataverse 사용자가 생성 및 업데이트할 수 있습니다. 그러나 프로세스와 데이터는 Supply Chain Management에서 제어합니다. Field Service에서 업데이트가 제공되는 경우 Supply Chain Management의 구매 주문 열 업데이트에 대한 제약 조건이 적용됩니다. 예를 들어 구매 주문이 완료된 경우 업데이트할 수 없습니다. 
- 구매 주문이 Supply Chain Management의 변경 관리에 의해 제어되는 경우 Field Service 사용자는 Supply Chain Management 승인 상태가 *초안* 인 경우에만 구매 주문을 업데이트할 수 있습니다.
- 여러 열은 Supply Chain Management에서만 관리되며 Field Service에서 업데이트할 수 없습니다. 업데이트할 수 없는 열을 알아보려면 제품의 매핑 테이블을 검토하세요. 단순함을 위해 이러한 열의 대부분은 Dataverse 페이지에서 읽기 전용으로 설정됩니다. 

    예를 들어 가격 정보 열은 Supply Chain Management에서 관리합니다. Supply Chain Management에는 Field Service가 혜택을 받을 수 있는 무역 계약이 있습니다. **단가**, **할인**, **순액** 과 같은 열은 Supply Chain Management에서만 제공됩니다. 가격이 Field Service와 동기화되었는지 확인하려면 구매 주문 데이터가 입력되었을 때 Dataverse의 **구매 주문** 및 **구매 주문 제품** 페이지에서 **동기화** 기능을 사용해야 합니다. 자세한 내용은 [Dynamics 365 Supply Chain Management 주문형 조달 데이터와 동기화](#sync-procurement)를 참조하세요.

- **합계** 열은 Supply Chain Management에 구매 주문의 최신 합계가 없기 때문에 Field Service에서만 사용할 수 있습니다. Supply Chain Management의 총계는 Field Service에서 사용할 수 없는 여러 매개변수를 기반으로 계산됩니다.
- 구매 주문 라인은 조달 카테고리만 지정되거나 지정된 제품이 해당 품목의 품목인 경우 *서비스* 제품 유형 또는 Field Service 제품 유형은 Supply Chain Management에서만 시작할 수 있습니다. 라인은 Dataverse에 동기화되며 Field Service에서 볼 수 있습니다.
- Supply Chain Management가 아닌 Field Service만 설치된 경우 **창고** 열은 구매 주문서의 필수 항목입니다. 그러나 Supply Chain Management가 설치된 경우 Supply Chain Management는 특정 상황에서 창고가 지정되지 않은 구매 주문 라인을 허용하기 때문에 이 요구 사항이 완화됩니다.
- 제품 영수증(Dataverse의 구매 주문 영수증)은 Supply Chain Management에서 관리하며 Supply Chain Management가 설치된 경우 Dataverse에서 생성할 수 없습니다. Supply Chain Management의 제품 입고는 Supply Chain Management에서 Dataverse로 동기화됩니다.
- Supply Chain Management에서 미달 배달이 허용됩니다. OneFSSCM 솔루션은 제품 영수증 라인(또는 Dataverse의 구매 주문서 영수증 제품)이 생성되거나 업데이트되면 인벤토리 분개 행이 Dataverse에 생성되어 미달 배달 시나리오에 대해 주문한 나머지 수량을 조정하는 경우 생성됩니다.

## <a name="unsupported-scenarios"></a>지원되지 않는 시나리오

- Field Service는 Supply Chain Management에서 취소된 구매 주문에 라인이 추가되는 것을 방지합니다. 해결 방법으로 Field Service에서 구매 주문의 시스템 상태를 변경한 다음 Field Service 또는 Supply Chain Management에서 새 라인을 추가할 수 있습니다.
- 조달 행이 두 시스템의 재고 수준에 영향을 미치지만 이 통합은 Supply Chain Management 및 Field Service 전반에 걸쳐 재고 정렬을 보장하지 않습니다. Field Service와 Supply Chain Management에는 재고 수준을 업데이트하는 다른 프로세스가 있습니다. 이러한 프로세스는 조달 범위를 벗어납니다.

## <a name="status-management"></a>상태 관리

Field Service의 구매 주문 상태는 Supply Chain Management의 상태와 다릅니다.

### <a name="field-service-purchase-order-and-purchase-order-product-statuses"></a>Field Service 구매 주문 및 구매 주문 제품 상태

| 헤더 - 시스템 상태 | 헤더 - 승인 상태 | 항목 상태 |
|---|---|---|
| <ul><li>초안</li><li>제출됨</li><li>취소됨</li><li>수령한 제품</li><li>청구됨</li></ul> | <ul><li>Null</li><li>승인됨</li><li>거부됨</li></ul> | <ul><li>보류 중</li><li>수령함</li><li>취소됨</li></ul> |

### <a name="supply-chain-management-purchase-order-and-purchase-order-line-statuses"></a>Supply Chain Management 구매 발주 및 구매 발주 라인 상태

라인 승인 상태는 라인 워크플로우가 있는 경우에만 활성화됩니다.

| 헤더 - 문서 상태 | 헤더 - 승인 상태 | 라인 상태 | 라인 승인 상태 |
|---|---|---|---|
| <ul><li>오픈 오더(백오더)</li><li>수령함</li><li>송장 발부됨</li><li>취소됨</li></ul> | <ul><li>초안</li><li>검토 중</li><li>승인됨</li><li>거부됨</li><li>외부 검토 중</li><li>확인됨</li><li>확정됨</li></ul> | <ul><li>오픈 오더(백오더)</li><li>수령함</li><li>송장 발부됨</li><li>취소됨</li></ul> | <ul><li>제출되지 않음</li><li>검토 중</li><li>승인됨</li><li>거부됨</li></ul> |

상태 열에는 다음 규칙이 적용됩니다.

- Supply Chain Management의 상태는 Field Service에서 업데이트할 수 없습니다. 그러나 경우에 따라 Supply Chain Management의 구매 주문 상태가 변경되면 Field Service의 상태가 업데이트됩니다.
- Supply Chain Management의 구매 주문이 변경 관리 중이고 변경이 처리 중인 경우 승인 상태는 *초안* 또는 *검토 중* 입니다. 이 경우 Field Service 승인 상태는 *Null* 로 설정됩니다.
- Supply Chain Management의 구매 발주 승인 상태가 *승인됨*, *외부 검토 중*, *확인됨* 또는 *확정됨* 으로 설정되면 Field Service 구매 주문 승인 상태는 *승인됨* 으로 설정됩니다.
- Supply Chain Management의 구매 발주 승인 상태가 *거부됨* 으로 설정되면 Field Service 구매 주문 승인 상태는 *거부됨* 으로 설정됩니다.
- Supply Chain Management의 문서 헤더 상태가 *오픈 오더(백오더)* 로 변경되고 Field Service 구매 주문 상태가 *초안* 또는 *취소됨* 이면 Field Service 구매 주문 상태가 *제출됨* 으로 변경됩니다.
- Supply Chain Management의 문서 헤더 상태가 *취소됨* 으로 변경되고 Field Service의 구매 주문 영수증 제품이 구매 주문과 연결되지 않은 경우(구매 주문 제품을 통해) Field Service 시스템 상태는 *취소됨* 으로 설정됩니다.
- Supply Chain Management의 구매 발주 라인 상태가 *취소됨* 인 경우 Field Service의 구매 주문 제품 상태가 *취소됨* 으로 설정됩니다. 또한 Supply Chain Management의 구매 발주 라인 상태가 *취소됨* 에서 *백오더* 로 변경되면 Field Service의 구매 주문 제품 항목 상태가 *보류 중* 으로 설정됩니다.

## <a name="sync-with-the-supply-chain-management-procurement-data-on-demand"></a><a id="sync-procurement"></a>Supply Chain Management 주문형 조달 데이터와 동기화

Supply Chain Management에는 Supply Chain Management의 보조 프로세스에 의존하는 무역 계약, 할인 및 기타 시나리오를 처리하는 조달 데이터가 포함됩니다. 조달 엔진은 복잡한 규칙을 사용하여 주어진 구매 주문에 대한 최적의 가격을 결정합니다. 이중 쓰기를 사용하는 경우 데이터가 두 환경에서 항상 동기화된 상태로 유지되지는 않습니다. 특히 Dataverse에서 행이 생성되거나 업데이트된 시나리오에서 Supply Chain Management에서 후속 프로세스를 트리거할 수 있습니다.

## <a name="sync-the-procurement-data-from-supply-chain-management"></a>Supply Chain Management에서 조달 데이터와 동기화

1. Dataverse에서 **재고 \> 구매 주문** 으로 이동합니다.
2. **새로 만들기** 를 선택하여 새 구매 주문을 생성하거나 기존 구매 주문의 행을 선택합니다.
3. 구매 발주 또는 구매 발주 라인에서
4. 작업 창에서 **동기화** 를 선택합니다.

Supply Chain Management에서 공유하는 Dataverse 및 Field Service의 모든 열이 동기화됩니다.

다음은 **동기화** 함수를 사용할 수 있는 상황입니다.

- Dataverse에서 동일한 행을 여러 번 연속으로 변경하는 경우 **동기화** 함수를 실행합니다.
- 변경 사항이 Dataverse의 두 번째 연속 변경 사항인지 여부가 확실하지 않은 경우 **동기화** 함수를 실행하는 것이 합리적일 수 있습니다.
- Supply Chain Management에서 값 업데이트에 대한 오류 메시지를 받으면 **동기화** 함수를 실행하고 Dataverse에서 업데이트를 다시 시도합니다.

## <a name="cancelling-the-posting-process"></a>게시 프로세스 취소

처리 중에 제품 영수증 전기 프로세스가 취소되면 Dataverse에서 이중 쓰기가 제품 영수증 행을 생성할 수 있습니다. 그러나 Supply Chain Management에서 제품 입고 행을 생성하지 마세요. 이 상황은 이중 쓰기가 분산 트랜잭션을 지원하지 않기 때문에 발생합니다.

## <a name="templates"></a>템플릿

조달 관련 문서 통합에 사용할 수 있는 템플릿은 다음과 같습니다.

| Supply Chain Management | Field Service | 설명 |
|---|---|---|
| [구매 주문 헤더 V2](mapping-reference.md#183) | msdyn\_Purchaseorders | 이 테이블에는 구매 주문 헤더를 나타내는 열이 포함되어 있습니다. |
| [구매 주문 라인 엔터티](mapping-reference.md#181) | msdyn\_PurchaseOrderProducts | 이 테이블에는 구매 주문의 라인을 나타내는 행이 포함되어 있습니다. 제품 번호는 동기화에 사용됩니다. 이것은 제품 치수를 포함하여 제품을 SKU(재고 보관 단위)로 식별합니다. Dataverse와 제품 통합에 대한 자세한 내용은 [통합된 제품 경험](product-mapping.md)을 참조하세요. |
| [제품 영수증 헤더](mapping-reference.md#185) | msdyn\_purchaseorderreceipts | 이 테이블에는 제품 입고가 Supply Chain Management에 전기될 때 생성되는 제품 입고 헤더가 포함되어 있습니다. |
| [제품 수령 라인](mapping-reference.md#184) | msdyn\_purchaseorderreceiptproducts | 이 테이블에는 제품 입고가 Supply Chain Management에 전기될 때 생성되는 제품 입고 라인이 포함되어 있습니다. |
| [구매 주문 라인 일시 삭제 엔터티](mapping-reference.md#182) | msdyn\_purchaseorderproducts | 이 테이블에는 일시 삭제된 구매 발주 라인에 대한 정보가 포함되어 있습니다. Supply Chain Management의 구매 주문 라인은 변경 관리가 켜져 있는 경우 구매 주문이 확인되거나 승인된 경우에만 일시 삭제할 수 있습니다. 행은 Supply Chain Management 데이터베이스에 있으며 **IsDeleted** 로 표시됩니다. Dataverse 소프트 삭제 개념이 없으므로 이 정보를 Dataverse에 동기화하는 것이 중요합니다. 이러한 방식으로 Supply Chain Management에서 일시 삭제된 라인은 Dataverse에서 자동으로 삭제될 수 있습니다. 이 경우 Dataverse의 라인을 삭제하는 논리는 Supply Chain Management 확장에 있습니다. |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
