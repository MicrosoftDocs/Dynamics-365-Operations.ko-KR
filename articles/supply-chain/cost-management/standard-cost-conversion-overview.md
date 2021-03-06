---
title: 표준 비용 변환 개요
description: 이 문서에서는 표준 비용 변환을 설정하고 실행하는 데 도움이 되는 프로세스 개요를 제공합니다. 나열된 단계는 표준 비용 변환을 위한 전제 조건을 완료한 후 완료하기 위한 것입니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "78212"
- intro-internal
ms.assetid: d601d9d5-1de3-4868-aff4-534dca01d624
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9796449bee4361b2b871af10d30341c2f0760ab1
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449662"
---
# <a name="standard-cost-conversion-overview"></a>표준 비용 변환 개요

[!include [banner](../includes/banner.md)]

이 문서에서는 표준 비용 변환을 설정하고 실행하는 데 도움이 되는 프로세스 개요를 제공합니다. 나열된 단계는 표준 비용 변환을 위한 전제 조건을 완료한 후 완료하기 위한 것입니다. 

**표준 비용 변환** 페이지를 사용하여 선택한 항목 배치에 대한 인벤토리 모델을 실제 원가 계산 방식에서 표준 원가 계산 방식으로 변환합니다. 변환 프로세스에는 전제 조건 인벤토리 마감, 전환 시작 날짜 및 계획된 전환 날짜로 정의되는 전환 기간 동안의 여러 단계, 전환 및 관련 인벤토리 마감이 포함됩니다.

-   전환 기간 전 인벤토리 마감 – 인벤토리 마감은 이전 평가 방법을 사용하여 항목의 미결 거래를 정산하기 때문에 전제 단계를 나타냅니다. 전환 기간 동안 송장과 같은 소급 거래를 입력하고 전기하여 이전 기간을 마감할 수 있습니다. 인벤토리 마감 날짜는 이전 평가 방법에서 완전히 벗어나도록 전환 시작 날짜보다 하루 전이어야 합니다.
-   전환 기간 중 전환 단계 – **표준 비용 전환** 페이지를 사용하여 새 원가 계산 버전에 대한 사용자 정의 식별자도 포함하는 전환 레코드를 생성합니다. 변환이 필요한 항목을 식별한 다음 새 원가계산 버전에서 항목의 보류 중인 표준 원가를 입력합니다. 선택한 항목을 확인하여 변환을 방해할 수 있는 문제를 식별하고 문제를 해결한 다음 다른 확인을 수행합니다. 항목이 검사를 성공적으로 통과한 후 변환 레코드의 상태를 **준비** 로 변경합니다. 계획된 변환 일자에 변환을 수행하고 선택적으로 인벤토리 마감을 포함합니다. 전환 기간 동안 항목의 인벤토리 이동은 이전 인벤토리 모델에 따라 전기되고 평가됩니다. 그런 다음 변환이 성공적으로 완료된 후 인벤토리 이동은 표준 비용으로 재평가됩니다.
-   전환 전 인벤토리 마감 – 인벤토리 마감은 계획된 전환 날짜에 전환의 일부로 포함되거나 전환 전 별도의 단계로 수행될 수 있습니다.

변환 프로세스가 성공적으로 완료된 후 각 품목에 대한 인벤토리 모델은 표준 비용을 기반으로 하며 품목의 표준 비용이 활성화됩니다. 후속 인벤토리 거래는 품목의 표준 비용으로 평가됩니다. 또한 시스템은 입고 및 출고에 대한 품목의 총실사 트랜잭션을 변환 일자를 기준으로 표준 원가로 변환합니다. 시스템은 또한 품목의 재무 현인벤토리를 표준 원가로 변환하고 가치의 차이를 인벤토리 재평가로 전기합니다. 변환 후에 발생하는 모든 거래는 항목의 표준 비용으로 평가됩니다. 인벤토리 마감은 전환일 하루 전에 수행되어야 하기 때문에 전환일 이전에는 소급 거래를 입력할 수 없습니다. 인벤토리 마감이 하루 전에 수행된 경우에만 전환을 수행할 수 있습니다. 이 인벤토리 마감은 취소할 수 없습니다.

