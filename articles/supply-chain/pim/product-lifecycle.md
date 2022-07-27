---
title: 제품 수명 주기 상태 개요
description: 제품 수명 주기 상태는 출시된 제품 또는 제품 변형의 수명 주기 상태를 문서화합니다.
author: t-benebo
ms.date: 01/06/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: f71ce701adbe60b69b25e41810dda7adeec1d390
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449716"
---
# <a name="product-lifecycle-state-overview"></a>제품 수명 주기 상태 개요

[!include [banner](../includes/banner.md)]

제품 수명 주기 상태는 출시된 제품 또는 제품 변형의 수명 주기 상태를 문서화합니다. 제품 수명 주기 상태는 일반적으로 제품 관리자 또는 제품 마스터 데이터 관리자인 사용자가 정의합니다. 기준 계획과 같은 특정 비즈니스 프로세스는 특정 수명 주기 상태의 영향을 받을 수 있습니다.

릴리스된 제품 또는 제품 변형은 특정 제품 또는 변형이 현재 있는 수명 주기 상태를 문서화하는 제품 수명 주기 상태와 연관될 수 있습니다. 상태 이름 및 설명을 할당하여 제품 수명 주기 상태를 원하는 수만큼 정의할 수 있습니다. 하나의 수명 주기 상태를 새로 릴리스된 제품의 기본 상태로 선택할 수 있습니다. 출시된 제품 변형은 생성 시 출시된 제품 마스터에서 제품 수명 주기 상태를 상속합니다. 출시된 제품 마스터에서 수명 주기 상태를 변경할 때 원래 상태가 동일한 모든 기존 변형을 업데이트하도록 선택할 수 있습니다.  

## <a name="create-a-new-product-lifecycle-state"></a>새 제품 수명 주기 상태 생성

- 새 제품 수명 주기 상태를 만들려면 [새 제품 수명 주기 상태 만들기](tasks/new-product-lifecycle-state.md)를 참조하세요.

- 기본 제품 수명 주기 상태를 만들려면 [기본 제품 수명 주기 상태 만들기](tasks/default-product-lifecycle-state.md)를 참조하세요.

## <a name="associate-product-lifecycle-states-to-released-products"></a>출시된 제품에 제품 수명 주기 상태 연결  

제품 수명 주기 상태를 릴리스된 제품 또는 제품 변형에 연결하는 방법에는 여러 가지가 있습니다.

- 새로 출시된 제품을 만들 때 기본 **제품 수명 주기 상태** 가 자동으로 할당됩니다.
- 법인에 제품을 릴리스하면 기본 **제품 수명 주기 상태** 가 자동으로 할당됩니다.
- 법인에 제품 변형을 릴리스하면 이 법인에서 출시된 제품 마스터와 연결된 **제품 수명 주기 상태** 가 새 변형에 자동으로 할당됩니다.

다음을 사용하여 제품 수명 주기 상태를 수동으로 업데이트할 수 있습니다.

- **릴리스된 제품** 목록 페이지 또는 **세부정보 보기**.
- **출시된 제품 변형** 목록 페이지 또는 **세부정보 보기**.
- 수요를 기반으로 더 이상 사용되지 않는 제품 또는 제품 변형을 찾고 수명 주기 상태를 연결합니다.  

자세한 내용:

- 제품 수명 주기 상태를 출시된 제품 마스터에 연결하려면 [출시된 제품 마스터에 제품 수명 주기 상태 할당](tasks/product-lifecycle-state-released-product-master.md)을 참조하세요.

- 제품 수명 주기 상태를 릴리스 제품에 연결하려면 [출시된 제품 마스터에 제품 수명 주기 상태 할당](tasks/product-lifecycle-state-released-product.md)을 참조하세요.

## <a name="impact-on-master-planning"></a>기준 계획에 미치는 영향

제품 수명 주기 상태에는 다음의 하나의 제어 플래그만 있습니다. **계획에 대해 활성**. 기본적으로 이것은 생성된 모든 제품 수명 주기 상태에 대해 **예** 로 설정되지만 **아니요** 로 변경할 수 있습니다. **아니요** 로 설정하면 관련 출시 제품 또는 출시 제품 변형은 다음과 같습니다.

- 기준 계획에서 제외됩니다.
- BOM 수준 계산에서 제외됩니다.

제품 수명 주기 상태를 사용하여 기준 계획 및 BOM 수준 계산에서 제품을 제외하는 방법에 대한 자세한 내용은 [기준 계획에서 제품을 제외하도록 제품 수명 주기 상태 만들기](tasks/exclude-products-master-planning.md)를 참조하세요.

> [!NOTE]
> 성능상의 이유로, 특히 재사용할 수 없는 제품 구성 변형으로 작업하는 경우 더 이상 사용되지 않는 릴리스된 모든 제품 또는 제품 변형을 기준 계획을 위해 비활성화된 제품 수명 주기 상태와 연결하는 것이 좋습니다.  

