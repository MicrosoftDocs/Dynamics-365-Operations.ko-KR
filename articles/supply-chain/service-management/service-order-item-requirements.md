---
title: 서비스 주문 항목 요구 사항
description: 이 토픽에서는 서비스 주문 항목 요구 사항에 대해 설명합니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ae211cb24e3ed0e9e54643448ee378a20658ad89
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448600"
---
# <a name="service-order-item-requirements"></a>서비스 주문 항목 요구 사항

[!include [banner](../includes/banner.md)]

서비스 주문을 생성하여 고객에게 제공하는 서비스를 추적하고 관리할 수 있습니다. 서비스 주문에 대한 특정 품목을 예약해야 하는 경우 해당 품목에 대한 재고 품목 요구사항을 생성할 수 있습니다. 품목 요구 사항은 재고에서 즉시 소비되거나 품목에 대한 생산 주문을 시작할 수 있습니다.

품목 거래 대신 품목 소요량을 사용하면 품목이 실제로 사용되기 직전에 납품을 계획하고, 구매 주문을 생성하고, 무역 계약 프레임워크에 품목을 포함하고, 생산 계획에 품목 소요량을 포함할 수 있습니다.

서비스 주문에 대한 항목 요구 사항은 프로젝트를 통해 처리됩니다. 서비스 주문에 대한 항목 요구사항을 생성하려면 서비스 주문을 프로젝트에 첨부해야 합니다.

서비스 주문에 대한 항목 요구 사항이 생성되는 즉시 개별 서비스 주문의 **프로젝트** 또는 **판매 주문** 양식을 통해 볼 수 있습니다.

## <a name="view-an-item-requirement-from-a-service-order"></a>서비스 주문에서 항목 요구 사항 보기

1. **서비스 관리** \> **일반** \> **서비스 주문** \> **서비스 주문** 으로 이동합니다.
1. **디스패치** 를 선택한 다음 **항목 요구 사항** 을 선택하여 **항목 요구 사항** 양식을 엽니다.
1. **프로젝트** 탭을 선택하고 **서비스 주문** 필드를 확인하여 항목 요구 사항의 서비스 주문을 확인합니다.

## <a name="delete-service-orders-with-item-requirements"></a>항목 요구 사항이 있는 서비스 주문 삭제

서비스 주문에 항목 요구사항이 생성된 경우 서비스 주문을 삭제할 수 없습니다. 서비스 주문을 삭제하려면 먼저 항목 요구사항을 삭제해야 합니다.

1. **서비스 관리** \> **일반** \> **서비스 주문** \> **서비스 주문** 으로 이동합니다.
1. **디스패치** 를 선택한 다음 **항목 요구 사항** 을 선택하여 **항목 요구 사항** 양식을 엽니다. 이 양식은 서비스 주문에서 생성된 항목 요구 사항을 나열합니다.
1. 삭제할 품목 요구 사항을 선택한 다음 **삭제** 를 선택합니다.

–또는–

1. **프로젝트 관리 및 회계** \> **공통** \> **프로젝트** \> **모든 프로젝트** 로 이동합니다.
1. 항목 요구 사항이 생성된 서비스 주문이 있는 프로젝트를 엽니다.
1. **프로젝트** 양식의 오른쪽 창에서 **항목 요구 사항** 을 선택합니다. **항목 요구 사항** 양식에는 선택한 프로젝트와 연결된 항목 요구 사항이 나열됩니다.
1. 삭제할 품목 요구 사항을 선택한 다음 **삭제** 를 선택합니다.

## <a name="see-also"></a>참고 항목

[항목 요구 사항(양식)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))



[!INCLUDE[footer-include](../../includes/footer-banner.md)]