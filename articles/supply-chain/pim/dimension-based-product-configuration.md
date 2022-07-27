---
title: 차원 기반 제품 구성 개요
description: 차원 기반 제품 구성은 단일 제품 기준 및 해당 BOM에서 다양한 제품 변형을 생성하기 위한 간단한 솔루션을 나타냅니다.
author: t-benebo
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19821"
- intro-internal
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8811d4a43dba05e63b270893600a622527834901
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449677"
---
# <a name="dimension-based-product-configuration-overview"></a>차원 기반 제품 구성 개요

[!include [banner](../includes/banner.md)]

차원 기반 제품 구성은 단일 제품 기준 및 해당 BOM에서 다양한 제품 변형을 생성하기 위한 간단한 솔루션을 나타냅니다.

차원 기반 제품 구성은 세 가지 기본 제공 제품 구성 기술 중 하나입니다. 다른 두 가지 기술은 미리 정의된 변형 및 제약 조건 기반 구성입니다. 세 가지 기술 모두 제품 기준을 시작점으로 사용하고 사용자가 하나의 제품 기준에 대해 여러 제품 변형을 생성할 수 있도록 합니다.

## <a name="key-concepts"></a>주요 컨셉
차원 기반 제품 구성은 다음 주요 개념을 기반으로 합니다.

-   제품 기준
-   구성 제품 크기
-   구성 그룹
-   BOM(자재 명세서)
-   구성 경로
-   구성 규칙

### <a name="product-masters"></a>제품 기준

제품 기준은 모든 제품 구성 프로세스의 시작점입니다. 차원 기반 제품 구성의 경우 이 특정 구성 기술이 포함된 제품 기준과 구성 제품 차원을 포함하는 제품 차원 그룹이 필요합니다.

### <a name="configuration-product-dimension"></a>구성 제품 크기

구성 제품 차원은 차원 기반 구성 기술을 사용하여 제품 기준에 대한 제품 변형을 식별하는 데 사용됩니다. 구성 차원 값은 사용자가 입력하며 개별 제품 변형을 식별하는 데 도움이 됩니다.

### <a name="configuration-groups"></a>구성 그룹

구성 그룹은 중앙 저장소에 정의되며 모든 차원 기반 제품 구성 모델에 사용할 수 있습니다. 구성 그룹은 개별 BOM 라인과 연관되며 상호 배타적인 라인 그룹을 함께 유지합니다. 즉, 단일 제품 변형에 대해 그룹에서 하나의 라인만 선택할 수 있습니다.

### <a name="bill-of-materials-bom"></a>BOM(자재 명세서)

BOM은 치수 기반 제품 구성을 위한 빌딩 블록을 나타냅니다. 여기에는 모든 제품 변형에 사용할 수 있는 모든 다른 제품이 포함되어야 합니다. BOM의 각 행은 구성 그룹을 참조할 수 있습니다. 라인이 구성 그룹을 참조하지 않으면 모든 제품 변형에 포함됩니다.

### <a name="configuration-route"></a>구성 경로

구성 경로는 제품 구성 프로세스 중에 사용자에게 표시될 구성 그룹의 순서를 결정합니다.

### <a name="configuration-rules"></a>구성 규칙

구성 규칙은 BOM의 한 구성 그룹에 포함된 제품이 동일한 BOM의 다른 구성 그룹에 있는 제품을 포함하거나 제외하도록 하는 메커니즘을 나타냅니다.

## <a name="product-modeling-process"></a>제품 모델링 프로세스
차원 기반 제품에 대한 제품 모델을 구축하기 위한 자연스러운 순서는 관련 구성 그룹을 정의하는 것으로 시작됩니다. BOM에 사용될 모든 제품이 제품 모델이 구축된 회사에 출시되었는지 확인하는 것이 중요합니다. 이러한 빌딩 블록을 사용하여 사용자는 BOM을 생성하고 모든 관련 BOM 라인에 구성 그룹을 할당할 수 있습니다. BOM이 완료되면 적절한 순서로 구성 그룹을 주문하기 위해 구성 경로를 정의할 수 있습니다. [![차원 기반 제품 모델링 프로세스.](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) 함께 사용해야 하거나 함께 사용하지 않아야 하는 서로 다른 구성 그룹의 특정 제품이 있는 경우 이러한 제품 관계를 적용하는 구성 규칙을 생성할 수 있습니다. BOM이 BOM 버전을 통해 차원 기반 제품 마스터와 함께 연결되고 둘 다 승인 및 활성화되면 제품 구성을 생성하고 각 구성에 대한 이름을 입력할 수 있습니다. 구성은 트랜잭션이 생성되기 전에 정의하거나 특정 구성이 필요할 때 수행할 수 있습니다.

### <a name="suggested-use"></a>권장 사용

치수 기반 구성 기술은 가변성이 제한된 제품에 가장 잘 사용되며 표준 제품 치수 크기, 색상, 스타일 및 구성의 조합은 특정 제품 변형을 식별하는 데 적합하지 않습니다. 프레임 높이, 바퀴 크기, 브레이크 유형 및 다른 기어가 있는 자전거가 그 예일 수 있습니다.

### <a name="next-step"></a>다음 단계 

다음 8가지 작업 가이드는 완료해야 하는 순서대로 나열되어 있습니다. 

1.  [차원 기반 제품 마스터 만들기](tasks/create-dimension-based-product-master.md)
2.  [치수 기반 제품 마스터 릴리스](tasks/release-dimension-based-product-master.md)
3.  [출시된 제품 기준의 기본 설정 완료](tasks/complete-basic-setup-released-product-master.md)
4.  [구성 그룹 정의](tasks/define-configuration-groups.md)
5.  [치수 기반 제품 기준에 대한 자재 명세서 생성](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [구성 경로 정의](tasks/define-configuration-route.md)
7.  [구성 규칙 만들기](tasks/create-configuration-rules.md)
8.  [차원 기반 구성 생성](tasks/create-dimension-based-configurations.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]