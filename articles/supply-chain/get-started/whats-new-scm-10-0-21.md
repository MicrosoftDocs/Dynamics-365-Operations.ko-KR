---
title: Dynamics 365 Supply Chain Management 10.0.21의 새로운 기능 또는 변경된 기능(2021년 10월)
description: 이 토픽에서는 Dynamics 365 Supply Chain Management 10.0.21의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: kamaybac
ms.date: 10/28/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ec7fcb97bd46551846ccee13b369a1b02a589688
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449893"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10021-october-2021"></a>Dynamics 365 Supply Chain Management 10.0.21의 새로운 기능 또는 변경된 기능(2021년 10월)

[!include [banner](../includes/banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 버전 10.0.21의 새로 추가되거나 변경된 기능에 관해 나열합니다. 이 버전의 빌드 번호는 10.0.960이며 다음과 같이 확인할 수 있습니다.

- **프리뷰 릴리스:** 2021년 8월
- **릴리스 일반 공급(자체 업데이트):** 2021년 9월
- **릴리스 일반 공급(자동 업데이트):** 2021년 10월

## <a name="features-included-in-this-release"></a>이번 릴리스에 포함된 기능

다음 표에는 이 릴리스에 포함된 기능이 나열되어 있습니다. *기능* 열은 각 기능의 공식 릴리스 날짜를 볼 수 있는 [릴리스 계획](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)에 대한 링크를 제공합니다. *추가 정보* 열은 관련 문서에 대한 자세한 정보 및/또는 링크를 제공합니다.

이러한 기능의 대부분은 사용하기 전에 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 사용하여 활성화해야 합니다.

| 기능 영역 | 기능 | 추가 정보 |
|---|---|---|
| 재고&nbsp;및&nbsp;물류 | [Dynamics 365 Supply Chain Management용 Global Inventory Accounting 추가 기능](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/global-inventory-accounting-add-in-dynamics-365-supply-chain-management) | [Global Inventory Accounting 홈 페이지](../global-inventory-accounting/global-inventory-accounting-home.md) |
| 재고&nbsp;및&nbsp;물류 | [상계 계정에 연결된 코드를 사용하여 현재고 조정 전기](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/post-on-hand-adjustments-using-configurable-reason-codes-connected-offset-accounts) | [재고 집계 사유 코드](../warehousing/reason-codes-for-counting-journals.md) |
| 재고&nbsp;및&nbsp;물류 | [판매 견적 참조 데이터 내보내기 정책](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy) | 견적에서 참조하는 데이터 변경으로 인해 해당 견적(또는 라인)이 다음 증분 내보내기에 포함되는지 여부를 선택합니다. 이러한 견적이나 라인을 포함하지 않도록 선택하면 증분 내보내기가 더 빨리 실행됩니다.<br><br>이 기능은 **수취 계정 매개 변수** 페이지에 **변경 추적 중 판매 견적 참조 데이터 건너뛰기** 라는 설정을 추가합니다. |
| 재고&nbsp;및&nbsp;물류 | [봉인된 입찰](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sealed-bidding) | [RFQ에 대한 봉인된 입찰](../procurement/sealed-bidding.md) |
| 재고&nbsp;및&nbsp;물류 | [인벤토리 가시성 추가 기능에 대한 소프트 예약](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/soft-reservation-inventory-visibility-add-in) | [인벤토리 가시성 예약](../inventory/inventory-visibility-reservations.md) |
| 재고&nbsp;및&nbsp;물류 | [리베이트 관리를 위한 공제 및 캐치 웨이트 향상](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/deduction-catch-weight-enhancements-rebate-management) | [공제 워크벤치를 사용하여 공제 관리](../rebate-management/deduction-workbench.md )<br><br>[리베이트 처리, 검토 및 게시](../rebate-management/process-review-post.md)<br><br>[리베이트 관리 거래](../rebate-management/rebate-management-deals.md) |
| 재고&nbsp;및&nbsp;물류 | [창고 앱 단계 지침](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Warehouse Management 모바일 앱에 대한 단계 제목 및 지침 사용자 정의](../warehousing/mobile-app-titles-instructions.md) |
| 재고&nbsp;및&nbsp;물류 | [착륙 비용에 대한 작업 휴식 및 추적 업데이트](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/work-breaks-tracking-updates-landed-cost) | [보관 추적 업데이트](../landed-cost/update-tracking-putaway.md )<br><br>[미착 상품 처리](../landed-cost/in-transit-processing.md) |
| 기준 계획 | [계획 최적화를 위한 음수 일수](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/negative-days-support-planning-optimization) | [연기 허용 범위(음수일)](../master-planning/planning-optimization/delay-tolerance.md) |

## <a name="feature-enhancements-included-in-this-release"></a>이번 릴리스에 포함된 기능 개선 사항

다음 표에는 이 릴리스에 포함된 기능 개선 사항이 나열되어 있습니다. 이들 각각은 기존 기능을 점진적으로 개선합니다. 개선 사항일 뿐이므로 [릴리스 계획](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features)에 나열되지 않습니다. 그러나 이러한 개선 사항이 기존 사용자 지정 또는 기본 설정과 충돌하지 않도록 하기 위해 각 기능은 기본적으로 해제되어 있습니다(달리 명시되지 않는 한). 이러한 기능을 사용하려면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 명시적으로 활성화해야 합니다.

| 모듈 | 기능&nbsp;관리의&nbsp;기능&nbsp;이름 | 추가 정보 |
|---|---|---|
| 비용 관리 | 재고 마감 진행 내역 | 이 프리뷰 기능을 사용하면 재고 마감 진행 상황을 자세히 볼 수 있습니다. |
| 조달 및 소싱 | 여러 구매 요청이 워크플로에 있을 때 일반 예산 예약의 과소비 방지 | 이 프리뷰 기능은 사용자가 일반 예산 예약 라인의 잔여 잔액을 초과하는 구매 요청을 제출하고 승인할 때 오류 검사를 개선합니다. 이는 여러 구매 요청이 워크플로에 있을 때 일반 예산 예약의 과소비를 방지하는 데 도움이 됩니다. |
| 생산 관리 | 생산 현장 실행 인터페이스에서 전체 일련 번호, 배치 및 번호판 번호 표시 | 이 기능은 생산 현장 실행 인터페이스에서 일련 번호, 배치 및 번호판 번호 목록을 볼 수 있는 향상된 경험을 제공합니다. 제한된 수의 문자가 있는 카드 보기에서 전체 값을 표시하기에 충분한 공간을 제공하는 목록 보기로 표시가 변경됩니다. 이 목록은 특정 번호를 검색하는 기능도 제공합니다. |
| 영업 및 마케팅 | 게시를 위해 선택할 수 있는 판매 주문의 수를 제한합니다. | 이 기능으로 판매 주문 목록 페이지에서 확인, 피킹 목록, 포장 전표, 송장을 게시할 때 선택할 수 있는 판매 주문의 최대 수를 설정할 수 있습니다. 자동으로 활성화됩니다. 이 기능은 **수취 계정 매개 변수** 페이지에 게시하기 위한 **최대 판매 주문 수** 라는 설정을 추가합니다. 새 설정의 기본값은 *100* 입니다. 이 기능은 많은 판매 주문이 선택되었을 때 판매 주문 목록 페이지의 성능을 향상시키는 데 도움이 됩니다. 이는 정기 작업에서 처리할 수 있는 판매 주문 수에 영향을 주지 않습니다. |
| 창고 관리 | ASN에서 보관 작업 분리 | 이 기능은 규모 단위(분산 하이브리드 토폴로지의 일부로)에서 창고 관리 워크로드를 실행할 때 사전 배송 통지(ASN)를 보내고 받는 데 필요합니다. 보관 작업에 대한 정보를 저장하는 전용 새 데이터베이스 테이블을 추가합니다. 이전에는 이 정보가 ASN에도 사용된 테이블에 저장되었습니다. |
| 창고 관리 | 슬롯 혼합 장치 | 시스템이 혼합된 단위(예: 상자와 케이스 모두)를 포함하는 위치에 항목을 넣을 수 있습니다. 각 슬롯 템플릿 라인에 대해 이 기능을 사용하면 라인이 품목을 혼합 단위 또는 단일 단위 위치에 넣어야 하는지 여부를 선택할 수 있습니다. |
| 창고 관리 | 포장 스테이션에서 컨테이너를 닫거나 다시 열 때 더 빠른 API 사용 | 이 프리뷰 기능이 활성화되면 수동 포장 스테이션 처리 중에 컨테이너를 닫거나 다시 여는 성능을 향상시키는 새로운 경량 프로세스를 사용하여 컨테이너와 관련된 재고 트랜잭션이 생성됩니다. |

## <a name="features-turned-on-by-default-in-this-release"></a>이 릴리스에서 기본적으로 켜져 있는 기능

다음 표에는 10.0.21에서 기본적으로 켜져 있는 기능이 나열되어 있습니다. 원자적으로 켜진 대부분의 기능은 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 끌 수 있습니다.

| 기능 이름 | 활성화 날짜 | 기능을 추가한 날짜 | 기능 상태 | 모듈 |
| :--- | :--- | :--- | :--- | :--- |
| 현재고 보고서 스토리지 | 2021년 9월 1일 | 2020년 4월 1일 | 기본적으로 켜짐 | 재고 및 창고 관리 |
| 전송 주문 취소 | 2021년 9월 1일 | 2020년 7월 13일 | 기본적으로 켜짐 | 재고 및 창고 관리 |
| 인벤토리 분개장 잠금 해제 | 2021년 9월 1일 | 2020년 8월 17일 | 기본적으로 켜짐 | 재고 및 창고 관리 |
| 재고 관리에 대한 저장된 보기 | 2021년 9월 1일 | 2020년 9월 30일 | 기본적으로 켜짐 | 재고 및 창고 관리 |
| BOM 라인에서 BOM 버전으로 이동 | 2021년 9월 1일 | 2019년 11월 11일 | 기본적으로 켜짐 | 재고 및 창고 관리 |
| 재고 분개장에서 측정 단위 및 단위 수량 사용 | 2021년 9월 1일 | 2019년 11월 11일 | 기본적으로 켜짐 | 재고 및 창고 관리 |
| 빈 배치 특성 값 허용 | 2021년 9월 1일 | 2019년 11월 11일 | 기본적으로 켜짐 | 재고 및 창고 관리 |
| 재고 이전 주문 라인의 라인 번호 자동 증가 | 2021년 9월 1일 | 2019년 10월 11일 | 기본적으로 켜짐 | 재고 및 창고 관리 |
| 재고 분개장 승인 워크플로 | 2021년 9월 1일 | 2020년 1월 6일 | 기본적으로 켜짐 | 재고 및 창고 관리 |
| 재고 품질 관리 매개 변수 경고 기능 활성화 | 2021년 9월 1일 | 2019년 10월 7일 | 기본적으로 켜짐 | 재고 및 창고 관리 |
| 판매 라인에서 이전 주문 생성 | 2021년 9월 1일 | 2019년 8월 31일 | 기본적으로 켜짐 | 재고 및 창고 관리 |
| 수요 예측 세부 정보에 대한 예측 모델 선택 | 2021년 9월 1일 | 2019년 10월 11일 | 기본적으로 켜짐 | 기준 계획 |
| 기준 계획 진행 상황 시각화 | 2021년 9월 1일 | 2019년 10월 7일 | 기본적으로 켜짐 | 기준 계획 |
| 계획 최적화를 위한 자동 확정 | 2021년 9월 1일 | 2019년 10월 11일 | 기본적으로 켜짐 | 기준 계획 |
| 계획 주문의 병렬 확정 | 2021년 9월 1일 | 2019년 8월 31일 | 기본적으로 켜짐 | 기준 계획 |
| 입찰 제출 성공 메시지 | 2021년 9월 1일 | 2019년 5월 15일 | 기본적으로 켜짐 | 조달 및 소싱 |
| RFQ 참조 링크가 PO에 추가됨 | 2021년 9월 1일 | 2019년 8월 31일 | 기본적으로 켜짐 | 조달 및 소싱 |
| 일괄 공급업체 협업에서 승인된 구매 주문을 확인하는 기능 | 2021년 9월 1일 | 2019년 9월 10일 | 기본적으로 켜짐 | 조달 및 소싱 |
| cXML 개선 사항 구매 | 2021년 9월 1일 | 2019년 11월 11일 | 기본적으로 켜짐 | 조달 및 소싱 |
| &quot;공개된 견적 요청 열기&quot; 링크를 타일로 표시 | 2021년 9월 1일 | 2020년 9월 30일 | 기본적으로 켜짐 | 조달 및 소싱 |
| RFO 질문과 답변 | 2021년 9월 1일 | 2020년 2월 19일 | 기본적으로 켜짐 | 조달 및 소싱 |
| 위험 물질 제품 정보 및 배송 문서 | 2021년 9월 1일 | 2020년 6월 14일 | 기본적으로 켜짐 | 제품 정보 관리 |
| 기본 주문 수량에 대한 엄격한 검증 | 2021년 9월 1일 | 2020년 6월 24일 | 기본적으로 켜짐 | 제품 정보 관리 |
| 원산지 관리 기능 | 2021년 9월 1일 | 2020년 7월 13일 | 기본적으로 켜짐 | 제품 정보 관리 |
| 출시된 제품에 대한 저장된 조회수 | 2021년 9월 1일 | 2020년 9월 30일 | 기본적으로 켜짐 | 제품 정보 관리 |
| 작업 승인 및 이전 대화 상자 개선 사항 | 2021년 9월 1일 | 2019년 10월 11일 | 기본적으로 켜짐 | 생산 관리 |
| 작업 카드 디바이스에 추가된 완료 보고용 번호판 | 2021년 9월 1일 | 2019년 8월 31일 | 기본적으로 켜짐 | 생산 관리 |
| 작업 카드 터미널 페이지에 휴식 중지 단추가 추가되었습니다. | 2021년 9월 1일 | 2020년 2월 19일 | 기본적으로 켜짐 | 생산 관리 |
| 외주 품목의 부분 입고를 활성화하고 공급업체 유형의 BOM 라인에 대한 스크랩 계산 문제를 수정합니다. | 2021년 9월 1일 | 2019년 11월 11일 | 기본적으로 켜짐 | 생산 관리 |
| 생산 관리에 대한 저장된 보기 | 2021년 9월 1일 | 2020년 8월 17일 | 기본적으로 켜짐 | 생산 관리 |
| 제조용 Dynamics 365 Guides | 2021년 9월 1일 | 2020년 7월 13일 | 기본적으로 켜짐 | 생산 관리 |
| 생산 현장 실행 | 2021년 9월 1일 | 2020년 9월 30일 | 기본적으로 켜짐 | 생산 관리 |
| 작업 카드 디바이스 및 작업 카드 디바이스를 살균할 수 있도록 잠그는 기능 | 2021년 9월 1일 | 2020년 5월 10일 | 기본적으로 켜짐 | 생산 관리 |
| 판매 주문에 대한 비용 할당 | 2021년 9월 1일 | 2020년 9월 30일 | 기본적으로 켜짐 | 영업 및 마케팅 |
| 게시를 위해 선택할 수 있는 판매 주문의 수를 제한합니다. | 2021년 9월 1일 | 2021년 9월 1일 | 기본적으로 켜짐 | 영업 및 마케팅 |
| 판매 주문 업데이트 내역 정리 | 2021년 9월 1일 | 2021년 9월 1일 | 기본적으로 켜짐 | 영업 및 마케팅 |
| 순환 재고 작업의 번호 시퀀스 변경 | 2021년 9월 1일 | 2019년 10월 7일 | 기본적으로 켜짐 | 창고 관리 |
| 웨이브 수요 보충 기반 작업 | 2021년 9월 1일 | 2019년 10월 7일 | 필수 | 창고 관리 |
| &quot;모든 로드&quot; 및 &quot;로드 세부 정보&quot; 페이지에서 총 값 필드 숨기기 | 2021년 9월 1일 | 2019년 10월 7일 | 기본적으로 켜짐 | 창고 관리 |
| 웨이브 레이블 인쇄 | 2021년 9월 1일 | 2020년 2월 19일 | 필수 | 창고 관리 |
| 구매 주문 재고 트랜잭션을 로드와 연결 | 2021년 9월 1일 | 2020년 1월 6일 | 필수 | 창고 관리 |
| 향상된 번호판 레이블 레이아웃 | 2021년 9월 1일 | 2020년 2월 19일 | 기본적으로 켜짐 | 창고 관리 |
| 조직 전체 작업 차단 | 2021년 9월 1일 | 2020년 2월 19일 | 필수 | 창고 관리 |
| 작업 라인 세부 정보 | 2021년 9월 1일 | 2019년 10월 11일 | 기본적으로 켜짐 | 창고 관리 |
| 모바일 디바이스 인벤토리 이동 인벤토리 상태 필드를 편집 가능하게 만들기 | 2021년 9월 1일 | 2019년 10월 16일 | 기본적으로 켜짐 | 창고 관리 |
| 일괄 작업에서 아웃바운드 배송 확인 | 2021년 9월 1일 | 2020년 7월 13일 | 기본적으로 켜짐 | 창고 관리 |
| 모바일 디바이스에서 수신 요약 페이지 표시 여부 제어 | 2021년 9월 1일 | 2020년 4월 1일 | 기본적으로 켜짐 | 창고 관리 |
| 모호한 &#39;Loc/LP&#39; 이름을 해결하라는 프롬프트 | 2021년 9월 1일 | 2020년 4월 1일 | 기본적으로 켜짐 | 창고 관리 |
| 로드 항목을 받는 동안 창고 앱에서 제품 변형 및 추적 규모 캡처 | 2021년 9월 1일 | 2020년 5월 10일 | 기본적으로 켜짐 | 창고 관리 |
| 웨이브 하중 건물 템플릿 요구 사항을 충족하지 않는 하중 생성을 허용하지 마세요. | 2021년 9월 1일 | 2020년 8월 17일 | 기본적으로 켜짐 | 창고 관리 |
| 다중 SKU 위치 지시문에 대한 모든 작업 평가 | 2021년 9월 1일 | 2020년 9월 30일 | 기본적으로 켜짐 | 창고 관리 |

## <a name="new-and-updated-documentation-resources"></a>신규 및 업데이트된 문서 리소스

최근에 다음 도움말 항목을 추가하거나 크게 업데이트했습니다. 이전 섹션에 나열된 것처럼 이 릴리스에 추가된 새로운 기능과 반드시 관련이 있는 것은 아니지만 기존 기능을 최대한 활용하는 데 도움이 될 수 있습니다.

| 기능 영역 | 신규 또는 업데이트된 토픽 |
|---|---|
| 기준 계획 | [재고 예측](../master-planning/inventory-forecast.md) |
| 기준 계획 | [계획 최적화에서 사용하지 않는 매개 변수](../master-planning/planning-optimization/not-used-parameters.md) |
| 기준 계획 | [보충 방법 및 수량 수정](../master-planning/planning-optimization/replenishment-methods-quantity-modification.md) |
| 기준 계획 | [무한 용량으로 스케줄링](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| 기준 계획 | [계획 기록 및 계획 로그 보기](../master-planning/planning-optimization/plan-history-logs.md) |
| 창고 관리 | [컨테이너 포장 전략](../warehousing/container-packing-strategy-overview.md) |
| 창고 관리 | [순환 재고 예시 시나리오](../warehousing/cycle-counting-scenarios.md) |
| 창고 관리 | [V2 데이터 엔터티를 통해 인바운드 ASN 가져오기](../warehousing/import-asn-v2-data-entity.md) |
| 창고 관리 | [판매 주문 및 이전 주문에 대한 초과 피킹](../warehousing/over-picking-for-sales-and-transfer-orders.md) |
| 창고 관리 | [웨이브 중 웨이브 라벨 인쇄 예약](../warehousing/configure-task-based-wave-label-printing.md) |
| 창고 관리 | [Warehouse Management 모바일 앱의 새로운 기능 또는 변경된 사항](../warehousing/whats-new-wma.md) |

## <a name="additional-resources"></a>추가 리소스

### <a name="platform-updates-for-finance-and-operations-apps"></a>금융 및 운영 앱용 플랫폼 업데이트

Microsoft Dynamics 365 Supply Chain Management 10.0.21에는 플랫폼 업데이트가 포함됩니다. 자세히 알아보려면 [금융 및 운영 앱 버전 10.0.21에 대한 플랫폼 업데이트(2021년 10월)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21.md)를 참조하세요.

### <a name="bug-fixes"></a>버그 수정

10.0.21의 일부인 각 업데이트에 포함된 버그 수정에 대한 정보는 LCS(Lifecycle Services)에 로그인하여 [KB 문서](https://fix.lcs.dynamics.com/Issue/Details?bugId=605166&dbType=3&qc=4b9449bf0d947113983bd0697140bf4d8727bfafd5566aa682cb38db343374de)를 참조하세요.

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
