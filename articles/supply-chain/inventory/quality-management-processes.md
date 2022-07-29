---
title: 품질 및 부적합 관리 개요
description: 이번에는 Microsoft Dynamics 365 Supply Chain Management의 품질 및 부적합 관리 기능을 소개하고 이러한 기능이 공급망에서 제품 품질을 개선하는 데 어떻게 도움이 되는지 설명합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling, InventNonConformanceHistory, InventNonConformanceTable, InventQualityOrderLineResults, InventQualityOrderTable, InventTestCorrection, InventTestDiagnosticType, InventTestInstrument, InventTestReportSetup, InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "11574"
- intro-internal
ms.assetid: 5ac8a059-5cb4-4cb5-ba14-b944bd08dae9
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1bb4bcb7f554c22b4e1ab1b41867bd2d3dcca4d4
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449746"
---
# <a name="quality-and-nonconformance-management-overview"></a>품질 및 부적합 관리 개요

[!include [banner](../includes/banner.md)]

이번에는 Microsoft Dynamics 365 Supply Chain Management의 품질 및 부적합 관리 기능을 소개하고 이러한 기능이 공급망에서 제품 품질을 개선하는 데 어떻게 도움이 되는지 설명합니다.

품질 보증에는 제품 테스트 및 부적합 원자재 관리가 포함됩니다. 품질 관리 프로세스는 공급망에서 높은 수준의 제품 품질을 보장하는 데 도움이 됩니다. 이러한 프로세스는 공급망 프로세스를 최적화하고 고객 만족도를 높이는 데도 도움이 됩니다. 품질 관리는 해당 제품의 원산지 관계없이 부적합 제품을 처리할 때 처리 시간을 관리하는 데 도움이 될 수 있습니다. 진단 결과를 수정 작업에 연결할 수 있습니다. 시스템은 문제를 수정하기 위한 작업을 예약할 수 있으므로 향후 이러한 문제의 재발을 방지하는 데 도움이 됩니다. 또한, 품질 관리를 통해 문제 유형별로 문제(내부 문제 포함)를 추적하고 솔루션을 단기 또는 장기로 식별할 수 있습니다. 핵심 성과 지표(KPI)에 대한 통계는 이전에 발생한 부적합 문제와 이를 수정하기 위해 적용된 솔루와션에 대한 통찰력을 제공합니다. 과거 데이터를 사용하여 이전에 취한 품질 측정의 효율성을 검토하고 향후 적절한 측정을 결정할 수 있습니다.

품질 관리는 원산지와 상관없이 부적합 제품을 취급할 때 소요 시간을 관리하는 데 도움이 될 수 있습니다. 진단 유형은 수정 보고와 연결되어 있기 때문에 Supply Chain Management는 문제를 수정하고 재발을 방지하기 위한 작업을 예약할 수 있습니다.

부적합 관리 기능 외에도 품질 관리에는 문제 유형별로 문제를 추적하고(문제가 내부 문제인 경우에도) 단기 또는 장기 솔루션을 식별하는 기능이 포함됩니다. 핵심 성과 지표(KPI)에 대한 통계는 이전 부적합 문제의 이력과 이를 수정하는 데 사용된 솔루션에 대한 통찰력을 제공합니다. 과거 데이터를 사용하여 이전 품질 측정의 효율성을 검토하고 향후 사용할 적절한 측정을 결정할 수 있습니다.

품질 연관을 설정할 때 Supply Chain Management는 다양한 비즈니스 프로세스, 이벤트 및 조건에 대한 품질 주문을 생성할 수 있습니다. 품질 연관은 특정 품목, 특정 품목 그룹 또는 모든 품목을 포함할 수 있습니다.

## <a name="examples-of-the-use-of-quality-management"></a>품질 관리 사용 예시

품질 관리는 유연하며 특정 수준의 공급망 운영 요구 사항을 충족하기 위해 다양한 방식으로 구현될 수 있습니다. 다음 예는 이러한 기능의 가능한 사용을 보여줍니다.

