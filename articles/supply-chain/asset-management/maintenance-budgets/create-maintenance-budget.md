---
title: 유지 관리 예산 만들기
description: 이 토픽에서는 자산 관리에서 유지 관리 예산을 만드는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a375eb7c208479615b2d5e7cf78168ffd7ac8b16c52c85a7ef5a41aa69c947d5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447280"
---
# <a name="create-maintenance-budgets"></a>유지 관리 예산 만들기

[!include [banner](../../includes/banner.md)]

 



유지 관리 예산은 예방적 유지 관리에 대한 예상 비용의 개요를 제공하는 데 사용됩니다. 예산 라인은 예산 기간 동안 예상 시작 날짜가 있는 유지 관리 일정 라인을 기반으로 계산됩니다.

유지 관리 예산은 자산 관리에서 사용되는 비용 유형을 기반으로 합니다. **예방**, **시정** 및 **투자**. 투자 유지를 위한 예산 비용은 예산 기간 중 교체 날짜와 관련 교체 가치가 있는 활성 자산에 포함됩니다. 예산 산정에 과거 정정일이 포함된 경우에는 수정 유지비를 포함합니다. 이 경우 유지 관리 예산을 계산하는 동일한 미래 기간에 대해 이전 기간의 수정 비용이 계산됩니다.

## <a name="create-a-maintenance-budget"></a>유지 관리 예산 만들기

1. **자산 관리** \> **문의** \> **유지 관리 예산** \> **예산** 을 선택합니다.
2. **예산 만들기** 를 선택합니다.
3. **유지 관리 예산** 필드에 예산 ID를 입력합니다.
4. **설명** 필드에 설명을 입력합니다.
4. **기간** 빠른 탭의 **시작 날짜** 및 **종료 날짜** 필드에서 예산 기간의 시작 날짜와 종료 날짜를 입력합니다.
5. 이전 기간의 실제 비용을 기준으로 계산된 수정 예산 비용을 포함하려면 **시정 시작 날짜** 필드에 해당 비용이 포함되어야 하는 기간의 시작 날짜를 입력합니다.
6. 예산에 필요한 세부 사항 수준에 따라 5개의 **그룹화 기준** 빠른 탭에서 관련 옵션을 설정합니다.
7. **확인** 을 선택합니다.
8. **예산 라인** 을 선택하여 **유지 관리 예산 라인** 페이지를 열면 해당 기간 동안 생성된 모든 예산 라인을 볼 수 있습니다.
9. 예산을 승인하려면 **유지 관리 예산** 페이지에서 예산을 선택한 다음 **승인** 을 선택합니다. 그런 다음 **예산 승인** 대화 상자에서 **확인** 을 선택합니다. 사용자의 이름은 **유지 관리 예산** 페이지의 **승인자** 필드에 입력됩니다.

    > [!NOTE]
    > 유지 관리 예산을 승인한 후에는 승인을 먼저 제거하지 않는 한 **유지 관리 예산 라인** 페이지에서 관련 라인을 다시 계산하거나 조정할 수 없습니다. 유지 관리 예산의 승인을 제거하려면 **유지 관리 예산** 페이지에서 예산을 선택한 다음 **승인** 을 선택합니다. 그런 다음 **예산 승인** 대화 상자에서 **확인** 을 선택합니다.

![유지 관리 예산.](media/01-maintenance-budgets.png)

기존 예산을 복사하여 새 유지 관리 예산을 만들 수도 있습니다. **유지 관리 예산** 페이지에서 복사할 예산을 선택한 다음 **복사** 를 선택합니다. 이 접근 방식은 예를 들어 한 달에 대한 예산을 만들고 다른 달에 복사하려는 경우에 유용합니다.

> [!NOTE]
> 유지 관리 예산은 유지 관리 일정 라인을 기준으로 예산 비용만 계산합니다. 같은 기간에 대한 실제 비용을 계산하려면 **자산 비용 컨트롤** 페이지에서 해당 계산을 수행할 수 있습니다. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]