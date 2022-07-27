---
title: 변형 가중치를 사용하여 구매 주문에 변형 제품 추가
description: 이 절차는 변형 가중치를 사용하여 제품의 각 변형에 대한 구매 주문 라인을 자동으로 채우는 단계를 안내합니다.
author: t-benebo
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f9523410447c102481dd2c709b1fa3dd69d03e8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447844"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a>변형 가중치를 사용하여 구매 주문에 변형 제품 추가

[!include [banner](../../includes/banner.md)]

이 절차는 변형 가중치를 사용하여 제품의 각 변형에 대한 구매 주문 라인을 자동으로 채우는 단계를 안내합니다. 구매하려는 제품의 수량을 선택하면 제품 변형에 구성된 중량을 기반으로 제안된 수량과 함께 제품의 모든 변형에 대한 구매 주문 라인이 생성됩니다. 이 절차에는 제품 치수 및 제품 변형에 대한 중량 값을 구성하는 단계가 포함되어 있지 않습니다. 이 절차에서는 데모 데이터에서 USRT 회사를 사용합니다.

1. 지급 계정 > 구매 주문 > 모든 구매 주문으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 공급업체 계정 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
5. 일반 섹션의 확장을 토글합니다.
6. 사이트 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. 창고 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
9. 목록에서 원하는 레코드를 찾아 선택합니다.
10. 목록에서 선택한 행의 링크를 클릭합니다.
11. 확인을 클릭합니다.
12. 라인 세부 정보 섹션의 확장을 토글합니다.
13. 변형 탭을 클릭합니다.
14. 라인 추가를 클릭합니다.
15. 목록에서 선택한 행을 표시합니다.
16. 품목 번호 필드에 '0140'을 입력합니다.
17. 수량을 '1000'으로 설정합니다.
18. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]