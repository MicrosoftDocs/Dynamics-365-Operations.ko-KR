---
title: 생산에서 하청계약 작업 관리
description: 이 토픽에서는 Dynamics 365 Supply Chain Management에서 하청 작업을 관리하는 방법에 대해 설명합니다. 즉, 자원에 할당된 생산 작업이 공급업체에서 관리되는 방식을 설명합니다.
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeanDocumentServiceCreation, PlanActivity, ProdBOMVendorListPage, ProdRoute, ProdTable, ProdTableListPage, PurchAgreementSubcontractorLookup, RouteTable, WrkCtrResourceGroup, ProdBOMVendorListPagePreviewPane, ProdBOMVendor
audience: Application User
ms.reviewer: kamaybac
ms.custom: 268174
ms.assetid: fe47c498-4f48-42a2-a0cf-5436c19ab3ea
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7e80efc751ccf9243163d23ed48fd17923326f89
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449212"
---
# <a name="manage-subcontracting-work-in-production"></a>생산에서 하청계약 작업 관리

[!include [banner](../includes/banner.md)]

이 토픽에서는 Dynamics 365 Supply Chain Management에서 하청 작업을 관리하는 방법에 대해 설명합니다. 즉, 자원에 할당된 생산 작업이 공급업체에서 관리되는 방식을 설명합니다.

[생산 프로세스](production-process-overview.md)에서 작업은 공급업체가 소유하거나 관리하는 리소스에 의해 수행될 수 있습니다. 일반적으로 공급업체 리소스는 회사 자체 리소스의 사용 가능한 용량을 초과하는 주기적인 초과 수요를 평준화하는 데 사용됩니다. 공급업체는 특정 [리소스 기능](resource-capabilities.md)이나 리소스를 더 저렴한 가격에 제공할 수도 있습니다.  

생산 프로세스에 사용되는 공급업체 리소스에 따라 자재 및 반제품을 먼저 공급업체 사이트로 운송해야 하기 때문에 [경로](routes-operations.md)에 추가 물류 요구 사항이 있는 경우가 많습니다. 그런 다음 하청 작업의 결과는 다음 작업에 할당된 위치 또는 완제품 창고로 운송되어야 합니다.  

하청계약 작업이나 활동을 사용하는 경우 생산, 원가 계산, 예측, 계획 및 일정 수립에 필요한 작업의 정의에서 자재, 반제품 및 완제품. 마지막으로 이러한 자원에는 회계 및 비용 관리를 위한 자체 프로세스가 필요합니다.  

내부 자원의 경우 일반적으로 일정 기간 동안 고정 비용 비율이 할당됩니다. 이에 반해 하청계약 자원의 비용은 관련 서비스의 구매 가격을 기준으로 한다. 서비스는 다른 제품으로 정의되며 주어진 하청 작업에 대한 조달 및 구매 프로세스를 구동하는 데 사용됩니다.  

현재 Supply Chain Management에는 반제품에 대한 명확한 개념이 없습니다. 원자재를 완제품으로 변환하기 위해 두 번 이상의 공정이 필요한 생산 오더의 경우 완제품은 마지막 공정에서만 재고로 전기됩니다. 이전 공정에서 생산하는 반제품은 WIP(재공품)로 계상되지만 재고에 전기되거나 추적되지 않습니다. 경로와 BOM(자재 명세서)을 여러 개의 작은 단위로 분할할 수 있지만 이 접근 방식은 관리해야 하는 제품, 자재 명세서 및 경로의 수를 늘립니다.  

생산 작업을 위한 하청계약 작업을 모델링하는 방법에는 두 가지가 있습니다. 이러한 방법은 하청계약 프로세스를 모델링할 수 있는 방식, 반제품이 프로세스에서 표현되는 방식 및 비용 관리가 관리되는 방식에서 다릅니다.

-   생산 주문 또는 배치 주문에서 루트 작업의 하청 계약
    -   서비스 제품은 재고 제품이어야 하며 BOM의 일부여야 합니다.
    -   이 방법은 FIFO(선입 선출) 또는 표준 비용을 지원합니다.
    -   반제품은 프로세스에서 서비스 제품으로 대표됩니다.
    -   비용 관리는 하청계약 작업과 관련된 비용을 재료비에 할당합니다.
-   린 생산 흐름에서 생산 흐름 활동의 하청계약
    -   이 서비스는 재고가 없는 서비스 제품이며 BOM의 일부가 아닙니다.
    -   이 방법은 구매 계약을 서비스 계약으로 사용합니다.
    -   이 방법은 역산 원가 계산을 사용합니다.
    -   이 방법을 사용하면 집계 및 비동기 조달이 가능합니다. (자재 흐름은 조달 프로세스와 무관합니다.)
    -   비용 관리는 자체 비용 분석 블록에 외주 작업을 할당합니다.

