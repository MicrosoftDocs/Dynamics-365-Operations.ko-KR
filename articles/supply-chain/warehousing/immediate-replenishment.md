---
title: 즉각적인 보충
description: 이 토픽에서는 위치 지시문이 재고를 할당하지 못한 경우 즉시 보충을 사용하여 재고를 보충할 수 있는 방법에 대해 설명합니다.
author: Mirzaab
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSReplenishmentTemplates
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 15a3cc4c50e49a50c354834761425cd107c23a9d79677e022cb1d339bb48c918
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446896"
---
# <a name="immediate-replenishment"></a>즉각적인 보충

[!include [banner](../includes/banner.md)]

즉시 보충을 사용하면 위치 지시 라인이 재고를 할당하지 못한 직후에 재고를 보충할 수 있습니다. 보충은 위치 지시문 설정의 한 줄을 기반으로 합니다. 해당 라인에 지정된 UOM에 재고가 없는 경우 해당 UOM이 즉시 보충됩니다.

즉각적인 보충은 재고 할당이 위치 지시문에서 더 많은 라인을 기반으로 하는 경우 그리고 수요는 할당이 끝날 때 합산되고 위치 지시문의 마지막 라인에 지정된 측정 단위로 보충되는 경우에 대체 방법을 제공합니다.

즉시 보충 사용의 이점은 보충이 특정 단위로 제한될 수 있고 수량을 특정 위치로 보낼 수 있다는 것입니다.

## <a name="business-scenario"></a>비즈니스 시나리오

예를 들어, "상자" 및 "각" 측정 단위에 대해 별도의 피킹 영역이 있는 창고가 있습니다. 가능한 한 많은 상자를 선택한 다음 "각각" 영역에서 상자보다 적은 나머지 수량을 선택하여 선택 프로세스를 최적화하려고 합니다.

이 경우 즉시 보충을 사용할 수 있습니다. 위치 지시문에서 수요 수량에 대해 피킹할 수 있는 박스가 부족해지는 즉시 수요 보충이 사용되도록 박스에 대한 즉시 보충을 설정할 수 있습니다. 이러한 방식으로 피킹에 가능한 한 많은 상자가 포함되도록 피킹 프로세스를 최적화합니다. 즉각적인 보충은 상자의 보충을 생성하고 수량은 "각" 측정 단위로 선택되도록 수요가 전달되지 않습니다. 즉, "개별" 측정 단위로 선택해야 하는 수량(즉, 상자보다 작은 수량)만 "각" 영역에서 선택됩니다. "상자" 영역에서 부족이 발생하는 경우 총 수요에서 가능한 많은 상자를 선택할 수 있습니다. 나머지 수량은 "각각" 영역에서 선택됩니다.

## <a name="where-it-applies"></a>적용되는 곳

보충 템플릿이 설정된 위치 지시 라인에 대한 할당이 실패한 경우 웨이브 실행 중 즉시 보충이 사용됩니다.

## <a name="set-up-immediate-replenishment"></a>즉각적인 보충 설정

- **창고 관리** \> **설정** \> **위치 지시문** 으로 이동한 다음 **라인** 탭의 **즉시 보충 템플릿** 목록에서 웨이브 수요에 대한 보충 템플릿을 선택합니다.

보충 템플릿은 위치 지시 라인이 전용 측정 단위를 할당하지 못한 경우 적용됩니다.

## <a name="troubleshooting"></a>문제 해결

위치 지시 라인에 대해 즉시 보충이 선택되었지만 해당 위치 지시 라인에 대해 수요 보충 템플릿을 사용할 때 생성된 보충 작업이 없는 경우 두 가지 주요 원인을 조사해야 합니다.

- 적용되는 수요 보충 템플릿이 **보충** 유형의 올바른 위치 템플릿 및 작업 템플릿을 사용하도록 설정되어 있는지 확인하세요.
- 수요 보충 템플릿이 보충을 위해 현재고를 검색하는 위치에 현재고가 충분한지 확인하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]