## <a name="1-define-a-standard-cost-conversion-record-and-the-associated-costing-version"></a>1. 표준 원가 변환 레코드 및 관련 원가 계산 버전 정의
**표준 비용 변환** 페이지를 사용하여 변환 레코드를 생성합니다. 기존 전환 기록이 완료된 경우에만 새 전환 기록을 생성할 수 있습니다. 계획된 전환 기간의 기간은 전환 시작 날짜와 계획된 전환 날짜로 정의됩니다. 계획된 전환 기간은 하루만큼 짧을 수 있습니다. 계획된 전환 기간은 변환 프로세스가 모든 단계를 완료할 수 있는 충분한 시간을 갖도록 하는 데 도움이 됩니다. 전환 프로세스를 시작하기 전에 결제가 완료되도록 하려면 전환 시작 날짜 하루 전 날짜에 인벤토리 마감을 수행해야 합니다. 전환 시작 날짜와 인벤토리 마감 날짜가 올바르게 정렬되었는지 확인하기 위해 전환 시작 날짜를 기존 인벤토리 마감 후 하루로 변경하거나 인벤토리 마감을 수행할 수 있습니다. 변환 레코드를 입력할 때 변환된 항목에 대한 표준 비용을 포함할 새 원가 계산 버전에 대한 사용자 정의 식별자도 입력합니다. 전환 기록을 저장할 때 비용 계산 버전이 자동으로 생성됩니다.

## <a name="2-review-and-change-the-new-costing-version-for-the-conversion-record"></a>2. 전환 기록에 대한 새로운 원가계산 버전 검토 및 변경
**전환** 원가 계산 유형에서 알 수 있듯이 새 원가 계산 버전은 전환 기록 전용입니다. 전용 원가계산 버전은 표준 원가에 대한 원가계산 버전과 유사하며 변환 레코드와 연관된 품목에 대한 품목 원가 레코드를 포함합니다. 전환 기록에 대한 전용 원가계산 버전에는 다음 설정이 있으며 필요에 따라 다양한 탭에서 이 설정을 검토하고 수정해야 합니다.

-   **원가 계산 유형:** 이 필드는 **표준 원가** 로 설정해야 합니다.
-   **버전:** 식별자는 비용 계산 버전 ID에 대한 변환 레코드에 입력된 정보를 반영합니다.
-   **이름:** 기본적으로 이름은 비어 있습니다. 선택적으로 이름을 입력할 수 있습니다.
-   **차단:** 이 필드는 **아니요** 로 설정해야 합니다. 변환 레코드의 상태를 **준비** 로 변경할 때까지 비용 레코드를 원가계산 버전에 입력할 수 있습니다. **준비** 상태는 선택한 항목이 확인되었으며 비용 레코드에 대한 변경이 허용되지 않아야 함을 나타냅니다.
-   **차단 활성화:** 이 필드는 **예** 로 설정해야 합니다. 전용 비용 계산 버전에서는 보류 중인 비용 레코드를 수동으로 활성화할 수 없습니다. 활성화는 변환을 수행할 때 발생합니다.
-   **시작 날짜:** 시작 날짜는 변환 레코드에 입력된 계획된 변환 날짜를 반영합니다.
-   **사이트:** 모든 사이트에 대한 비용 레코드를 입력할 수 있도록 이 필드를 비워 둡니다.
-   **가격 유형 필드 그룹 허용:** 비용 가격 레코드만 입력할 수 있도록 이 필드를 **예** 로 설정합니다.
-   **대체 원칙:** 이 필드는 **없음** 으로 설정됩니다. 다른 비용 계산 버전에서 활성화된 비용 정보가 필요한 경우 대체 원칙을 **활성** 으로 변경합니다. 예를 들어, 제조 품목의 비용을 계산하기 위해 구성 요소, 비용 범주 및 간접 비용에 대한 비용 정보가 필요할 수 있습니다.
-   **대체 원가 계산 버전:** 이 필드를 비워 둡니다.

