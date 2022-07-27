---
title: Dynamics 365 Supply Chain Management 10.0.23의 새로운 기능 또는 변경된 기능(2022년 1월)
description: 이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 10.0.23의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: kamaybac
ms.date: 10/15/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 83d19f92984c9f67242946aa8faf445d9d2bd881
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449572"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10023-january-2022"></a>Dynamics 365 Supply Chain Management 10.0.23의 새로운 기능 또는 변경된 기능(2022년 1월)

[!include [banner](../includes/banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 버전 10.0.23의 새로 추가되거나 변경된 기능에 관해 나열합니다. 이 버전의 빌드 번호는 10.0.1037이며 다음과 같이 확인할 수 있습니다.

- **출시 프리뷰:** 2021년 10월
- **릴리스 일반 공급(자체 업데이트):** 2021년 12월
- **릴리스 일반 공급(자동 업데이트):** 2022년 1월

## <a name="features-included-in-this-release"></a>이번 릴리스에 포함된 기능

다음 표에는 이 릴리스에 포함된 기능이 나열되어 있습니다. *기능* 열은 각 기능의 공식 릴리스 날짜를 볼 수 있는 [릴리스 계획](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)에 대한 링크를 제공합니다. *추가 정보* 열은 관련 문서에 대한 자세한 정보 및/또는 링크를 제공합니다. 기능을 켜는 방법을 결정하려면 *활성화:* 열을 참조하세요. 기능 관리 사용법에 대한 자세한 내용은 [기능 관리 개요](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 참조하세요. 이 항목이 처음 게시된 후 빌드에 포함된 기능을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 기능 영역 | 기능 | 추가 정보 |  에 의해 활성화됨 |
|---|---|---|---|
| 전체 주소록 | 주소 설정에서 각 국가/지역에 대한 기본 주/도 정의 | 이제 전체 주소록에 대한 주소 설정에서 각 국가/지역에 대한 기본 시/도를 정의할 수 있습니다. 기본 시/도가 설정되면 해당 국가/지역에 대한 새 카운티 또는 시 레코드를 만들 때 시/도 필드에 입력된 기본값이 됩니다. [주소 설정](../../fin-ops-core/fin-ops/organization-administration/global-address-book-address-setup.md?toc=/dynamics365/supply-chain/toc.json)도 참조하세요. | 기본적으로 활성화되어 있습니다. |
| 재고&nbsp;및&nbsp;물류 | [Warehouse Management 모바일 앱에서 작업 일시 중지](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/park-tasks-warehouse-management-mobile-app) | [모바일 디바이스 메뉴 항목의 단계에 대한 우회 구성](../warehousing/warehouse-app-detours.md) | 기능 관리(*창고 관리 앱 우회*) |
| 재고&nbsp;및&nbsp;물류 | [창고 앱 프로모션 필드](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [모바일 디바이스에서 단계에 대한 승격 필드 구성](../warehousing/warehouse-app-promoted-fields.md)| 기능 관리(*창고 앱 승격 필드*) |
| 제조 | [제조 실행 시스템 통합](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-systems-integration) | [타사 제조 실행 시스템과 통합](../production-control/mes-integration.md) | 기능 관리(*제조 실행 시스템 통합*) |
| 제조 | [생산 현장 실행 인터페이스의 연산품, 부산물에 대한 보고](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | [작업자가 생산 현장 실행 인터페이스를 사용하는 방법](../production-control/production-floor-execution-use.md) | 기능 관리(*생산 현장 실행 인터페이스의 연산품, 부산물에 대한 보고*) |
| 계획 | [우선순위 기반 계획을 위한 계획 최적화 지원](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-priority-based-planning) | [우선 순위 기반 계획](../master-planning/planning-optimization/priority-based-planning.md) | 기능 관리(*계획 최적화를 위한 우선 순위 기반 MRP 지원*) |

## <a name="feature-enhancements-included-in-this-release"></a>이번 릴리스에 포함된 기능 개선 사항

다음 표에는 이 릴리스의 새로운 기능 개선 사항이 나열되어 있습니다. 이러한 개선 사항 각각은 기존 기능을 점진적으로 개선합니다. 개선 사항일 뿐이므로 [릴리스 계획](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)에 나열되지 않습니다. 그러나 이러한 개선 사항이 기존 사용자 지정 또는 기본 설정과 충돌하지 않도록 하기 위해 각 기능은 기본적으로 해제되어 있습니다(달리 명시되지 않는 한).

이러한 기능을 켜거나 끄려면 다음 표의 *기능 관리의 기능 이름* 열에 표시된 이름을 사용하여 나열되는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 수행해야 합니다.

| 모듈 | 기능 관리의 기능 이름 | 추가 정보 |
|---|---|---|
| 자산 관리 | 작업 주문 분개장의 비용에 대한 계정 상계 | 이 기능을 사용하면 작업 주문 분개장에 나열된 각 비용에 대해 상계 계정을 지정할 수 있습니다. 일반적으로 각 비용에 공급업체 계정을 연결할 수 있지만 다른 계정 유형도 지원됩니다. **작업 주문 분개장** 페이지의 **경비** 빠른 탭에 두 개의 새 열(**상쇄 계정 유형** 및 **상쇄 계정**)을 추가합니다.|
| 비용 관리 | 표준 원가 반올림 재평가를 위한 관련 전표 생성 | <p>재고 재무 전기(예: 판매 주문 송장 또는 재고 트랜잭션)가 수행될 때 이 기능을 사용하면 시스템에서 관련 표준 원가 반올림 재평가에 대해 별도의 증서를 생성하고 이를 관련 증빙으로 재무 전기 증빙에 첨부합니다.</p><p>이 기능이 없으면 시스템은 동일한 전표 전기에 대한 표준 원가 반올림 재평가를 기록합니다. 재평가에서는 세션 또는 시스템 날짜를 사용하는 반면 재무 전기에서는 전기 날짜를 사용하기 때문에 이러한 동작으로 인해 날짜 정보가 충돌할 수 있습니다.</p> |
| 재고 및 창고 관리 | \[러시아\] 판매 주문에 대한 재무 바우처의 수정 플래그에 따라 오기 정정 재무 재고 거래 기장 | 이 기능은 러시아의 신용 메모 수정 기능에 영향을 줍니다. 총계정원장의 수정 옵션에 따라 판매 송장에 대한 재고 거래를 전기할 수 있습니다. 이 기능이 활성화되면 재고 거래의 금융 상품권의 **수정** 플래그와 재고 거래의 **스토르노** 플래그 사이에 더 이상 불일치가 없습니다. |
| 재고 및 창고 관리 | (러시아) 재고 잔액 회전율 보고서 계산 일괄 실행 | Supply Chain Management 러시아어 현지화의 경우 이 기능을 사용하면 *재고 잔액 회전율* 보고서를 일괄적으로 실행하여 저장하고 이전에 생성된 보고서를 볼 수 있습니다. |
| 재고 및 창고 관리 | (러시아) 재고 관리에서 국가 또는 지역별 기본 양식에서 현지 언어로 번역 사용 | Supply Chain Management 러시아어 현지화의 경우 이 기능을 사용하면 다음 러시아어 특정 재고 인쇄물에서 제품/항목 이름 및 측정 단위에 대한 러시아어 번역을 사용할 수 있습니다. 계수 목록(INV-3), 계수 목록(INV-5), 및 카운팅 목록(INV-6). |
| 기준 계획 | 수요 예측을 위한 Azure Machine Learning Service | 이 기능을 사용하면 Azure Machine Learning 서비스에서 기록 데이터를 기반으로 수요 예측을 생성할 수 있습니다. 자세한 내용은 [수요 예측 설정](../master-planning/demand-forecasting-setup.md)을 참조하세요. |
| 조달 및 소싱 | 구매 주문 업데이트 내역 정리 | 이 기능을 사용하면 구매 주문 업데이트와 관련된 임시 기록 레코드를 정리할 수 있습니다. **모든 구매 주문** 페이지의 작업 창에 **구매 업데이트 기록 정리** 라는 새 단추가 추가됩니다. 기본적으로 이 기능은 켜져 있습니다. |
| 생산 관리 | (프리뷰) 자동 전기 불출 목록에 대한 창고 활성화 자재 자동 피킹 | 이 기능을 사용하면 자동 전기, 파생 및 백플러시된 선택 목록 분개장에 대한 재고 차원을 자동으로 선택하고 해결할 수 있습니다. |
| 생산 관리 | 계획된 소비 일자에 대한 원자재 만료 검증 | 이 기능은 생산 중에 사용할 원자재 배치를 예약할 때 배치 만료 날짜를 확인하는 방법을 변경합니다. 이 기능을 사용하면 생산 BOM 라인 또는 배치 주문 공식 라인에 설정된 대로 배치 만료 날짜가 계획된 소비 날짜(원자재 날짜)에 대해 검증됩니다. 이 기능이 비활성화되면 배치 만료 날짜는 이전과 같이 생산 또는 배치 주문의 계획된 배송 날짜와 비교하여 검증됩니다. |
| 영업 및 마케팅 | 연령에 따라 판매 업데이트 기록 정리 | 이 기능을 사용하면 **판매 업데이트 내역 정리** 정기 작업을 실행할 때 보관할 최대 레코드 기간을 설정할 수 있습니다. 오래된 기록은 삭제됩니다. 기간은 항상 작업이 실행된 날짜를 기준으로 계산되기 때문에 주기적으로 작업을 실행하도록 설정할 때 유용합니다. 이 기능이 없으면 가장 오래된 기록의 특정 날짜만 보관하도록 설정할 수 있습니다. |
| 영업 및 마케팅 | "상위 100" 고객 보고서 성능 향상 | 이 기능은 사용자 지정 쿼리를 허용하는 대신 항상 모든 고객(의도된 용도)에 대해 보고서를 실행하여 **상위 100개** 고객 보고서의 성능을 향상시킵니다. 이 기능이 활성화되면 **상위 100개** 보고서 대화 상자에서 모든 **포함할 레코드** 설정이 비활성화됩니다. |
| 창고 관리 | 아웃바운드 주문을 창고로 릴리스하기 위한 스케일 유닛 지원 | 이 기능이 활성화되면 아웃바운드 주문이 허브에서 주문이 이행될 배율 단위로 직접 해제될 수 있습니다. |

## <a name="new-and-updated-documentation-resources"></a>신규 및 업데이트된 문서 리소스

최근에 다음 도움말 항목을 추가하거나 크게 업데이트했습니다. 이러한 항목은 이전 섹션에 나열된 것처럼 이 릴리스에 추가된 새 기능과 반드시 관련이 있는 것은 아닙니다. 그러나 기존 기능을 최대한 활용하는 데 도움이 될 수 있습니다.

| 기능 영역 | 신규 또는 업데이트된 토픽 |
|---|---|
| 엔지니어링 변경 관리 | [엔지니어링 특성 및 엔지니어링 특성 검색](../engineering-change-management/engineering-attributes-and-search.md)은 이제 엔지니어링 특성 상속이 작동하는 방식을 설명합니다. |
| 기준 계획 | [수요 예측을 사용한 기준 계획](../master-planning/planning-optimization/demand-forecast.md) 및 [예측 감소 키](../master-planning/reduction-keys.md)는 이제 감소 키를 사용하는 방법에 대한 추가 정보를 제공합니다. |
| 기준 계획 | 이제 [품목에 대한 안전 재고 처리](../master-planning/safety-stock-replenishment.md)에서 최소/최대 키 사용에 대한 자세한 정보를 제공합니다. |
| 기준 계획 | [재고 예측](../master-planning/inventory-forecast.md)은 이제 예측 할당에 대한 추가 정보를 제공합니다. |
| 기준 계획 | [공급 일정](../master-planning/supply-schedule.md) |
| 창고 관리 | [글로벌 모바일 디바이스 매개 변수](../warehousing/mobile-device-parameters.md) |
| 창고 관리 | [앵커링](../warehousing/anchoring.md) |
| 영업 및 마케팅 | 이제 [내부 거래 설정](../sales-marketing/intercompany-trade-set-up.md) 및 관련 항목부터 시작하여 내부 거래에 대해 자세히 설명합니다. |
| 재고 관리 | [재고 가시성 추가 기능 개요](../inventory/inventory-visibility.md) 및 관련 항목을 시작으로 재고 가시성 설명서가 확장 및 업데이트되었습니다. |

## <a name="additional-resources"></a>추가 리소스

### <a name="platform-updates-for-finance-and-operations-apps"></a>금융 및 운영 앱용 플랫폼 업데이트

Microsoft Dynamics 365 Supply Chain Management 10.0.23에는 플랫폼 업데이트가 포함됩니다. 자세히 알아보려면 [금융 및 운영 앱 버전 10.0.23에 대한 플랫폼 업데이트(2021년 11월)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-23.md)를 참조하세요.

### <a name="bug-fixes"></a>버그 수정

10.0.23의 일부인 각 업데이트에 포함된 버그 수정에 대한 정보는 LCS(Lifecycle Services)에 로그인하여 [KB 문서](https://fix.lcs.dynamics.com/Issue/Details?bugId=627874&dbType=3&qc=9b7e01944eb8b43f9c3aac4be26811c27be205847d6d2a240424f34f7e722910)를 참조하세요.

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