## <a name="subcontracting-of-route-operations"></a>경로 작업 하청계약
생산 또는 배치 주문에 대한 경로 작업의 하청계약을 사용하려면 서비스 조달에 사용되는 서비스 제품을 **서비스** 유형의 제품으로 정의해야 합니다. 또한 **인벤토리 정책** 에서 **재고 제품** 옵션이 **예** 로 설정된 항목 모델 그룹이 있어야 합니다. 이 옵션은 제품이 제품 입고 시 재고로 회계처리되는지(**재고 제품** = **예**) 또는 제품이 손익 계정에 비용 처리되는지(**재고 제품** = **아니오**) 정의합니다. 이 동작은 모순되는 것처럼 보일 수 있지만 이 정책이 있는 제품만 비용 관리에서 계획 비용을 계산하고 생산 주문이 종료될 때 실제 비용을 결정하는 데 사용할 수 있는 재고 트랜잭션을 생성한다는 사실에 기반합니다.  

계획 및 비용 계산에서 고려하려면 서비스를 BOM에 추가해야 합니다. BOM 라인은 **공급업체** 유형이어야 하며 서비스가 할당되는 경로 작업에 할당되어야 합니다. 이 경로 작업에는 작업 및 관련 서비스를 해당 공급업체 계정에 연결하는 **공급업체** 유형의 리소스를 가리키는 비용 계산 리소스 및 리소스 요구 사항이 있어야 합니다.  

이 구성을 사용하면 생산 주문의 추정치를 기반으로 관련 서비스 제품에 대한 구매 주문이 생성됩니다. 서비스의 구매 주문은 하청계약 작업의 앵커로 사용됩니다. 하청계약 작업은 생산 관리의 **하청계약 작업** 목록 페이지를 통해 관리할 수 있습니다. 하청 작업은 원자재를 선적하고 최종적으로는 반제품을 공급업체에 출하하여 작업을 준비하는 데 사용됩니다. 또한 서비스 제품이 반제품의 도착을 식별하는 데 사용되는 품목 도착 시 외주 작업의 결과 제품을 수신하는 데 사용됩니다. 구매 주문 라인이 입고되면 생산 공정이 완료된 것으로 업데이트됩니다.  

생산 주문에는 여러 작업이 있을 수 있으며 각 작업은 다른 공급업체에 할당될 수 있습니다. 따라서 종단 간 생산 주문은 여러 구매 주문을 트리거할 수 있습니다.

## <a name="subcontracting-of-production-flow-activities"></a>생산 흐름 활동의 하청계약
[린 제고](lean-manufacturing-overview.md) 솔루션은 [생산 흐름](tasks/create-production-flow-version.md)의 활동과 관련된 서비스로 외주 작업을 모델링합니다(작업 가이드 항목). 따라서 이러한 유형의 하청계약을 [활동 기반 하청계약](activity-based-subcontracting.md)이라고도 합니다. 특별 비용 그룹 유형인 **직접 아웃소싱** 이 도입되었으며 하도급 서비스는 완제품 BOM의 일부가 아닙니다. 린 제고를 사용하는 경우 모든 활동은 하나 이상의 생산 흐름 활동과 관련될 수 있는 간판에 의해 정의됩니다. 지금까지 그 설명은 생산 주문에 대한 설명처럼 들립니다. 그러나 생산 주문은 항상 완제품으로 끝나야 하지만 칸반을 생성하여 반제품을 공급할 수 있습니다. 새로운 제품과 BOM 레벨을 소개할 필요가 없습니다.  

칸반 규칙은 매우 동적일 수 있으므로 생산 흐름에서 동일한 제품에 대해 다양한 공급 변형을 모델링할 수 있습니다. 린 하청계약을 사용하면 자재 흐름과 재정 흐름이 엄격하게 분리됩니다. 모든 자재 흐름은 칸반 활동으로 표시됩니다. 서비스 제품에 대한 구매 주문 및 해당 서비스의 입고 전기는 생산 흐름의 간판 작업 상태에 따라 자동화될 수 있습니다. 칸반 작업은 구매 주문이 생성되기 전에 시작하고 완료할 수 있습니다. 하청계약 문서(서비스의 구매 주문 및 구매 영수증)는 기간 및 서비스별로 집계할 수 있습니다. 따라서 공급업체가 단일 흐름에서 하청계약 서비스를 제공하는 고도로 반복적인 작업에서도 구매 문서 및 라인의 수를 작게 유지할 수 있습니다.

### <a name="modeling-subcontracting-in-a-production-flow"></a>생산 흐름에서 하청계약 모델링

