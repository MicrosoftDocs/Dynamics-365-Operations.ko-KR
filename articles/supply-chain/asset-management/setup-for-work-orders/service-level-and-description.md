---
title: 서비스 수준 및 설명
description: 이 토픽에서는 자산 관리의 서비스 수준 및 설명에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectServiceLevel, EntAssetWorkOrderStandardDescription, EntAssetWorkOrderServiceLevel, EntAssetServiceLevelLookup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 32e6dd6ba7291e8ea1cb78eeed2d8e2fcec0f6dd3cbd039336be0169730101ba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447103"
---
# <a name="service-level-and-description"></a>서비스 수준 및 설명

[!include [banner](../../includes/banner.md)]

 

작업 주문을 생성할 때 해당 서비스 수준을 정의하고 일반 설명을 추가할 수 있습니다. **작업 주문 서비스 수준** 페이지에서 작업 주문 서비스 수준을 생성하고 **작업 주문 설명** 페이지에서 설명을 생성할 수 있습니다.

## <a name="create-a-service-level"></a>서비스 수준 만들기

1. **자산 관리** \> **설정** \> **작업 주문** \> **서비스 수준** 을 선택합니다.
2. **새로 만들기** 를 선택합니다.
3. **서비스 수준** 필드에서 서비스 수준(예: 숫자)을 입력합니다.
4. **이름** 필드에 이름을 입력합니다.

    **작업 주문** 빠른 탭에서는 예상 시작 및 종료 날짜와 시간을 정의할 수 있습니다. 이 빠른 탭의 필드는 작업 주문이 시작되고 종료되어야 하는 기간을 정의합니다. 수동으로 생성된 작업 주문과 유지 관리 요청을 기반으로 생성된 작업 주문에 사용됩니다. 

5. **시작일** 필드에서 작업 주문이 시작되어야 하는 기간을 정의하는 일 수를 입력합니다. 일 수는 작업 주문 생성 날짜부터 계산됩니다. 예를 들어 작업 주문이 생성될 때 시작되어야 하는 경우 **0** 을 입력합니다. 작업 주문이 생성된 후 1주일 이내에 시작되어야 하는 경우 **7** 을 입력합니다.
6. 작업 주문의 시작 시간을 설정하려면 시작 날짜 외에 **시작 시간 설정** 옵션을 **예** 로 설정합니다. 그런 다음 **시작 시간** 필드에 시작 시간을 입력합니다. 옵션을 **아니요** 로 설정하면 현재 시간이 사용됩니다.
7. **종료일** 필드에서 작업 주문이 종료되어야 하는 기간을 정의하는 일 수를 입력합니다. 일 수는 작업 주문 시작 날짜부터 계산됩니다. 예를 들어 작업 주문이 시작 날짜로부터 일주일 이내에 종료되어야 하는 경우 **7** 을 입력합니다.
8. 작업 주문의 종료 시간을 설정하려면 종료 날짜 외에 **종료 시간 설정** 옵션을 **예** 로 설정합니다. 그런 다음 **종료 시간** 필드에 종료 시간을 입력합니다. 옵션을 **아니요** 로 설정하면 현재 시간이 사용됩니다.
9. **저장** 을 선택합니다.

![작업 주문 서비스 수준 페이지.](media/19-setup-for-work-orders.png)

## <a name="create-a-description"></a>설명 만들기

1. **자산 관리** \> **설정** \> **작업 주문** \> **설명** 을 선택합니다.
2. **새로 만들기** 를 선택합니다.
3. **설명** 필드에 설명을 입력합니다.
4. **저장** 을 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]