---
title: 차원 생성 및 차원 구성원 가져오기
description: 원가 회계는 다른 모듈의 마스터 데이터가 필요한 독립 모듈입니다.
author: ShylaThompson
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6febb8a48cf6496fb7f4c2ee9f5281d47aa1ccae1a8ecc51c908b3810302e11c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450808"
---
# <a name="create-dimensions-and-import-dimension-members"></a>차원 생성 및 차원 구성원 가져오기

[!include [banner](../includes/banner.md)]

원가 회계는 다른 모듈의 데이터가 필요한 독립 모듈입니다. 이 데이터는 다음과 같이 분류됩니다.

-  비용 요소
-  비용 개체
-  통계적 차원

**비용 요소** 는 계정 차트의 비용 관련 항목에 해당합니다. **비용 개체** 는 추정, 비용 할당 또는 직접 측정하려는 제품, 비용 센터 및 프로젝트와 같은 모든 유형의 재무 차원에 해당합니다. **통계 차원** 및 해당 구성원은 비금전적 항목을 등록하는 데 사용됩니다. 통계 차원 구성원은 비용 분배 및 할당의 할당 기준으로 사용할 수 있습니다 

다음 다이어그램은 원가 회계에 사용되는 차원을 보여줍니다.

[![원가 회계 차원.](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)

데이터를 원가 회계로 가져온 후 이를 사용하여 조직의 모든 수준에서 관리자에게 인사이트를 제공하는 다양한 관점을 구축할 수 있습니다. 다음 항목에서는 차원 생성 및 차원 구성원 가져오기에 대한 정보를 제공합니다. 

-  [비용 요소 차원](cost-elements.md)
-  [비용 요소 생성](./tasks/create-cost-elements.md)
-  [비용 개체 차원](cost-objects.md)
-  [비용 요소 차원 구성원을 차원 구성원의 공통 집합에 매핑](map-cost-elements-dimension-members.md)
-  [비용 요소 차원 매핑](./tasks/map-cost-element-dimension.md)
-  [통계 차원 구성원 및 통계 측정값 공급자 템플릿](statistical-measure-provider-template.md)








[!INCLUDE[footer-include](../../includes/footer-banner.md)]