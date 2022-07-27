---
title: Dynamics 365 Supply Chain Management 10.0.26 프리뷰(2022년 5월)
description: 이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 10.0.26의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: kamaybac
ms.date: 03/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: fae25eb1cb9dd4059b9d49e47cbb0060e717c9bc
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2022
ms.locfileid: "8450088"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10026-may-2022"></a>Dynamics 365 Supply Chain Management 10.0.26 프리뷰(2022년 5월)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management 프리뷰 버전 10.0.26의 새로 추가되거나 변경된 기능에 관해 나열합니다. 이 버전의 빌드 번호는 10.0.1192이며 다음과 같이 확인할 수 있습니다.

- **프리뷰 릴리스:** 2022년 3월
- **릴리스 일반 공급(자체 업데이트):** 2022년 4월
- **릴리스 일반 공급(자동 업데이트):** 2022년 5월

## <a name="features-included-in-this-release"></a>이번 릴리스에 포함된 기능

다음 표에는 이 릴리스에 포함된 기능이 나열되어 있습니다. 이 항목이 처음 게시된 후 빌드에 포함된 기능을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 기능 영역 | 기능 | 추가 정보 |  에 의해 활성화됨 |
|---|---|---|---|
| 재고 및 물류 | [고급 창고 관리 항목을 지원하는 재고 가시성 현재 쿼리](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-visibility-support-advanced-warehouse-management) | 업데이트 예정 | 기능 관리:<br>*인벤토리 가시성에서 창고 항목 활성화* |
| 재고 및 물류 | [재고 가시성 추가 기능에 대한 약속 가능](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/available-to-promise-inventory-visibility-add-in) | 업데이트 예정 | 서비스 구성에 의해 활성화됨 |
| 제조 | [생산 현장 실행 인터페이스의 공칭 무게 항목](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/catch-weight-items-production-floor-execution-interface) | [작업자가 생산 현장 실행 인터페이스를 사용하는 방법](../production-control/production-floor-execution-use.md) | 기능 관리:<br>*(프리뷰) 생산 현장 실행 인터페이스에서 공칭 무게 항목에 대한 보고* |
| 제조 | 생산 현장 실행 인터페이스의 내 작업 탭 <!-- KFM: Add link to release plan when available --> | [작업자가 생산 현장 실행 인터페이스를 사용하는 방법](../production-control/production-floor-execution-use.md) | 기능 관리:<br>*생산 현장 실행 인터페이스의 내 작업 탭* |

## <a name="feature-enhancements-included-in-this-release"></a>이번 릴리스에 포함된 기능 개선 사항

다음 표에는 이 릴리스에 포함된 기능 개선 사항이 나열되어 있습니다. 이러한 개선 사항 각각은 기존 기능을 점진적으로 개선합니다. 개선 사항일 뿐이므로 [릴리스 계획](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features)에 나열되지 않습니다. 그러나 이러한 개선 사항이 기존 사용자 지정 또는 기본 설정과 충돌하지 않도록 하기 위해 각 기능은 기본적으로 해제되어 있습니다(달리 명시되지 않는 한).

이러한 기능을 켜거나 끄려면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 수행해야 합니다.

