---
title: 초과/미달 트랜잭션
description: 이 항목은 초과/미달 트랜잭션에 대한 정책의 세부 사항을 설정하는 데 도움이 되는 정보를 제공하여 시스템이 입고 시점에 상품의 초과 처리 및 미달 처리를 관리하는 방법을 결정할 수 있도록 합니다.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMOverUnderTrans, ITMOverUnderToleranceTable, ITMOverUnderReasonTable, ITMOverUnderToleranceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 60f4f31e9da762a89b034961a703e1d7b1bbd903
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449347"
---
# <a name="overunder-transactions"></a>초과/미달 트랜잭션

[!include [banner](../../includes/banner.md)]

항해의 주문이 처리될 때 시스템은 소비를 위해 최종 목적지 창고에 입고된 품목 수량이 항해와 연관된 구매 발주 라인에 지정된 수량과 일치할 것으로 예상합니다. 그러나 구매 발주 라인의 정확한 수량은 항상 창고에 입고되지 않기 때문에 **상륙 비용** 모듈은 상품의 초과 수령 및 미달 수령을 처리하는 데 사용되는 일련의 규칙을 정의합니다. 이러한 규칙은 원래 구매 주문서에 송장이 발행되어 더 이상 수정할 수 없기 때문에 특히 중요합니다. 초과/미달 트랜잭션 정책의 세부 사항을 설정함으로써 시스템이 상품 수령 시의 초과 처리 및 미달 처리를 관리하는 방법을 결정할 수 있습니다. 또한 **초과/미달 트랜잭션** 페이지를 사용하여 초과 및 미달 재고를 수동으로 관리할 수도 있습니다.

## <a name="overunder-tolerances"></a>초과/미달 허용 오차

초과 배달 및 미달 배달 허용 오차를 설정하여 오류를 일으키지 않고 항해에서 처리할 수 있는 초과 및 미달 수량 또는 볼륨을 지정합니다. 항해 라인 영수증이 이러한 허용 오차를 벗어난 경우 추가 처리를 위해 항해 라인을 닫으려면 먼저 수정 및 해결해야 합니다.

허용 오차를 구성하려면 **상륙 비용 \> 초과/미달 설정 \> 초과/미달 허용 오차** 로 이동합니다. 여기에서 허용 오차 기록을 보고, 편집하고, 추가하고, 제거할 수 있습니다. 다음 표에서는 각 레코드에 사용할 수 있는 필드에 대해 설명합니다.

| 필드 | 설명 |
|---|---|
| 계정 코드 | <p>다음 값 중 하나를 선택하여 허용 오차가 적용되는 공급업체의 범위를 정의합니다.</p><ul><li>**테이블** – 초과/미달 허용 오차는 행에 대해 선택된 공급업체에만 적용됩니다.</li><li>**그룹** – 초과/미달 허용 오차는 행에 대해 선택된 공급업체 허용 오차 그룹의 모든 공급업체에 적용됩니다.</li><li>**모두** – 초과/미달 허용 오차는 모든 공급업체에 적용됩니다.</li></ul> |
| 계정 관계 | **계정 코드** 필드에서 선택한 값에 따라 초과/미달 허용 오차가 적용되는 공급업체 또는 공급업체 그룹을 선택합니다. |
| 항목 코드 | <p>다음 값 중 하나를 선택하여 허용 오차가 적용되는 항목의 범위를 정의합니다.</p><ul><li>**테이블** – 초과/미달 허용 오차는 행에 대해 선택된 항목에만 적용됩니다.</li><li>**그룹** – 초과/미달 허용 오차는 행에 대해 선택된 항목 허용 오차 그룹의 모든 항목에 적용됩니다.</li><li>**모두** – 초과/미달 허용 오차는 모든 항목에 적용됩니다.</li></ul> |
| 항목 관계 | **항목 코드** 필드에서 선택한 값에 따라 초과/미달 허용 오차가 적용되는 항목 또는 항목 그룹을 선택합니다. |
| 금액 허용 오차 | 전체 구매 주문에 적용해야 하는 금액 허용 오차를 입력합니다. |
| 백분율 허용 오차 | 개별 구매 주문 라인에 적용해야 하는 백분율 허용 오차를 입력합니다. |

