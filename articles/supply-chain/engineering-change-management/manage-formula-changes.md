---
title: 수식 및 해당 성분의 변경 사항 관리
description: 이 토픽에서는 수식 관리를 수행하고 제조 마스터 데이터를 처리하기 위한 변경 사항을 관리하는 방법에 대해 설명합니다.
author: t-benebo
ms.date: 05/19/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 31953fd29c471e52bd63dbb02c20f5f224c3cae2
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449944"
---
# <a name="manage-changes-in-formulas-and-their-ingredients"></a>수식 및 해당 성분의 변경 사항 관리

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management의 공정 제조 기능을 사용하는 경우 관련 수식 관리 기능을 사용하여 다음 변경 사항을 관리할 수도 있습니다.

- **수식 및 계획 항목:** 슈식과 그 연산품 및 부산물의 성분에 대한 변경 사항을 관리합니다.
- **연산품 및 부산물:** 수식에서 연산품 및 부산물의 수량 및 기타 정보를 편집합니다.
- **공칭 무게 항목:** 공칭 무게 항목에 대한 변경 사항을 관리합니다.

## <a name="turn-this-feature-on-or-off"></a>이 기능 켜기 또는 끄기

이 토픽에 설명된 기능을 사용하려면 *엔지니어링 변경 관리* 및 *수식 및 해당 성분에 대한 변경 관리* 기능이 모두 시스템에 켜져 있어야 합니다. 이러한 기능을 켜거나 끄는 방법에 대한 자세한 내용은 [엔지니어링 변경 관리 개요](product-engineering-overview.md)를 참조하세요.

## <a name="feature-naming-conventions"></a>기능 명명 규칙

Supply Chain Management UI(사용자 인터페이스) 및 문서에서 변경 관리 기능은 일반적으로 *엔지니어링 변경 관리* 라고 하고 관리 가능한 제품은 일반적으로 *엔지니어링 제품* 이라고 합니다. 이 용어는 일반적으로 프로세스 제조 수식 관리와 관련이 없지만 엔지니어링 변경 관리는 단순한 변경 관리로 생각해야 하며 엔지니어링 제품은 버전이 지정된 제품으로 생각해야 합니다.

## <a name="work-with-formula-change-management-features"></a>수식 변경 관리 기능으로 작업

다음 목록에는 엔지니어링 변경 관리 기능이 수식 관리에 적용되는 방식이 요약되어 있습니다. 또한 추가 정보에 대한 링크를 제공합니다. 수식 변경 관리는 엔지니어링 변경 관리 기능을 활용하기 때문에 수식과 그 성분을 관리하는 데 사용할 수 있도록 엔지니어링 변경 관리가 일반적으로 어떻게 작동하는지 알아야 합니다.

- **중앙 집중식 제품 데이터 관리** – 관리되는 릴리스 프로세스를 통해 기업 전체의 사용자가 정확하고 관련성이 높은 제품 데이터를 사용할 수 있도록 하는 조직을 설정합니다. 자세한 내용은 [엔지니어링 회사 및 데이터 소유권 규칙](engineering-org-data-ownership-rules.md)을 참조하세요.
- **제품 버전 관리** – 제품 버전을 통해 제품의 변경 사항을 추적하고 공급망의 모든 단계에서 제품을 제어합니다. 이러한 방식으로 수식의 변경 사항을 추적할 수 있습니다. 자세한 내용은 [엔지니어링 버전 및 엔지니어링 제품 범주](engineering-versions-product-category.md)를 참조하세요.
- **제품 수명 주기 관리** – 조직 전체에서 제품 데이터의 가시성을 관리하고 공급망의 각 단계에서 제품 버전의 가용성을 제어합니다. 특정 비즈니스 프로세스에서 제품 버전을 사용할 수 있는 경우를 세부적으로 제어할 수 있으며 비즈니스 요구 사항에 맞게 고유한 수명 주기 상태를 생성할 수 있습니다. 자세한 내용은 [제품 수명 주기 상태 및 트랜잭션](product-lifecycle-state-transactions.md)을 참조하세요.
- **수식 변경 관리** – 조직 전체의 사용자가 수식 변경을 요청할 수 있습니다. 변경 주문을 사용하여 제안된 변경의 영향을 평가하고 문서화합니다. 변경 프로세스와 제품 및 해당 수식의 새 버전 릴리스를 관리하는 워크플로를 추가합니다. 자세한 내용은 [엔지니어링 제품의 변경 사항 관리](engineering-change-management.md)를 참조하세요.
- **준비 상태 제어** – 시스템 확인 및 사용자 지침(질문지 및 체크리스트)을 사용하여 제품이 출시되기 전에 필요한 모든 제품 데이터가 완전히 입력되었는지 확인합니다. 자세한 내용은 [제품 준비](product-readiness.md)를 참조하세요.
- **향상된 제품 출시 기능** – 완전히 정의된 버전의 제품 및 수식을 조직(법인)에서 다른 법인으로 출시합니다. 출시 전에 제품 정보를 검토하거나 편집해야 하는지 여부도 결정할 수 있습니다. 자세한 내용은 [릴리스 제품 구조](release-product-structure.md)를 참조하세요.

이전 목록에 링크된 대부분의 항목은 BOM(자재 명세서)을 기반으로 하는 예를 제공합니다. 그러나 수식은 비슷한 방식으로 작동합니다. 다음은 변경 관리(또는 수식 변경 관리만)를 사용하여 수식과 BOM을 관리할 때 알아두면 유용한 몇 가지 추가 개념입니다.

- 각 [제품 엔지니어링 범주](engineering-versions-product-category.md)에 대해 생산 유형(BOM, 수식 또는 계획 품목)을 지정할 수 있습니다. 해당 카테고리를 사용하는 제품에 캐치-웨이트 지원이 필요한지 여부도 지정할 수 있습니다.
- 연산품과 부산물은 엔지니어링 제품이 아닙니다. 따라서 버전이 지정되지 않습니다. 변경해야 하는 경우 새 제품을 만드세요. 이 접근 방식을 사용하면 유지 관리가 더 쉬워집니다.
- BOM이고 하위 수식 품목이 있는 최종 품목을 관리할 수 있습니다. 이 기능은 수식을 포함하는 BOM 및/또는 BOM이 포함된 수식의 모든 조합에 대해 작동합니다.
