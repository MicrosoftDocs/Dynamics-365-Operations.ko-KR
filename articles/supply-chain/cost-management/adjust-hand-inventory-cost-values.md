---
title: 현재고 비용 값 조정
description: 현재고 조정 페이지를 사용하여 재고 마감 프로세스가 실행된 후 현재고 수량의 원가 값을 조정합니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAdjInventOnHand
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53231
ms.assetid: bc1fde9f-5ad9-4339-8ae8-e2839b792eb2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fe79369fe4a85f34f7648699e90b726356ce6122594e60f21b27180982b7b149
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447223"
---
# <a name="adjust-on-hand-inventory-cost-values"></a>현재고 비용 값 조정

[!include [banner](../includes/banner.md)]

현재고 조정 페이지를 사용하여 재고 마감 프로세스가 실행된 후 현재고 수량의 원가 값을 조정합니다.

**현재고 조정** 페이지를 사용하여 재고 마감 프로세스가 실행된 후 현재고 수량의 원가 값을 조정할 수 있습니다. **참고:** **현재고 조정** 페이지를 열려면 **마감 및 조정** 페이지에서 완료된 재고 마감 프로세스의 기록을 선택한 다음 **조정** &gt; **보유** 를 클릭합니다. **예:** 2월에 다음 거래가 있습니다.

-   2월 1일: USD 10.00 비용으로 수량 2에 대한 재고 재정 영수증
-   2월 5일: USD 13.00 비용으로 수량 2에 대한 재고 재정 영수증
-   2월 19일: USD 11.00의 실행 평균 비용으로 수량 1에 대한 재고 재정 발행

본 상품은 FIFO(선입선출) 재고 모델로 설정되었으며, 2월 28일 현재 재고 마감이 이루어졌습니다. USD 11.00의 금융 이슈 거래는 2월 1일자 금융 영수증을 기준으로 정산되며 USD 1.00이 조정됩니다. 그러면 다음 재고 입고에 미결 재고 수량이 포함됩니다.

-   2월 1일: USD 10.00의 비용으로 수량 1개
-   2월 5일: USD 13.00의 비용으로 수량 1개

이 두 품목의 비용을 USD 15.00으로 설정하려면 현재고 조정 옵션을 사용하여 마지막 재고 마감 기간을 기준으로 미결 현재고 수량을 조정합니다. **참고:** 현재고 조정 트랜잭션의 전기일은 마지막 재고 마감일이 됩니다. 이 날짜는 수정할 수 없습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]