## <a name="overunder-reasons"></a>초과/미달 사유

초과 또는 미달 수량이 수신된 항해 라인과 연관되는 경우 초과 또는 미달 수량에 대한 사유를 식별해야 할 수 있습니다. 이 경우 입고시 입고 라인에서 초과 배달 또는 미달 배달 사유를 선택할 수 있습니다.

초과 배송 및 미달 배송 사유를 설정하려면 **상륙 비용 \> 초과/미달 설정 \> 초과/미달 사유** 로 이동합니다. 여기에서 사용 가능한 초과 배송 및 미달 배송 사유를 확인, 편집, 추가 및 제거할 수 있습니다. 다음 표에서는 각 사유에 사용할 수 있는 필드에 대해 설명합니다.

| 필드 | 설명 |
|---|---|
| 초과/미달 사유 | 초과 입고 또는 미달 입고 트랜잭션의 사유에 대한 고유한 이름을 입력합니다. |
| 설명 | 초과/미달 사유에 대한 설명을 입력합니다. |
| 이동 | 초과/미달 사유와 연결된 이동 분개장을 선택합니다. 이 필드는 **재고 저널 이름** 페이지(**재고 관리 설정 \> 분개장 이름 \> 재고**)에서 *이동* 분개장 유형과 관련이 있는 사용 가능한 모든 저널을 나열합니다. |

## <a name="item-overunder-tolerance-groups"></a>항목 초과/미달 허용 오차 그룹

허용 오차가 유사한 항목을 함께 그룹화할 수 있습니다. 이러한 방식으로 해당 그룹의 모든 항목에 대해 초과/미달 허용 오차를 동시에 설정할 수 있습니다.

항목 초과/미달 허용 오차 그룹을 설정하려면 **상륙 비용 \> 초과/미달 설정 \> 항목 초과/미달 허용 오차 그룹** 으로 이동합니다. 여기에서 초과/미달 허용 오차 그룹 기록을 보고, 편집하고, 추가하고, 제거할 수 있습니다. 다음 표에서는 각 레코드에 사용할 수 있는 필드에 대해 설명합니다.

| 필드 | 설명 |
|---|---|
| 초과/미달 허용 오차 그룹 | 그룹의 고유한 이름을 입력합니다. *1% 변동* 과 같이 허용 오차를 설명하는 이름을 선택합니다. |
| 설명 | 그룹에 대한 설명을 입력합니다. |

## <a name="vendor-overunder-tolerance-groups"></a>공급업체 초과/미달 허용 오차 그룹

정기적으로 초과 배달 또는 미달 배달하는 공급업체를 그룹화할 수 있습니다. 그런 다음 그룹별로 초과/미달 허용 오차를 설정할 수 있습니다.

공급업체 초과/미달 허용 오차 그룹을 설정하려면 **상륙 비용 \> 초과/미달 설정 \> 공급업체 초과/미달 허용 오차 그룹** 으로 이동합니다. 여기에서 초과/미달 허용 오차 그룹 기록을 보고, 편집하고, 추가하고, 제거할 수 있습니다. 다음 표에서는 각 레코드에 사용할 수 있는 필드에 대해 설명합니다.

| 필드 | 설명 |
|---|---|
| 초과/미달 그룹 | 그룹의 고유한 이름을 입력합니다. 그룹에 속하는 공급업체 유형을 설명하는 이름을 선택합니다. |
| 설명 | 그룹에 대한 설명을 입력합니다. |

## <a name="view-and-process-overunder-transactions"></a>초과/미달 트랜잭션 조회 및 처리

