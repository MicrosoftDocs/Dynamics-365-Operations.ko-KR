---
title: 제품 정보 개요
description: 이 토픽에서는 제품 정보 관리에 대한 정보를 제공합니다. 제품 정보 관리는 모든 법인의 공유 제품 정의, 분류 및 식별자와 함께 작동하며 제품의 특정 구성도 비즈니스 프로세스에 맞게 조정합니다.
author: t-benebo
ms.date: 06/01/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductListPage, EcoResProductVariantMaintainWorkspace, EcoResProductVariantPerCompanyImagePart, EcoResProductRelationType,EcoResProductAvailabilityPart,  EcoResProductReleasedSelect, EcoResProductLookup, EcoResProductVariantsPendingReleaseFormPart, EcoResProductSearchLookup, EcoResProductNumberRename, EcoResDimensionBasedConfigWorkspace, EcoResProductVariantImagePart, EcoResProductImagePart, EcoResProductVariantsPerCompanyPart, InventItemIdLookupByDefaultOrderSetting, EcoResProductReleaseSessions, EcoResProductVariantMaintainWorkspaceConfiguration, EcoResProductProcessManufacturingWorkspaceConfiguration, EcoResProductMasterVariantsPart, EcoResProductDiscreteManufacturingWorkspaceConfiguration, EcoResProductVariantAvailabilityPart, EcoResProductInformationFactBox, EcoResProductLookupTest, EcoResProductImageTest, EcoResProductReleasedRecentlyCreatedFormPart, EcoResPhysicalProductDimensions, PdsMRCRegulatedListItem, EcoResProductAvailabilityPart, PdsMRCRestrictionList, InventItemIdLookupAllocationId, EcoResProductAvailability, EcoResProductEntityAttributeTableFieldAssociation, EcoResProductImagePart, EcoResProductRelation, EcoResProductReleaseAddProduct, EcoResProductPerCompanyListPage, EcoResProductParameters, PdsMRCRestrictedItemByCountryState, EngChgCasePreview, InventTablePreview, PdsMRCItemDetails, EngChgCaseAssociate, PdsMRCCustomerHistory, PdsMRCVendorHistory, PdsMRCRestrictedCountryStateByItem, InventItemIdGroupLookup, InventLocationLookup, PdsMRCValidityIntervalbyCountry, PdsMRCValidityIntervalbyCountry, PdsMRCEventTracker, PdsMRCReportingCountry, PdsMRCDocument, PdsMRCReportingList, PdsMRCItemCAS, GraphicsTestForm, EngChgPicklist
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c8aabeed66f864d1d1060a6452a3b554611c295
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449860"
---
# <a name="product-information-overview"></a>제품 정보 개요

[!include [banner](../includes/banner.md)]



이 토픽에서는 제품 정보 관리에 대한 정보를 제공합니다. 제품 정보 관리는 모든 법인의 공유 제품 정의, 분류 및 식별자와 함께 작동하며 제품의 특정 구성도 비즈니스 프로세스에 맞게 조정합니다. 

제품 정보는 모든 산업 분야의 공급망 및 상거래 애플리케이션의 근간입니다. 제품에 대한 정보를 중앙에서 관리하는 데 중점을 둔 프로세스 및 기술(예: 공급망 전반)을 나타냅니다. 공유 제품 정의, 문서, 특성 및 식별자를 사용하는 것이 중요합니다. 비즈니스 솔루션의 다양한 모듈에서 특정 제품, 제품군 또는 제품 범주와 관련된 비즈니스 프로세스를 관리하려면 제품별 정보 및 구성이 필요합니다.

## <a name="product-definition"></a>제품 정의

제품은 주로 제품 번호, 이름 및 설명으로 정의됩니다. 그러나 제품 또는 서비스를 설명하기 위해 다른 데이터도 필요합니다.

- 제품 타입: 항목 또는 서비스
- 제품 하위 유형: 고유한 제품 또는 제품 마스터
- 제품 변형 모델의 정의:

     - 제품 크기 및 크기 그룹
     - 제품 명명법
     - 제품 구성 모델

- 하나 이상의 범주와 제품 연결
- 제품 및 범주 특성의 정의
- 제품 이미지
- 첨부 파일
- 측정 단위 및 관련 변환
- 모든 이름 및 설명에 대한 번역

## <a name="distribution-export-and-import-of-product-data"></a>제품 데이터의 배포, 내보내기 및 가져오기

제품 정의는 Supply Chain Management에서 생성할 수 있습니다. 또한 PLM(제품 수명 주기 관리), PDM(제품 데이터 관리) 또는 PIM(제품 정보 관리) 시스템에서 가져올 수 있습니다. 둘 이상의 Supply Chain Management 인스턴스가 사용되는 경우 일반적으로 하나의 인스턴스가 다른 모든 인스턴스에 대한 제품 데이터의 마스터로 사용됩니다. 이 접근 방식은 제품 정의 데이터를 한 인스턴스에서 다른 인스턴스로 내보내고 가져올 수 있는 대규모 데이터 엔터티 집합에서 지원됩니다.

많은 인스턴스에 제품 데이터 배포를 지원하기 위해 Supply Chain Management에서 Microsoft Dataverse을 사용할 수 있습니다. 제품 정의는 Supply Chain Management 인스턴스에서 Microsoft Dataverse로 내보낼 수 있습니다. 그런 다음 제품 정의를 사용하여 Dynamics 365 Sales와 같은 다른 비즈니스 응용 프로그램을 제품 데이터로 프로비저닝할 수 있습니다.