- 사전 정의된 기준에 따라 품질 관리 프로세스를 자동으로 시작합니다(특정 공급 업체로부터 구매 주문의 창고 등록 발생 시 등).
- 검사 중 재고를 차단하여 승인되지 않은 재고가 사용되지 않도록 합니다(구매 주문 수량의 전체 차단).
- 검사해야 하는 현재 총 집계량을 정의하기 위해 품질 연관의 일부로 품목 샘플링을 사용합니다. 샘플링은 고정 수량, 백분율 또는 전체 번호판을 기반으로 할 수 있습니다.
- 부분 입고에 대한 품질 주문을 생성합니다. 주문과 함께 물리적으로 받은 수량을 기반으로 품질 주문을 생성하려면 **품목 샘플링** 페이지에서 **업데이트된 수량당** 확인란을 선택해야 합니다.
- 최소, 최대 및 목표 테스트 값을 포함하는 테스트 유형을 생성하고 사전 정의된 검증 결과가 있는 질적 대 정량적 테스트를 수행합니다.
- 품질 측정 허용 오차를 제어하기 위해 허용 가능한 품질 수준(AQL)을 지정합니다.
- 테스트 영역 및 테스트 도구와 같이 검사 작업에 필요한 리소스를 지정합니다.

> [!NOTE]
> _창고 프로세스에 대한 품질 관리_ 기능은 품질 관리 기능을 확장합니다. 이 기능을 사용하는 경우 품질 관리가 활성화되었을 때 작동하는 방식을 보여주는 예시는 [창고 프로세스에 대한 품질 관리](quality-management-for-warehouses-processes.md)를 참조하세요.

## <a name="controlling-the-quality-management-process"></a>품질 관리 프로세스 제어

다음은 품질 관리 프로세스를 제어할 수 있는 몇 가지 방법입니다.

- 인바운드 작업의 경우 '제품 수령 시' 또는 아웃바운드 작업의 경우 '제품 픽업 시'와 같은 트리거 포인트를 기반으로 하는 품질 주문을 생성합니다.
- 테스트 결과를 문서화하고 결과가 설정된 테스트 기준 및 AQL을 충족하는지 확인합니다.
- 검사 프로세스 중 보고의 일부로 자세한 제품 사양 및 사용자별 메모에 대한 문서 관리를 사용합니다.
- 부적합 제품을 유지 보수하고 해당 제품을 추가 부적합 정보와 연관시켜 문제의 기존 원인을 추적합니다.
- 부적합 관리 비용을 문서화합니다. 이 비용에는 품목(예비 부품 등), 기타 비용, 부적합 사항을 수정하는 데 필요한 작업표 시간이 포함될 수 있습니다.
- 품질 주문과 연결된 수정 처리를 사용하여 오류 수정 프로세스를 예약합니다.

[![품질 관리 프로세스](media/quality-management-process-diagram.png)](media/quality-management-process-diagram.png)

## <a name="product-testing-and-quality-orders"></a>제품 테스트 및 품질 주문

제품 테스트는 일반적으로 품질 관리라고 하며 품질 주문을 사용합니다. 품질 관리 기능을 사용하여 다음을 수행할 수 있습니다.

- 원자재에 대해 수행해야 하는 테스트를 정의합니다. 이러한 테스트에는 품질 사양, 해당 테스트 도구, 테스트를 설명하는 문서, 샘플링 계획 및 AQL이 포함됩니다.
- 구매 또는 생산 주문과 같은 특정 주문이나 특정 재고 수량에 대해 수행해야 하는 테스트를 식별하는 품질 주문을 생성합니다. 품질 주문을 수동으로 생성하거나 품질 지침에 따라 품질 주문을 자동으로 생성할 수 있습니다.
- 입고 또는 출고 원자재에 대한 테스트 요구 사항을 식별하는 품질 주문이 자동으로 생성될 수 있도록 각 비즈니스 프로세스에서 구매, 격리, 생산 또는 판매 주문과 관련된 품질 지침을 정의합니다.
- 테스트 결과를 품질 순서로 기록하고 AQL에 대해 테스트 결과를 검증하고 테스트 결과를 보여주는 분석 인증서를 인쇄합니다.

