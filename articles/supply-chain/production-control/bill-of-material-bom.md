---
title: 자재 명세서 및 공식
description: 이 항목에서는 제품 및 제품 변형 정의의 중심 부분인 재료 명세서(자재 명세서) 및 공식에 대한 정보를 제공합니다.
author: johanhoffmann
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, EcoResProductProcessManufacturingWorkspace, ProdBOM, ProdJournalTransBOM, ProdBOMCurrent, PmfBOMDesignerEditCoBy, ProdJournalPickingListLineSummary, ProdBOMOverview, PmfCoReqPlanning, EcoResProductProdTypeFormulaNoActiveFormulaFormPart, EcoResItemsMissingActiveRouteVersionFormPart, EcoResItemsProdTypeBOMExpiringBOMFormPart, BOMDesignerBOMVersion, BOMExpandPurch, BOMChangeLine, BOMExpandSales, EcoResItemsProdTypeBOMExpiringRouteFormPart, EngChgEcmBomDesigner, EngChgEcmProductBOMItemIdLookup, EngChgEcmProductBOMConsistOf, EngChgEcmBOMCopyDialog, EngChgEcmBomDesignerEditBom, BOMDesignerFilterDialog, BOMDesignerFilterDialog, BOMPartOf, BOMSetupReportFinish, EcoResItemsMissingActiveBOMVersionFormPart, BOMIdLookup, EcoResProductProdTypeFormulaNoActiveRouteFormPart, BOMExpandPurchRFQ, EngChgCaseRouteTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19331
ms.assetid: c19b437a-2de2-4728-9477-2bcb0c2b1f5e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 12a70720775d9903a875dd1759ea2372f1f3b122
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449065"
---
# <a name="bills-of-materials-and-formulas"></a>자재 명세서 및 공식

[!include [banner](../includes/banner.md)]

이 항목에서는 제품 및 제품 변형 정의의 중심 부분인 재료 명세서(자재 명세서) 및 공식에 대한 정보를 제공합니다. BOM 및 공식은 특정 제품에 필요한 재료 또는 성분을 지정합니다. 공식은 또한 특정 생산 컨텍스트에서 받는 부산물 및 부산물을 지정합니다. 

## <a name="bills-of-materials"></a>자재 명세서

BOM(자재 명세서)은 제품을 생산하는 데 필요한 구성 요소를 정의합니다. 구성 요소는 원료, 반제품 또는 재료가 될 수 있습니다. 경우에 따라 BOM에서 서비스를 참조할 수 있습니다. 그러나 BOM은 일반적으로 필요한 *물질적 자원* 을 설명합니다.  

제품을 구축하는 데 필요한 작업 및 리소스를 설명하는 경로 또는 생산 흐름과 결합될 때 BOM은 제품의 예상 비용을 계산하기 위한 기초를 형성합니다.  

BOM은 다음 정보로 설명되는 개별 엔티티입니다.

-   BOM ID
-   BOM 이름
-   구성 요소 및 성분을 설명하는 BOM 라인
-   BOM을 사용할 수 있는 제품 및 기간을 정의하는 BOM 버전

단일 BOM은 고유 ID로 식별되는 단일 레벨을 설명합니다. 구성 요소에는 BOM 버전에서 참조하는 자체 BOM이 있을 수 있습니다. BOM 디자이너에서 특정 제품에 대한 전체 BOM 계층을 표시하고 편집할 수 있습니다.

### <a name="formulas-co-products-and-by-products"></a>공식, 부산물 및 부산물

공식은 일반적으로 공정 제조에 사용되는 BOM의 하위 유형입니다. 성분 및 성분 외에도 공식은 부산물 및 부산물을 설명합니다. 실제 버전에서 공식에 대한 부산물 및 부산물의 정의에는 공식 버전이 필요합니다. 공식은 일반적으로 공식 버전에 정의된 하나의 특정 완제품(공식 또는 계획 품목)에 대해 정의됩니다.

### <a name="boms-in-the-product-lifecycle"></a>제품 수명 주기의 BOM

제품 수명 주기에서 다양한 유형의 BOM이 다음과 같은 다양한 이유로 생성될 수 있습니다.