| 모듈 | 기능 관리의 기능 이름 | 추가 정보 |
|---|---|---|
| 조달 및 소싱 | 입고된 제품의 등록 수량과 입고되지 않은 제품의 나머지 부분을 영수증 및 공급업체 송장으로 전기 | 이 기능은 공급업체 송장 및 구매 주문에 대한 인바운드 배송을 처리할 때 재고가 없는 제품(예: 서비스)의 수량을 전기하는 방법을 변경합니다. 이 기능은 판매 포장 전표에 대한 수량을 전기할 때 이미 제공된 *등록 수량 및 비재고 제품* 옵션의 동작과 일치하도록 변경하여 영수증 및 공급업체 송장 전기를 위한 *등록 수량 및 서비스* 수량 옵션의 동작을 수정합니다.<br><br>*등록 수량 및 서비스* 수량 옵션을 사용하여 제품 영수증 또는 공급업체 송장을 전기하면 시스템은 재고 제품의 등록 수량을 전기하고 재고가 없는 제품의 나머지 수량(서비스 및 비서비스 모두 포함)을 전기합니다. 이 기능이 없어도 시스템은 여전히 등록된 재고 제품 수량(재고 품목으로 구성된 서비스 포함)을 게시하지만 항상 비재고 서비스 제품의 전체 주문 수량을 게시합니다(*서비스* 유형이 아닌 비재고 제품은 무시). |
| 조달 및 소싱 | 회사 간 판매 및 구매 주문 라인에서 추적 규모 동기화 | 이 기능을 사용하면 일련번호 및 배치 번호 추적 차원이 본지사 판매 및 구매 주문 라인에서 동기화되는지 여부를 제어할 수 있습니다. 고객 및 공급업체에 대한 **내부 거래** 설정 페이지의 **구매 주문 정책** 및 **판매 주문 정책** 탭 모두에 새 설정을 추가합니다. 또한 명확성을 위해 몇 가지 관련 주변 설정의 이름을 업데이트합니다.<br><br>고급 창고 관리(WMS)를 사용하는 경우 이 기능은 배치 및 일련 번호가 대상 대상 예약 계층의 위치보다 위에 있을 때만 배치 및 일련 번호를 동기화한다는 점에 유의하세요. |
| 제품 정보 관리 | 제품 특성 값 정리 | 이 기능은 **제품 특성 값 정리** 라는 주기적인 작업을 추가합니다. 이 작업은 제품 범주를 통해 더 이상 제품과 연결되지 않은 제품 특성 값 레코드를 정리합니다. |
| 재고 및 창고 관리 | (러시아) WMS 지원 품목이 포함된 구매 주문에 대한 GTD 발행 시 불일치 방지 | 이 기능은 러시아어 현지화 전용입니다. WMS(Advanced Warehousing)가 활성화된 품목을 포함하는 수입 구매 주문에 대해 러시아 GTD(통관 신고 번호)를 발행할 때 발생하는 불일치를 방지합니다. GTD 발행 프로세스는 사용자 정의 저널에 포함된 송장에 대한 관련 재고 트랜잭션의 일부 재고 차원 값을 변경하여 구매 주문에 대한 작업 레코드와 구매에 대한 재고 트랜잭션 사이에 불일치를 초래합니다. 이 기능이 활성화되면 GTD 발급 프로세스에서 이러한 불일치를 제거하는 조정 작업이 생성됩니다. |
| 창고 관리 | GS1 바코드를 위한 향상된 파서 | 이 기능은 GS1 기호 데이터에 대한 향상된 파서를 추가합니다. 새로운 구문 분석기는 GS1 기호 구문 분석을 위한 GS1 일반 사양 알고리즘을 구현하고 더 강력한 데이터 유효성 검사를 제공합니다. |
| 창고 관리 | 새 적재 계획 워크벤치 페이지 | 두 개의 새로운 로드 계획 워크벤치 페이지(**인바운드 로드 계획 워크벤치** 및 **아웃바운드 로드 계획 워크벤치**)를 추가합니다. |
| 창고 관리 | 창고 관리 애플리케이션 - 공백 GTD | 이 기능은 러시아어 현지화 전용입니다. Warehouse Management 모바일 앱을 사용하는 작업자는 필요할 때 러시아 세관 신고 번호(GTD)를 공백으로 둘 수 있습니다. GTD 추적 차원이 공백 값을 허용하도록 설정된 경우 시스템은 현재고가 사용 가능한 경우 재고 작업에 대해 GTD에 공백 값을 허용합니다. |

## <a name="new-and-updated-documentation-resources"></a>신규 및 업데이트된 문서 리소스

최근에 다음 도움말 항목을 추가하거나 크게 업데이트했습니다. 이러한 항목은 이전 섹션에 나열된 것처럼 이 릴리스에 추가된 새 기능과 반드시 관련이 있는 것은 아닙니다. 그러나 기존 기능을 최대한 활용하는 데 도움이 될 수 있습니다.

| 기능 영역 | 신규 또는 업데이트된 토픽 |
|---|---|
| 비용 관리 | 업데이트된 예제와 다이어그램이 다음 주제 각각에 추가되었습니다.<ul><li>[물리적 가치 및 표시가 있는 FIFO](../cost-management/fifo-physical-value-marking.md)</li><li>[물리적 가치 및 표시가 있는 LIFO](../cost-management/lifo-physical-value-marking.md)</li><li>[물리적 가치 및 표시가 있는 LIFO 날짜](../cost-management/lifo-date-physical-value-marking.md)</li><li>[실행 평균 원가](../cost-management/running-average-cost-price.md)</li><li>[물리적 가치 및 표시가 있는 가중 평균](../cost-management/weighted-average-physical-value-marking.md)</li></ul> |
| 조달 및 소싱 | [구매 주문 행 데이터 불일치](../troubleshooting/procurement/purchase-order-line-data-issues.md) |

## <a name="additional-resources"></a>추가 리소스

### <a name="platform-updates-for-finance-and-operations-apps"></a>금융 및 운영 앱용 플랫폼 업데이트

Microsoft Dynamics 365 Supply Chain Management 10.0.26에는 플랫폼 업데이트가 포함됩니다. 자세히 알아보려면 [금융 및 운영 앱 버전 10.0.26에 대한 플랫폼 업데이트(2022년 5월)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-26.md)를 참조하세요.<!-- KFM Confirm link -->

### <a name="bug-fixes"></a>버그 수정

10.0.26의 일부인 각 업데이트에 포함된 버그 수정에 대한 정보는 LCS(Lifecycle Services)에 로그인하여 [KB 문서](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864)를 참조하세요.

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
