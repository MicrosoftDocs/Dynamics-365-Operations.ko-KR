---
title: 비용 개체 차원
description: 비용을 분석할 때 비용 요소 차원을 사용하여 비용이 어디로 유입되는지 결정합니다. 비용 개체 차원을 사용하여 비용을 할당해야 하는 위치를 결정합니다. 이 토픽에서는 비용 개체 차원에 대한 정보를 제공합니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimensionMember, CAMCostObject
audience: Application User
ms.reviewer: roschlom
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: e266a9ee2f47b819a4074291ad4a52d8df46ce1abe4f16308a3645375cd2dd80
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450268"
---
# <a name="cost-object-dimensions"></a>비용 개체 차원

[!include [banner](../includes/banner.md)]

비용을 분석할 때 비용 요소 차원을 사용하여 비용이 어디로 유입되는지 결정합니다. 비용 개체 차원을 사용하여 비용을 할당해야 하는 위치를 결정합니다. 이 토픽에서는 비용 개체 차원에 대한 정보를 제공합니다.

비용 개체는 비용을 추정하거나 할당하거나 직접 측정하려는 모든 유형의 개체일 수 있습니다. 일반적인 비용 개체에는 제품, 프로젝트, 리소스, 부서, 비용 센터 및 지리적 지역이 포함됩니다. 경영진은 비용 개체를 사용하여 비용을 수량화하고 수익성 분석을 추진합니다.

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a>비용 개체 차원 및 비용 개체 차원 구성원
비용 개체를 *비용 개체 차원* 이라고 합니다. 비용 개체 차원이 참조해야 하는 엔터티를 결정한 후에는 개별 차원 값을 지정하거나 다른 소스 시스템에서 원가 회계로 가져와야 합니다. 이러한 개별 차원 값을 *비용 개체 차원 구성원* 이라고 합니다. 예를 들어 비용 센터라는 재무 차원을 비용 개체 차원으로 사용하려고 합니다. 비용이 개별 비용 센터로 유입되는 방식을 확인하려면 비용 개체 차원 구성원을 가져와야 합니다. 이 경우 비용 개체 차원 구성원은 판매, 생산, 관리 및 지리적 위치와 같은 실제 비용 센터입니다. 다음 스크린샷은 실제 비용 센터를 비용 개체 차원 구성원으로 사용하는 비용 개체 차원으로서 비용 센터의 예를 보여줍니다. 

[![비용 센터를 비용 개체 차원으로 보여주는 스크린샷.](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)

## <a name="import-cost-object-dimension-members-through-data-connectors"></a>데이터 커넥터를 통해 비용 개체 차원 구성원 가져오기
비용 개체 차원 구성원을 더 쉽게 가져오려면 데이터 커넥터를 사용하여 비용 개체 차원으로 사용할 엔터티에서 값을 검색합니다. 미리 빌드된 데이터 커넥터 또는 사용자가 빌드한 사용자 지정 데이터 커넥터를 사용할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]