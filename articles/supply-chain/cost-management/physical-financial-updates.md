---
title: 물리적 및 재정 업데이트
description: 이 항목에서는 재고 수량을 늘리거나 줄이는 트랜잭션 유형에 대한 개요를 제공합니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3c7b354a7524a6e96da8e2a9eeca0d4f21b9fb0a6d515620ab3fe446425af17c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446827"
---
# <a name="physical-and-financial-updates"></a>물리적 및 재정 업데이트

[!include [banner](../includes/banner.md)]

이 항목에서는 재고 수량을 늘리거나 줄이는 트랜잭션 유형에 대한 개요를 제공합니다. 

재고 트랜잭션은 Dynamics 365 Supply Chain Management에서 물리적으로 업데이트되고 재정적으로 업데이트될 수 있습니다. 일부 유형의 물리적 및 재정적 트랜잭션은 재고 수량을 늘리는 반면 다른 유형은 수량을 줄입니다.

## <a name="physical-increases"></a>물리적 증가
실제 트랜잭션이 게시되면 트랜잭션 레코드의 상태는 **수신됨** 입니다. 다음 트랜잭션은 물리적 증가로 간주됩니다.

-   구매 주문 영수증
-   판매 주문 포장 전표 반환
-   생산 주문이 완료된 것으로 보고
-   생산 주문 불출 목록의 부산물

## <a name="financial-increases"></a>재정적 증가
재정 영수증 트랜잭션이 전기될 때 수량을 증가시키는 트랜잭션 레코드의 상태는 **구매함** 입니다. 다음 트랜잭션은 재정적 증가로 간주됩니다.

-   공급업체 송장
-   판매 주문 반품 송장
-   생산 주문 원가 계산
-   이동, 손익, 계산, BOM 및 이전과 같은 양수 수량 재고 분개장

## <a name="transactions-that-increase-quantity"></a>수량을 증가시키는 트랜잭션
수량을 증가시키는 트랜잭션은 실행 평균 비용 가격으로 전기됩니다. 계산된 실행 평균 비용 가격은 재정적으로 추적되는 각 재고 차원에 대한 이러한 각 트랜잭션의 비용을 기반으로 합니다. 평균 비용 가격 실행에 대한 자세한 내용은 [실행 평균 비용 가격](running-average-cost-price.md)을 참조하세요.

## <a name="transactions-that-decrease-quantity"></a>수량을 감소시키는 트랜잭션
계산된 누적 평균 원가는 해당 재고와 연결된 재고 모델에 관계없이 수량을 줄이는 트랜잭션이 전기될 때 사용됩니다. 수량을 줄이는 트랜잭션은 전기되기 전에 다른 트랜잭션에 표시되지 않아야 합니다. 실제 현재고가 음수가 되면 **품목** 페이지에서 해당 품목에 대해 정의된 재고 원가가 사용됩니다. 

> [!NOTE]
> 다중 사이트 기능이 활성화된 경우 이 비용은 대신 **기본 주문 설정** 페이지의 해당 사이트에 대해 정의된 인벤토리 비용이 됩니다.

## <a name="physical-issues-vs-financial-issues"></a>물리적 문제 및 재정적 문제
실제 문제 트랜잭션이 게시되면 트랜잭션 레코드의 상태는 **공제됨** 입니다. 다음 트랜잭션은 물리적 문제로 간주됩니다.

-   생산 주문 불출 목록 분개장
-   판매 주문 포장 전표
-   구매 주문 포장 전표 반환

재정 트랜잭션이 게시되면 트랜잭션 레코드의 상태는 **판매됨** 입니다. 다음 트랜잭션은 재정적 문제로 간주됩니다.

-   생산 주문 종료
-   판매 주문 송장
-   공급업체 송장 반품
-   이동, 손익, 계산, BOM 및 이전과 같은 음수 수량 재고 분개장

수량을 감소시키는 트랜잭션은 실행 평균 비용 가격으로 전기됩니다. 따라서 각 품목에 부여된 재고 모델에 따라 출고 트랜잭션을 입고 트랜잭션으로 정산하기 위해서는 재고 마감 절차가 필요합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]