---
title: 제품 구성을 위한 솔버 전략
description: 이 토픽에서는 솔버 전략을 사용하여 제품 구성의 성능을 향상시키는 방법에 대해 설명합니다.
author: t-benebo
ms.date: 02/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCCreateProductConfigurationModel, PCProductConfigurationModelListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 37e8f2c9557ee6fc827d60ca6dc83cd638b6378a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447850"
---
# <a name="solver-strategy-for-product-configuration"></a>제품 구성을 위한 솔버 전략

[!include [banner](../includes/banner.md)]

이 토픽에서는 솔버 전략을 사용하여 제품 구성의 성능을 향상시키는 방법에 대해 설명합니다.

솔버 전략의 개념은 Microsoft Dynamics AX 2012 R2용 누적 업데이트 7(CU7)에서 처음 도입되었습니다. Microsoft Dynamics AX 2012 R3 및 Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3의 누적 업데이트 8(CU8)에서 확장되었습니다.

이제 솔버 전략 개념은 다음 전략으로 구성됩니다.

- 기본
- 최소 도메인 먼저
- 위에서 아래로
- Z3

## <a name="solver-strategy"></a>솔버 전략 

제품 구성 모델은 [제약 조건 만족 문제(CSP)](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)로 공식화될 수 있습니다. Microsoft Solver Foundation(MSF)은 제품 구성 모델에서 사용할 수 있는 CSP를 해결하기 위해 두 가지 유형의 솔버 전략을 제공합니다. 이러한 솔버 전략은 문제가 해결될 때 CSP의 변수가 고려되는 순서를 결정하는 데 사용되는 [휴리스틱](https://techterms.com/definition/heuristic)에 의존합니다. 휴리스틱은 문제 또는 문제 클래스가 해결될 때 성능에 상당한 영향을 미칠 수 있습니다.

제품 구성 모델에 대한 솔버 전략은 휴리스틱과 함께 사용되는 솔버를 결정합니다. **기본**, **최소 도메인 우선** 및 **하향식** 전략은 MSF의 두 솔버를 사용하는 반면 **Z3** 전략은 Z3 솔버를 사용합니다. 

실제 고객 구현 연구에 따르면 제품 구성 모델에 대한 솔버 전략을 변경하면 응답 시간을 몇 분에서 밀리초로 줄일 수 있습니다. 따라서 제품 구성 모델에 가장 효율적인 전략을 찾기 위해 다양한 솔버 전략을 시도해 볼 가치가 있습니다.

## <a name="change-the-settings-for-the-solver-strategy"></a>솔버 전략에 대한 설정 변경

솔버 전략을 변경하려면 **제품 구성 모델** 페이지의 작업 창에서 **모델 속성** 을 선택합니다. 그런 다음 **모델 세부 정보 편집** 대화 상자에서 솔버 전략을 선택합니다.

[![솔버 전략을 변경합니다.](./media/solver-strategy.png)](./media/solver-strategy.png)

현재, 어떤 솔버 전략이 제약 기반 제품 구성에 가장 효율적인 전략인지 자동으로 감지하는 로직은 없습니다. 따라서 솔버 전략을 하나씩 시도해야 합니다.

다음 표는 다양한 시나리오에서 사용할 솔버 전략에 대한 권장 사항을 제공합니다.

| 솔버 전략      | 이 시나리오에서 전략 사용 |
|----------------------|-----------------------------------|
| 기본              | **기본** 전략은 테이블 제약 조건에 의존하는 모델을 해결하도록 최적화되었습니다. 고객 구현 연구에 따르면 이 전략은 테이블 제약 조건이 광범위하게 사용되는 시나리오에서 가장 효율적인 전략입니다. |
| 최소 도메인 먼저 | **최소 도메인 우선** 전략과 **하향식** 전략은 밀접하게 관련되어 있습니다. 고객 구현 연구에 따르면 **하향식** 전략이 **최소 도메인 우선** 전략을 능가하는 것으로 나타났습니다. 그러나 **최소 도메인 우선** 전략은 이전 버전과의 호환성을 위해 제품에 유지됩니다. 이러한 솔버 전략은 모두 테이블 제약 조건이 사용되지 않는 여러 산술 표현식을 포함하는 모델을 풀 때 더 효율적인 것으로 나타났습니다. 그러나 어떤 경우에는 **기본** 전략은 이 두 가지 전략을 능가합니다. 따라서 각 전략을 시도하는 것을 잊지 마세요. |
| 위에서 아래로             | **최소 도메인 우선** 전략과 **하향식** 전략은 밀접하게 관련되어 있습니다. 고객 구현 연구에 따르면 **하향식** 전략이 **최소 도메인 우선** 전략을 능가하는 것으로 나타났습니다. 그러나 **최소 도메인 우선** 전략은 이전 버전과의 호환성을 위해 제품에 유지됩니다. 이러한 솔버 전략은 모두 테이블 제약 조건이 사용되지 않는 여러 산술 표현식을 포함하는 모델을 풀 때 더 효율적인 것으로 나타났습니다. 그러나 어떤 경우에는 **기본** 전략은 이 두 가지 전략을 능가합니다. 따라서 각 전략을 시도하는 것을 잊지 마세요. |
| Z3                   | **Z3** 전략을 기본 솔버 전략으로 사용하는 것이 좋습니다. 성능과 확장성이 걱정된다면 다른 전략을 평가할 수 있습니다. |

## <a name="additional-resources"></a>추가 리소스

[제품 구성 개요](build-product-configuration-model.md)

[휴리스틱](https://techterms.com/definition/heuristic)

[제약 조건 만족 문제](http://aima.cs.berkeley.edu/2nd-ed/newchap05.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]