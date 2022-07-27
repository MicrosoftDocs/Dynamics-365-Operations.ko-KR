---
title: 새 거래 계약 생성
description: 이 절차는 특정 고객과 합의한 새 제품 판매 가격을 등록하는 무역 계약을 생성하는 방법을 보여줍니다.
author: Henrikan
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TradeNonStockedConversion, TradeNonStockedConversionChangeWizard, TradeNonStockedConversionCheckWorksheet, TradeNonStockedConversionWizard, TradeNonStockedRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a16a39d95605900be0fa1e339b8cd0755ba85189
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448618"
---
# <a name="create-a-new-trade-agreement"></a>새 거래 계약 생성

[!include [banner](../../includes/banner.md)]

이 절차는 특정 고객과 합의한 새 제품 판매 가격을 등록하는 무역 계약을 생성하는 방법을 보여줍니다. 데모 데이터 회사 USMF 또는 자체 데이터에서 이 절차를 실행할 수 있습니다. 자신의 데이터를 사용하는 경우 이 가이드를 시작하기 전에 기본 관계가 "가격(판매)"으로 설정된 무역 계약 저널 이름이 있는지 확인해야 합니다.

## <a name="create-and-post-a-new-trade-agreement-journal"></a>새로운 무역 협정 저널 작성 및 게시

1. **탐색 창 > 모듈 > 영업 및 마케팅 > 가격 및 할인 > 무역 계약 저널** 로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **이름** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
4. 목록에서 원하는 레코드를 찾아 선택합니다.
5. **작업 창** 에서 **라인** 을 클릭합니다.
6. **계정 코드** 필드에서 '테이블'을 선택합니다.
    
    이 예에서는 특정 고객의 가격을 업데이트하고 있으므로 테이블을 선택해야 합니다. 제품의 정가를 업데이트하는 경우 새 가격이 모든 고객에게 유효하도록 '모두'를 선택합니다. 다른 고객 세그먼트 간에 가격을 차별화하는 경우 그룹을 선택합니다. 그룹을 선택하려면 고객 가격 그룹을 설정해야 합니다.  

7. **계정 선택** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
8. 목록에서 원하는 레코드를 찾아 선택합니다.
9. **항목 코드** 필드에서 '테이블'을 선택합니다.
    
    '가격(판매)' 유형의 거래 계약을 입력할 때, **항목 코드** 필드에서 '테이블'만 선택해야 합니다. 가격은 절대값이며 모든 제품 또는 제품 그룹에 대해 동일할 수 없기 때문입니다.
    
10. **항목 관계** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
11. 목록에서 계약에 포함할 제품을 선택합니다. 선택한 제품을 기록해 둡니다.  
12. **시작 수량** 필드에 최소 수량을 입력합니다.
    - 고객이 새 가격을 적용받기 전에 최소 수량을 주문해야 하는 경우 여기에서 해당 수량을 지정해야 합니다.  
    - **종료 수량** 필드에 값을 입력하여 계약 가격이 유효하지 않은 최대 수량을 지정합니다. 여러 수량 할인을 기준으로 가격 및 할인을 제공하는 경우 각 수량 브래킷을 각각 **시작 수량** 및 **종료 수량** 필드에서 최소 및 최대 수량 쌍으로 지정합니다.
13. **통화 금액 필드** 에 가격을 입력합니다.
14. **세부 정보** 섹션의 **시작 날짜** 필드에 이 계약이 유효한 날짜를 입력합니다.
15. **저장** 을 클릭합니다.
16. **유효성 검사** 를 클릭합니다.
17. **선택한 라인 확인** 을 클릭합니다.
18. **확인** 을 클릭합니다.
19. **전기** 를 클릭합니다.
20. **확인** 을 클릭합니다.

## <a name="view-trade-agreements-for-a-product"></a>제품에 대한 무역 계약 보기

1. **탐색 창 > 모듈 > 제품 정보 관리 > 제품 > 출시된 제품** 으로 이동합니다.
2. 목록에서 가격이 방금 업데이트된 제품을 찾아 선택합니다.
3. **작업 창** 에서 **판매** 를 클릭합니다.
4. **무역 협정 보기** 를 클릭합니다.
    
    방금 생성한 가격 거래 계약의 세부 정보를 검토합니다.

5. 페이지를 닫습니다.

## <a name="additional-resources"></a>추가 리소스

### <a name="whitepaper"></a>백서

자세한 내용은 다음 백서를 다운로드하세요(AX2012를 지원하기 위해 작성되었지만 Dynamics 365 Supply Chain Management에 여전히 적용)

- [무역 계약](https://download.microsoft.com/download/0/2/9/02972c8b-0159-4936-a3ef-1e64252b2d2f/TradeAgreementsInAX.pdf)

### <a name="community-blogs"></a>커뮤니티 블로그

- [Dynamics 365 for Finance and Operations의 판매 가격](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]