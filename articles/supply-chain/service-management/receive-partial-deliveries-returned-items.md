---
title: 반품 품목의 부분 배송 수령
description: 부분 배송은 반품 주문 배송이 아닌 반품 주문 라인을 기준으로 정의됩니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: db02356afe06244f062f4e7c67a5db0a36900469
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447892"
---
# <a name="receive-partial-deliveries-of-returned-items"></a>반품 품목의 부분 배송 수령    

[!include [banner](../includes/banner.md)]


부분 배송은 반품 주문 배송이 아닌 반품 주문 라인을 기준으로 정의됩니다.

즉, 한 반품 주문 라인에 표시된 전체 수량을 받았지만 반품 주문의 다른 라인에서는 아무것도 받지 못한 경우 납품은 부분 납품이 아닙니다. 그러나 반품 주문 라인에서 특정 품목의 10개 단위를 반품해야 하지만 4개만 받은 경우 부분 납품입니다.

반품 배송에 반품 주문 라인의 전체 수량보다 적은 양이 포함되어 있는 경우 배송을 따로 보관하고 나머지 반품된 수량이 도착할 때까지 기다리거나 일부 수량을 등록하고 전기할 수 있습니다.

## <a name="register-and-post-a-partial-quantity"></a>일부 수량 등록 및 게시

1.  **도착 개요 - 창고: %1, 선착장: %2, 분개 이름: %3** 양식에서 도착 반품 주문을 선택한 후, 양식에서 **도착 시작** 을 클릭하여 도착 분개를 만든 다음 **분개를 클릭하여 영수증에서** \> **도착 표시** 를 클릭하여 **위치 분개** 양식을 엽니다.

2.  작업할 분개 라인을 선택한 다음 **라인** 을 클릭하여 **분개 라인, 위치** 양식을 엽니다.

3.  일부 수량만 도착한 품목 번호의 라인을 선택한 다음 **기능** \> **분할** 을 클릭하여 **분할** 양식을 엽니다.

4.  **분할 수량** 필드에 입고된 총 품목 수에 대한 수량을 입력한 후 **확인** 을 클릭하세요.

5.  **분개 라인, 위치** 양식에서 도착한 품목 수량에 대한 라인을 선택한 다음 **전기** 를 클릭합니다. 품목이 도착한 후 추가 수량에 대한 라인을 전기할 수 있습니다.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]