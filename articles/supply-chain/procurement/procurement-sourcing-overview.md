---
title: 조달 및 소싱 개요
description: 이 문서에서는 조달 및 소싱 모듈에서 사용할 수 있는 기능에 대한 개요를 제공합니다.
author: Henrikan
ms.date: 05/06/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogListPage, CatVendorCatalogListPage, PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "58021"
- intro-internal
ms.assetid: eea24e23-a803-4de0-a218-6485757cde1b
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7be7696716e887a7fa4ea4af234db20c6e161b5
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449719"
---
# <a name="procurement-and-sourcing-overview"></a>조달 및 소싱 개요

[!include [banner](../includes/banner.md)]

이 문서에서는 조달 및 소싱 모듈에서 사용할 수 있는 기능에 대한 개요를 제공합니다.

조달 및 소싱은 제품 및 서비스의 필요성을 식별하는 것부터 제품 조달, 영수증, 송장 및 공급업체와의 지불 처리에 이르기까지 모든 단계를 다룹니다. 구매 정책 및 워크플로를 정의하여 특정 비즈니스 요구에 맞게 조달 프로세스를 구성할 수 있습니다.

## <a name="identifying-a-need-for-product-and-services"></a>제품 및 서비스의 필요성 식별

제품 또는 서비스에 대한 필요성은 직원이 제품을 요구하는 경우와 같이 *요청* 에서 발생할 수 있습니다. *제품 카탈로그* 는 선택할 수 있는 제품의 선택을 안내하도록 설정하거나 카탈로그에 아직 제공되지 않은 제품에 대한 요청을 수행하여 구매 부서에서 제품을 공급할 수 있는 방법을 고려할 수 있습니다.  

*지출 한도* 는 요청 지출을 제한하는 데 사용할 수 있으며, *구매 워크플로* 는 주문이 발생하기 전에 승인을 요구하는 옵션을 추가합니다. 필요한 경우 예산 기금 할당을 지정할 수도 있습니다.  

조달 부서는 필요한 제품 및 서비스에 대한 공급업체를 식별하며 여기에는 여러 잠재적 공급업체에 발송하는 *견적 요청* 이 포함될 수 있습니다. 요청되는 제품의 사양을 공유할 수 있으며 잠재적인 공급업체는 이러한 사양을 보고 일치하는 제품을 제공할 수 있는지 확인할 수 있습니다. 공급업체는 입찰을 반환한 다음 조달할 공급업체를 선택하기 전에 조달 부서에서 검토합니다.  

구매 주문에는 견적 프로세스에 대한 보다 포괄적인 요청에 대한 대안으로 공급업체에 *구매 문의* 를 보낼 수 있는 옵션이 포함됩니다. 구매 조회는 주문에 대한 가격, 할인 및 배송 날짜와 같은 조건을 설정하는 데 사용할 수 있습니다. 공급업체가 **공급업체** 포털을 사용하도록 설정된 경우 구매 조회 기능이 비활성화됩니다. 대신 주문이 **공급업체** 포털에서 공유되며 *확인 요청* 이 전송되면 공급업체에서 직접 주문을 확인할 수 있습니다.  

*공급업체 카탈로그* 는 공급업체가 제공할 수 있는 제품 구색에 대한 정보를 수집하는 데 사용할 수 있습니다. 공급업체는 자체 카탈로그를 게시할 수 있으므로 카탈로그를 최신 상태로 유지하기가 더 쉽습니다. 제품에 *승인된 공급업체 목록* 을 첨부할 수 있으며 이는 새 구매 주문이 열릴 때 공급업체 선택을 안내하고 의도하지 않은 공급업체의 사용을 방지하는 데 도움이 됩니다.

## <a name="procurement"></a>조달

*구매 주문* 은 다음과 같은 다양한 방법으로 생성할 수 있습니다.

- 구매가 필요한 수요를 식별한 기준 계획의 결과입니다. 이 프로세스는 계획된 구매 주문을 생성하고 이러한 프로세스가 릴리스되면 구매 주문이 생성됩니다.
- 조달로 이어지는 구매 요청 처리를 통해.
- 구매 주문이 계약에서 릴리즈된 주문으로 생성되는 구매 계약 처리를 통해. 이는 구매 계약을 사용하여 총괄 주문을 나타낼 때 일반적으로 사용됩니다.
- 생성된 구매 주문이 다른 문서를 기반으로 하지 않는 경우 수동으로.

*구매 승인 워크플로* 로 구성된 구매 주문은 승인된 것으로 기록되기 전에 승인이 필요하며 주문이 추가로 처리되기 전에 승인이 필요합니다.

구매 주문은 공급업체와 계약이 체결되었음을 나타내기 위해 *확인* 됩니다. 그런 다음 구매 주문은 궁극적으로 청구되거나 취소될 때까지 다양한 상태를 통해 점진적으로 진행됩니다.  

구매 주문을 만들 때 많은 필드가 **공급업체** 페이지에 저장된 공급업체에 대한 정보의 기본값으로 미리 채워져 있습니다. 즉, 기본값을 재정의하도록 선택할 수 있지만 구매 주문서에 입력해야 하는 필드 수가 제한되어 있습니다.

