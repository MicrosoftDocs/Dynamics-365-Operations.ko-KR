---
title: 일회성 공급자에 대한 구매 발주 생성
description: 이 절차에서는 일회성 공급자에 대한 구매 주문을 만드는 방법을 보여줍니다.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e89a9d1b382efa3b90b8d70e84777321e9595f4a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449227"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>일회성 공급자에 대한 구매 발주 생성

[!include [banner](../../includes/banner.md)]

이 절차에서는 일회성 공급자에 대한 구매 주문을 만드는 방법을 보여줍니다. 공급업체 계정을 수동으로 생성할 필요 없이 구매 주문과 함께 공급업체가 자동으로 생성됩니다. 구매 주문은 일반적으로 구매 에이전트가 생성합니다. 이 가이드에 표시된 예제는 USMF 데모 데이터 회사에서 사용할 수 있습니다. 미지급금 매개변수 페이지에서 일회성 공급업체 계정이 설정되어 있어야 한다는 전제 조건이 있습니다.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>일회성 공급자에 대한 구매 발주 생성
1. 조달 및 소싱 > 구매 주문 > 모든 구매 주문으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 일회성 공급자 필드에서 예를 선택합니다.
    * 공급업체 계정이 자동으로 생성되어 구매 주문에 할당됩니다. 공급업체 계정은 미지급금 매개변수 페이지의 일반 탭에 지정된 템플릿을 기반으로 생성됩니다.  
4. 이름 필드에 공급자의 이름을 입력합니다.
5. 확인을 클릭합니다.
    * 이제 구매 주문을 완료하고 다른 주문처럼 처리할 수 있습니다. 이 작업을 수행하는 방법과 관련된 특별한 특성은 없습니다. 송장은 주문과 함께 생성된 공급업체 계정의 만기 거래를 설명하고 지불이 처리됩니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]