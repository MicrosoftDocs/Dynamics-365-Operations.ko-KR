---
title: 판매 계약 입력
description: 이 토픽에서는 고객 중 한 명이 시간 경과에 따라 특별 할인을 받는 대가로 합의된 금액으로 제품을 구매하기로 약정하는 판매 계약을 생성하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm, SalesAgreementCustomerReferencesPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Service industries
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee2c1494842c5fd2aa598546ba655c33d6fd3f16
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448099"
---
# <a name="enter-sales-agreements"></a>판매 계약 입력

[!include [banner](../../includes/banner.md)]

이 토픽에서는 고객 중 한 명이 시간 경과에 따라 특별 할인을 받는 대가로 합의된 금액으로 제품을 구매하기로 약정하는 판매 계약을 생성하는 방법에 대해 설명합니다. 데모 데이터 회사 USMF 또는 자체 데이터에서 이 절차를 실행할 수 있습니다.


## <a name="set-up-sales-agreement-header"></a>판매 계약 헤더 설정
1. 탐색 창에서 **모듈 > 영업 및 마케팅 > 판매 계약 > 판매 계약** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **고객 계정** 필드의 드롭다운 메뉴에서 원하는 레코드를 선택합니다.
4. **고객 계정 분류** 필드의 드롭다운 메뉴에서 원하는 레코드를 선택합니다.
5. **일반** 섹션을 확장합니다.
6. **기본 약정** 필드에서 **제품 가치 약정** 을 선택합니다 약정 유형은 계약 계약이 이행되는 방식을 정의하기 위해 계약에 지정해야 하는 필수 기준입니다. 미리 정의된 네 가지 유형을 사용하여 수량 또는 값으로 표현되는 고객의 약정 목표를 설정할 수 있습니다. 수량 약정 유형은 특정 제품에만 적용할 수 있지만 가치 기반 유형은 특정 제품과 비특정 제품의 판매에 모두 적용됩니다.  
7. **만료 날짜** 필드에서 계약을 만료하려는 미래 날짜로 날짜를 설정합니다.
8. **확인** 을 선택합니다.

## <a name="set-up-product-value-commitment-lines"></a>제품 가치 약정 라인 설정
1. **라인 추가** 를 선택합니다.
2. **품목 번호** 필드의 드롭다운 메뉴에서 원하는 레코드를 선택합니다. 계약에 대해 선택한 약정 유형은 계약 라인에 입력할 수 있는 정보의 종류에 영향을 줍니다. 예를 들어, 가치 기반 계약의 경우 고객이 귀하로부터 상품을 구매하기로 약정한 총 순 금액(합의된 통화로)을 지정해야 합니다. 이 예에서는 고객이 제품의 특정 가치를 구매하는 계약을 생성하기 때문에 라인의 **수량** 및 **단위** 필드를 사용할 수 없습니다.   
3. **순 금액** 필드에 고객이 구매하기로 약정한 금액을 입력합니다.
4. **할인 퍼센트** 필드에 이 계약에 연결된 고객의 판매 주문 라인에 적용할 퍼센트 값을 입력합니다.
5. **라인 세부 정보** 섹션을 확장합니다.
6. **최대 적용됨** 필드에서 **예** 를 선택합니다.
    - **최대 적용됨** 을 선택하면 약정의 특별 가격, 할인 및/또는 지불 조건을 사용하는 모든 판매 주문 라인의 총액이 약정에 지정된 금액을 초과할 수 없습니다.  
    - 최소 및 최대 릴리스 금액은 선택한 계약을 사용하는 각 판매 주문에서 판매되어야 하는 값 범위를 지정합니다.   
7. **판매 계약 헤더** 섹션을 확장합니다. 계약 상태가 **유효** 로 설정되어 있지 않으면 판매 주문을 계약과 연결할 수 없으므로 해당 계약의 이행에 기여할 수 없습니다. 이 단계에서 상태를 수동으로 변경할 수 있습니다. 그러나 일반적으로 고객에 대한 계약을 확인하면 상태가 변경됩니다.  
8. 작업 창에서 **판매 계약** 을 선택합니다.
9. **확인** 을 선택합니다. **계약을 유효한 것으로 표시** 옵션이 **예** 로 설정되어 있는지 확인합니다.  
10. **보고서 인쇄** 필드에서 **예** 를 선택합니다.
11. **확인** 을 선택합니다.
12. 페이지를 닫습니다. 이제 계약이 유효합니다. 고객의 주문을 계약에 연결하여 커밋된 목표에 대해 상쇄할 수 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]