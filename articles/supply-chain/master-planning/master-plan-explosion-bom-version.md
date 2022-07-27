---
title: BOM 버전의 폭발
description: 이 문서에서는 BOM(자재 명세서) 버전의 폭발적인 증가와 관련된 기준 일정 시나리오에 대해 설명합니다.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be4dfc85ad7ab01df9a95a394896873e2d649e12
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448789"
---
# <a name="explosion-of-a-bom-version"></a>BOM 버전의 폭발

[!include [banner](../includes/banner.md)]

이 문서에서는 BOM(자재 명세서) 버전의 폭발적인 증가와 관련된 기준 일정 시나리오에 대해 설명합니다.

BOM(자재 명세서) 버전의 수요 폭발은 특정 사이트 및 가능하면 특정 창고에서 각 BOM 라인 항목에 대한 수요를 생성합니다. 사이트별 BOM에서는 각 BOM 라인에 대해 특정 창고를 정의할 수 있습니다. 또한 각 BOM 라인에 대해 품목의 치수 설정에 따라 창고가 필요한지 여부가 결정됩니다. 그러면 각 BOM 라인 항목에 대한 결과 수요가 추가 수요 폭발의 시작점이 됩니다. 이 기준 계획 시나리오에는 다음 조건이 포함됩니다.

-   사이트 차원은 필수이며 수요 트랜잭션에 입력해야 합니다.
-   사이트 차원이 일관적입니다. 따라서 하위 수요에 대한 사이트는 초기 수요 트랜잭션의 사이트와 동일합니다.

다음 그림은 기준 계획 수요 폭발의 프로세스를 보여줍니다. ![BOM 버전을 사용한 수요 폭발.](./media/multisitedemandexplosionscenariousingbomversion.gif)

## <a name="additional-resources"></a>추가 리소스

[BOM 버전 확인](master-plan-bom-version-determined.md)

[기준 계획 및 다중 사이트 기능 개요](master-plan-multisite-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]