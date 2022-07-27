---
title: Dynamics 365 Supply Chain Management 10.0.20의 새로운 기능 또는 변경된 기능(2021년 8월)
description: 이 토픽에서는 Dynamics 365 Supply Chain Management 10.0.20의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: kamaybac
ms.date: 05/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: a8f46165a89f064878d2e8af1b0b174b04eca37e
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2021
ms.locfileid: "8449386"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10020-august-2021"></a>Dynamics 365 Supply Chain Management 10.0.20의 새로운 기능 또는 변경된 기능(2021년 8월)

[!include [banner](../includes/banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 버전 10.0.20의 새로 추가되거나 변경된 기능에 관해 나열합니다. 이 버전의 빌드 번호는 10.0.886이며 다음과 같이 확인할 수 있습니다.

- **프리뷰 릴리스:** 2021년 5월
- **릴리스 일반 공급(자체 업데이트):** 2021년 7월
- **릴리스 일반 공급(자동 업데이트):** 2021년 8월

## <a name="features-included-in-this-release"></a>이번 릴리스에 포함된 기능

다음 표에는 이 릴리스에 포함된 기능이 나열되어 있습니다. *기능* 열은 각 기능의 공식 릴리스 날짜를 볼 수 있는 [릴리스 계획](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features)에 대한 링크를 제공합니다. *추가 정보* 열은 관련 문서에 대한 자세한 정보 및/또는 링크를 제공합니다.

이러한 기능의 대부분은 사용하기 전에 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 사용하여 활성화해야 합니다.

| 기능 영역 | 기능 | 추가 정보 |
|---|---|---|
| 재고&nbsp;및&nbsp;물류 | [판매 주문 내역 성능 향상](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | 이 기능을 사용하면 판매 주문, 특히 많은 라인이 포함된 주문을 열 때 사용자 인터페이스의 응답성이 향상됩니다. |
| 제조 | [프로세스 자동화 흐름을 호출하여 품질 주문 생성](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/invoke-process-automation-flows-create-quality-orders) | [프로세스 자동화 흐름을 호출하여 품질 주문 생성](../production-control/process-automation-quality-orders.md ) |
| 제조 | [제조를 위한 향상된 생산 현장 실행 인터페이스](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-manufacturing) | [생산 현장 실행 인터페이스 구성](../production-control/production-floor-execution-configure.md) |
| 계획 | [계획 최적화를 위한 무한 용량 예약](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-infinite-capacity-support-planning-optimization) | [무한 용량으로 스케줄링](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| 제품 정보 관리 | [공식 및 해당 성분의 변경 사항 관리](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/engineering-change-management-support-process-manufacturing) | [공식 및 해당 성분의 변경 사항 관리](../engineering-change-management/manage-formula-changes.md) |
| 제품 정보 관리 | [제품 준비 확인](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/product-readiness-checks) | [제품 준비](../engineering-change-management/product-readiness.md) |

## <a name="feature-enhancements-included-in-this-release"></a>이번 릴리스에 포함된 기능 개선 사항

다음 표에는 이 릴리스에 포함된 기능 개선 사항이 나열되어 있습니다. 이들 각각은 기존 기능을 점진적으로 개선합니다. 개선 사항일 뿐이므로 [릴리스 계획](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features)에 나열되지 않습니다. 그러나 이러한 개선 사항이 기존 사용자 지정 또는 기본 설정과 충돌하지 않도록 하기 위해 각 기능은 기본적으로 해제되어 있습니다(달리 명시되지 않는 한). 이러한 기능을 사용하려면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 명시적으로 활성화해야 합니다.

| 모듈 | 기능&nbsp;관리의&nbsp;기능&nbsp;이름 | 추가 정보 |
|---|---|---|
| 기준 계획 | 조정된 수요 예측의 병렬 승인 | 이 기능을 사용하면 **조정된 수요 예측** 페이지에서 조정된 수요 예측을 동시에 승인할 수 있습니다. 이 기능의 목적은 많은 수의 예측이 승인될 때 성능을 높이는 것입니다. 권한 부여 시 사용자는 권한 부여 대화 상자에서 **스레드 수** 를 지정할 수 있습니다. |
| 기준 계획 | (프리뷰) 계획된 대량 및 포장 배치 주문에 대한 배치 가능한 확정 및 통합 | 이 기능을 사용하면 배치 작업을 사용하여 계획된 대량 및 포장 주문을 확정하고 통합할 수 있습니다. |
| 생산 관리 | 일반 경로 복사 | 이 기능은 사용자가 항목에 특정하지 않은 경로를 복사할 수 있도록 경로 복사 기능을 향상시킵니다. 경로 복사 기능을 사용하여 항목에 아직 할당되지 않은 경로를 덮어쓴 후 시스템이 모든 관련 정보(예: 사이트, 경로 그룹, 리소스 요구 사항 및 다양한 시간)를 업데이트할 수 있습니다. |
| 생산 관리 | 경로 작업이 변경될 때 관련 리소스 요구 사항 업데이트 | 이 기능을 사용하면 사용자가 기존 경로 단계의 작업을 변경한 후 시스템에서 관련 리소스 요구 사항을 업데이트할 수 있습니다. |
| 제품 정보 관리 | 시간 초과를 방지하기 위한 자제 명세서 보고서 사전 처리 | 이 기능을 사용하면 자재 명세서 보고서가 사전 처리됩니다. 이렇게 하면 보고서에 대한 데이터 로드가 클 때 시간 초과 문제를 피할 수 있습니다. |
| 조달 및 소싱 | 조달 관련 워크플로 재설정 활성화 | 이 미리 보기 기능을 사용하면 구매 주문, 공급업체 변경 및 구매 요청과 같은 워크플로를 초안 상태로 재설정할 수 있습니다. |
| 운송 관리 | 운임 청구서를 폐기할 때 공급업체 송장 저널 생성 활성화 | 이 기능이 활성화되면 지불 공급업체 옵션을 사용할 때 조정을 위해 해당 공급업체 송장 분개장이 생성됩니다. 그렇지 않으면 송장 분개장이 항상 생성됩니다. |
| 창고 관리 | 보충 작업을 위해 선택한 템플릿 검증 | 이 기능은 사용자가 보충 작업을 설정할 때 유효한 보충 템플릿을 선택하도록 합니다. 이것은 사용자가 템플릿 없이 보충 작업을 생성하고 보충 작업을 생성하지 않고 처리하는 데 오랜 시간이 걸릴 수 있는 *웨이브 수요* 유형의 템플릿을 선택하는 것을 방지합니다. |

## <a name="new-and-updated-documentation-resources"></a>신규 및 업데이트된 문서 리소스

최근에 다음 도움말 항목을 추가하거나 크게 업데이트했습니다. 이전 섹션에 나열된 것처럼 이 릴리스에 추가된 새로운 기능과 반드시 관련이 있는 것은 아니지만 기존 기능을 최대한 활용하는 데 도움이 될 수 있습니다.

| 기능 영역 | 신규 또는 업데이트된 토픽 |
|---|---|
| 엔지니어링 변경 관리 | [제품 수명 주기 상태 및 트랜잭션](../engineering-change-management/product-lifecycle-state-transactions.md) |
| 재고 관리 | [인벤토리 가시성 추가 기능](../inventory/inventory-visibility.md)<br><br>[품질 및 부적합 관리 개요](../inventory/quality-management-processes.md)(모든 관련 품질 관리 토픽 포함) |
| 조달 및 소싱 | [공급업체 인증 유지](../../finance/public-sector/manage-vendor-certification.md) |
| 생산 관리 | [생산 현장 실행 인터페이스 스타일 지정](../production-control/production-floor-execution-styles.md) |
| 창고 관리 | [Warehouse Management 모바일 앱에 대한 단계 아이콘 및 제목 할당](../warehousing/step-icons-titles.md)<br><br>[수동 재고 이동의 지연 처리](../warehousing/deferred-processing-manual-inventory-movement.md) |

## <a name="additional-resources"></a>추가 리소스

### <a name="platform-updates-for-finance-and-operations-apps"></a>금융 및 운영 앱용 플랫폼 업데이트

Microsoft Dynamics 365 Supply Chain Management 10.0.20에는 플랫폼 업데이트가 포함됩니다. 자세히 알아보려면 [금융 및 운영 앱 버전 10.0.20에 대한 플랫폼 업데이트(2021년 7월)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20.md)를 참조하세요.

### <a name="bug-fixes"></a>버그 수정

10.0.20의 일부인 각 업데이트에 포함된 버그 수정에 대한 정보는 LCS(Lifecycle Services)에 로그인하여 [KB 문서](https://fix.lcs.dynamics.com/Issue/Details?bugId=586707&dbType=3&qc=d0dad8eee2af234e8c288e2a7df14c579004518673d014be511f900cfed008f8)를 참조하세요. 

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: 2021 릴리스 웨이브 1 계획

비즈니스 앱 또는 플랫폼에서 예정된 기능과 최근에 출시된 기능이 궁금하신가요?

[Dynamics 365: 2021 릴리스 웨이브 1 계획](/dynamics365-release-plan/2021wave1/)을 확인하세요. 계획에 사용할 수 있는 단일 문서에 모든 세부 사항을 처음부터 끝까지, 위에서 아래로 캡처했습니다.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>제거 및 사용되지 않는 Supply Chain Management 기능

[Dynamics 365 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능](removed-deprecated-features-scm-updates.md) 항목은 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능에 대해 설명합니다.

- *제거된* 기능은 더 이상 제품에서 사용할 수 없습니다.
- *더 이상 사용되지 않는* 기능은 현재 개발 중이 아니며 향후 업데이트에서 제거될 수 있습니다.

제품에서 기능이 제거되기 전에, 지원 중단 알림은 제거 12개월 전에 [Dynamics 365 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능](removed-deprecated-features-scm-updates.md) 항목에 공지됩니다.

컴파일 시간에만 영향을 미치지만 샌드박스 및 프로덕션 환경과 바이너리 호환되는 호환성이 손상되는 변경의 경우 사용 중단 시간은 12개월 미만입니다. 일반적으로 컴파일러에 대해 수행해야 하는 기능 업데이트입니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