## <a name="default-migration-import-and-export"></a>기본 마이그레이션, 가져오기 및 내보내기

제품 수명 주기 상태는 데이터 엔터티에서 지원되며 수명 주기 상태는 릴리스된 제품 데이터 엔터티 또는 출시된 변형 데이터 엔터티를 통해 가변 상태로 설정할 수 있습니다.

## <a name="find-obsolete-products-and-products-variants"></a>더 이상 사용되지 않는 제품 및 제품 변형 찾기

시뮬레이션 분석을 실행하여 더 이상 사용되지 않는 릴리스된 제품 또는 제품 변형을 찾은 다음 해당 제품 수명 주기 상태를 업데이트할 수 있습니다. 더 이상 사용되지 않는 제품을 찾으려면 [더 이상 사용되지 않는 제품 변형 찾기 및 제품 수명 주기 상태 할당](tasks/obsolete-product-variants.md)을 참조하세요. 이 항목에서는 사용되지 않는 출시 제품 또는 제품 변형을 찾는 방법과 제품 수명 주기 상태를 사용되지 않는 제품에 연결하는 방법을 보여줍니다. 또한 시뮬레이션 없이 업데이트를 실행할 때 시뮬레이션 결과를 보는 방법을 보여주며 얼마나 많은 제품 및 제품 변형이 새 제품 수명 주기 상태와 연관될 것인지 평가합니다.  

시뮬레이션 모드에서 분석을 실행하면 더 이상 사용되지 않는 것으로 식별된 제품 및 제품 변형이 특정 형식으로 표시되어 쉽게 검토할 수 있습니다. 분석은 거래 및 특정 마스터 데이터를 검색하여 변동 기간 내에 수요가 없고 수요를 유발할 수 있는 마스터 데이터가 없는 제품을 식별합니다. 변동 기간 내에 새로 릴리스된 제품은 분석에서 제외될 수 있습니다. 분석 시뮬레이션이 예상 결과를 반환하면 사용자는 분석을 실행하고 분석에서 더 이상 사용되지 않는 것으로 식별된 모든 제품에 대해 새 제품 수명 주기 상태를 설정할 수 있습니다.  

> [!NOTE]
> 모든 분석 및 업데이트는 동일한 법인 내에서 이루어져야 합니다.  

## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a>출시된 제품 또는 제품 변형을 선택하고 업데이트하는 기준

다음 기준을 사용하여 출시된 제품 및 제품 변형을 선택하고 업데이트합니다.

- 제품 또는 제품 변형의 제품 수명 주기 상태는 원하는 새 상태와 달라야 합니다.
- 제품 또는 제품 변형은 선택 대화 상자에 입력한 일 수를 기반으로 며칠 전에 생성되었습니다.
- 제품 또는 제품 변형에 대해 진행 중인 생산 주문(= 상태 < 종료됨)이 없습니다.
- 제품 또는 제품 변형에 대해 진행중인 재고 거래(= 상태 발행 ReservPhysical to QuotationIssue 또는 상태 영수증 QuotationReceipt에 등록됨)이 없습니다.
- 제품 또는 제품 변형에 대한 지난 일수 내에 재고 거래가 없습니다.
- 제품 또는 제품 변형에 대한 미래 수요 또는 공급 예측이 없습니다.  
- 제품 또는 제품 변형에 대한 항목 적용 범위에 최소 재고 수준이 설정되지 않았습니다.
- 제품 또는 제품 변형에 대한 활성 고정 수량 칸반 규칙이 없습니다.  
- 제품 또는 제품 변형에 대한 서비스 주문 라인이 없습니다.
- 제품 또는 제품 변형에 대한 활성 또는 미래 판매 또는 구매 계약 라인이 없습니다.
- 제품 또는 제품 변형이 계획을 위해 활성 상태인 제품 또는 변형에 대해 만료되지 않은 승인된 BOM 버전과 연결된 BOM에서 사용되지 않습니다.

## <a name="related-topics"></a>관련 토픽

- [새 제품 수명 주기 상태 생성](tasks/new-product-lifecycle-state.md)
- [기본 제품 수명 주기 상태 생성](tasks/default-product-lifecycle-state.md)
- [출시된 제품 마스터에 제품 수명 주기 상태 할당](tasks/product-lifecycle-state-released-product-master.md)
- [출시된 제품에 제품 수명 주기 상태 할당](tasks/product-lifecycle-state-released-product.md)
- [사용되지 않는 제품 변형 찾기 및 제품 수명 주기 상태 할당](tasks/obsolete-product-variants.md)
- [기준 계획에서 제품을 제외하는 제품 수명 주기 상태 생성](tasks/exclude-products-master-planning.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]