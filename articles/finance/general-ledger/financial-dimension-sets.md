---
title: 재무 차원 집합
description: 이 항목에서는 재무 차원 집합에 관해 설명하고 사용을 최적화하기 위한 몇 가지 팁을 제공합니다.
author: yukonpeegs
ms.date: 03/07/2022
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 9274e7f85005ab27d9f2b35fbb0be42e216941c9
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/07/2022
ms.locfileid: "8451747"
---
# <a name="financial-dimension-sets"></a>재무 차원 집합

[!include [banner](../includes/banner.md)]

이 항목에서는 재무 차원 집합에 관해 설명하고 사용을 최적화하기 위한 몇 가지 팁을 제공합니다.

차원 집합은 사용자 정의된 방식으로 총계정원장 데이터를 요약하는 데 사용할 수 있는 재무 차원의 순서가 지정된 목록입니다. 차원 집합의 주요 용도는 시산표를 정의하는 것입니다.

유일한 표준 차원 집합은 주 계정만 포함하는 차원 집합입니다.

**재무 차원 집합** 페이지를 사용하여 재무 차원 집합을 만들고 관리할 수 있습니다.

## <a name="dimension-set-balances"></a>차원 집합 잔액

차원 집합에는 재무 차원에 기반을 두는 잔액이 있을 수 있습니다. 잔액은 총계정원장에 있으며 차원 집합 정의에 기반을 둡니다. 잔액은 총계정원장 데이터에서 요약되며 검색 시(예: 시산표가 생성될 때) 성능을 개선하는 데 도움이 됩니다.

## <a name="create-balances"></a>잔액 생성

현재 잔액이 없는 차원 집합의 잔액을 초기화하려면 **잔액 생성** 버튼을 사용합니다.

> [!NOTE]
> 잔액 업데이트는 모든 총계정원장 게시 작업에 영향을 미치므로 잔액이 있는 차원 집합의 수를 제한하는 것이 좋습니다.

## <a name="update-balances"></a>잔액 업데이트

잔액에 최신 총계정원장 게시 작업을 포함하려면 **잔액 업데이트** 버튼을 사용합니다. 잔액 업데이트는 가벼운 작업입니다. 마지막 업데이트 이후 발생한 총계정원장 게시 작업만 처리해야 합니다.

> [!NOTE]
> 시산표를 표시하면 표시된 잔액이 최신 상태인지 확인하기 위해 업데이트가 강제됩니다. 가장 자주 사용하는 차원 집합을 빠르게 업데이트하려면 정기 일괄 처리를 사용하는 것이 좋습니다. 이렇게 하면 시산표 사용자가 기다려야 하는 시간을 최소화하는 데 도움이 됩니다.

## <a name="rebuild-balances"></a>잔액 재구축

잔액을 처음부터 다시 만들려면 **잔액 재구축** 버튼을 사용합니다. 이렇게 하면 총계정원장의 데이터와 일치하는지 확인할 수 있습니다. 잔액을 재구축하려면 많은 처리가 필요하며 일반적으로 필수가 아닙니다.

> [!NOTE]
> 정기적으로 잔액을 재구축해야 하는 시나리오가 발생하면 고객 지원에 문의하는 것이 좋습니다. 고객 지원을 통해 잔액이 총계정원장의 데이터와 일치하지 않는 이유를 확인할 수 있습니다.

## <a name="clear-balances"></a>잔액 정산

잔액을 제거하고 추가 업데이트를 중지하려면 **잔액 정산** 버튼을 사용합니다. 그러면 차원 집합이 더는 총계정원장 게시 작업에 영향을 미치지 않습니다.

## <a name="delete-a-dimension-set"></a>차원 집합 삭제

특정 차원 집합에 대한 잔액 데이터의 잠재적인 문제를 해결하기 위해 차원 집합을 **삭제하고 다시 생성** 하지 마세요. 차원 집합을 다시 만드는 데는 비용이 많이 듭니다. 문제에 대한 추가 지원을 위해 고객 지원에 문의하세요. 


자세한 내용은 [재무 차원](financial-dimensions.md)을 참조하세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
