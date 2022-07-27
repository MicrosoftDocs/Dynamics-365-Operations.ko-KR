---
title: Dynamics 365 Supply Chain Management 10.0.24의 새로운 기능 또는 변경된 기능(2022년 2월)
description: 이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 10.0.24의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: kamaybac
ms.date: 12/03/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: a254e20dd7fcc29ca520282b4bf9fcd903e4de58
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/02/2022
ms.locfileid: "8449899"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10024-february-2022"></a>Dynamics 365 Supply Chain Management 10.0.24의 새로운 기능 또는 변경된 기능(2022년 2월)

[!include [banner](../includes/banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 버전 10.0.24의 새로 추가되거나 변경된 기능에 관해 나열합니다. 이 버전의 빌드 번호는 10.0.1084이며 다음과 같이 확인할 수 있습니다.

- **릴리스 프리뷰:** 2021년 12월
- **릴리스 일반 공급(자체 업데이트):** 2022년 1월
- **릴리스 일반 공급(자동 업데이트):** 2022년 2월

## <a name="features-included-in-this-release"></a>이번 릴리스에 포함된 기능

다음 표에는 이 릴리스에 포함된 기능이 나열되어 있습니다. 이 항목이 처음 게시된 후 빌드에 포함된 기능을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 기능 영역 | 기능 | 추가 정보 |  에 의해 활성화됨 |
|---|---|---|---|
| 분산 하이브리드 토폴로지 | [배율 단위에서 향상된 창고 실행 워크로드](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-warehouse-execution-workloads-scale-units) | [클라우드 및 에지 스케일 유닛을 위한 창고 관리 워크로드](../cloud-edge/cloud-edge-workload-warehousing.md) | 기본적으로 활성화되어 있습니다. |
| 분산 하이브리드 토폴로지 | [클라우드 및 에지 스케일 유닛에 대한 창고 관리 워크로드에 대한 생산 주문 시작](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-manufacturing-execution-workloads-scale-units) | [클라우드 및 에지 스케일 유닛을 위한 제조 실행 워크로드](../cloud-edge/cloud-edge-workload-manufacturing.md) | 기능 관리(*클라우드 및 에지 배율 단위에 대한 창고 관리 워크로드에 대한 생산 주문 시작*)  |
| 계획 | [재주문마진 및 발행마진에 대한 계획 최적화 지원](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-reorder-margin-issue-margin) | [안전 여유](../master-planning/planning-optimization/safety-margins.md) | 기본적으로 활성화되어 있습니다. |

## <a name="feature-enhancements-included-in-this-release"></a>이번 릴리스에 포함된 기능 개선 사항

다음 표에는 이 릴리스에 포함된 기능 개선 사항이 나열되어 있습니다. 이러한 개선 사항 각각은 기존 기능을 점진적으로 개선합니다. 개선 사항일 뿐이므로 [릴리스 계획](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)에 나열되지 않습니다. 그러나 이러한 개선 사항이 기존 사용자 지정 또는 기본 설정과 충돌하지 않도록 하기 위해 각 기능은 기본적으로 해제되어 있습니다(달리 명시되지 않는 한).

이러한 기능을 켜거나 끄려면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 수행해야 합니다.

| 모듈 | 기능 관리의 기능 이름 | 추가 정보 |
|---|---|---|
| 생산 관리 | 생산 주문에 대한 주문형 자재 가용성 확인 | 이 기능을 사용하면 **생산 현장 관리** 작업 영역에서 사용할 수 있는 **릴리스할 생산 주문** 페이지를 더 빨리 열 수 있습니다. 이 기능이 없으면 시스템은 페이지를 여는 즉시 나열된 모든 생산 주문에 대해 자재를 사용할 수 있는지 여부를 자동으로 확인하므로 주문이 많을 경우 상당한 시간이 소요될 수 있습니다. 이 기능이 활성화되면 시스템은 대신 필요한 경우 선택한 주문에 대해서만 자재 검사를 시작하는 데 사용할 수 있는 도구 모음 단추를 제공합니다. |
| 생산 관리 | (프리뷰) 생산 현장 실행 인터페이스(비 WMS)에 재료 소비 등록 | 이 기능을 통해 작업자는 생산 현장 실행 인터페이스를 사용하여 자재 소비, 배치 번호 및 일련 번호를 등록할 수 있습니다. 이 기능은 고급 창고 프로세스(WMS)를 사용할 수 없는 항목을 지원하기만 합니다. WMS 지원 항목에 대한 지원은 향후 릴리스로 예정되어 있습니다.<p>일부 제조업체, 특히 공정 산업에 속한 제조업체는 각 배치 또는 생산 주문에 소비되는 재료의 양을 명시적으로 등록해야 합니다. 예를 들어, 작업자는 저울을 사용하여 작업하면서 소모되는 재료의 양을 측정할 수 있습니다. 완전한 자재 추적성을 보장하기 위해 이러한 조직은 각 제품을 생산할 때 사용된 배치 번호도 등록해야 합니다. |
| 생산 관리 | 클라우드 및 에지 배율 단위에 대한 창고 관리 워크로드에서 완료함으로 보고 | 이 기능을 사용하면 작업자가 Warehouse Management 모바일 앱을 사용하여 앱이 클라우드 또는 에지 규모 단위의 창고 관리 워크로드에 대해 실행될 때 완료된 생산 또는 배치 주문을 보고할 수 있습니다. 자세한 내용은 [완료로 보고 및 배율 단위에 보관](../cloud-edge/cloud-edge-workload-manufacturing.md#RAF)을 참조하세요. |
| 창고 관리 | 새 적재 계획 워크벤치 페이지 | 두 개의 새로운 로드 계획 워크벤치 페이지(**인바운드 로드 계획 워크벤치** 및 **아웃바운드 로드 계획 워크벤치**)를 활성화합니다. |

## <a name="new-and-updated-documentation-resources"></a>신규 및 업데이트된 문서 리소스

최근에 다음 도움말 항목을 추가하거나 크게 업데이트했습니다. 이러한 항목은 이전 섹션에 나열된 것처럼 이 릴리스에 추가된 새 기능과 반드시 관련이 있는 것은 아닙니다. 그러나 기존 기능을 최대한 활용하는 데 도움이 될 수 있습니다.

| 기능 영역 | 신규 또는 업데이트된 토픽 |
|---|---|
| 비용 관리 | [재고 가치 보고서](../cost-management/inventory-value-report-storage.md) |
| 비용 관리 | [재고 가치 보고 예시 및 로직](../cost-management/inventory-value-report-examples.md) |
| 기준 계획 | [계획 최적화에서 사용하는 날짜 및 시간 매개 변수](../master-planning/planning-optimization/date-time-used.md) |
| 기준 계획 | [수요 예측 설정](../master-planning/demand-forecasting-setup.md) |
| 기준 계획 | [안전 재고 분개장을 사용하여 항목에 대한 최소 적용 범위 업데이트](../master-planning/safety-stock-journal.md) |
| 생산 관리 | [생산 현장 실행 인터페이스 사용자 지정](../production-control/production-floor-execution-customize.md) |
| 생산 관리 | [생산 현장 실행 인터페이스 스타일 지정](../production-control/production-floor-execution-styles.md) |
| 영업 및 마케팅 | [판매 내역 정리 실적 개선](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| 창고 관리 | [모바일 디바이스 사용자 계정](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>추가 리소스

### <a name="platform-updates-for-finance-and-operations-apps"></a>금융 및 운영 앱용 플랫폼 업데이트

Microsoft Dynamics 365 Supply Chain Management 10.0.24에는 플랫폼 업데이트가 포함됩니다. 자세히 알아보려면 [금융 및 운영 앱 버전 10.0.24에 대한 플랫폼 업데이트(2022년 2월)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-24.md)를 참조하세요.

### <a name="bug-fixes"></a>버그 수정

10.0.24의 일부인 각 업데이트에 포함된 버그 수정에 대한 정보는 LCS(Lifecycle Services)에 로그인하여 [KB 문서](https://fix.lcs.dynamics.com/Issue/Details?bugId=641306&dbType=3&qc=5b1d5e49c96b8a5cfb5601889a413e6f3773ba6500f9bc47310dcc5c54fff42f)를 참조하세요.

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 및 산업 클라우드: 2021 릴리스 웨이브 2 계획

비즈니스 앱 또는 플랫폼에서 예정된 기능과 최근에 출시된 기능이 궁금하신가요?

[Dynamics 365 및 산업 클라우드: 2021 릴리스 웨이브 2 계획](/dynamics365-release-plan/2021wave2/)을 확인하세요. 계획에 사용할 수 있는 단일 문서에 모든 세부 사항을 처음부터 끝까지, 위에서 아래로 캡처했습니다.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>제거 및 사용되지 않는 Supply Chain Management 기능

[Dynamics 365 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능](removed-deprecated-features-scm-updates.md) 항목은 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능에 대해 설명합니다.

- *제거된* 기능은 더 이상 제품에서 사용할 수 없습니다.
- *더 이상 사용되지 않는* 기능은 현재 개발 중이 아니며 향후 업데이트에서 제거될 수 있습니다.

제품에서 기능이 제거되기 전에, 지원 중단 알림은 제거 12개월 전에 [Dynamics 365 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능](removed-deprecated-features-scm-updates.md) 항목에 공지됩니다.

컴파일 시간에만 영향을 미치지만 샌드박스 및 프로덕션 환경과 바이너리 호환되는 호환성이 손상되는 변경의 경우 사용 중단 시간은 12개월 미만입니다. 일반적으로 컴파일러에 대해 수행해야 하는 기능 업데이트입니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
