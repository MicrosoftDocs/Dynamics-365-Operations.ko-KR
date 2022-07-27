---
title: 품목 교체 주문 생성
description: 품목 교체 주문은 일반적으로 제품이 반품 및 검사된 후에 생성됩니다.
author: josaw1
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnReplaceItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 57bbb8eb638b990914dc00f9700ff0c1925c48852862b02e09f3f26415d3e347
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446944"
---
# <a name="create-an-item-replacement-order"></a>품목 교체 주문 생성 

[!include [banner](../includes/banner.md)]


품목 교체 주문은 일반적으로 제품이 반품 및 검사된 후에 생성됩니다. 그러나 반품되기 전에 품목을 교체해야 하는 경우 또는 원래 품목이 반품되지 않을 경우 반품 주문을 생성한 후 즉시 품목 교체 주문을 생성할 수 있습니다.

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a>반품된 항목을 받은 후 교체 주문 생성

1.  **영업 및 마케팅** \> **공통** \> **반품 주문** \> **모든 반품 주문** 을 클릭합니다.

2.  새 반품 주문을 생성하거나 목록에서 반품된 주문을 선택하여 **반품 주문 - RMA 번호: %1, %2** 양식을 엽니다.

3.  **반품 라인** 을 클릭한 다음 **교체 품목** 을 선택합니다.

4.  반품된 상품을 교체할 상품을 선택합니다. 항목 사양을 입력한 다음 **적용** 을 클릭합니다.

5.  **포장 전표** 를 클릭하여 반품 주문에 대한 포장 명세서를 생성합니다. 선택한 교체 품목에 대한 판매 주문이 생성됩니다.
    
    교체 품목에 대한 판매 주문이 생성된 후 판매 계약이 자동으로 검색되고 해당 판매 계약이 있는 경우 판매 주문에 적용됩니다.

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a>반품된 항목을 받기 전 교체 주문 생성

1.  **영업 및 마케팅** \> **공통** \> **반품 주문** \> **모든 반품 주문** 을 클릭합니다.

2.  새 반품 주문을 생성하거나 목록에서 반품 주문을 선택하여 **반품 주문 - RMA 번호: %1, %2** 양식을 엽니다.

3.  반품된 품목에 대한 판매 주문을 식별하려는 경우 **판매 주문 찾기** 를 클릭합니다. **판매 주문 찾기** 양식을 완료한 다음 **확인** 을 클릭하여 양식을 닫고 **반품 주문 - RMA 번호: %1, %2** 양식으로 돌아갑니다. 반품된 품목에 대한 판매 주문 라인이 반품 주문에 복사됩니다.

4.  **교체 주문** 을 클릭하여 **판매 주문 생성** 양식을 엽니다.

5.  **반품 주문 라인 복사** 확인란을 선택하여 **반품 주문 - RMA 번호:%1, %2** 양식에서 선택한 반품 주문의 세부 정보를 이 판매 주문으로 이전합니다.

6.  필요에 따라 세부 정보를 입력하거나 수정합니다.
    
    3단계에서 판매 주문을 식별하고 반품된 품목의 판매 주문 라인이 판매 계약에 연결된 경우 품목 교체 주문에 대한 해당 판매 계약의 식별자가 자동으로 **판매 계약 ID** 필드에 표시됩니다.

7.  **확인** 을 클릭하여 **판매 주문 생성** 양식을 닫고 **판매 주문** 을 열면 새 판매 주문에 대한 정보를 계속 입력할 수 있습니다. 적용 가능한 모든 반품 주문 라인이 신규 판매 주문에 복사됩니다. 
    
    판매 계약의 식별자가 **판매 계약 ID** 필드에 자동으로 표시되는 경우 판매 계약이 품목 교체 주문에 대한 판매 주문 헤더에 연결된 것입니다. 판매 계약에 아직 이행되지 않은 적용 가능한 약정이 있고 판매 계약이 만료되기 전에 판매 주문이 생성된 경우 판매 계약 라인과 판매 주문 라인 간에 링크가 설정됩니다. 따라서 품목 가격과 같은 판매 계약의 정보가 새 판매 주문 라인에 복사됩니다. 
  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]