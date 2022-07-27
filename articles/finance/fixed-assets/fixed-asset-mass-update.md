---
title: 고정 자산 대량 업데이트
description: 장부를 사용하는 경우 동일한 장부에 속한 자산 그룹에 대한 감가상각 규칙을 변경할 수 있습니다.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 087f110da6a0d9582ee6b04a59ade24a5ed3fc68
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451093"
---
# <a name="fixed-asset-mass-update"></a>고정 자산 대량 업데이트

[!include [banner](../includes/banner.md)]

장부를 사용하는 경우 동일한 장부에 속한 자산 그룹에 대한 감가상각 규칙을 변경할 수 있습니다.

예를 들어 미국에 거주하고 자산의 40% 이상을 해당 연도의 4분기에 사용했다면 분기 중간 감가상각 규칙을 사용해야 합니다. 대량 업데이트 프로세스를 사용하여 새로운 감가상각 규칙이 필요한 모든 자산을 변경할 수 있습니다. 

자산에 대한 감가상각 규칙을 업데이트하면 해당 자산에 대해 존재하는 모든 감가상각 거래가 삭제됩니다. 또한 해당 자산에 대한 감가상각 조정 거래, 보너스 감가상각 거래 및 특별 감가상각 거래도 삭제됩니다. 

이미 처분한 자산에 대한 감가상각 규칙을 업데이트하려면 먼저 기존 처분 거래를 삭제해야 합니다. 또한 처분 프로세스로 인해 생성된 모든 거래를 삭제해야 합니다. 

자산에 대한 감가상각 규칙을 업데이트한 후 각 자산에 대한 감가상각 및 특별 감가상각을 처리할 수 있습니다. 조정이 필요한 경우 수동으로 감가상각을 조정할 수도 있습니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