## <a name="nonconformance"></a>부적합

부적합은 품질 문제가 있는 품목을 설명합니다. 부적합 프로세스를 통해 부적합 원자재의 수량, 문제 원인, 문제 유형 및 설명 메모를 설명하는 부적합 주문을 생성할 수 있습니다. 부적합 원자재의 분석을 더 쉽게 하기 위해 문제 유형의 분류를 정의할 수 있습니다. 또한, 부적합 태그와 부적합 보고서를 인쇄하여 부적합 원자재의 처리를 안내할 수 있습니다. 예를 들어, 태그 및 보고서는 **사용 불가** 또는 **사용 제한** 을 나타낼 수 있습니다.

다음 표에서는 6가지 기본 부적합 유형을 나열하고 각 유형에 대해 기록해야 하는 정보를 설명합니다.

| 부적합 유형 | 소스 정보 |
|---|---|
| 고객 | 고객 계정 번호, 판매 주문 번호 또는 판매 주문 거래의 로트 번호입니다. 예를 들어, 부적합은 특정 판매 주문 배송 또는 제품 품질에 대한 고객 피드백과 관련될 수 있습니다. |
| 서비스 요청 | 고객 계정 번호, 판매 주문 번호 또는 판매 주문 거래의 로트 번호입니다. 예를 들어, 부적합은 특정 판매 주문 배송 또는 품목 품질에 대한 고객의 불만과 관련될 수 있습니다. |
| 공급 업체 | 공급 업체 계정 번호, 구매 주문 번호 또는 구매 주문 거래의 로트 번호입니다. 예를 들어, 부적합은 구매 주문 영수증이나 공급하는 부품에 대한 공급 업체의 우려와 관련될 수 있습니다. |
| 생산 | 생산 주문 거래의 생산 주문 번호 또는 로트 번호입니다. 예를 들어, 부적합은 생산된 특정 배치와 관련될 수 있습니다. |
| 내부 | 품질 주문 번호 또는 품질 주문 거래의 로트 번호입니다. 예를 들어, 부적합은 품질 주문의 일부로 수행되는 테스트 또는 제품 품질에 대한 직원의 우려와 관련될 수 있습니다. |
| 부산물 생산 | 일괄 생산 주문과 관련된 부산물 생산 주문 부적합입니다. |

부적합은 문제 유형과 관련이 있습니다. **문제 유형** 은 각 부적합 유형과 연관될 수 있는 문제 유형을 지정하는 문제 유형 페이지에서 정의됩니다. 예를 들어, **서비스 요청** 유형의 부적합에 대한 문제 유형은 고객 불만의 분류를 반영할 수 있는 반면, **내부** 유형의 부적합에 대한 문제 유형은 결함 코드의 분류를 나타낼 수 있습니다.

새 부적합을 생성할 때 부적합 유형과 문제 유형을 선택합니다. 초기 승인 상태는 조치 요청을 나타내는 **신규** 입니다. 다음 단계는 승인 상태를 **승인됨** 또는 **거부됨** 으로 변경하여 부적합 사항에 대해 조치를 취하거나 하지 않을 것임을 나타내는 것입니다. 또한, 부적합 사항을 닫고(별도의 확인란을 선택하여) 부적합 사항을 완료했음을 나타내거나 부적합 사항을 다시 열어 추가 고려 사항이 필요함을 나타낼 수 있습니다.

