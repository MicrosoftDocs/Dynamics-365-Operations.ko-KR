---
title: 운송 관리 상태
description: 이 토픽에서는 운송 상태를 생성하고 해당 상태를 운송업체 상태에 매핑하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9c5570d3b5b436a35bb57d051bc06cde8b78934e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448252"
---
# <a name="transportation-management-statuses"></a>운송 관리 상태

[!include [banner](../includes/banner.md)]

운송업체에서 제공한 코드를 해석하려면 운송 상태에 대한 마스터 코드를 설정하세요. 이를 통해 운송업체와 통합하여 상태를 제공할 수 있습니다. 운송 마스터 상태 코드에 대해 제공하는 운송 상태는 화물, 선적 또는 컨테이너의 상태를 추적하는 데 도움이 될 수 있습니다. 화물, 선적 또는 컨테이너에 대한 특정 운송 상태는 데이터 통합을 통해서만 업데이트할 수 있으며 사용자 인터페이스를 통해 수동으로 업데이트할 수는 없습니다.

## <a name="create-a-transportation-status"></a>전송 상태 만들기

전송 상태를 생성하려면 다음 단계를 따르세요.

1. **운송 관리 \> 설정 \> 운송 상태 마스터** 로 이동합니다.
1. **새로 만들기** 를 선택하여 운송 상태 마스터를 만듭니다.
1. **운송 상태 마스터** 필드에 운송 상태에 대한 고유 코드를 입력합니다.
1. **운송 유형** 필드에서 운송 유형으로 *운송업체* 또는 *허브* 를 선택합니다.
1. 이름과 운송 상태를 입력합니다.
1. 페이지를 닫습니다.

## <a name="map-a-transportation-status-to-a-carrier-status"></a>운송 상태를 운송업체 상태에 매핑

운송 상태를 운송업체 상태에 매핑하려면 다음 단계를 따르세요.

1. **운송 관리 \> 설정 \> 운송업체 \> 운송업체 운송 상태** 로 이동합니다.
1. **신규** 를 선택하여 운송업체의 코드를 운송 상태 마스터 코드로 매핑합니다.
1. 운송업체 및 운송업체 서비스의 고유 ID를 선택합니다.
1. 선택한 운송업체 코드에 매핑할 운송 상태 코드를 선택합니다.
1. 운송업체에서 사용하는 외부 코드를 입력합니다.
1. 페이지를 닫습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]