---
title: 입고 창고에서 매장으로 제품 크로스 도킹
description: 이 절차는 구매 주문의 수신 위치에서 하나 이상의 상점으로 제품을 배포하기 위해 크로스 도킹을 만들고 처리하는 단계를 안내합니다.
author: Mirzaab
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailBuyersPushPerPackage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e65535a1879eab229f185e0e97d81a304fd292d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448576"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a>입고 창고에서 매장으로 제품 크로스 도킹

[!include [banner](../../includes/banner.md)]

이 절차는 구매 주문의 수신 위치에서 하나 이상의 상점으로 제품을 배포하기 위해 크로스 도킹을 만들고 처리하는 단계를 안내합니다. 사용자는 여러 구성을 정의하고 시스템이 제품 배포 방법을 제안하도록 하거나 제품이 배포되는 위치와 각 상점에 배포되는 양을 수동으로 입력할 수 있습니다. 이 절차에는 보충 규칙, 조직 계층 및 상점 가중치와 같이 크로스 도킹에서 사용할 수 있는 데이터 설정이 포함되지 않습니다. 이 절차는 USRT 데모 회사를 사용합니다.

1. 모든 구매 주문으로 이동합니다.
2. 목록에서 구매 주문을 선택하고 링크를 클릭하여 주문을 엽니다.
3. 작업 창에서 소매 및 상거래를 클릭합니다.
4. 크로스 도킹을 클릭합니다.
5. 편집을 클릭합니다.
    * 범주를 사용하여 라인 섹션의 항목을 필터링할 수 있습니다.  
6. 목록에서 원하는 레코드를 찾아 선택합니다.
7. 크로스 도킹 수량 필드에 값을 입력하여 선택한 제품의 구매 수량 중 어느 정도를 분배해야 하는지 지정합니다.
8. 추가 크로스 도킹 수량 필드에 값을 입력하여 구매 가능한 제품에 대해 분배할 수량을 지정합니다.
9. 배포 필드에 '위치 가중치'를 입력합니다.
    * 다른 유형을 선택하여 배포에 다른 규칙을 사용할 수 있습니다.  
10. 보충 계층 필드에서 값을 선택합니다.
11. 관련 분류 필드에서 예를 선택합니다.
12. 수량 계산을 클릭합니다.
13. 주문 생성을 클릭합니다.
14. 예를 클릭합니다.
15. 목록에서 제품을 수령한 창고를 찾아 선택합니다.
16. 선택한 창고에 대해 생성된 주문을 보려면 주문을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]