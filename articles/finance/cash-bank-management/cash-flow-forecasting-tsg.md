---
title: 현금 흐름 예측 설정 문제 해결
description: 이 토픽에서는 현금 흐름 예측을 구성할 때 가질 수 있는 질문에 대한 답변을 제공합니다. 현금 흐름 설정, 현금 흐름 업데이트 및 현금 흐름 Power BI에 대한 자주 묻는 질문(FAQ)을 다룹니다.
author: panolte
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 39860a1960706aae7d223c8d2e810d39edc41b11deb80026925e6655f8e23ee8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450508"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>현금 흐름 예측 설정 문제 해결

[!include [banner](../includes/banner.md)]

이 토픽에서는 현금 흐름 예측을 구성할 때 가질 수 있는 질문에 대한 답변을 제공합니다. 현금 흐름 설정, 현금 흐름 업데이트 및 현금 흐름 Power BI에 대한 자주 묻는 질문(FAQ)을 다룹니다.

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a>하나의 법인에 대해서만 현금 흐름이 표시되는 이유는 무엇입니까?

현금 흐름 예측은 법인별로 구성 및 계산됩니다. Power BI 보고서 및 Finance Insights의 현금 흐름 예측 기능은 결과를 보여줍니다.

예측을 보려는 각 법인에 대해 현금 흐름 예측을 설정해야 합니다. 모든 법인의 현금 흐름 예측 구성을 검토합니다. 또는 현금 흐름 예측을 위한 모든 법인의 구성을 검토하고 의도한 대로 설정되었는지 확인합니다.

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a>Power BI에 모든 현금 흐름 데이터가 표시되지 않는 이유는 무엇입니까?

현금 흐름 예측이 Power BI 보기에 표시되려면 몇 가지 단계를 완료해야 합니다. 다음 체크리스트를 검토하고 모든 단계가 완료되었는지 확인하십시오.

- 각 법인에 대한 현금 흐름을 설정합니다.
- 총계정원장 매개 변수에서 시스템 통화 및 시스템 환율 유형을 설정합니다.
- 원장 회계 통화 및 환율 유형을 설정합니다.
- 거래 통화와 회계 통화 간의 환율을 입력합니다.
- 회계 통화와 시스템 통화 간의 환율을 입력합니다.
- 회계 통화와 각 은행 통화 간의 환율을 입력합니다.

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a>현금 흐름 Power BI이 이전 버전에서 작동했지만 지금은 비어 있는 이유는 무엇입니까?

엔터티 스토어의 "현금 흐름 측정 V2" 및 "LedgerCovLiquidityMeasurement" 측정값이 구성되었는지 확인합니다. 엔터티 스토어의 데이터 작업 방법에 대한 자세한 내용은 [Power BI와 엔터티 스토어 통합](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md)을 참조하세요. Power BI 콘텐츠를 보는 데 필요한 모든 단계가 완료되었는지 확인합니다. 자세한 내용은 [현금 개요 Power BI 콘텐츠](Cash-Overview-Power-BI-content.md)를 참조하십시오.

## <a name="have-the-entity-store-entities-been-refreshed"></a>엔터티 스토어 엔터티가 새로 고쳐졌습니까?

데이터가 최신 상태이고 정확한지 확인하려면 엔터티를 주기적으로 새로 고쳐야 합니다. 특정 엔터티를 수동으로 새로 고치려면 **시스템 관리 \> 설정 \> 엔터티 스토어** 로 이동하여 엔터티를 선택한 다음 **새로 고침** 을 선택합니다. 데이터는 자동으로 업데이트될 수도 있습니다. **엔터티 스토어** 페이지에서 **자동 새로 고침 사용** 옵션을 **예** 로 설정합니다.

## <a name="which-calculation-method-should-be-used-when-calculating-cash-flow-forecasts"></a>현금 흐름 예측을 계산할 때 어떤 계산 방법을 사용해야 합니까?

현금 흐름 예측 계산 방법에는 두 가지 중요한 선택 옵션이 있습니다. **신규** 옵션은 마지막 일괄 처리 작업이 실행된 이후 변경된 새 문서 및 문서에 대한 현금 흐름 예측을 계산합니다. 이 옵션은 문서의 더 작은 하위 집합을 처리하기 때문에 더 빠르게 실행되는 경향이 있습니다. **합계** 옵션은 시스템의 모든 문서에 대한 현금 흐름 예측을 다시 계산합니다. 이 옵션은 완료해야 할 작업이 더 많기 때문에 시간이 더 걸립니다.

### <a name="how-do-i-improve-the-performance-of-the-cash-flow-forecasting-recurring-batch-job"></a>현금 흐름 예측 정기 일괄 처리 작업의 성능을 향상시키려면 어떻게 합니까?

**신규** 계산 방법을 사용하여 사용량이 적은 시간에 매일 한 번씩 현금 흐름 예측을 실행하는 것이 좋습니다. 이 방법을 일주일에 6일 사용하는 것이 좋습니다. 그런 다음 활동량이 가장 적은 날에 **합계** 계산 방법을 사용하여 매주 한 번 현금 흐름 예측을 실행합니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