### <a name="prices-and-discounts"></a>가격 및 할인

가격 및 할인에는 제공하는 가격, 할인 및 리베이트 조건에 대한 정보가 포함됩니다. 가격 및 할인은 *무역 계약* 으로 나타낼 수 있습니다. 무역 계약은 가격 또는 할인이 포함된 공급업체 가격 목록을 나타내며 계약이 유효한 특정 날짜 집합이 있습니다. 가격 및 할인은 협상 조건의 전제 조건으로 특정 수량 또는 금전적 금액을 구매하기로 약정하는 것과 같은 조건으로 *구매 계약* 을 통해 협상하고 나타낼 수 있습니다. *리베이트 계약* 은 특정 제품 또는 제품 그룹의 조달이 구매 금액 또는 수량에 따라 공급업체로부터 리베이트를 유발할 수 있는 공급업체와 함께 생성될 수 있습니다.

### <a name="delivery-options"></a>배달 옵션

구매 주문과 관련된 배달 프로세스에는 다양한 옵션이 있습니다. 주문한 제품은 *배달* 일정으로 분할될 수 있으며, 여기서 주문 수량의 일부는 다른 날짜에 배달되도록 계획할 수 있습니다. 배달에는 판매 주문에서 시작된 *직접 배달* 도 포함될 수 있습니다. 이 배달은 구매 주문에 제품 영수증이 기록됨과 동시에 판매 주문에 대한 포장 전표 생성을 자동화합니다. 구매 주문은 또한 일치하는 회사 간 판매 주문에서 제품을 주문하는 *회사 간 주문* 체인(회사 간 구매 주문이라고도 함)의 일부가 될 수 있습니다. 이 상황에서 일부 단계는 두 개의 관련된 회사 간 주문에서 자동화됩니다.

### <a name="supplementary-items"></a>보충 항목

제품은 *추가 항목* 을 포함하도록 설정할 수 있습니다. 주문 중인 상품과 관련된 상품을 제안하는 기능입니다. 추가 제품이 필요할 수도 있고 선택 사항일 수도 있습니다. 경우에 따라 다른 상품 구매 시 함께 제공되는 무료 상품으로 보조 상품이 추가될 수 있습니다.

### <a name="purchase-order-charges"></a>구매 주문 요금

구매 주문에 요금을 할당할 수 있습니다. 이는 자동 청구 설정을 통해 자동으로 발생하거나 청구를 수동으로 추가하여 발생할 수 있습니다. 헤더 레벨 또는 주문 라인 레벨에서 주문에 요금을 지정할 수 있습니다. 요금 회계는 다양한 방법으로 설정할 수 있습니다. 예를 들어 비용을 제품 비용으로 계상하도록 설정할 수 있습니다. 이렇게 하면 주문을 확인하기 전에 주문 라인 수준에서 비용을 할당해야 합니다. 주문 헤더에서 라인으로 비용을 할당하는 데 도움이 되는 옵션이 있습니다.

## <a name="product-receipt-and-invoicing"></a>제품 수령 및 송장 발행

실제 제품이 포함된 구매 주문은 일반적으로 창고 내에서 *도착 등록* 이 이루어져야 하며, 그 후에 주문에 대한 *제품 영수증* 이 등록됩니다. 요청을 충족하는 제품이 포함된 구매 주문은 제품을 요청한 직원도 *영수증 확인* 을 제공해야 하도록 구성할 수 있습니다.  

일부 구매 주문에는 창고에서 수령할 필요가 없는 서비스 또는 기타 비물리적 제품인 제품이 포함됩니다. 제품을 서비스로 만들거나 *조달 카테고리* 를 이러한 주문에 대한 구매 주문서에서 직접 사용할 수 있습니다. 이러한 주문을 사용하면 제품 수령 회계를 건너뛰고 주문이 직접 청구되거나 사전 도착 등록 없이 구매 주문에서 제품 수령 등록이 수행되는 경우가 있습니다.  

상품 수령 시 특정 용도로 자동 소모될 수 있습니다. 여기에는 직접 배송을 통한 암시적 소비, 프로젝트에 대한 소비 또는 제품을 고정 자산으로 회계하는 것이 포함됩니다.  

공급업체로부터 *공급업체 송장* 이 도착하면 먼저 구매 주문과 별개로 *송장 등록부* 에 기록된 다음 나중에 구매 주문에 대한 기록으로 승인될 수 있습니다. 구매 주문과 함께 공급업체 송장을 기록하는 것은 송장에 대한 제품 영수증의 일치를 포함합니다.  

*회계 분배* 는 원장 내에서 회계를 수행하는 방법을 설명하기 위해 구매 주문서에 지정할 수 있으며, 이것이 구성에 포함될 때 예산 자금 할당을 얻는 방법을 정의할 수도 있습니다.  

송장 처리된 구매 주문서는 *공급업체 지불* 을 처리할 수 있는 미지급금 내의 공급업체 계정에 부채를 기록합니다.

## <a name="vendor-performance"></a>공급업체 실적

구매 실적 및 검토는 지출 분석 및 공급업체 실적 분석이 포함된 *조달 및 미지급금 보고서* 를 통해 지원됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]