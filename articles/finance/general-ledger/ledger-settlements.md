---
title: 원장 결산
description: 이 항목은 원장 결산 페이지를 사용하여 원장 거래를 결산하고 결산을 취소하는 방법을 설명합니다.
author: kweekley
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-11-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: e98b012210338e7f18cb874eefbc8a023aa4428b
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8451516"
---
# <a name="ledger-settlements"></a>원장 결산

[!include [banner](../includes/banner.md)]

원장 결산은 총계정원장에서 출금 및 입금 거래를 일치시키는 프로세스입니다. 출금 및 입금 금액 결산은 원장 계정의 잔액을 해당 잔액을 구성하는 세부 거래와 조정하는 데 사용됩니다.

결산된 거래는 문의 및 신고에서 제외될 수 있습니다. 이렇게 하면 원장 계정의 잔액을 구성하는 미결 원장 거래를 더 쉽게 분석할 수 있습니다.

> [!IMPORTANT] 
> 지급 계정(AP) 및 수취 계정(AR) 모듈에도 송장 및 지불 결산 기능이 있습니다. AR 및 AP 보조원장에서 결산이 발생하면 해당 원장 항목이 자동으로 결산되지 않습니다.

## <a name="ledger-settlement-features"></a>원장 결산 기능
Microsoft Dynamics 365 Finance 버전 10.0.21에서는 **총계정원장 매개 변수** 페이지의 **고급 원장 결산 활성화** 옵션이 제거되었습니다. 이제 고급 원장 결산은 항상 활성화됩니다.
Finance 버전 10.0.25에서는 **원장 결산과 연말 마감 사이의 인식** 기능이 도입되었습니다. 이 기능은 원장 결산과 총계정원장 연말 마감의 기본 기능을 변경합니다. **기능 관리** 작업 영역에서 이 기능을 활성화하기 전에 [원장 결산과 연말 마감 사이의 인식](awareness-between-ledger-settlement-year-end-close.md)을 참조하세요.

## <a name="set-up-ledger-settlement"></a>원장 결산 설정
원장 결산을 하려는 주 계정을 선택해야 합니다. 이러한 주 계정을 선택하는 방법에는 두 가지가 있습니다.

1. **총계정원장**  >  **원장 설정**  >  **총계정원장 매개 변수** 로 이동합니다.
2. **원장 결산** 탭에서 주 계정을 선택하려는 계정 차트를 선택합니다.
3. 원장 결산을 하려는 주 계정을 선택합니다. 계정 차트는 전역이기 때문에 선택한 계정 차트가 할당된 모든 회사에는 원장 결산을 위해 같은 주 계정이 선택됩니다.

  -또는-

1. **총계정원장** > **정기 작업** > **원장 결산** 으로 이동합니다.
2. **원장 결산 계정** 을 선택합니다.
3. 대화 상자에서 원장 결산을 수행할 계정 차트 및 주 계정을 선택합니다. 이 대화 상자는 바로 가기입니다. 여기에 추가하는 모든 주 계정은 **총계정원장 매개 변수** 페이지에도 반영됩니다.

같은 기본 절차를 사용하여 언제든지 원장 결산에서 주 계정을 제거할 수 있습니다. 주 계정의 제거는 이전 원장 결산에 영향을 미치지 않습니다. 그러나 **원장 결산** 페이지에 더는 주 계정과 거래 내역이 표시되지 않습니다.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>결산 거래
원장 거래를 결산하려면 다음 단계를 따르세요.

1. **총계정원장** > **정기 작업** > **원장 결산** 으로 이동합니다.
2. 페이지 상단에서 필터를 설정합니다.

    - 날짜 범위를 선택합니다. 또는 날짜 간격 코드를 선택하여 날짜 범위를 자동으로 채웁니다. 회계 연도에 걸친 거래에 대해서는 원장 결산을 수행하지 않는 것이 좋습니다.
    - 필요에 따라 기장 계층을 변경합니다. 다른 기장 계층에 있는 거래는 결산할 수 없습니다.
    - 주 계정과 차원을 별도로 표시하려면 재무 차원 집합을 선택합니다.

3. **거래 표시** 를 선택하면 설정한 필터와 일치하는 모든 거래와 이전 섹션에서 계정 차트 목록을 설정할 때 지정한 계정 목록이 표시됩니다.

    - 필터 또는 차원 집합을 변경하는 경우 **거래 표시** 를 다시 선택해야 합니다.
    - 개별 주 계정에 대한 거래를 필터링하려면 **원장 계정** 필드에 필터를 사용합니다. 서로 다른 주 계정에 게시되는 거래에 대해서는 원장 결산을 하지 않는 것이 좋습니다.

4. 결산할 라인을 선택합니다. 페이지 상단의 **선택된 금액** 필드의 값이 선택한 라인의 총 금액을 반영하기 위해 증가하거나 감소합니다.
5. 거래 선택을 마쳤으면 **선택한 항목 표시** 를 선택합니다. 선택한 각 거래의 **표시됨** 열에 확인 표시가 나타납니다. 또한 그리드 위의 **표시된 금액** 필드의 값이 표시된 라인의 총 금액을 반영하기 위해 증가하거나 감소합니다.
6. **표시된 금액** 필드의 값이 **0**(영)인 경우 **표시된 거래 결산** 을 선택합니다. 표시된 거래 상태가 **결산됨** 으로 업데이트됩니다.

    > [!IMPORTANT]
    > 활성 법인에 대해 결산됨으로 표시한 모든 거래는 필터를 적용했기 때문에 현재 원장 결산 페이지에 표시되지 않는 경우에도 결산됩니다.

## <a name="make-transactions-easier-to-find"></a>거래를 더 쉽게 찾을 수 있게 표시
**원장 결산** 페이지에는 결산에 필요한 거래를 더 쉽게 볼 수 있는 기능이 포함되어 있습니다.

- **표시됨** 필터를 사용하여 **표시됨** 확인란이 선택되었는지에 따라 거래를 필터링합니다.
- **상태** 필터를 사용하여 상태에 따라 거래를 필터링합니다.
- 금액을 절대값으로 정렬하려면 **절대 금액으로 정렬** 을 선택합니다. 이런 식으로 금액이 같은 출금과 입금을 그룹화할 수 있습니다.

## <a name="reverse-a-settlement"></a>결산 취소
실수로 수행한 결산을 취소할 수 있습니다.

1. [거래 결산](#settle-transactions)의 1~3의 단계를 수행하여 관심이 있는 거래를 표시합니다.
2. **상태** 필터에서 **결산됨** 을 선택합니다.
3. 취소할 라인을 선택합니다.
4. **표시된 거래 취소** 를 선택합니다. 같은 결산 ID를 가진 모든 거래의 상태가 **미결산** 으로 업데이트됩니다.

    > [!IMPORTANT]
    > 같은 결산 ID를 가진 모든 거래는 표시되지 않더라도 취소됩니다. 예를 들어 네 라인이 표시되고 결산되었습니다. 네 라인이 모두 동일한 결산 ID를 갖습니다. 네 라인 중 하나를 선택하고 **표시된 거래 취소** 를 선택하면 네 라인이 모두 취소됩니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
