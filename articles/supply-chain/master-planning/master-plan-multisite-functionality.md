---
title: 기준 계획 및 다중 사이트 기능 개요
description: 기준 계획에서는 사이트 및 창고 재고 차원의 설정을 고려합니다.
author: ChristianRytt
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2434"
- intro-internal
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e594cfd71201c6a629c04d5557c117649e6b19b0
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449638"
---
# <a name="master-planning-and-multisite-functionality-overview"></a>기준 계획 및 다중 사이트 기능 개요

[!include [banner](../includes/banner.md)]

기준 계획에서는 사이트 및 창고 재고 차원의 설정을 고려합니다. 

사이트 차원은 필수이며 창고 차원을 필수로 설정할 수 있습니다.

차원이 필수인 경우 모든 재고 트랜잭션에 차원 값을 입력해야 합니다. 따라서 기준 계획 중에는 초기 수요에 대한 부지와 창고를 알고 있다. 사이트 차원도 일관되어 하위 수준 수요가 폭발적으로 증가하는 동안 사이트 가치가 변경되지 않습니다.

창고가 필수로 설정되어 있지 않으면 초기 수요에서 알 수 없습니다. 계획 엔진은 항목, 개별 창고 및 주문 라인의 상세내역에 대해 정의된 설정을 기반으로 사용할 창고를 결정해야 합니다.

다음 주제에서는 다양한 설정이 정의된 경우 계획 엔진이 작동하여 사용할 창고를 결정하는 방법에 대해 설명합니다.

[사이트 및 창고 적용 범위에 대한 기준 계획, 창고는 필수임](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[현장 적용 범위용 기준 계획, 필수 창고](master-plan-site-coverage-warehouse-mandatory.md)

[사이트 및 창고 적용 범위에 대한 기준 계획, 창고는 필수 사항이 아님](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[현장 적용 범위용 기준 계획, 창고는 필수가 아님](master-plan-site-coverage-warehouse-not-mandatory.md)

[BOM 버전 확인](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]