---
title: 재고 여부 확인
description: 이 절차에서는 특정 품목 번호에 대한 현재고 및 실제 현재고를 확인하는 방법을 보여줍니다.
author: yufeihuang
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand, InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c1533dc677c53e90d73077e06a67c71cebc1b7e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448741"
---
# <a name="check-the-availability-of-stock"></a>재고 여부 확인

[!include [banner](../../includes/banner.md)]

이 절차에서는 특정 품목 번호에 대한 현재고 및 실제 현재고를 확인하는 방법을 보여줍니다. 또한 아이템과 관련된 공급 정보를 얻는 방법을 보여줍니다. 실제 현재고는 사용 가능한 현재고입니다. 즉, 구매, 입고 및 등록됩니다. 현재고에는 사용 가능한 현재고뿐만 아니라 주문 및 예상되지만 아직 입고되거나 등록되지 않은 재고도 포함됩니다. 데모 데이터 회사 USMF에서 이 절차를 수행하거나 자신의 데이터를 사용할 수 있습니다. USMF를 사용하는 경우 표시된 예제 값을 사용할 수 있습니다. 이러한 작업은 일반적으로 창고 작업자가 수행합니다.


## <a name="check-on-hand-inventory-for-an-item"></a>품목에 대한 현재고 확인
1. **탐색 창 > 모듈 > 재고 관리 > 조회 및 보고서 > 현재고** 로 이동합니다.
2. **품목 번호** 행을 선택합니다. 품목 번호별로 현재고를 조회하려면 테이블이 **보유 재고** 로 설정되고 필드가 **품목** 번호로 설정된 행을 선택합니다.
3. **기준** 필드에서 조회할 항목을 선택합니다. USMF 데모 데이터 회사를 사용하는 경우 'M9201'을 선택할 수 있습니다.  
4. **확인** 을 클릭합니다.
5. **작업 창** 에서 **차원** 을 클릭합니다. **차원** 탭을 사용하면 현재고에 대해 보고 싶은 세부 정보의 정도를 선택할 수 있습니다. 예약과 관련된 데이터가 필요한 경우 고급 창고(WMS) 프로세스를 사용하는 품목에 대한 모든 재고 차원을 표시해야 합니다.
6. **확인** 을 클릭합니다.
7. **작업 창** 에서 **관련 정보** 를 클릭합니다. 이 옵션이 표시되지 않는 경우 추가 작업 창 옵션을 보려면 줄임표 단추(...)를 클릭해야 할 수 있습니다.
8. **공급 개요** 를 클릭합니다. **공급 개요** 탭에서는 현재고 수량, 리드 타임 및 공급업체 정보와 같은 특정 품목에 대한 공급 정보를 제공합니다.  
9. **현재고** 섹션을 펼칩니다.
10. **공급업체** 섹션을 펼칩니다.
11. 페이지를 닫습니다.
12. 페이지를 닫습니다.

## <a name="check-physical-on-hand-inventory"></a>실제 보유 재고 확인
1. **탐색 창 > 모듈 > 창고 관리 > 조회 및 보고서 > 실제 보유 재고** 로 이동합니다.
2. **품목 번호** 필드에 값을 입력합니다. 사이트 및 창고 필드를 사용하여 항목 목록을 필터링할 수 있습니다. 
3. 페이지를 새로 고칩니다.
4. **작업 창** 에서 **차원 표시** 를 클릭합니다. 차원 표시 탭을 사용하면 현재고에 대해 보고 싶은 세부 정보의 정도를 선택할 수 있습니다.
5. **확인** 을 클릭합니다.
6. 페이지를 닫습니다.

## <a name="check-on-hand-inventory-by-location"></a>위치별 보유 재고 확인
1. **탐색 창 > 모듈 > 창고 관리 > 조회 및 보고서 > 위치별 보유 재고** 로 이동합니다.
2. **창고** 필드에 값을 입력합니다. USMF 데모 데이터 회사를 사용하는 경우 '51'을 선택할 수 있습니다.  
3. 페이지를 새로 고칩니다.
4. **차원 표시** 를 클릭합니다.
5. **확인** 을 클릭합니다.
6. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]