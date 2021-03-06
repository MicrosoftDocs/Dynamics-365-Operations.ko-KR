---
title: 연기 허용 범위(음수일)
description: 이 토픽에서는 연기 허용 범위 계산 및 계획 최적화에서 계획 주문 생성에 미치는 영향에 대한 정보를 제공합니다.
author: ChristianRytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ccf827983694eab2037c73aa3251846b051e66f1
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/25/2021
ms.locfileid: "8449398"
---
# <a name="delay-tolerance-negative-days"></a>연기 허용 범위(음수일)

[!include [banner](../../includes/banner.md)]

연기 허용 범위 기능을 사용하면 계획 최적화가 적용 범위 그룹에 대해 설정된 **음수 일수** 값을 고려할 수 있습니다. 기준 계획 수립 시 적용되는 연기 허용 범위를 연장하기 위해 사용합니다. 이러한 방식으로 기존 공급이 짧은 연기 후에 수요를 충족할 수 있는 경우 새로운 공급 주문을 생성하는 것을 피할 수 있습니다. 기능의 목적은 주어진 수요에 대해 새로운 공급 주문을 생성하는 것이 타당한지 여부를 결정하는 것입니다.

## <a name="turn-on-the-feature-in-your-system"></a>시스템에 기능 사용 설정

시스템에서 연기 허용 범위 기능을 사용 가능하게 하려면 [기능 관리](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)로 이동하여 *계획 최적화 기능에 대한 음수 일수* 를 켭니다.

## <a name="delay-tolerance-in-planning-optimization"></a>계획 최적화의 연기 허용 범위

연기 허용 범위는 기존 공급이 이미 계획된 경우 새로운 보충을 주문하기 전에 기꺼이 기다릴 수 있는 리드 타임 이후의 일 수를 나타냅니다. 연기 허용 범위는 영업일이 아닌 달력 날짜를 사용하여 정의됩니다.

기준 계획 수립 시 연기 허용 범위를 계산할 때 **음수 일수** 설정을 고려합니다. **적용 범위 그룹** 페이지 또는 **항목 적용 범위** 페이지에서 **음수 일수** 값을 설정할 수 있습니다.

시스템은 연기 허용 범위 계산을 *가장 빠른 보충 일자* 에 연결합니다. 이는 오늘 일자에 리드 타임을 더한 것과 같습니다. 연기 허용 범위는 다음 공식을 사용하여 계산됩니다. 여기서 *max()* 는 두 값 중 큰 값을 찾습니다.

*max(가장 빠른 보충 일자, 요구 납기 일자)* – *요구 납기 일자* + *음수 일수*

이 공식은 제품 리드 타임 동안 충분한 공급이 있을 때 기준 계획이 새로운 공급 주문을 생성하지 않도록 합니다.

> [!NOTE]
> 계획 최적화의 연기 허용 범위 계산은 항상 기본 제공 기준 계획의 동적 음수 일수 계산을 사용합니다. **기준 계획 매개 변수** 페이지의 **동적 음수 날짜 사용** 설정은 이 동작에 영향을 주지 않습니다.

기존 공급이 계산된 연기 허용 범위보다 작거나 같은 수요 연기를 의미하는 경우 계획 최적화는 기존 공급을 수요와 페깅합니다. 어떤 경우에는 공급 과잉으로 끝나는 것보다 수요를 연기시키는 것이 더 낫습니다.

다음 하위 섹션에서는 연기 허용 범위가 계획 최적화에서 계획 주문 생성에 미치는 영향을 보여주는 예를 제공합니다.

### <a name="example-1"></a>예시 1

제품의 구성은 다음과 같습니다.

- **리드 타임:** *10*
- **음수 일수:** *2*

제품에 대한 수요와 공급은 다음과 같습니다.

- **오늘의 수요:** 수량 10개에 대한 판매 주문
- **12일 이내 공급:** 10개 구매 주문

기존 공급은 12일 이내에 수요를 충족할 수 있으며 그 기간은 연기 허용 범위와 같습니다. 따라서 기준 계획이 실행될 때 계획 주문이 생성되지 않습니다.

### <a name="example-2"></a>예시 2

제품의 구성은 다음과 같습니다.

- **리드 타임:** *10*
- **음수 일수:** *0*

제품에 대한 수요와 공급은 다음과 같습니다.

- **오늘의 수요:** 수량 10개에 대한 판매 주문
- **12일 이내 공급:** 10개 구매 주문

기존 공급은 12일 후에만 수요를 충족할 수 있습니다. 그러나 연기 허용 범위는 10일입니다. 따라서 기준 계획이 실행되면 수량 10개에 대한 계획 주문이 생성됩니다.

### <a name="example-3"></a>예시 3

제품의 구성은 다음과 같습니다.

- **리드 타임:** *10*
- **음수 일수:** *2*

제품에 대한 수요와 공급은 다음과 같습니다.

- **11일 이내 수요:** 수량 10개에 대한 판매 주문
- **14일 이내 공급:** 10개 구매 주문

기존 공급은 3일 후에만 수요를 충족할 수 있습니다. 그러나 연기 허용 범위는 2일입니다. (이 경우 연기 허용 범위에는 음수 2일만 포함됩니다. 제품 리드 타임 이후이기 때문에 수요 일자는 포함되지 않습니다. 따라서 기준 계획이 실행될 때 수량 10개에 대한 계획 주문이 생성됩니다.
