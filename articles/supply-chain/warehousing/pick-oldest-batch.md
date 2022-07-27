---
title: 모바일 디바이스에서 가장 오래된 배치 선택
description: 이 항목에서는 모바일 디바이스에서 가장 오래된 배치를 선택하는 옵션을 설정하고 적용하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: d96221ae14610057cceed304efa01261eb01aef134e4bdad10ccd0386bd52cf9
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446950"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a>모바일 디바이스에서 가장 오래된 배치 선택

[!include [banner](../includes/banner.md)]

모바일 디바이스 메뉴를 통해 **가장 오래된 배치 선택** 구성에 액세스할 수 있으며 창고 작업자가 현재 위치에서 가장 오래된 배치를 선택하도록 강제하거나 경고할 수 있습니다.  

## <a name="where-it-applies"></a>적용되는 곳
가장 오래된 배치 선택은 모바일 디바이스 메뉴 항목에 구성되며 항목 아래 배치에 대한 선택에 영향을 줍니다.

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a>가장 오래된 배치 선택에 대한 구성을 설정하는 방법 
기존 작업을 사용하도록 설정된 항목의 경우 모바일 디바이스 메뉴에서 **가장 오래된 배치 선택** 을 **없음**, **경고** 또는 **강제** 로 설정할 수 있습니다.

**없음**: 작업자는 메시지를 받지 않으며 자신의 위치에서 배치를 선택할 수 있습니다.

**경고** 및 **강제**: 작업자가 배치를 선택하면 만료일이 가장 오래된 배치 목록이 배치 컨트롤 위에 표시됩니다. 위치가 번호판 제어되는 경우 가장 오래된 배치가 있는 번호판 목록이 번호판 제어 위에 표시됩니다. 
-   **경고**: 작업자가 표시된 목록에 없는 번호판이나 배치를 선택하면 컨트롤이 비어 있고 선택할 이전 배치가 있다는 경고가 표시됩니다. 작업을 계속하려면 작업자가 동일한 번호판이나 배치를 다시 선택할 수 있습니다.  
-   **강제**: 작업자는 선택할 이전 배치가 있다는 메시지를 계속 수신합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]