역동적이고 기민한 조직에서는 제품 정보 데이터가 매일 변경됩니다. 따라서 정확하고 실제적인 제품 데이터의 유지 관리는 그 자체로 중요한 비즈니스 프로세스입니다.

## <a name="product-masters-and-product-variants"></a>제품 마스터 및 제품 변형

제품이 고객 요구 사항에 빠르게 적응해야 하는 기민한 세계에서 제품 정의는 고유 제품 대신 제품 세트를 지정합니다. Supply Chain Management에서는 이러한 일반 제품을 *제품 마스터* 라고 합니다. 제품 마스터는 비즈니스 프로세스에서 고유한 제품이 설명되고 작동하는 방식을 지정하는 정의와 규칙을 보유합니다. 이러한 정의를 기반으로 고유한 제품을 생성할 수 있습니다. 이러한 고유 제품을 *제품 변형* 이라고 합니다.

제품 마스터는 제품 크기 그룹 및 구성 기술과 연결되어 비즈니스 규칙을 지정합니다. 제품 크기(색상, 크기, 스타일 및 구성)는 관련 제품의 특정 동작을 정의하고 추적하기 위해 애플리케이션 전체에서 사용할 수 있는 특정 특성 세트입니다. 이러한 크기는 사용자가 제품을 검색하고 식별하는 데도 도움이 됩니다.

## <a name="configuration-technologies"></a>구성 기술

세 가지 구성 기술 중에서 선택할 수 있습니다.

- 사전 정의된 변형은 사전 정의된 제품 크기로 정의됩니다. 변형 정의에는 색상, 스타일 및 크기와 같은 특정 유효한 차원 조합의 정의가 포함됩니다. 각 조합은 고유한 제품 변형을 생성합니다.
- 차원 기반 구성은 일반적으로 제조 시나리오에서 사용되며 BOM(자재 명세서) 정의에서 구성 차원을 사용할 수 있습니다. 특정 구성을 선택한 후 시스템은 계획 및 생산을 위해 해당 구성에 유효한 BOM 라인의 하위 집합을 사용합니다. 하나의 공유 BOM이 제품의 모든 구성에 사용되기 때문에 이 개념을 *전역 BOM* 이라고도 합니다.
- 제약 기반 구성은 제품 구성 모델을 사용하여 단일 모델에서 제품의 가능한 모든 변형을 설명하는 데 필요한 모든 가능한 특성 및 구성 요소를 설명합니다. 특성 조합의 제약 조건은 정규식 또는 테이블 기반 제약 조건을 통해 설명할 수 있습니다. 구성 모델 및 구성자는 제품 정보 관리에서 더욱 중요해지고 있으며 모든 산업 분야에서 사용됩니다.

Supply Chain Management을 계획할 때 비즈니스 프로세스에 대한 올바른 구성 기술을 선택하는 것이 매우 중요합니다. 제품은 구현 후에 한 모델에서 다른 모델로 변환할 수 없습니다.

## <a name="product-variant-model-definition-workspace"></a>제품 변형 모델 정의 작업 영역

**제품 변형 모델 정의** 작업 영역은 제품 마스터에 대한 개요를 제공합니다. 또한 특정 법인에 대한 마스터 및 관련 변형 릴리스의 상태를 보여줍니다.

## <a name="released-products"></a>출시된 제품

특정 법인에 출시되는 제품을 *출시 제품* 이라고 합니다. 제품은 한 번에 하나의 법인 또는 여러 법인에 대량으로 출시될 수 있습니다. 제품의 다양한 속성 및 특성을 법인별로 추가해야 할 수 있으므로 **출시된 제품 유지 관리** 작업 영역을 통해 각 법인 또는 법인의 하위 조직에서 최근에 출시된 제품을 모니터링하고 완료할 수 있습니다.

### <a name="released-product-maintenance-workspace"></a>제품 유지 관리 작업 영역 출시

**내 작업 영역 구성** 메뉴 항목에서 **출시된 제품 유지 관리** 작업 영역을 구성할 수 있습니다. 작업 영역을 필터링할 범주 계층 및 범주를 선택합니다. 작업 영역에서 관련 제품 데이터를 조정하기 위해 **최근 출시 제품** 및 **중지 출시 제품** 에 대한 타임펜스를 일 단위로 정의할 수도 있습니다.

작업 영역은 타일 요약 및 두 개의 목록으로 구성됩니다. **열린 사례** 목록에는 완료하고 닫지 않은 선택한 제품 범주 계층 구조의 제품이 있는 제품 변경 사례가 표시됩니다. **최근 출시** 목록은 작업 영역 구성에서 설정한 타임펜스 내에서 출시된 제품을 보여줍니다. 목록의 각 항목에 대해 유효성 검사가 실행되고 유효성 검사 상태가 표시됩니다. 이 상태는 법인에 필요한 구성이 완료되지 않았음을 나타낼 수 있습니다. 목록에서 **출시된 제품 세부정보**, **제품 특성 유지**, **제품 카테고리 유지**, **기본 주문 설정**, **텍스트 번역** 페이지에 직접 액세스하여 필요한 제품 구성을 완료할 수 있습니다.

### <a name="manually-creating-a-new-released-product"></a>새로 출시된 제품을 수동으로 생성

조직의 비즈니스 프로세스 및 이 기능을 사용해야 하는지 여부에 대한 규칙에 따라 출시된 제품을 한 번의 실행으로 수동으로 생성할 수 있습니다. 이 기능은 새 제품을 생성하고 현재 법인에 자동으로 릴리스합니다. 새 제품을 만들려면 **출시 제품 유지 관리** 작업 영역 또는 **출시 제품** 목록 페이지에서 **출시 제품** 을 클릭하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]