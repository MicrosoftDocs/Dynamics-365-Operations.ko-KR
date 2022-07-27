---
title: BOM 버전 확인
description: 수요 전개 중에 품목의 기본 주문 유형이 생산인 경우 계획 엔진은 사이트를 기반으로 유효한 BOM 버전을 찾습니다.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConsistOf, BOMDesigner, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 370091eed4ee050031d5d135aa7b1d8d0fe82491
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448363"
---
# <a name="determine-the-bom-version"></a>BOM 버전 확인

[!include [banner](../includes/banner.md)]

수요 전개 중에 품목의 기본 주문 유형이 생산인 경우 계획 엔진은 사이트를 기반으로 유효한 BOM 버전을 찾습니다. 

사이트 차원은 항상 알려져 있으며 수요 트랜잭션에 명시되어 있습니다. 다음 프로세스는 사용할 BOM 버전을 결정하는 데 사용됩니다.

-   수요 지점의 품목에 대해 정의된 BOM 버전이 있는 경우 지점별 BOM이 사용됩니다.
-   수요 지점의 품목에 대해 정의된 지점별 BOM 버전이 없는 경우 일반 BOM이 사용됩니다. 일반 BOM은 사이트를 명시하지 않으며 여러 사이트에 유효합니다. 일반 BOM이 있으면 사용합니다.
-   사용할 일반 BOM 버전이 없으면 수요 폭발이 이 지점에서 중지됩니다.

사이트별이든 일반이든 유효한 BOM 버전은 날짜 및 수량에 대한 필수 기준을 충족해야 합니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]