전용 원가계산 버전의 품목 원가 정보는 **표준 원가 변환** 페이지에서만 관리할 수 있습니다. **원가 버전 설정** 페이지 또는 **원가 버전 유지 관리** 페이지를 사용하여 변환하는 동안 원가 버전에 대한 비용을 계산할 수 없습니다. 그러나 변환 프로세스를 완료한 후 이 페이지를 사용하여 전용 원가계산 버전을 유지할 수 있습니다.

## <a name="3-identify-the-items-to-convert-to-standard-cost"></a>3. 표준원가로 환산할 항목 식별
**표준 비용 변환** 페이지를 사용하여 표준 비용으로 변환해야 하는 개별 항목을 식별합니다. **표준 비용 변환에 항목 추가** 페이지를 사용하여 여러 항목을 추가할 수 있습니다. 일반적으로 비용이 올바르게 계산되도록 모든 제조 품목을 단일 변환 기록에 포함해야 합니다.

## <a name="4-enter-or-calculate-the-pending-standard-cost-for-each-item-that-is-being-converted"></a>4. 변환 중인 각 항목에 대해 보류 중인 표준 비용을 입력하거나 계산합니다.
**품목 가격** 페이지를 사용하여 구매 품목 및 이전 품목에 대한 전용 원가계산 버전에서 보류 중인 표준 원가를 입력합니다. 비용 레코드는 사이트별로 다르며 항목의 보류 비용은 모든 사이트에 대해 입력해야 합니다. **품목 가격** 페이지를 사용하여 제조 품목에 대해 보류 중인 표준 비용을 계산합니다. 제조 품목의 보류 비용은 사이트가 이전 사이트를 나타내지 않는 한 모든 제조 사이트에 대해 계산되어야 합니다. 이 경우 보류 비용은 수동으로 입력해야 합니다. 일부 품목에는 색상, 크기 또는 구성 제품 치수가 있을 수 있습니다. **표준 비용 변환** 페이지에서 **변형별 비용 가격 사용** 확인란은 제품 차원의 모든 조합에 대한 표준 비용을 표시합니다. 이 확인란의 선택을 취소하면 항목에 대해 보류 중인 비용만 입력해야 합니다.

## <a name="5-check-and-resolve-any-issues-for-the-items-that-are-being-converted"></a>5. 변환 중인 항목에 대한 문제 확인 및 해결
**표준 비용 변환 확인** 보고서를 사용하여 변환 중인 항목에 대한 문제를 식별합니다. 항목에 문제가 없으면 전환 레코드의 상태가 **확인됨** 으로 변경됩니다. 항목에 문제가 있는 경우 문제를 해결한 다음 항목 상태가 **확인됨** 으로 변경될 때까지 보고서를 다시 실행해야 합니다. 항목의 문제를 적시에 해결할 수 없는 경우 선택적으로 변환 기록에서 항목을 삭제한 다음 나중에 항목을 변환할 수 있습니다.

## <a name="6-change-the-status-of-the-conversion-record-to-ready"></a>6. 전환 기록의 상태를 준비로 변경
변환 레코드의 상태가 **준비** 로 변경되면 시스템은 표준 비용 변환을 실행하기 전에 최종 확인을 수행합니다. 다음 조건이 충족된 경우에만 상태가 **준비됨** 으로 변경됩니다.

-   전환 기록의 모든 항목은 **확인됨** 상태입니다.
-   전환 시작 날짜 하루 전 날짜에 인벤토리 마감이 수행되었습니다. 전환 시작 날짜와 인벤토리 마감 날짜가 올바르게 정렬되었는지 확인하기 위해 전환 시작 날짜를 기존 인벤토리 마감 후 하루로 변경하거나 인벤토리 마감을 수행할 수 있습니다.

## <a name="7-back-up-the-database-before-conversion"></a>7. 변환 전 데이터베이스 백업
변환 중에 오류가 발생한 경우 백업을 통해 데이터베이스를 복원할 수 있습니다.