입고된 물품의 수량과 초기화된 수량과 일치하지 않을 경우 초과 및 미달 트랜잭션이 발생합니다. 도착 분개장의 수량은 처리된 수량으로만 업데이트되어야 합니다.

항해 라인 접수가 처리되면 공급업체에 대해 초과/미달 허용 오차를 설정할 수 있습니다. 그런 다음 항목을 검토하고 검증합니다. 허용 오차는 백분율, 현지 금액 또는 둘 다로 설정할 수 있습니다.

입고된 품목이 허용 오차 범위 내에 있는 경우 시스템에서 이동 분개장을 생성합니다. 이 분개장은 항해 매개 변수 페이지에서 지정할 수 있습니다. 또한 초과/미달 트랜잭션이 생성됩니다. 예를 들어 주문 값은 $100이고 수령 금액은 $99이며 이러한 값은 허용 오차 규칙을 충족합니다. 이 경우 미달 수량에 대한 음수 이동 분개장이 생성됩니다.

입고된 항목이 허용 오차를 벗어난 경우 시스템은 수량 차이에 대해 초과/미달 트랜잭션을 생성합니다.

초과/미달 트랜잭션을 보고 처리하려면 **상륙 비용 \> 문의 \> 초과/미달 트랜잭션** 으로 이동합니다. 여기에서 초과/미달 트랜잭션은 초과 수령 또는 과소 수령된 항해의 모든 항목과 연관됩니다. **초과/미달 트랜잭션** 페이지를 사용하여 항해와 관련된 모든 초과/미달 트랜잭션을 해결하는 것이 좋습니다. 또한 미달 배달 창고 트랜잭션을 수동으로 해결하기 위해 이동 또는 집계 분개장을 사용하지 **않는** 것이 좋습니다. 대신 **초과/미달 트랜잭션** 페이지를 사용하여 미달 배달 창고 수량을 관리해야 합니다.

### <a name="upper-overview-tab"></a>상단 개요 탭

초과/미달 트랜잭션을 보려면 **초과/미달 트랜잭션** 페이지 상단에 있는 **개요** 탭을 선택합니다. 다음 표에서는 그리드에서 사용할 수 있는 필드에 관해 설명합니다.

| 필드 | 설명 |
|---|---|
| 초과/미달 트랜잭션 번호 | 도착 분개장이 처리될 때 자동으로 생성된 초과/미달 트랜잭션 레코드의 고유 이름입니다. |
| 항해 | 구매 라인이 연결된 항해입니다. |
| 배송 컨테이너 | 구매 라인이 연결된 컨테이너입니다. |
| 도착 분개장 | 초과/미달 라인이 생성된 도착 분개장입니다. |
| 참조 | 초과/미달 트랜잭션과 관련된 구매 주문 또는 이전 주문에 대한 참조입니다. |
| 번호 | 초과/미달 트랜잭션에서 참조되는 구매 주문입니다. |
| 공급 업체 계정 | 초과 또는 미달과 관련된 공급업체입니다. |
| 미착 상품 번호 | 해당하는 경우 미착 상품 번호입니다. |
| 품목 번호 | 초과 또는 미달과 관련된 품목 번호입니다. |
| 원래 수량 | 배송에 첨부된 구매 주문 라인의 원래 수량입니다. |
| 받은 수량 | 실제로 받은 수량입니다. |
| 차이 | 예상 도착 분개장 금액과 도착 분개장에 전기된 금액 간의 차이입니다. 음수 값은 상품의 초과 배송을 나타냅니다. |
| 남은 수량 | 도착 분개장 라인에 남아 있는 수량입니다. |
| 초과/미달 배달 | 입고된 수량이 초과인지 미달인지를 나타내는 값입니다. |
| 상태 | 초과/미달 트랜잭션의 상태입니다. **[상륙 비용 매개 변수](landed-cost-parameters.md)** 페이지의 설정에 따라 초과 배달은 초과 배달 금액에 대한 이동 분개장을 자동으로 생성하고 분개장을 게시할 수 있습니다. 이 경우 초과/미달 트랜잭션 상태는 *완료됨* 상태가 됩니다. 미달 배송 창고에서 상품을 이동하기 위해 조치가 필요한 경우 레코드 상태는 *진행 중* 이 됩니다. |
| 초과/미달 사유 | 초과/미달 트랜잭션과 연결된 사유입니다. |
| 기타 재고 규모 | 필요에 따라 그리드의 추가 차원에 대한 열을 표시할 수 있습니다. 이러한 차원에는 배치 번호, 재고 상태 및 창고가 포함됩니다. 작업 창에서 **재고 \> 차원 표시** 를 선택하여 포함할 차원을 선택할 수 있는 대화 상자를 엽니다. |

