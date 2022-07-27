---
title: 서비스 주문에 대한 항목 요구 사항 만들기
description: 이 토픽에서는 서비스 주문에 대한 항목 요구 사항을 만드는 방법에 대해 설명합니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 75a05147883f1592b3a09e02e238661f6c20cf27
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448807"
---
# <a name="create-item-requirements-for-service-orders"></a>서비스 주문에 대한 항목 요구 사항 만들기

[!include [banner](../includes/banner.md)]

서비스 주문을 생성하여 고객에게 제공하는 서비스를 추적하고 관리할 수 있습니다. 서비스 주문에 대한 특정 품목을 예약해야 하는 경우 해당 품목에 대한 재고 품목 요구사항을 생성할 수 있습니다. 품목 요구 사항은 재고에서 즉시 소비되거나 품목에 대한 생산 주문을 시작할 수 있습니다.

품목 거래 대신 품목 소요량을 사용하면 품목이 실제로 사용되기 직전에 납품을 계획하고, 구매 주문을 생성하고, 무역 계약 프레임워크에 품목을 포함하고, 생산 계획에 품목 소요량을 포함할 수 있습니다.

서비스 주문에 대한 항목 요구 사항은 프로젝트를 통해 처리됩니다. 서비스 주문에 대한 항목 요구사항을 생성하려면 서비스 주문을 프로젝트에 할당해야 합니다. 서비스 주문에 대한 품목 요구 사항을 생성한 후 선택한 프로젝트의 **프로젝트** 양식에서 품목 요구 사항을 볼 수 있습니다.

## <a name="create-an-item-requirement-for-a-service-order"></a>서비스 주문에 대한 항목 요구 사항 만들기

1. **서비스 관리** \> **일반** \> **서비스 주문** \> **서비스 주문** 으로 이동합니다.
1. 항목 요구 사항을 생성할 서비스 주문을 선택합니다.
1. **작업 창** 의 **파견** 탭에서 **항목 요구 사항** 을 선택합니다.
1. **항목 요구 사항** 양식에 필수 항목에 대한 정보를 입력합니다. 특정 필드에 대한 자세한 내용은 [항목 요구 사항(양식)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))을 참조하세요.

## <a name="create-an-item-requirement-for-a-service-agreement"></a>서비스 계약에 대한 항목 요구 사항 만들기

1. **서비스 관리** \> **공통** \> **서비스 계약** \> **서비스 계약** 으로 이동합니다.
1. 항목 요구 사항을 생성할 서비스 계약을 엽니다.
1. **라인** 빠른 탭에서 **추가** 를 선택하여 새 라인을 만듭니다.
1. **트랜잭션 유형** 필드에서 **항목** 을 선택합니다.
1. **항목 설정** 필드에서 **항목 요구 사항** 을 선택합니다.
1. **품목 번호** 필드에서 서비스 계약에 필요한 항목을 선택합니다.
1. **라인 세부 정보** 빠른 탭에서 **제품 치수** 탭의 **대지** 필드에 있는 항목의 인벤토리 사이트를 선택합니다.
1. 계약 라인에서 서비스 주문을 **라인** 빠른 탭에서 **서비스 주문 생성** 을 선택한 다음 **서비스 주문 생성** 양식에 관련 정보를 입력합니다.

## <a name="see-also"></a>참고 항목

[자동으로 서비스 주문 생성하기](create-service-orders-automatically.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