문서를 첨부하여 부적합에 대한 의견을 입력할 수 있습니다. 문서 유형 페이지를 사용하여 부적합에 대한 고유한 **문서 유형** 을 정의하는 것이 좋습니다. 이후 **보고서 설정** 페이지를 사용하여 이 문서 유형에 대한 주석을 부적합 보고서 및 부적합 태그에 인쇄해야 하는지를 정의할 수 있습니다. 적합성 보고서 및 부적합 태그는 원자재 처분에 도움이 될 수 있습니다. 부적합과 관련된 선택 기준에 따라 보고서와 태그를 선택적으로 생성할 수 있습니다. 이러한 기준에는 부적합 번호, 품목, 고객, 공급 업체 및 상태가 포함됩니다.

부적합 보고서에는 부적합 번호, 품목 및 문제 유형이 표시됩니다. 보고서 설정 정책에 따라 보고서는 부적합에 대한 관련 참고 사항을 표시할 수도 있습니다. 부적합 태그는 유사한 정보를 표시하며 결함이 있는 원자재의 처리를 안내하기 위해 부적합에 할당한 격리 구역 및 유형(**사용 제한** 또는 **사용 불가** 등)도 포함합니다.

## <a name="approved-nonconformance"></a>승인된 부적합

승인된 부적합에 대해 하나 이상의 관련 작업을 선택적으로 정의할 수 있습니다. 관련 작업은 수행해야 하는 작업을 설명하고 정의한 품질 작업 목록과 작업 사유에 대한 설명 텍스트를 포함합니다. 공정을 정의한 후 작업을 수행하는 데 필요한 기타 비용, 품목 및 작업표 노동 시간을 선택적으로 정의할 수 있습니다. 관련 작업에 대해서는 계산된 비용이 표시되고 부적합에 대해서는 계산된 총 비용이 표시됩니다. 계산된 원가와 기본 내역(품목, 노동 시간, 잡비 등)은 참고 자료로 품질 관리 기능에서만 사용됩니다.

선택적으로 먼저 품질 주문 조회를 수행한 후, 새 품질 주문을 생성하여 부적합에서 품질 주문을 생성할 수 있습니다. 예를 들어, 품질 주문은 결함이 있는 원자재를 테스트(또는 재테스트)해야 할 필요성을 식별할 수 있습니다. 새로 생성된 품질 주문은 기존 부적합에 대한 링크를 표시합니다.

선택적으로 하나의 부적합을 다른 부적합에 연결하고 기존 부적합에서 새 부적합을 생성할 수 있습니다. 예를 들어 링크는 품질 문제 간의 상호 연결을 반영할 수 있습니다.

## <a name="correction-handling"></a>수정 처리

**수정** 페이지에서는 수정해야 하는 부적합 목록을 생성할 수 있습니다. 각 수정 품목은 문제를 발견하게 한 진단 유형과 연관됩니다. **수정** 페이지에는 수정 작업을 수행해야 하는 사람과 시기에 대한 정보도 포함되어 있습니다. 수정 사항에 문서를 첨부하여 문제점 및 필요한 시정조치의 세부 사항을 설명할 수 있습니다. 부적합 사항이 해결되거나 수정된 ​​후 **완료됨** 옵션을 선택하여 수정 품목을 '닫습니다'. 솔루션이 단기 솔루션임을 나타낼 수도 있습니다.

문서 유형 페이지를 사용하여 수정을 위해 고유한 **문서 유형** 을 정의하는 것이 좋습니다. 이후 **보고서 설정** 페이지를 사용하여 이 문서 유형에 대한 설명을 수정 보고서에 인쇄할지를 정의할 수 있습니다. 인쇄된 수정 보고서에는 부적합 사항 및 관련 부적합 사항에 대한 정보가 표시됩니다. 보고서에는 진단 유형 및 관련 수정 참고 사항과 같은 수정 정보도 포함됩니다.

## <a name="additional-resources"></a>추가 리소스

- [품질 및 부적합 관리 활성화](enable-quality-management.md)
- [재고 차단](inventory-blocking.md)
- [격리 명령](quarantine-orders.md)
- [제품 품질 검사](tasks/inspect-quality-goods.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]