### <a name="upper-general-tab"></a>상단 일반 탭

상단 **개요** 탭에서 현재 선택된 라인에 대한 자세한 정보를 보려면 **초과/미달 트랜잭션** 페이지 상단에 있는 **일반** 탭을 선택합니다. 이 탭의 정보에는 사용 가능한 모든 차원의 값이 포함됩니다. 이 정보는 원래 구매 주문에서 가져옵니다.

### <a name="lower-overview-tab"></a>하단 개요 탭

상단 **개요** 탭에서 선택된 행에 대한 문서 유형을 보려면 **초과/미달 트랜잭션** 페이지 하단에 있는 **개요** 탭을 선택합니다. 다음 표에서는 사용 가능한 필드에 대해 설명합니다.

| 필드 | 설명 |
|---|---|
| 새 문서 유형 | 이 필드는 선택한 초과/미달 트랜잭션 라인에 표시되는 조치에 따라 *이동 분개장* 또는 *구매 주문* 중 하나로 설정됩니다. |
| 번호 | 선택한 초과/미달 트랜잭션 라인과 연관된 구매 주문 또는 이동 분개장에 대한 참조 및 링크입니다. |
| 초과/미달 사유 | 선택된 초과/미달 라인과 연결된 사유입니다. |
| 수량 | 선택한 초과/미달 트랜잭션 라인과 연관된 구매 주문 또는 이동 분개장에 대해 사용자가 선택한 수량입니다. |

### <a name="lower-general-tab"></a>하단 일반 탭

선택한 초과/미달 트랜잭션 라인과 연관된 초과/미달 트랜잭션 번호, 로트 ID 및 차원 번호를 보려면 **초과/미달 거래** 페이지 하단에 있는 **일반** 탭을 선택합니다. 

### <a name="process-overunder-transactions"></a>초과/미달 트랜잭션 처리

**초과/미달 트랜잭션** 페이지의 작업 창은 페이지에서 선택한 트랜잭션을 처리하기 위한 다음 명령을 제공합니다. 각 명령을 통해 각 트랜잭션을 처리하는 방법을 선택할 수 있습니다.

- **만들기 \> 이동** – 선택한 트랜잭션에 대한 이동 분개장을 작성하여 전기합니다. 미달 트랜잭션의 경우 예상 입고 수량과 실제 입고 수량의 차이에 대해 이동 분개장이 자동으로 생성되고 전기됩니다. 공급업체가 비용 차이를 인식하도록 하려면 초과 트랜잭션에 대해 이 명령을 선택하세요.
- **만들기 \> 구매 주문** – 선택한 트랜잭션의 예상 입고 수량과 실제 입고 수량의 차이에 대한 구매 주문을 생성합니다. 조직에서 비용 차이를 인식할 경우 초과 트랜잭션에 대해 이 명령을 선택합니다.
- **만들기 \> 목적지로 이동** – 이 명령은 이전 명령에만 적용됩니다. 초과 또는 미달 수량을 목적지 창고로 이전하려면 선택합니다.
- **만들기 \> 출발지로 이동** – 이 명령은 이전 명령에만 적용됩니다. 초과 또는 미달 수량을 출발지 창고로 이전하려면 선택합니다.