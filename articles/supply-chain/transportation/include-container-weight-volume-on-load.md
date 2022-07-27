---
title: 적재 시 컨테이너 중량 및 부피 포함
description: 이 토픽에서는 적재 시 컨테이너 중량 및 부피를 포함하도록 기능을 설정하고 적용하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRateRouteWorkbench, TMSDriverLogListPage, TMSTransportationTender
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 52b42bd0b97564a493a50331d1424ca8084b389b29518f012f443d9cf722efe7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447139"
---
# <a name="include-container-weight-and-volume-on-load"></a>적재 시 컨테이너 중량 및 부피 포함

[!include [banner](../includes/banner.md)]

적재물에 컨테이너 중량 및 부피를 포함하는 기능은 적재 중인 컨테이너 및 항목의 총 중량 및 부피를 명확하게 나타냅니다.

적재 화물에는 단일 배송 또는 여러 배송이 포함되며 이러한 배송에는 단일 판매 주문 또는 여러 판매 주문에 속하는 고유한 항목이 포함됩니다. 항목은 컨테이너 내부에 저장되고 컨테이너는 적재 화물에 적재됩니다. 컨테이너 외부에 있는 항목도 적재의 일부가 될 수 있습니다. 이러한 조건을 기반으로 시스템은 컨테이너와 품목의 무게와 부피를 고려하여 적재의 무게와 부피 값을 계산합니다.

계산된 값이 정확하지 않은 경우 하중의 무게와 부피에 대한 실제 값을 입력하여 조정할 수 있습니다. 중량 및 부피 값은 운송 관리 프로세스에 사용됩니다. 예를 들어, 값은 요금 경로 워크벤치에서 사용되며, 여기에서 적재에 대한 요금 및 경로를 정의하는 데 도움이 되며 운송 입찰 및 운전자 체크인에도 사용됩니다.

## <a name="where-it-applies"></a>적용되는 곳

화물에 컨테이너 중량 및 부피를 포함하는 기능은 요금 경로 워크벤치, 운송 입찰, 운전자 체크인과 같은 운송 관리 프로세스에 적용됩니다.

## <a name="how-it-is-set-up"></a>설정 방법

적재에 대해 고려해야 하는 컨테이너의 수는 컨테이너의 무게와 부피를 기준으로 계산되며 컨테이너가 사용되는 비율입니다.

-   컨테이너의 무게와 부피를 설정하려면 **창고 관리** \> 설정 **설정** \> **컨테이너** \> **컨테이너 유형** 을 클릭합니다.

-   컨테이너 사용률을 설정하려면 **창고 관리** \> **설정** \> **컨테이너** \> **컨테이너 그룹** 을 클릭한 다음 **컨테이너 사용률** 필드에 값을 입력합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]