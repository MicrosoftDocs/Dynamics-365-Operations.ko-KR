---
title: Field Service의 계약 송장을 Supply Chain Management의 무료 텍스트 송장과 동기화
description: 이 토픽에서는 Dynamics 365 Field Service의 계약 송장을 Dynamics 365 Supply Chain Management의 자유 텍스트 송장과 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.
author: Henrikan
ms.date: 04/10/2018
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
ms.openlocfilehash: 70f1c072c3a2a1b201aac1f1d2beea9979a3b792
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449803"
---
# <a name="synchronize-agreement-invoices-in-field-service-to-free-text-invoices-in-supply-chain-management"></a>Field Service의 계약 송장을 Supply Chain Management의 무료 텍스트 송장과 동기화

[!include[banner](../includes/banner.md)]



이 토픽에서는 Dynamics 365 Field Service의 계약 송장을 Dynamics 365 Supply Chain Management의 자유 텍스트 송장과 동기화하는 데 사용되는 템플릿 및 기본 작업에 대해 설명합니다.

## <a name="templates-and-tasks"></a>템플릿 및 작업

다음 템플릿 및 기본 작업은 Field Service의 계약 송장을 Supply Chain Management의 자유 텍스트 송장으로 동기화하는 데 사용됩니다.

**데이터 통합의 템플릿 이름**

- 계약 송장(Field Service에서 Supply Chain Management로)

**데이터 통합 프로젝트의 작업 이름**

- 송장 헤더
- 송장 라인

계약 송장의 동기화를 수행하려면 다음 동기화가 필요합니다.

- 제품(Sales에서 Supply Chain Management로) - 직접

## <a name="entity-set"></a>엔터티 세트

| Field Service  | Supply Chain Management                 |
|----------------|----------------------------------------|
| 송장       | Dataverse 고객 자유 텍스트 송장 헤더 |
| invoicedetails | Dataverse 고객 자유 텍스트 송장 라인   |

## <a name="entity-flow"></a>엔터티 흐름

Field Service의 계약에서 생성된 송장은 Microsoft Dataverse 데이터 통합 프로젝트를 통해 Supply Chain Management와 동기화할 수 있습니다. 자유 텍스트 송장의 회계 상태가 **처리 중** 인 경우 이러한 송장에 대한 업데이트는 Supply Chain Management의 자유 텍스트 송장과 동기화됩니다. 무료 텍스트 송장이 Supply Chain Management에 전기되고 회계 상태가 **완료됨** 으로 업데이트되면 Field Service에서 업데이트를 더 이상 동기화할 수 없습니다.

## <a name="field-service-crm-solution"></a>Field Service CRM 솔루션

**계약 출처가 있는 라인 있음** 열이 **송장** 테이블에 추가되었습니다. 이 열은 계약에서 생성된 송장만 동기화되도록 보장하는 데 도움이 됩니다. 송장에 계약에서 비롯된 송장 라인이 하나 이상 포함된 경우 값은 **true** 입니다.

**계약 출처가 있는 라인 있음** 열이 **송장 라인** 테이블에 추가되었습니다. 이 열은 계약에서 생성된 송장 라인만 동기화되도록 보장하는 데 도움이 됩니다. 송장 라인이 계약에서 시작된 경우 값은 **true** 입니다.

**송장 날짜** 는 Supply Chain Management의 필수 필드입니다. 따라서 동기화가 발생하기 전에 열에 Field Service의 값이 있어야 합니다. 이 요구 사항을 충족하기 위해 다음 논리가 추가됩니다.

- **송장 날짜** 열이 **송장** 테이블에서 비어 있는 경우(즉, 값이 없는 경우) 계약에서 시작된 송장 라인이 추가될 때 현재 날짜로 설정됩니다.
- 사용자는 **청구서 날짜** 열을 변경할 수 있습니다. 그러나 사용자가 계약에서 비롯된 청구서를 저장하려고 할 때 청구서의 **청구서 날짜** 열이 비어 있으면 비즈니스 프로세스 오류가 발생합니다.

## <a name="prerequisites-and-mapping-setup"></a>전제 조건 및 매핑 설정

### <a name="in-supply-chain-management"></a>Supply Chain Management에서

Field Service의 계약 송장에서 생성된 Supply Chain Management의 자유 텍스트 송장을 구별하려면 통합을 위해 송장 출처를 설정해야 합니다. 송장에 **계약 송장** 통합 유형의 송장 출처가 있는 경우 **외부 송장 번호** 필드가 **판매 송장** 헤더에 표시됩니다.

송장 헤더에 표시되는 것 외에도 **외부 송장 번호** 정보는 Field Service 계약 송장에서 생성된 송장이 Supply Chain Management에서 Field Service로 송장 동기화 중에 필터링되도록 보장하는 데 사용할 수 있습니다.

1. **수취 계정** \> **설정** \> **청구서 출처 코드** 로 이동합니다.
2. **새로 만들기** 를 선택하여 청구서 출처를 만듭니다.
3. **판매 출처** 열에 판매 출처의 이름(예: **SalesOrder**)을 입력합니다.
4. **설명** 필드에 **Field Service 계약 송장** 과 같은 설명을 입력합니다.
5. **출처 유형 할당** 확인란을 선택합니다.
6. **송장 출처 유형** 필드를 **계약 송장 통합** 으로 설정합니다.
7. **저장** 을 선택합니다.

### <a name="in-the-data-integration-project"></a>데이터 통합 프로젝트에서

작업: **청구서 라인**  

Supply Chain Management 필드 **기본 계정 표시 값** 의 기본값이 원하는 값과 일치하도록 업데이트되었는지 확인합니다.

기본 템플릿 값은 **401100** 입니다.

## <a name="template-mapping-in-data-integration"></a>데이터 통합의 템플릿 매핑

다음 그림은 데이터 통합에서 템플릿 매핑을 보여줍니다.

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-headers"></a>계약 청구서(Field Service에서 Supply Chain Management로) 청구서 헤더

[![청구서 헤더에 대한 데이터 통합의 템플릿 매핑.](./media/FSFreeTextInvoice1.png)](./media/FSFreeTextInvoice1.png)

### <a name="agreement-invoices-field-service-to-supply-chain-management-invoice-lines"></a>계약 청구서(Field Service에서 Supply Chain Management로) 청구서 라인

[![청구서 라인에 대한 데이터 통합의 템플릿 매핑.](./media/FSFreeTextInvoice2.png)](./media/FSFreeTextInvoice2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]