---
title: Dynamics 365 Supply Chain Management 버전 10.0.19의 새로운 기능 또는 변경된 기능(2021년 6월)
description: 이 토픽에서는 Dynamics 365 Supply Chain Management 10.0.19의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 03ed2d52f44bd38910b01ffbd3767f750da2cbf8
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2021
ms.locfileid: "8449599"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-version-10019-june-2021"></a>Dynamics 365 Supply Chain Management 버전 10.0.19의 새로운 기능 또는 변경된 기능(2021년 6월)

[!include [banner](../includes/banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 버전 10.0.19의 새로 추가되거나 변경된 기능에 관해 나열합니다. 이 버전의 빌드 번호는 10.0.837이며 다음과 같이 확인할 수 있습니다.

- **프리뷰 릴리스:** 2021년 4월
- **릴리스 일반 공급(자체 업데이트):** 2021년 6월
- **릴리스 일반 공급(자동 업데이트):** 2021년 6월

## <a name="features-included-in-this-release"></a>이번 릴리스에 포함된 기능

다음 표에는 이 릴리스에 포함된 기능이 나열되어 있습니다. *기능* 열은 각 기능의 공식 릴리스 날짜를 볼 수 있는 [릴리스 계획](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features)에 대한 링크를 제공합니다. *추가 정보* 열은 관련 문서에 대한 자세한 정보 및/또는 링크를 제공합니다.

이러한 기능의 대부분은 사용하기 전에 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 사용하여 활성화해야 합니다.

| 기능 영역 | 기능 | 추가 정보 |
|---|---|---|
| 재고&nbsp;및&nbsp;물류 | [공급업체가 제출한 은행 세부정보 승인 및 저장](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/approve-save-vendor-submitted-bank-details) | [공급업체 은행 계좌 정보 유지 관리](../../finance/accounts-payable/maintain-vendor-bank-info.md) |
| 재고 및 물류 | [담당자 데이터 엔터티 내보내기 최적화](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | 이 기능이 활성화되면 참조된 데이터를 변경해도 관련 연락처가 다음 증분 내보내기에 포함되지 않습니다. 이 기능이 비활성화되면 참조된 데이터를 변경해도 관련 연락처가 다음 증분 내보내기에 포함됩니다. |
| 재고 및 물류 | [저울 단위를 사용하여 창고 실행 기능을 점진적으로 향상](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[메시지 프로세서 메시지](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[창고 재고 조정](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[클라우드 및 에지 스케일 유닛을 위한 창고 관리 워크로드](../cloud-edge/cloud-edge-workload-warehousing.md) |
| 재고 및 물류 | [판매 견적 페이지의 문서 소개 및 문서 결론 필드에 대한 조회 기능](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | 이 기능은 **판매 견적** 페이지의 **문서 소개** 및 **문서 결론** 필드에 대한 조회 기능을 추가합니다.<br><br>기본적으로 이 기능은 켜져 있습니다. |
| 재고 및 물류 | [맞춤형 하드웨어에서 에지 스케일 유닛으로 창고 실행](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [LBD를 사용하여 맞춤형 하드웨어에 에지 스케일 유닛 배포](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| 제조 | [맞춤형 하드웨어에서 에지 스케일 유닛으로 제조 실행](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [LBD를 사용하여 맞춤형 하드웨어에 에지 스케일 유닛 배포](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| 계획 | 쿼리 기반 계획 주문 확정 | [확정 계획 주문](../master-planning/planning-optimization/planned-order-firming.md) |
| 제품 정보 관리 | [변형 제안 페이지 개선 사항](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [미리 정의된 제품 변형 생성](../pim/tasks/create-predefined-product-variants.md) |

## <a name="feature-enhancements-included-in-this-release"></a>이번 릴리스에 포함된 기능 개선 사항

다음 표에는 이 릴리스에 포함된 기능 개선 사항이 나열되어 있습니다. 이들 각각은 기존 기능을 점진적으로 개선합니다. 개선 사항일 뿐이므로 [릴리스 계획](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features)에 나열되지 않습니다. 그러나 이러한 개선 사항이 기존 사용자 지정 또는 기본 설정과 충돌하지 않도록 하기 위해 각 기능은 기본적으로 해제되어 있습니다(달리 명시되지 않는 한). 이러한 기능을 사용하려면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 명시적으로 활성화해야 합니다.

| 모듈 | 기능&nbsp;관리의&nbsp;기능&nbsp;이름 | 추가 정보 |
|---|---|---|
| 영업 및 마케팅 | 판매 내역 정리 실적 개선 | 판매 업데이트가 많은 환경에서 판매 내역 정리를 자주 실행하지 않으면 시간이 오래 걸릴 수 있습니다. 기간을 줄이고 안정성을 개선하기 위해 이 기능은 정리를 제한된 기간 동안 실행되는 배치로 분할합니다. 가능한 경우 데이터베이스 기능을 활용하여 잠금을 최소화하고 정리 중 트랜잭션 테이블 조인을 방지합니다. 자세한 내용은 [판매 내역 정리 성능 개선 사항](../sales-marketing/sales-update-history-cleanup-performance-improvements.md)을 참조하세요. |
| 영업 및 마케팅 | 내부 거래 주문에 대해 요청된 입고 날짜를 확인 날짜로 업데이트합니다. | 이 기능을 사용하면 회사 간 직접 배송을 사용할 때 판매 및 구매 날짜 필드 값이 어떻게 되는지 제어할 수 있습니다. 시스템이 요청된 날짜를 업데이트할지 아니면 업데이트를 건너뛸지 선택할 수 있습니다. 업데이트를 건너뛰면 요청한 날짜가 고객이 요청한 날짜를 나타냅니다. 업데이트를 활성화하면 요청된 날짜(배송 날짜 제어를 사용할 때)는 처음에 고객이 요청한 것을 나타냅니다. *없음* 과 다른 경우 배달 날짜 제어는 처음에 요청한 것보다 우선합니다. 내부 거래 공급업체 또는 고객 설정에서 **확인 날짜 설정과 함께 새로운 업데이트 요청 수신 날짜** 를 사용하여 이 옵션을 설정할 수 있습니다.<br><br>이 기능이 비활성화되면 시스템은 배송 날짜 제어 규칙에 따라 원래 판매 주문의 요청된 입고 날짜를 덮어쓰지만 요청한 배송 날짜는 그대로 유지됩니다. |
| 창고 관리 | 창고로 출고 시 가장 가까운 판매 단위로 수량 반올림 | 이 기능은 출고 시 주문 수량을 창고로 제한할 수 있는 옵션을 추가합니다. 활성화하면 주문 수량은 가장 가까운 전체 판매 단위로 내림되며 1개 미만의 판매 단위에 대한 수량을 포함하는 주문은 릴리스가 거부됩니다. |
| 창고 관리 | 조직 전반의 "작업 생성 일정" 웨이브 방식 | 이 기능을 활성화하면 *일정 작업 생성* 웨이브 방법이 모든 법인에서 병렬로 실행되도록 구성됩니다. 몇 가지 추가 설정도 영향을 받습니다. 자세한 내용은 [웨이브 중 작업 생성 예약](../warehousing/configure-wave-schedule-work-creation.md)을 참조하세요. |

## <a name="new-and-updated-documentation-resources"></a>신규 및 업데이트된 문서 리소스

최근에 다음 도움말 항목을 추가하거나 크게 업데이트했습니다. 이전 섹션에 나열된 것처럼 이 릴리스에 추가된 새로운 기능과 반드시 관련이 있는 것은 아니지만 기존 기능을 최대한 활용하는 데 도움이 될 수 있습니다.

| 기능 영역 | 신규 또는 업데이트된 토픽 |
|---|---|
| 엔지니어링 변경 관리 | [엔지니어링 변경 관리 FAQ](../engineering-change-management/change-management-faq.md) |
| 조달 및 소싱 | [공급업체의 카테고리 요청](../procurement/category-requests-from-vendors.md) |
| 제품 정보 관리 | [측정 단위 관리](../pim/tasks/manage-unit-measure.md)<br><br>[제품 구성 모델 계산](../pim/config-model-calculations.md) |
| 생산 관리 | [작업 ID에 대한 통합 번호 시퀀스](../production-control/unified-job-ids.md) |
| 운송 관리 | [LTL 클래스](../transportation/ltl-class.md)<br><br>[NMFC 코드](../transportation/nmfc-codes.md) |
| 창고 관리, 웨이브 생성 및 처리 | [웨이브 생성 및 처리](../warehousing/wave-processing.md)<br><br>[웨이브 처리를 위한 창고 매개 변수](../warehousing/wave-warehouse-parameters.md)<br><br>[웨이브 템플릿](../warehousing/wave-templates.md)<br><br>[웨이브 할당](../warehousing/wave-allocation-method.md)<br><br>[웨이브 중 작업 생성 일정 잡기](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[컨테이너화](../warehousing/wave-containerization.md)<br><br>[웨이브 실행 알림](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>추가 리소스

### <a name="platform-updates-for-finance-and-operations-apps"></a>금융 및 운영 앱용 플랫폼 업데이트

Microsoft Dynamics 365 Supply Chain Management 10.0.19에는 플랫폼 업데이트가 포함됩니다. 자세히 알아보려면 [금융 및 운영 앱 버전 10.0.19에 대한 플랫폼 업데이트(2021년 6월)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md)를 참조하세요.

### <a name="bug-fixes"></a>버그 수정

10.0.19의 일부인 각 업데이트에 포함된 버그 수정에 대한 정보는 LCS(Lifecycle Services)에 로그인하여 [KB 문서](https://fix.lcs.dynamics.com/Issue/Details?bugId=575415)를 참조하세요.

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