-   **스케치/드래프트 BOM** – 이 BOM은 초기 설계 단계에서 필요한 자재의 추정 초안을 제공하고 비용 및 예상 제품 속성의 대략적인 추정을 수행하는 데 도움이 됩니다. 이 BOM은 일반적으로 ERP(전사적 자원 관리)에서 사용되지 않습니다.
-   **엔지니어링 BOM** – 이 BOM은 일반적으로 기존 제품 포트폴리오를 기반으로 하는 제품을 설계할 때 사용됩니다. 엔지니어링 BOM은 설계 프로세스를 단순화하고 복잡한 제품을 엔지니어링 모듈로 그룹화하도록 구성됩니다. 단순한 제품의 경우 실제 생산 공정을 위한 엔지니어링 BOM이 가능할 수 있습니다. 그러나 다른 제품의 경우 엔지니어링 BOM을 실제 생산 BOM으로 변환해야 합니다. 엔지니어링 BOMS는 일반적으로 BOM 계층에서 팬텀으로 표시됩니다. 엔지니어링 BOM을 제조 작업의 계획 및 실행에 사용할 수 있지만 이 접근 방식은 특히 많은 주문이 생성되는 반복 작업에서 비효율성을 유발할 수 있습니다.
-   **기획 BOM** – 이 BOM은 자재 요구 사항에 대한 계획을 수행하는 데 사용됩니다. 구성 요소 및 재료의 수요는 완제품의 수요를 기반으로 계산됩니다. BOM 원가 계산과 마찬가지로 BOM 계획은 특정 기간에 사용되는 재료의 특정 조합을 나타낼 수 있습니다.
-   **생산 BOM** – 특정 생산에 사용되는 실제 BOM입니다. 생산 BOM은 제품 생산에 사용되는 실제 자원을 고려해야 합니다. 생산 주문, 배치 주문 또는 칸반이 생성되면 팬텀으로 표시되는 여러 수준의 BOM이 한 수준으로 축소되고 해당 주문에 대한 작업에 분산됩니다.
-   **원가 계산 BOM** – 이 BOM은 제품의 예상 비용을 계산하는 데 사용됩니다. 예를 들어, 표준 원가를 사용하거나 주어진 제품의 예상 계획 원가를 계산할 때 원가계산 BOM을 사용할 수 있습니다. 원가계산 BOM은 사용될 것으로 예상되는 재료 및 자원의 특정 조합을 참조할 수 있습니다. 따라서 원가계산 BOM을 사용하여 기간에 대한 대표적인 추정 원가를 생성하고 시간 경과에 따른 변동을 방지할 수 있습니다.

구현에 실제로 사용되는 BOM 유형은 구현과 비즈니스 시나리오 및 요구 사항에 따라 다릅니다. 간단한 구현에서는 계획 BOM, 생산 BOM 및 원가 계산 BOM을 하나의 BOM으로 모델링할 수 있습니다. 엔지니어링 변경이 빈번하고 대체 경로가 여러 개인 환경에서는 더 많은 BOM 유형 세트가 필요할 수 있습니다.

### <a name="approval-of-boms-and-formulas"></a>BOM 및 공식 승인

각 BOM 및 공식은 별도로 승인되거나 승인되지 않을 수 있습니다. 일반적으로 BOM 및 공식 승인은 첫 번째 관련 BOM 버전이 승인될 때 발생합니다. 그러나 일부 비즈니스 시나리오에서 이러한 승인은 프로세스의 다른 단계일 수 있으며 다른 프로세스 소유자를 포함할 수 있습니다.  

BOM이 승인되지 않은 경우 관련된 모든 BOM 버전도 승인되지 않습니다.

## <a name="bom-and-formula-versions"></a>BOM 및 공식 버전
특정 BOM 또는 공식을 생산할 수 있는 제품 변형과 연관시키려면 BOM 버전 또는 공식 버전을 생성해야 합니다. BOM 버전 및 공식 버전의 유효성은 기간, 수량, 사이트, 특정 제품 치수 및 기타 기준에 따라 제한될 수 있습니다. 공식 버전에는 수율, 부산물 및 부산물 정의, 공식에 대한 비용 분배 지침과 같은 중요한 추가 속성이 있습니다.

### <a name="approval-of-bom-and-formula-versions"></a>BOM 및 공식 버전 승인

BOM 버전을 계획 또는 제조 프로세스에서 사용하려면 먼저 승인을 받아야 합니다. BOM 버전이 승인되면 사용자의 선택 및 인증 권한에 따라 관련 BOM도 승인될 수 있습니다. BOM 버전은 해당 BOM 자체가 승인된 경우에만 승인될 수 있음을 유의하시기 바랍니다.

### <a name="activation-of-the-default-bom-or-formula-version"></a>기본 BOM 또는 공식 버전 활성화

