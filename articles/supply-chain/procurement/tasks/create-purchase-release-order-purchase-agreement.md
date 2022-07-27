---
title: 구매 주문 생성 시 구매 계약 적용
description: 이 절차는 구매 주문을 생성할 때 구매 계약을 사용하는 방법을 보여줍니다.
author: Henrikan
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 130524dc8e0c8724e35bf13c6b250ab721383711
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448306"
---
# <a name="apply-a-purchase-agreement-when-creating-a-purchase-order"></a>구매 주문 생성 시 구매 계약 적용

[!include [banner](../../includes/banner.md)]

이 절차는 구매 주문을 생성할 때 구매 계약을 사용하는 방법을 보여줍니다. 구매 주문 헤더에 복사해야 하는 일반 조건이 있으므로 구매 주문을 생성할 때 구매 계약을 적용해야 합니다. 이 작업은 일반적으로 구매 에이전트가 수행합니다. 이 가이드의 전제 조건으로 공급업체 및 품목에 대한 제품 수량 약정이 포함된 효과적인 구매 계약이 있어야 합니다. 다른 유형의 약정과 구매 계약이 있는 경우에도 동일한 절차를 사용할 수 있습니다.

## <a name="create-a-purchase-order"></a>구매 주문 만들기

1. **생산 및 소싱 \> 작업 영역 \> 구매 주문 준비** 로 이동합니다.
1. 작업 창에서 **새 구매 주문** 을 선택합니다.
1. **구매 주문 생성** 대화 상자가 열립니다. **공급업체 계정** 을 선택합니다. 필요에 따라 다른 주소 필드를 검사하고 조정합니다.
1. **일반** 빠른 탭을 확장합니다.
1. **구매 계약** 필드에서 사용하려는 유효 계약을 찾아 선택합니다. 공급업체에 대해 사용 가능한 모든 계약이 여기에 나열됩니다.  
1. **예** 를 선택합니다.
1. **확인** 을 선택합니다.

## <a name="add-a-line"></a>라인 추가

1. **품목 번호** 필드에 값을 입력합니다. 약정에 특정 재고 또는 위치 차원이 있는 경우 계약을 사용하려면 구매 발주 라인에 동일한 값을 입력해야 합니다.
1. **사이트** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다. 사이트는 주문 또는 공급업체의 기본값으로 이미 채워져 있을 수 있습니다. 이 경우 이 단계를 건너뜁니다.  
1. 목록에서 원하는 레코드를 찾아 선택합니다.
1. 목록에서 선택한 행의 링크를 선택합니다.
1. **수량** 필드에 숫자를 입력합니다. 가격이 약정에서 복사되었는지 확인합니다.  

## <a name="look-up-the-commitment"></a>약정 조회

1. **업데이트 라인** 을 선택합니다.
1. **연결됨** 을 선택합니다. 여기에서 구매 계약에 대한 세부 정보를 얻을 수 있습니다. 예를 들어 가격과 가격 및 할인이 고정되어 있는지 여부를 확인할 수 있습니다. 즉, 구매 주문의 가격이나 할인을 약정과 다른 값으로 변경하면 시스템에서 링크를 제거하여 구매 주문 라인이 약속을 이행하지 않습니다. 또한 최대 적용 옵션이 선택되었는지 확인할 수 있습니다. 이는 약정을 이행하는 모든 구매를 합산하여 약정 수량을 초과할 수 없음을 의미합니다.  
1. 페이지를 닫습니다.

## <a name="look-up-the-purchase-agreement"></a>구매 계약 조회

1. **작업 창** 에서 **일반** 을 선택합니다.
1. **구매 계약** 을 선택합니다.
1. 페이지를 닫습니다.
1. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]