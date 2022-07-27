---
title: 모바일 디바이스의 창고 내 이전 배치 표시 구성
description: 이 토픽에서는 작업 라인의 현재 위치보다 오래된 배치가 있는 위치 목록을 표시하도록 모바일 디바이스를 설정하는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3d23a259f4c16026ee36f73b427f7d2e610a4b8d938c2e21ec9715d8d2b8137b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446752"
---
# <a name="configure-display-older-batches-within-warehouse-on-a-mobile-device"></a>모바일 디바이스의 창고 내 이전 배치 표시 구성

[!include [banner](../includes/banner.md)]

**창고 내 이전 배치 표시** 구성을 사용하면 작업 라인의 현재 위치보다 오래된 배치가 있는 위치 목록을 표시할 수 있습니다. 표시되는 위치 목록에는 해당 위치의 이전 배치에 대한 정보와 만료 날짜 및 각 배치의 총실사가 포함됩니다. 새 위치에서 선택하거나 현재 위치에서 계속 선택하도록 선택할 수 있습니다. 
- 새 위치에서 선택 - 선택할 새 위치를 선택하면 현재 작업 라인이 새 위치를 사용하도록 업데이트되고 작업은 새 위치에서 평소와 같이 계속됩니다. 새 위치가 유효하려면 전체 작업 라인에 사용할 수 있는 수량이 충분해야 합니다. 필요한 수량을 사용할 수 없는 경우 작업 라인이 업데이트되지 않고 목록이 표시됩니다. 
- 현재 위치에서 계속 피킹 - 현재 작업 라인 위치를 계속 사용하면 작업 라인에 대한 수량이 원래 위치에서 계속 피킹됩니다.

## <a name="where-it-applies"></a>적용되는 곳
창고 내 이전 배치 표시는 모바일 디바이스 메뉴 항목에 구성되어 있으며 항목 아래 배치에 대한 선택에 영향을 줍니다.

## <a name="set-up-display-older-batches-within-warehouse"></a>창고 내 이전 배치 표시 설정
**가장 오래된 배치 표시** 구성은 **가장 오래된 배치 선택** 옵션이 **경고** 로 설정된 경우 모바일 디바이스 메뉴 항목에서 사용할 수 있습니다.

- **창고 관리** > **설정** > **모바일 디바이스** > **모바일 디바이스 메뉴 항목** 에서 메뉴 항목에 대해 **기존 작업 사용** 을 **예** 로 설정하고 **가장 오래된 배치 선택** 필드에서 **경고** 를 선택하세요. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]