특정 BOM 또는 공식을 기준 계획에서 사용하거나 생산 주문 생성에 사용할 기본 BOM 버전 또는 공식 버전으로 설정하려면 버전을 활성화해야 합니다. 버전이 활성화되면 지정된 제약 조건(예: 기간, 사이트 또는 수량)에 대한 버전의 고유성이 확인됩니다. 활성화하려는 버전이 이미 활성화된 버전과 충돌하는 경우 오류 메시지가 나타납니다. 모호한 활성화를 방지하려면 충돌하는 버전을 비활성화하거나 버전의 제약 조건(일반적으로 마침표)을 수정해야 합니다.

### <a name="product-change-with-case-management"></a>사례 관리를 사용하는 제품 변경

신규 또는 변경된 BOM 및 BOM 버전의 승인 및 활성화를 위한 제품 변경 사례를 통해 BOM 버전 제약의 개요를 쉽게 볼 수 있습니다. 또한 한 활성화 날짜에 대한 특정 변경과 관련된 모든 BOM 및 공식을 승인하고 활성화할 수 있습니다.

### <a name="alternative-bom-versions"></a>대체 BOM 버전

경우에 따라 활성 BOM 버전이나 공식 버전을 예측, 판매 또는 상위 제품에 사용해서는 안 됩니다. 이 경우 대체 BOM 또는 공식에 대해 승인된 BOM 버전 또는 공식 버전이 있는 경우 요구사항(예측 라인, 판매 라인 또는 BOM 라인)의 일부로 승인된 특정 BOM을 선택할 수 있습니다.  

계획 주문, 생산 주문 또는 간판이 생성되면 계획자 또는 작업 현장 감독자는 요청된 계획 생산 날짜에 유효한 승인된 BOM 버전을 사용하여 특정 제품을 계획하거나 생산할 수 있습니다. 사용되는 BOM 버전은 기본 BOM 버전으로 활성화할 필요가 없습니다.

## <a name="bom-and-formula-lines"></a>BOM 및 공식 라인
각 자재, 서비스 또는 재료에 대해 BOM 라인이 생성됩니다. 라인은 지정된 제품 변형의 계획 소비를 정의하고 계획 소비와 관련된 다양한 속성도 정의합니다.  

BOM 라인은 다음과 같은 라인 유형을 가질 수 있습니다. **항목**, **팬텀**, **고정 공급**, **공급업체**.

### <a name="item"></a>항목

직접 소비되고 추가 폭발이나 고정 공급이 필요하지 않은 자재 또는 서비스에 대한 **항목** 라인 유형을 선택합니다.

### <a name="phantom"></a>팬텀

BOM 라인에 포함된 하위 레벨 BOM 항목을 전개하려는 경우 **팬텀** 라인 유형을 선택합니다. 마스터 스케줄링, 계획 원가 계산 또는 BOM 라인을 사용하는 생산 주문 추정 시 **팬텀** 유형에서 팬텀 BOM이 있는 제품 변형을 참조하는 상위 BOM 라인은 해당 제품 변형의 적용 가능한 활성 BOM 버전에 의해 결정된 대로 해당 BOM에서 BOM 라인으로 나열된 구성품 품목으로 대체됩니다. 제품 변형에 적용 가능한 활성 경로가 있는 경우 해당 경로의 작업이 상위 경로에 병합됩니다.  

팬텀은 일반적으로 엔지니어링 프로세스를 단순화하는 데 사용됩니다. 여러 수준에서 팬텀 BOM을 광범위하게 사용하면 특히 고도로 반복적인 제조 시나리오에서 성능에 영향을 미칩니다. 성능을 향상시키려면 팬텀의 깊은 계층 구조를 피해야 합니다. 대신 사전 분해된 프로덕션 BOM 및 경로를 사용하세요.

### <a name="pegged-supply"></a>고정 공급

하위 생산, BOM 라인 이벤트 간판 또는 BOM 라인이 참조하는 제품 변형에 대한 직접 구매 발주를 생성하려는 경우 **고정 공급** 라인 유형을 선택합니다. 생산 주문을 추정할 때 하위 생산, 이벤트 간판 또는 구매 주문이 생성됩니다. 필요한 품목 수량이 소비 생산 주문에 대해 자동으로 예약됩니다.

### <a name="vendor"></a>공급업체

생산 프로세스에서 외주업체를 사용하고 외주업체에 대해 자동으로 하위 생산 또는 구매 발주를 생성하려는 경우 **공급업체** 라인 유형을 선택합니다.  

**BOM의 외주 작업에 대한 참고 사항:** 하청업체가 수행하는 서비스 또는 작업은 인벤토리에서 추적되는 서비스 항목으로 생성되어야 합니다. 서비스 품목을 BOM 라인으로 상위 품목에 첨부해야 합니다. 경로에는 하청업체의 작업 리소스에 할당된 작업이 포함되어야 합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]