---
title: Dynamics 365 Supply Chain Management 10.0.25 프리뷰(2022년 4월)
description: 이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 10.0.25의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: kamaybac
ms.date: 03/14/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 26f67be72948e33738cf805b541d3c7e701f8dba
ms.sourcegitcommit: a8f4d7d21d9af17d80b1213e5e1a81f42fb8b928
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2022
ms.locfileid: "8450127"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10025-april-2022"></a>Dynamics 365 Supply Chain Management 10.0.25 프리뷰(2022년 4월)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 버전 10.0.25 프리뷰의 새로 추가되거나 변경된 기능에 관해 나열합니다. 이 버전의 빌드 번호는 10.0.1149이며 다음과 같이 확인할 수 있습니다.

- **릴리스 프리뷰:** 2022년 2월
- **릴리스 일반 공급(자체 업데이트):** 2022년 3월
- **릴리스 일반 공급(자동 업데이트):** 2022년 4월

## <a name="features-included-in-this-release"></a>이번 릴리스에 포함된 기능

다음 표에는 이 릴리스에 포함된 기능이 나열되어 있습니다. 이 항목이 처음 게시된 후 빌드에 포함된 기능을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 기능 영역 | 기능 | 추가 정보 |  에 의해 활성화됨 |
|---|---|---|---|
| 재고&nbsp;및&nbsp;물류 | [위험 물질 강화](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/hazardous-materials-enhancements) | 업데이트 예정 | 기능 관리:<br>*위험 물질 강화* |
| 재고&nbsp;및&nbsp;물류 | [포장 스테이션 포장 작업](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/packing-work-packing-stations) | 업데이트 예정 | 기능 관리:<br>*포장 스테이션 포장 작업* |
| 재고&nbsp;및&nbsp;물류 | [GS1 형식 표준을 사용하여 창고의 바코드 스캔](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | [GS1 바코드 및 QR 코드](../warehousing/gs1-barcodes.md) | 기능 관리:<br>*GS1 바코드 스캔* |
| 제조 | [생산 현장 실행 인터페이스의 자재 소비 및 예약](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/material-consumption-reservations-production-floor-execution-interface) | [작업자가 생산 현장 실행 인터페이스를 사용하는 방법](../production-control/production-floor-execution-use.md) | 기능 관리:<br>*(프리뷰) 생산 현장 실행 인터페이스(비 WMS)에 재료 소비 등록*<br><br>및/또는:<br><br>기능 관리:<br>*(프리뷰) 생산 현장 실행 인터페이스(WMS 활성화됨)에 재료 소비 등록* |
| 제조 | [배율 단위에 재료 소비 등록](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/register-material-consumption-scale-units) | [클라우드 및 에지 스케일 유닛을 위한 제조 실행 워크로드](../cloud-edge/cloud-edge-workload-manufacturing.md) | 기능 관리:<br>*모바일 앱에서 배율 단위에 자재 소비 등록* |
| 계획 | [계획 최적화 중앙 집중식 달력 유지 관리](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-centralized-calendar-maintenance) | [캘린더 및 마스터 플래닝](../master-planning/supply-chain-calendars-master-planning.md) | 기본적으로 활성화되어 있음 |
| 계획 | [기존 공급을 최적화하기 위한 최적화 제안 계획](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-suggestions-optimize-existing-supply) | [작업 메시지](../master-planning/action-messages.md) | 기본적으로 활성화되어 있음 |
| 계획 | 계획 주문 간소화 | [계획 주문 간소화](../master-planning/planning-optimization/planned-orders-simplified.md ) | 기능 관리:<br>*계획 주문 간소화* |

## <a name="feature-enhancements-included-in-this-release"></a>이번 릴리스에 포함된 기능 개선 사항

다음 표에는 이 릴리스에 포함된 기능 개선 사항이 나열되어 있습니다. 이러한 개선 사항 각각은 기존 기능을 점진적으로 개선합니다. 개선 사항일 뿐이므로 [릴리스 계획](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features)에 나열되지 않습니다. 그러나 이러한 개선 사항이 기존 사용자 지정 또는 기본 설정과 충돌하지 않도록 하기 위해 각 기능은 기본적으로 해제되어 있습니다(달리 명시되지 않는 한).

이러한 기능을 켜거나 끄려면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 수행해야 합니다.

| 모듈 | 기능 관리의 기능 이름 | 추가 정보 |
|---|---|---|
| 재고 및 창고 관리 | (폴란드) 여러 SAD 송장을 하나의 SAD에서 하나의 구매 주문 라인에 연결할 수 있습니다. | 이 기능을 사용하면 구매 발주 라인을 분할하고 단일 관리 문서(SAD)에 연결할 수 있습니다. 이러한 구매 발주 라인이 여러 다른 송장(예: 다른 선적)에 대해 전기될 때입니다. |
| 조달 및 소싱 | 회계 일자별로 여러 구매 주문을 단일 구매 요청으로 통합 | 이 기능을 사용하면 여러 구매 요청의 회계 날짜가 다른 경우 여러 구매 요청을 단일 구매 주문으로 통합할 수 있습니다. 구매 발주 생성 및 수요 통합 구매 정책 규칙을 설정하여 구매 발주 레벨에서 회계 일자별로 구매요청 라인을 그룹화하기 위한 결정을 자동화할 수 있습니다. 회계 날짜가 예산 예약 및 예산가집행에 사용되기 때문에 예산 통제가 활성화된 경우 회계 날짜별 구매 발주 통합은 지원되지 않습니다. 따라서 구매 요청에서 구매 주문으로 전환하는 동안 보관해야 합니다. |
| 조달 및 소싱 | 레거시 기본 RFQ 응답 필드 설정 표시 | 이 기능은 이전에 사용자 인터페이스에서 제거되었던 레거시 기본 견적 요청(RFQ) 응답 필드 설정을 다시 도입합니다. 이러한 설정은 즉시 사용할 수 있는 기능을 제공하지 않지만 필요에 따라 제공하도록 사용자 정의할 수 있습니다. 조직에서 이미 기본 RFQ 응답 필드 설정에 대한 기능을 추가했거나 추가할 계획인 경우 이 기능을 활성화하세요. 이 기능이 활성화되면 **조달 및 소싱 매개 변수** 페이지로 이동하여 **견적 요청** 탭을 열고 **견적 응답 필드에 대한 기본 요청** 을 선택하여 설정에 액세스할 수 있습니다. |
| 조달 및 소싱 | 구매 주문서의 활성 차원 링크 재무 차원이 있는 공급업체의 재무 차원 병합 | 이 기능을 사용하면 재무 차원과 사이트 인벤토리 차원 간의 링크를 설정한 경우 구매 요청 승인 후 활성 차원 링크 재무 차원이 있는 공급업체의 재무 차원을 병합할 수 있습니다. 구매 주문 생성 및 수요 통합 구매 정책 규칙은 구매 주문 헤더 레벨에서 활성 차원 링크 재무 차원이 있는 공급업체의 재무 차원 병합에 대한 결정을 유도하도록 설정할 수 있습니다. |
| 생산 관리 | (러시아) 생산 공식/BOM 및 생산 시 자동 GTD 예약/소비에 대한 기본 위치 설정 활성화 | 이 기능을 사용하면 수입 원자재로 생산하기 위한 추가 옵션을 사용할 수 있습니다(러시아어 현지화만 해당).<ul><li>자원 그룹과 창고 모두에서 생산 공식 및 BOM에 대한 자동 기본 위치를 설정하는 옵션입니다.</li><li>비 WMS 예약 알고리즘에 따라 WMS 활성화 창고에서 *GTD 번호* 차원에 의한 원자재 자동 예약. 이는 **작업 생성 방법** 이 *없음* 으로 설정된 *원자재 피킹* 에 대한 작업 정책이 존재하고 창고, 위치 및 품목 번호 설정이 생산(배치) 주문의 재고 트랜잭션과 일치하는 경우에 적용됩니다.</li><li>앞에서 설명한 획득 예약에 따라 불출 목록 게시 시 *GTD 번호* 차원에 따른 원자재 자동 소비.</li></ul> |
| 창고 관리 | (프리뷰) 인바운드 및 아웃바운드 웨어하우스 주문에 대한 배율 단위 지원 | 이 기능을 사용하면 시스템이 창고로 출고 프로세스 중에 아웃바운드 창고 주문을 생성하고 이전 주문이 배송된 상태로 전기될 때 인바운드 창고 주문을 생성합니다. 그런 다음 시스템은 각 인바운드 또는 아웃바운드 창고 주문을 주문 배송 또는 수령을 담당하는 저울 단위와 동기화합니다. 이 기능을 활성화한 후에는 창고 실행 워크로드를 업그레이드해야 합니다. 자세한 내용은 [클라우드 및 에지 스케일 유닛을 위한 창고 관리 워크로드](../cloud-edge/cloud-edge-workload-warehousing.md)를 참조하세요.<br><br>이 기능을 사용하려면 *ASN에서 작업 분리* 기능이 필요하며 창고 관리 모바일 앱에서 번호판 수신 프로세스를 사용하여 이전 주문을 수신하는 기능을 활성화합니다. |

## <a name="feature-state-changes-in-this-release"></a>이 릴리스의 기능 상태 변경 사항

다음 표에는 10.0.25부터 필수 또는 기본적으로 설정된 기능이 나열되어 있습니다. 이러한 모든 기능은 10.0.25로 업데이트하는 즉시 시스템에서 자동으로 켜집니다. 필수 기능은 끌 수 없지만 기본적으로 켜져 있는 기능은 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 사용하여 계속 끌 수 있습니다.

또한 이 표에는 이전에 공개 미리 보기에 있었지만 10.0.25에서 일반적으로 사용 가능하도록 변경된 기능이 나열되어 있습니다. 즉, 이제 프로덕션 환경에서 사용하는 것이 좋습니다. 이러한 기능은 달리 명시되지 않는 한 기본적으로 꺼져 있으므로 사용하려면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 사용하여 활성화해야 합니다.

| 모듈 | 기능 이름 | 기능 상태 |
| --- | --- | --- |
| 자산 관리 | [유지 관리 계획을 실행하는 동안 작업 주문을 그룹화하기 위한 규칙 적용](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md) | 정식 제공 |
| 자산 관리 | [카운터 기반 유지 관리 개선 사항](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md) | 정식 제공 |
| 비용 관리 | [비용 계산 수준](../cost-management/cost-calculation-level.md) | 정식 제공 |
| 비용 관리 | 재고 마감 취소에 대한 사용자 정의 배치 번호 설정 활성화 | 정식 제공 |
| 비용 관리 | [재고 마감 진행 내역](whats-new-scm-10-0-21.md) | 정식 제공 |
| 비용 관리 | [재고 표준 원가 재평가를 위한 재무 차원 기본값 설정 옵션](../cost-management/manage-standard-cost-updates.md) | 정식 제공 |
| 비용 관리 | 재고 가치 보고서 데이터 정리 | 기본적으로 켜짐 |
| 비용 관리 | [재고 가치 보고서 스토리지](../cost-management/inventory-value-report-storage.md) | 기본적으로 켜짐 |
| 비용 관리 | 그리드에 재고 마감 로그 표시 | 기본적으로 켜짐 |
| 엔지니어링 변경 관리 | [기존 제품에 대한 변경 관리 활성화](../engineering-change-management/change-management-existing-products.md) | 기본적으로 켜짐 |
| 엔지니어링 변경 관리 | [엔지니어링 변경 관리](../engineering-change-management/product-engineering-overview.md) | 기본적으로 켜짐 |
| 엔지니어링 변경 관리 | [생산을 위한 엔지니어링 알림](../engineering-change-management/engineering-change-management.md) | 기본적으로 켜짐 |
| 엔지니어링 변경 관리 | [엔지니어링 변경 관리를 위한 향상된 특성 상속](../engineering-change-management/engineering-attributes-and-search.md) | 기본적으로 켜짐 |
| 엔지니어링 변경 관리 | [공식 및 해당 성분의 변경 사항 관리](../engineering-change-management/manage-formula-changes.md) | 기본적으로 켜짐 |
| 엔지니어링 변경 관리 | [제품 준비 확인](../engineering-change-management/product-readiness.md) | 기본적으로 켜짐 |
| 엔지니어링 변경 관리 | [엔지니어링 제품에 대한 변형 생성](../engineering-change-management/engineering-variants.md) | 기본적으로 켜짐 |
| 재고 및 창고 관리 | BOM 라인에서 BOM 버전으로 이동 | 필수 |
| 기준 계획 | [계획된 대량 및 포장 배치 주문에 대한 배치 가능한 확정 및 통합](whats-new-scm-10-0-20.md) | 정식 제공 |
| 기준 계획 | 유지 관리가 포함된 리소스 계획 | 정식 제공 |
| 기준 계획 | 마스터 플랜 설정 마법사 기능 활성화 | 필수 |
| 기준 계획 | [수요 예측 세부 정보에 대한 예측 모델 선택](../master-planning/manual-adjustments-baseline-forecast.md) | 필수 |
| 기준 계획 | [기준 계획 진행 상황 시각화](../master-planning/tasks/monitor-master-planning-run.md) | 필수 |
| 기준 계획 | [계획 주문의 병렬 확정](../master-planning/planning-optimization/planned-order-firming.md) | 필수 |
| 기준 계획 | [필터링으로 계획 주문 확정](../master-planning/planning-optimization/planned-order-firming.md) | 기본적으로 켜짐 |
| 기준 계획 | [계획된 주문에 대한 저장된 보기](saved-views-scm.md) | 기본적으로 켜짐 |
| 조달 및 소싱 | 구매 요청 분배 재설정 버튼 비활성화 | 정식 제공 |
| 조달 및 소싱 | [조달 관련 워크플로 재설정 활성화](whats-new-scm-10-0-20.md) | 정식 제공 |
| 조달 및 소싱 | 일괄 공급업체 협업에서 승인된 구매 주문을 확인하는 기능 | 필수 |
| 조달 및 소싱 | 구매 계약 종료 상태 | 필수 |
| 조달 및 소싱 | 구매 계약과 연관된 PO 송장에 라인 추가 | 기본적으로 켜짐 |
| 조달 및 소싱 | 제품 영수증 기장 페이지에 주문 수량 필드 추가 | 기본적으로 켜짐 |
| 조달 및 소싱 | [공급업체가 공급업체 협업을 통해 조달 범주를 신청할 수 있도록 허용](../procurement/category-requests-from-vendors.md) | 기본적으로 켜짐 |
| 조달 및 소싱 | 구매 주문 금액의 시작 및 끝 금액 | 기본적으로 켜짐 |
| 조달 및 소싱 | 사이트 및 창고에 대한 비용 설정 | 기본적으로 켜짐 |
| 조달 및 소싱 | 연간 관세 기준 구매 관세 계산 사용 | 기본적으로 켜짐 |
| 조달 및 소싱 | [구매 계약 담당자](../procurement/purchase-agreements.md) | 기본적으로 켜짐 |
| 조달 및 소싱 | [구매 주문에 대한 저장된 보기](saved-views-scm.md) | 기본적으로 켜짐 |
| 제품 정보 관리 | [기본 주문 수량에 대한 엄격한 검증](../production-control/default-order-settings.md) | 필수 |
| 제품 정보 관리 | 시간 초과를 피하기 위한 자제 명세서 보고서 사전 처리 | 기본적으로 켜짐 |
| 제품 정보 관리 | 항목 템플릿을 사용할 때 별도로 기본 재무 차원 | 기본적으로 켜짐 |
| 제품 정보 관리 | 항목 템플릿에 대한 제품 차원 그룹 활성화 | 기본적으로 켜짐 |
| 제품 정보 관리 | 명명법에 따라 제품 변형 이름 재생성 | 기본적으로 켜짐 |
| 제품 정보 관리 | [변형 제안 페이지 개선 사항](../pim/tasks/create-predefined-product-variants.md) | 기본적으로 켜짐 |
| 생산 관리 | 향상된 생산 공칭 무게 수량 피킹 | 정식 제공 |
| 생산 관리 | 작업 카드 터미널 페이지에 휴식 중지 단추가 추가되었습니다. | 필수 |
| 생산 관리 | [작업 카드 디바이스에서 완료로 보고할 때 번호판 번호 자동 생성 사용](../production-control/production-floor-execution-configure.md) | 필수 |
| 생산 관리 | 외주 품목의 부분 입고를 활성화하고 공급업체 유형의 BOM 라인에 대한 스크랩 계산 문제를 수정합니다. | 필수 |
| 생산 관리 | [작업 카드 디바이스 및 작업 카드 디바이스를 살균할 수 있도록 잠그는 기능](../production-control/production-floor-execution-configure.md) | 필수 |
| 생산 관리 | 작업 승인 및 이전 대화 상자 개선 사항 | 필수 |
| 생산 관리 | [작업 카드 디바이스에 추가된 완료 보고용 번호판](../production-control/production-floor-execution-configure.md) | 필수 |
| 생산 관리 | [작업 카드 디바이스에서 레이블 인쇄](../production-control/production-floor-execution-configure.md) | 필수 |
| 생산 관리 | [생산 현장 실행](../production-control/production-floor-execution-configure.md) | 필수 |
| 생산 관리 | [생산 현장 실행 인터페이스를 위한 자산 관리 기능](../production-control/production-floor-execution-configure.md) | 기본적으로 켜짐 |
| 생산 관리 | [생산 현장 실행 인터페이스의 작업 검색](../production-control/production-floor-execution-configure.md) | 기본적으로 켜짐 |
| 생산 관리 | [기본 프로덕션 예약 재정의](../production-control/override-default-reservation-principle.md) | 기본적으로 켜짐 |
| 생산 관리 | [생산 현장 실행 인터페이스에서 전체 일련 번호, 배치 및 번호판 번호 표시](whats-new-scm-10-0-21.md) | 기본적으로 켜짐 |
| 영업 및 마케팅 | [판매 주문 내역 성능 향상](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-details-performance-enhancement) | 정식 제공 |
| 영업 및 마케팅 | 판매 견적 내역 성능 향상 | 정식 제공 |
| 영업 및 마케팅 | 판매 주문 참조 데이터 내보내기 정책 | 필수 |
| 영업 및 마케팅 | [판매 주문에서 구매 주문 라인 삭제 정책](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-order-purchase-order-line-deletion-policy) | 필수 |
| 영업 및 마케팅 | [판매 견적 참조 데이터 내보내기 정책](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy)| 필수 |
| 영업 및 마케팅 | [담당자 데이터 엔터티 내보내기 최적화](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization) | 기본적으로 켜짐 |
| 영업 및 마케팅 | 판매 견적 문서 소개 및 문서 결론 필드에 대한 조회 활성화 | 기본적으로 켜짐 |
| 영업 및 마케팅 | ["상위 100" 고객 보고서 성능 향상](whats-new-scm-10-0-23.md) | 기본적으로 켜짐 |
| 영업 및 마케팅 | 예상 고객 잔액 다시 계산 | 기본적으로 켜짐 |
| 영업 및 마케팅 | [공칭 무게가 있거나 없는 소수점 이하 자릿수가 있는 판매 반품 주문 라인 등록](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/sales-return-order-line-registration-decimal-precision-without-catch-weight) | 기본적으로 켜짐 |
| 영업 및 마케팅 | [영업 및 마케팅에 대한 저장된 보기](saved-views-scm.md) | 기본적으로 켜짐 |
| 영업 및 마케팅 | 단일 클릭 판매 주문 확인 | 기본적으로 켜짐 |
| 창고 관리 | [위치 지시문이 있는 크로스 도킹 템플릿](../warehousing/planned-cross-docking.md) | 정식 제공 |
| 창고 관리 | [차단된 재고를 샘플링하는 품질 주문에서 예상되는 수령을 비활성화합니다.](../inventory/inventory-blocking.md) | 정식 제공 |
| 창고 관리 | 번호판 수신 내역 | 정식 제공 |
| 창고 관리 | [자재 취급 장비 인터페이스](../warehousing/mhax.md) | 정식 제공 |
| 창고 관리 | [창고로 출고 시 가장 가까운 판매 단위로 수량 반올림](whats-new-scm-10-0-19.md) | 정식 제공 |
| 창고 관리 | 창고 앱 작업 목록에 대한 배율 단위 지원 | 정식 제공 |
| 창고 관리 | 배송 웨이브 라벨 세부정보 | 정식 제공 |
| 창고 관리 | [포장 스테이션에서 컨테이너를 닫거나 다시 열 때 더 빠른 API 사용](whats-new-scm-10-0-21.md) | 정식 제공 |
| 창고 관리 | [보충 작업을 위해 선택한 템플릿 검증](whats-new-scm-10-0-20.md) | 정식 제공 |
| 창고 관리 | 보충 템플릿이 기존 즉시 보충 작업을 사용하도록 허용(단위 간) | 필수 |
| 창고 관리 | WHS 사용자 생성 시 GUID 자동 할당 | 필수 |
| 창고 관리 | 로드 항목을 받는 동안 창고 앱에서 제품 변형 및 추적 규모 캡처 | 필수 |
| 창고 관리 | [추적 치수로 제어되는 품목의 재고 상태 변경](../inventory/inventory-statuses.md) | 필수 |
| 창고 관리 | [작업에서 작업 풀 변경](../warehousing/change-work-pool-on-work.md) | 필수 |
| 창고 관리 | [클러스터 위치 가득 참](../warehousing/cluster-position-full.md) | 필수 |
| 창고 관리 | [클러스터 보관 기능](../warehousing/putaway-clusters.md) | 필수 |
| 창고 관리 | [확인 및 이전](../warehousing/confirm-and-transfer.md) | 필수 |
| 창고 관리 | [일괄 작업에서 아웃바운드 배송 확인](../warehousing/confirm-outbound-shipments-from-batch-jobs.md) | 필수 |
| 창고 관리 | [모바일 디바이스에서 수신 요약 페이지 표시 여부 제어](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | 필수 |
| 창고 관리 | [수동 재고 이동 작업의 지연 처리](../warehousing/deferred-processing-manual-inventory-movement.md) | 필수 |
| 창고 관리 | 웨이브 하중 건물 템플릿 요구 사항을 충족하지 않는 하중 생성을 허용하지 마세요. | 필수 |
| 창고 관리 | [향상된 번호판 레이블 레이아웃](../warehousing/document-routing-layout-for-license-plates.md) | 필수 |
| 창고 관리 | [다중 SKU 위치 지시문에 대한 모든 작업 평가](../troubleshooting/warehousing/evaluate-multiple-location-directive-actions.md) | 필수 |
| 창고 관리 | "모든 로드" 및 "로드 세부 정보" 페이지에서 총 값 필드 숨기기 | 필수 |
| 창고 관리 | 번호판 라벨 빌드 구성 | 필수 |
| 창고 관리 | 관리자 또는 이와 유사한 신뢰할 수 있는 사용자를 위한 로드 라인 수동 수정 | 필수 |
| 창고 관리 | [위치 번호판 위치 지정](../warehousing/location-license-plate-positioning.md) | 필수 |
| 창고 관리 | [위치 제품 크기 혼합](../warehousing/location-product-dimension-mixing.md) | 필수 |
| 창고 관리 | 모바일 디바이스 인벤토리 이동 인벤토리 상태 필드를 편집 가능하게 만들기 | 필수 |
| 창고 관리 | 관리자 또는 이와 유사한 신뢰할 수 있는 사용자를 위한 수동 판매 라인 불출 서비스 | 필수 |
| 창고 관리 | [이전 주문 배송된 번호판을 대상 창고 이외의 다른 창고에서 사용하는 것을 방지합니다.](../warehousing/warehousing-mobile-device-app-license-plate-receiving.md) | 필수 |
| 창고 관리 | 모호한 'Loc/LP' 이름을 해결하라는 프롬프트 | 필수 |
| 창고 관리 | [품질 검사](../warehousing/quality-check.md) | 필수 |
| 창고 관리 | [새 창고 앱의 사용자 설정, 아이콘 및 단계 제목](../warehousing/install-configure-warehouse-management-app.md) | 필수 |
| 창고 관리 | [추가 위치 영역](../warehousing/additional-location-zones.md) | 기본적으로 켜짐 |
| 창고 관리 | [창고 앱에서 이전 주문 생성 및 처리](../warehousing/create-transfer-order-from-warehouse-app.md) | 기본적으로 켜짐 |
| 창고 관리 | 창고 모바일 디바이스에 대한 빠른 검증 가능 | 기본적으로 켜짐 |
| 창고 관리 | [창고 관리 현재고 정리 작업의 최대 실행 시간](../warehousing/onhand-cleanup.md) | 기본적으로 켜짐 |
| 창고 관리 | [아웃바운드 워크로드 시각화](../warehousing/outbound-workload-visualization.md) | 기본적으로 켜짐 |
| 창고 관리 | [창고 앱 이벤트 처리](../warehousing/warehouse-app-events.md) | 기본적으로 켜짐 |
| 창고 관리 | [적재 계획 워크벤치에 대한 저장된 보기](saved-views-scm.md) | 기본적으로 켜짐 |
| 창고 관리 | [작업 세부 정보 페이지에 대한 저장된 보기](saved-views-scm.md) | 기본적으로 켜짐 |
| 창고 관리 | [웨이브 처리를 위해 저장된 보기](saved-views-scm.md) | 기본적으로 켜짐 |
| 창고 관리 | [화물 처리를 위해 저장된 보기](saved-views-scm.md) | 기본적으로 켜짐 |
| 창고 관리 | [배송 처리를 위해 저장된 보기](saved-views-scm.md) | 기본적으로 켜짐 |
| 창고 관리 | [웨이브 일괄 작업 세부 정보](../warehousing/wave-processing.md) | 기본적으로 켜짐 |
| 창고 관리 | [웨이브 실행 알림](../warehousing/wave-execution-notifications.md) | 기본적으로 켜짐 |

## <a name="additional-resources"></a>추가 리소스

### <a name="platform-updates-for-finance-and-operations-apps"></a>금융 및 운영 앱용 플랫폼 업데이트

Microsoft Dynamics 365 Supply Chain Management 10.0.25에는 플랫폼 업데이트가 포함됩니다. 자세히 알아보려면 [금융 및 운영 앱 버전 10.0.25에 대한 플랫폼 업데이트(2022년 4월)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-25.md)를 참조하세요.

### <a name="bug-fixes"></a>버그 수정

10.0.25의 일부인 각 업데이트에 포함된 버그 수정에 대한 정보는 LCS(Lifecycle Services)에 로그인하여 [KB 문서](https://fix.lcs.dynamics.com/Issue/Details?bugId=654580&dbType=3&qc=3799fa965b008dd980d27cf740e4582e6384ec6601ae8a35b7eaec6f1287a868)를 참조하세요.

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 및 산업 클라우드: 2022 릴리스 웨이브 1 계획

비즈니스 앱 또는 플랫폼에서 예정된 기능과 최근에 출시된 기능이 궁금하신가요?

[Dynamics 365 및 산업 클라우드: 2022 릴리스 웨이브 1 계획](/dynamics365-release-plan/2022wave1/)을 확인하세요. 계획에 사용할 수 있는 단일 문서에 모든 세부 사항을 처음부터 끝까지, 위에서 아래로 캡처했습니다.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>제거 및 사용되지 않는 Supply Chain Management 기능

[Dynamics 365 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능](removed-deprecated-features-scm-updates.md) 항목은 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능에 대해 설명합니다.

- *제거된* 기능은 더 이상 제품에서 사용할 수 없습니다.
- *더 이상 사용되지 않는* 기능은 현재 개발 중이 아니며 향후 업데이트에서 제거될 수 있습니다.

제품에서 기능이 제거되기 전에, 지원 중단 알림은 제거 12개월 전에 [Dynamics 365 Supply Chain Management에서 제거되거나 더 이상 사용되지 않는 기능](removed-deprecated-features-scm-updates.md) 항목에 공지됩니다.

컴파일 시간에만 영향을 미치지만 샌드박스 및 프로덕션 환경과 바이너리 호환되는 호환성이 손상되는 변경의 경우 사용 중단 시간은 12개월 미만입니다. 일반적으로 컴파일러에 대해 수행해야 하는 기능 업데이트입니다.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
