---
title: Microsoft Dynamics 365 Field Service 개요와 통합
description: 이 토픽에서는 Microsoft Dynamics 365 Field Service와의 통합에 대한 개요를 제공합니다.
author: Henrikan
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 9428308211d51e7de8c61fb9aadef6ce1fd9886f
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449851"
---
# <a name="integration-with-microsoft-dynamics-365-field-service-overview"></a>Microsoft Dynamics 365 Field Service 개요와 통합

[!include[banner](../includes/banner.md)]



Supply Chain Management를 사용하면 Dynamics 365 Supply Chain Management와 Dynamics 365 Field Service 간의 비즈니스 프로세스를 동기화할 수 있습니다. 통합 시나리오는 확장 가능한 데이터 통합자 템플릿과 Microsoft Dataverse를 사용하여 구성되어 비즈니스 프로세스를 동기화할 수 있습니다.
표준 템플릿을 사용하여 추가 표준 및 사용자 정의 열과 테이블을 매핑하여 통합을 조정하고 특정 비즈니스 요구 사항을 충족할 수 있는 사용자 정의 통합 프로젝트를 생성할 수 있습니다. 

현장 서비스 통합은 기존 잠재 고객 대 현금 기능을 기반으로 합니다.

![Supply Chain Management와 Field Service 간의 비즈니스 프로세스 동기화.](./media/field-service-integration.png)

Field Service와 Supply Chain Management 간의 통합의 첫 번째 단계는 Field Service의 작업 주문 및 계약이 Supply Chain Management에서 청구될 수 있도록 하는 데 중점을 둡니다. 지원되는 흐름은 작업 주문의 정보가 판매 주문으로 Supply Chain Management에 동기화되는 Field Service에서 시작됩니다. Supply Chain Management에서 판매 주문은 송장 문서를 생성하기 위해 송장 발행됩니다. 또한 Field Service 계약 송장의 정보는 Supply Chain Management와 동기화됩니다. Microsoft Dynamics 365 데이터 통합자는 사용자 정의 가능한 프로젝트를 사용하여 데이터를 동기화합니다. 표준 템플릿을 사용하여 추가 표준 및 사용자 정의 열과 테이블을 매핑하여 통합을 조정하고 특정 요구 사항을 충족할 수 있는 사용자 정의 통합 프로젝트를 생성할 수 있습니다.

Field Service와 Supply Chain Management 간의 통합의 첫 번째 단계에서는 다음 항목을 동기화할 수 있습니다.

- [Supply Chain Management의 제품을 Field Service의 제품과 동기화](field-service-product.md)
- [Field Service의 작업 주문을 Supply Chain Management의 판매 주문과 동기화](field-service-work-order.md)
- [Field Service의 계약 송장을 Supply Chain Management의 무료 텍스트 송장과 동기화](field-service-invoice.md)

Field Service와 Supply Chain Management 간에 작업 주문을 동기화하는 방법의 예를 보려면 짧은 YouTube 비디오, [Microsoft Dynamics 365 통합과 작업 주문을 동기화하는 방법](https://www.youtube.com/watch?v=46ylO7raZAo)을 시청하세요.

## <a name="integration-with-field-service-including-inventory-and-project-information"></a>재고 및 프로젝트 정보를 포함한 Field Service와의 통합

이 두 번째 단계의 추가 기능은 현장 기술자에게 Supply Chain Management의 재고 정보에 대한 통찰력을 제공하여 재고 수준을 업데이트하고 자재 이전을 수행할 수 있도록 하는 데 중점을 두었습니다. 또한 판매된 제품을 설치하거나 서비스하는 회사는 프로젝트와의 통합을 통해 전체 판매 및 서비스 프로세스에 대한 더 나은 제어 및 가시성을 얻을 수 있습니다.

### <a name="functionality-includes-integration-of"></a>기능에는 다음의 통합이 포함됩니다.
- 창고 정보
- 현재고 정보
- 재고 이전
- 재고 조정
- Dynamics 365 Field Service 작업 주문과 연결된 Supply Chain Management 프로젝트
- Supply Chain Management 프로젝트에 대한 링크가 있는 Dynamics 365 Field Service 작업 주문은 이 프로젝트 번호를 판매 주문에 적용하여 프로젝트에서 송장 발행을 허용합니다. 

![재고 및 프로젝트 정보를 포함하여 Supply Chain Management와 Field Service 간의 비즈니스 프로세스 동기화.](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-supply-chain-management-enables-synchronization-with-the-following-templates"></a>Field Service와 Supply Chain Management 간의 통합의 두 번째 단계에서는 다음 템플릿과 동기화할 수 있습니다.
- 창고(Supply Chain Management에서 Field Service로) - Supply Chain Management에서 Field Service로의 창고[고급 쿼리] 
- 제품 재고(Supply Chain Management에서ㅓ Field Service로) - Supply Chain Management에서 Field Service까지의 재고 수준 정보[고급 쿼리] 
- 재고 조정(Field Service에서 Supply Chain Management로) - Field Service에서 Supply Chain Management로 재고 조정[고급 쿼리] 
- 재고 이전(Field Service에서 Supply Chain Management로) - Field Service에서 Supply Chain Management로 재고 이전[고급 쿼리] 
- 프로젝트(Supply Chain Management에서 Field Service로) - Supply Chain Management에서 Field Service까지의 프로젝트 목록 
- 프로젝트 작업 주문(Field Service에서 Supply Chain Management로) - Field Service의 작업 주문에서 Supply Chain Management의 판매 주문으로, 프로젝트 지원 포함 [고급 쿼리] 
- 재고 단위가 있는 Field Service 제품(Supply Chain Management에서 Sales로) - Supply Chain Management '판매 가능한 제품'에서 Sales '제품(Field Service, 재고 단위 포함) 

## <a name="system-requirements"></a>시스템 요구 사항

### <a name="system-requirements-for-supply-chain-management"></a>Supply Chain Management를 위한 시스템 요구 사항
Field Service 통합은 다음 버전을 지원합니다.

- Dynamics 365 for Finance and Operations 버전 8.1.2(2018년 12월)는 2018년 12월에 릴리스되었으며 플랫폼 업데이트 22(7.0.5095)가 포함된 애플리케이션 빌드 번호가 8.1.195입니다. 

### <a name="system-requirements-for-field-service"></a>Field Service를 위한 시스템 요구 사항
Field Service 통합 솔루션을 사용하려면 다음 구성 요소를 설치해야 합니다.

- Field Service(버전 8.2.0.286) 또는 Dynamics 365 9.1.x의 이후 버전 - 2018년 11월 출시
- Dynamics 365용 P2C(Prospect to Cash) 솔루션, 버전 1.15.0.1 이상 버전. 솔루션은 [`AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3)에서 다운로드할 수 있습니다.
- Dynamics 365용 'Field Service 통합, 프로젝트 및 재고' 솔루션, 버전 2.0.0.0 이상 버전. 솔루션은 [`AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2)에서 다운로드할 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]