[린 생산 흐름](lean-manufacturing-modeling-lean-organization.md)에서 프로세스 활동은 단일 공급업체 리소스가 있는 작업 셀(리소스 그룹)에 할당될 때 외주로 정의될 수 있습니다. 작업 셀이 하도급될 때 관련 프로세스 활동은 서비스 항목과 서비스 가격이 포함된 활성 구매 계약 라인에 연결되어야 합니다. 활동의 서비스 계약은 칸반 작업의 제품 수량과 결과 서비스 수량 간의 계산 비율도 정의합니다. 서비스 수량을 작업 수, 작업에 보고된 양호한 제품 수량 또는 총 제품 수량(이 총 수량에는 폐기 제품 포함)을 기반으로 계산할지 선택할 수 있습니다.  

이전 활동은 하도급으로 정의할 수도 있습니다. 이 정의는 이전 활동에서 운송에 대한 책임 당사자를 선택할 때 암시적으로 발생합니다. **발송인** 또는 **수취인** 을 선택할 때 해당 출처 또는 대상 창고가 공급업체 관리 창고인 경우 활동은 하청계약으로 간주됩니다. **운송업체** 를 선택하면 활동은 항상 외주됩니다. 외주 프로세스 활동과 마찬가지로 외주 이전 활동은 생산 흐름을 활성화하기 전에 서비스 계약에 연결해야 합니다.

### <a name="backflush-costing"></a>역산 원가 계산

하청계약 작업의 원가 회계는 린 제고 솔루션(역산 원가 계산)에 대한 원가 계산에 완전히 통합됩니다. 서비스의 구매 주문 입고가 전기되거나 송장이 발생하면 서비스 비용이 생산 흐름에 할당됩니다. 백플러시 원가 계산의 경우 외주 서비스의 차이는 실제 입고 및 송장 서비스 수량에 대해 입고된 제품의 표준 원가의 외주 블록을 상계하여 계산됩니다.

## <a name="material-supply-for-subcontracted-operations"></a>하청계약 작업을 위한 자재 공급
반제품 및 기타 관련 자재는 물리적으로 작업이 수행되는 장소로 이송되어야 합니다. 외주 작업 및 활동을 사용하는 경우 이러한 이전은 종종 공급업체 운영 사이트로의 추가 운송과 관련됩니다. BOM의 자재를 외주 작업에 할당하여 할당된 자원에 대한 자원 그룹의 입력 위치에서 자재를 준비해야 한다고 선언합니다. 그런 다음 기준 계획 또는 린 보충을 통해 해당 위치에 자재를 공급합니다.  

공급업체 사이트에 있는 재고를 모델링하려면 공급업체 관리 창고를 정의하는 것이 업계에서 가장 좋은 방법입니다. 새 창고를 만들고 공급업체 계정을 할당하여 공급업체 관리 창고를 쉽게 정의할 수 있습니다. 작업을 수행하기 전에 자재를 공급업체로 이전해야 함을 문서화하려면 공급업체 관리 창고를 자원을 보유하는 자원 그룹의 입력 창고에 할당해야 합니다.  

이 창고에서 자재를 보충하기 위해 여러 전략을 사용할 수 있습니다.

-   이전 주문
-   분개장 이전
-   칸반 철회
-   판매자 위치로 직접 구매

반제품은 이 규칙의 예외입니다. 반제품을 전송하려면 다음 옵션으로 제한됩니다.

-   생산 및 배치 주문의 경우 반제품은 **하청계약 작업** 목록 페이지에서 피킹 목록 분개장을 사용하여 논리적으로만 이전할 수 있습니다. 이 분개장은 반제품 및 원자재를 공급업체에 이전하는 데 사용할 수 있는 납품서 문서를 생성합니다.
-   생산 흐름의 외주 작업의 경우 반제품의 이전은 공급업체 위치에서 철수 또는 생산 간판 수령으로 문서화됩니다. 명시적 이전 활동을 모델링하기 위해 추가 이전 활동으로 생산 칸반을 종료할 수 있습니다.

**참고:** 단일 생산 주문의 생산 경로는 여러 사이트를 횡단할 수 없습니다. 이 규칙은 하청계약 작업에도 적용됩니다. 따라서 공급업체 관리 자재 위치를 나타내는 창고는 경로에서 사용되는 내부 리소스와 동일한 사이트에 정의되어야 합니다. 생산 흐름은 현장을 넘어갈 수 있지만 한 현장에서 다른 현장으로 반제품을 운송할 수는 없습니다. 그 작업은 비용 상황의 변화를 의미하기 때문입니다.  

일반적으로 아웃풋 창고 및 외주 자원 그룹의 위치는 경로 또는 생산 흐름에서 작업의 다음 단계의 창고 및 위치에 직접 할당됩니다. 이 설정은 발생하는 작업 보고의 양이나 모델링해야 하는 추가 전송 작업의 수를 줄이는 데 도움이 됩니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]