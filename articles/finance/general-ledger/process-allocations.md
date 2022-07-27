---
title: 프로세스 할당
description: 이 항목에서는 할당, Microsoft Dynamics 365 Finance의 할당 처리 옵션, 예산 계획에서 이를 사용할 수 있는 방법에 대한 정보를 제공합니다. 할당은 여러 원장 계정 조합에 금액을 분배하는 데 사용됩니다. 이는 비용이나 수익을 회계의 올바른 대상에 청구하는 데 도움이 됩니다.
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b79282abd0edf86f1a9f39fd869cf1fab28b9a4
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2021
ms.locfileid: "8451135"
---
# <a name="process-allocations"></a>프로세스 할당

[!include [banner](../includes/banner.md)]

이 항목에서는 할당, 할당 처리 옵션, 예산 계획에서 이를 사용할 수 있는 방법에 대한 정보를 제공합니다. 할당은 여러 원장 계정 조합에 금액을 분배하는 데 사용됩니다. 이는 비용이나 수익을 회계의 올바른 대상에 청구하는 데 도움이 됩니다.

이 프로세스를 지원하는 기능은 다음과 같습니다.

-   회계 분배에서 분할 작업을 사용하거나 재무 차원 기본 템플릿을 문서에 적용하여 거래 금액을 수동으로 할당합니다. 자세한 내용은 [회계 분포](../accounts-payable/accounting-distributions.md)를 참조하십시오.
-   개별 주 계정에 정의된 할당 조건에 따라 트랜잭션 금액을 자동으로 할당합니다. 할당 계정 항목은 회계 항목이 원본 원장 계정으로 정의된 기준을 충족할 때마다 비율 및 대상 원장 계정을 기준으로 각 저널에 대해 생성됩니다. 자세한 내용은 [주 계정 할당 조건](../general-ledger/main-account-allocation-terms.md)을 참조하십시오.
-   원장 할당 규칙에 따라 원장 잔액 또는 고정 금액을 자동으로 할당합니다. 원장 할당 규칙은 할당 저널을 사용하여 정기적으로 처리됩니다. 자세한 내용은 [할당 규칙](../general-ledger/ledger-allocation-rules.md)을 참조하십시오.

###  <a name="allocations-in-budget-planning"></a>예산 계획에서의 할당

원장 할당 규칙은 예산 계획에 사용할 수 있습니다. 예산 계획에서 원장 할당 규칙을 사용할 경우 할당 규칙은 원장에서와 동일한 방식으로 작동하지만 원본 데이터와 대상 데이터는 예산 계획에서 가져옵니다. 예산 계획에 사용할 원장 할당 규칙을 수동으로 선택할 수 있습니다. 또는 워크플로 프로세스의 일부로 실행되는 할당 예약을 사용할 수 있습니다.

> [!NOTE]
> 회사 간 원장 할당 규칙은 예산 계획에 사용할 수 없습니다.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