## <a name="8-perform-the-conversion-when-the-conversion-record-has-a-ready-status"></a>8. 변환 레코드가 준비 상태일 때 변환 수행
전환 프로세스에서는 계획된 전환 날짜 하루 전 날짜에 인벤토리 마감을 수행해야 합니다. 이 요구 사항은 전환 기간 동안 소급 거래를 입력할 수 없도록 하는 데 도움이 됩니다. 인벤토리 마감이 아직 수행되지 않은 경우 변환 프로세스의 일부로 수행할 것인지 묻는 메시지가 표시됩니다. 변환 프로세스는 한 번에 하나의 항목을 처리합니다. 항목의 하위 수준 코드를 기반으로 제품 구조에서 가장 낮은 항목으로 시작합니다. 항목이 성공적으로 변환되면 변환 레코드의 상태가 **변환됨** 으로 변경됩니다. 변환 프로세스가 중단된 경우 성공적으로 변환되지 않은 항목은 여전히 **선택됨** 상태가 됩니다. 변환 프로세스를 성공적으로 완료하면 다음과 같은 효과가 있습니다.

-   변환 기록의 상태는 **준비** 에서 **완료됨** 으로, 선택된 각 항목의 상태는 **확인됨** 에서 **변환됨** 으로 변경됩니다.
-   변환된 항목의 항목 모델 그룹은 표준 원가 인벤토리 모델이 있는 새 그룹을 반영하도록 변경됩니다.
-   변환된 항목에 대한 표준 원가는 전용 원가계산 버전에서 활성화되었습니다.
-   원가 계산 버전의 원가 계산 유형이 **변환** 에서 **표준 원가** 로 변경되었으며 원가 계산 버전은 이제 표준 원가에 대한 다른 원가 계산 버전과 같습니다.

## <a name="9-validate-and-reconcile-the-inventory-values-for-the-converted-items"></a>9. 변환된 항목의 인벤토리 값을 확인하고 조정
**차이 분석 명세서** 보고서를 사용하면 재평가 차이를 분석할 수 있고 **인벤토리 금액** 보고서를 통해 특정 날짜의 인벤토리 금액을 볼 수 있습니다.

-   재평가 편차를 분석합니다. **차이 분석 명세서** 보고서를 사용하여 변환된 품목에 대한 인벤토리 재평가 차이를 봅니다. **표준 비용 트랜잭션** 페이지를 사용하여 인벤토리가 있는 변환된 품목에 대한 인벤토리 재평가 트랜잭션을 볼 수도 있습니다.
-   전환 시작일 이전에 인벤토리 가치를 분석합니다. **인벤토리 가치** 보고서를 사용하여 변환된 품목의 인벤토리 가치를 봅니다. 보고서의 종료 날짜에는 전환 시작 날짜 하루 전의 날짜를 사용하세요.
-   변환 날짜 이전에 인벤토리 가치를 분석합니다. **인벤토리 가치** 보고서를 사용하여 변환된 품목의 인벤토리 가치를 봅니다. 보고서의 종료 날짜로 변환 날짜 하루 전을 반영하는 날짜를 사용하세요.
-   변환 날짜에 인벤토리 가치를 분석합니다. **인벤토리 가치** 보고서를 사용하여 변환 날짜의 인벤토리 가치를 봅니다. 보고서의 시작 날짜와 종료 날짜는 모두 변환 날짜와 일치해야 합니다. 보고서 선택 기준은 변환된 항목을 반영해야 합니다.
-   소급 인벤토리 이동을 분석합니다. **인벤토리 가치** 보고서를 사용하여 전환 후 입력된 소급 인벤토리 이동을 봅니다. "보고서의 시작 날짜 및 종료 날짜는 전환 시작 날짜 및 변환 날짜에서 1일을 뺀 날짜와 일치해야 합니다. 보고서 선택 기준은 변환된 항목을 반영해야 합니다. 보고서는 전환 기간 동안 표준 원가로 이루어진 인벤토리 이동을 보여줍니다.


## <a name="additional-resources"></a>추가 리소스

[표준 비용 변환을 위한 전제 조건](prerequisites-standard-cost-conversion.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]