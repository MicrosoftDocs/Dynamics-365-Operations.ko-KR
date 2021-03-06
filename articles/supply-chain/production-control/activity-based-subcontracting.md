---
title: 활동 기반 하청계약
description: 이 항목에서는 린 제고를 위한 생산 흐름에서 외주 활동을 사용하는 방법에 대해 자세히 설명합니다.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, PlanActivity, ReqSupplyDemandSchedule, PlanActivityServiceDetails, PlanActivityServiceWizard
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267034
ms.assetid: 15c76a51-fa6d-42d2-994a-c67df6bae6a9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c2e1efceb800930d9f9e19a109da80d8cfebe2e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447955"
---
# <a name="activity-based-subcontracting"></a>활동 기반 하청계약

[!include [banner](../includes/banner.md)]

이 항목에서는 린 제고를 위한 생산 흐름에서 외주 활동을 사용하는 방법에 대해 자세히 설명합니다.

Microsoft Dynamics 365 Supply Chain Management에서 하청계약에는 생산 주문과 린 제고의 두 가지 접근 방식이 있습니다. 린 제고 방식에서 하청계약 작업은 생산 흐름의 활동과 관련된 서비스로 모델링됩니다. 이름이 **직접 아웃소싱** 인 특수 유형의 비용 그룹 유형이 도입되었으며 하청계약 서비스는 더 이상 BOM(자재 명세서)의 일부가 아닙니다. 하청 작업의 원가 회계는 린 제고를 위한 원가 계산 솔루션에 완전히 통합됩니다.

## <a name="production-flows-that-involve-subcontractors"></a>하청업체를 포함하는 생산 흐름
생산 흐름의 기본 원칙은 활동이 하도급될 때 변경되지 않습니다. 자재는 여전히 위치 간에 흐르고, 프로세스 활동은 자재를 제품으로 변환하고, 이전 활동은 자재 또는 제품을 한 위치에서 다른 위치로 이동합니다. 공급업체 계정을 자원 그룹의 자원이나 창고에 지정하여 위치 및 작업 셀을 공급업체 관리로 모델링할 수 있습니다.  

이러한 기능을 기반으로 하는 린 제고는 재료 및 제품의 흐름을 지원하기 위해 특정 기능이 필요하지 않습니다. 공급업체를 생산 또는 운송 서비스 제공자로 포함하는 모든 가능한 시나리오는 생산 흐름 및 활동 아키텍처를 기반으로 모델링할 수 있습니다.  

예를 들어, 하청업체가 하청업체에 있는 슈퍼마켓에서 일합니다. 하청업체에서 처리 단위를 비우면 칸반 카드가 다음 배송과 함께 조립 셀로 반환됩니다. 그러면 하청업체의 슈퍼마켓이 채워집니다. 하청업체와의 이동은 피킹 및 선적 프로세스를 지원하기 위해 명시적 이전 활동으로 모델링할 수 있습니다. 물리적 전송을 지원하기 위해 명시적 등록이 필요하지 않은 경우 전송 활동을 생략할 수 있습니다.  

하청업체를 사용하여 생산 흐름의 전체 용량을 로드 밸런싱할 수 있습니다. 예를 들어, 생산 흐름은 예약된 칸반 규칙을 사용하여 모델링됩니다. 계획자는 칸반 일정 게시판을 사용하여 요청 시 두 작업 셀을 예약하고 로드 레벨을 지정합니다. 계획자는 **공급 일정** 페이지에서도 슈퍼마켓에 대한 통합 공급 일정을 모니터링합니다. 여러 하청업체를 하나 이상의 생산 흐름에서 모델링할 수 있으며, 여러 활동을 통해 동일한 제품을 동일한 위치에 공급하는 데 사용할 수 있는 여러 칸반 규칙이 있을 수 있습니다. 플래너는 칸반을 대체 칸반 규칙으로 변환하여 원래 내부 생산을 위해 생성된 칸반을 대체 프로세스로 일정을 조정할 수 있습니다. 실제로 작업 셀의 하도급 특성은 생산 흐름에 영향을 미치지 않습니다. 동일한 작동 원리가 두 개의 병렬 내부 작업 셀 또는 두 개의 외주 셀에 적용됩니다.   

생산 흐름의 다른 활동과 마찬가지로 외주 활동은 재고 및 비 재고(재공품\[WIP\]) 및 반제품 재료 및 제품을 소비 및 공급할 수 있습니다. 모든 경우에 하도급 활동을 스케줄링하고 실행하는 프로세스는 동일합니다. 또한 이러한 프로세스는 내부 작업 프로세스와 동일합니다.

## <a name="purchase-process-for-subcontracted-activities-services"></a>하청 활동(서비스)을 위한 구매 절차
외주 활동에 대한 구매 프로세스는 칸반 작업 진행에 의해 등록된 물리적 자재 흐름(예: 시작 또는 완료)을 기반으로 합니다. 하청 작업 비용과 같은 재정 흐름은 물리적 흐름을 따르는 2차 흐름입니다. 동시에 구매 프로세스는 모든 단계에서 구매 문서를 수동으로 조정할 수 있는 독립적인 프로세스입니다. 다음은 하청 활동을 위한 구매 절차입니다.

1.  구매 계약을 생성합니다. 서비스에 대한 구매 계약이 생성되고 생산 흐름의 활동에 연결됩니다.
2.  구매 주문을 만듭니다. 예약된 칸반 작업을 기반으로 서비스에 대한 릴리스 구매 주문을 생성할 수 있습니다. 동일한 서비스에 대한 작업을 일, 주 또는 월별로 구매 주문 라인으로 그룹화할 수 있습니다. 칸반 작업이 생성된 후 언제든지 구매 발주 라인을 생성할 수 있습니다. 구매 주문 라인은 사실 이후에도 생성될 수 있습니다. 이 옵션은 일반적으로 하청업체가 받는 칸반 또는 칸반 카드를 기반으로 하청업체가 추가 통지 없이 서비스를 제공하는 경우 선택됩니다. 이 경우 구매 주문서와 송장 간의 편차를 최소화할 수 있습니다.
3.  칸반 카드, 자재 및 피킹 목록을 생성하여 처리 준비를 위해 외주업체에 보낼 수 있습니다. 생산 흐름의 세부 모델링을 기반으로 하여 피킹 목록 및 준비 기능을 사용하여 프로세스 활동을 위한 칸반 보드에서 준비가 수행됩니다. 또는 피킹 목록과 시작 또는 완료를 사용하여 이동 작업을 위한 칸반 보드에서 준비를 수행합니다. 재고 자재의 경우 두 프로세스 모두 WMS-피킹 및 선적 프로세스에서 지원될 수 있습니다. 선하 증권은 요청 시 생성할 수 있습니다.
4.  칸반 처리 단위 및 칸반 카드를 생성합니다. 처리 후 카드는 하청업체에서 반환됩니다. 일반적으로 카드에는 배송된 물리적 자재를 지정하는 배송 메모가 포함됩니다. 제공된 서비스에 대한 참조는 필요하지 않습니다. 고객에게 자재나 제품의 도착은 칸반 카드에 따라 칸반 게시판에 등록됩니다. (모델링된 활동에 따라 프로세스 활동에 대한 칸반 보드 또는 전송 작업에 대한 칸반 보드가 사용됩니다.)
5.  영수증 통지를 만듭니다. 영수증 통지는 받은 서비스에 대한 포장 전표 문서를 대체하는 데 사용할 수 있습니다. 입고 권고는 선택한 기간 동안 외주 활동에 대해 완료된 칸반 작업을 기반으로 생성될 수 있습니다. 각 작업 영수증에 대해 관련 구매 발주 라인에 대한 권고가 생성됩니다. 영수증 통지를 인쇄하여 입고 확인서로 협력업체에 발송할 수 있습니다.
6.  송장을 생성합니다.

일정 기간 동안 하청업체에 송장이 발행되면 프로세스가 종료됩니다. 송장 일치는 생성된 수령 권고에 대해 수행됩니다. 입고 권고는 자재의 정확한 물리적 입고를 나타내므로 3방향 매칭이 단순화됩니다.

## <a name="configuring-activities-for-subcontracting"></a>하도급 활동 구성
다음 섹션에서는 하도급 활동을 구성하는 방법에 대해 설명합니다.

### <a name="subcontracted-services"></a>하도급 서비스

활동 기반 하도급에 사용되는 지불 항목은 다음 속성을 가진 제품이어야 합니다.

-   **제품 유형:** 서비스
-   **인벤토리 모델 그룹:** 재고 없음

이 요구 사항은 FIFO(선입 선출) 인벤토리 모델의 사용을 시행합니다. **참고:** 제품의 비용 계산을 위해서는 서비스의 표준 비용이 정의되어야 합니다. 공급업체와의 구매 계약이 필요합니다. 그렇지 않으면 활동 기반 하도급에 서비스를 사용할 수 없습니다.

### <a name="subcontracted-process-activities"></a>하도급 프로세스 활동

프로세스 활동을 외주 활동으로 구성하려면 다음 단계를 따르세요.

1.  하청 작업 셀을 구성합니다. 작업 셀을 외주로 구성하려면 **공급업체** 유형의 리소스를 만들고 작업 셀(리소스 그룹)과 연결해야 합니다. **직접 아웃소싱** 비용 그룹 유형의 런타임 비용 범주는 작업 셀에 지정되어야 합니다. 설정 및 수량에 대한 비용 범주는 필요하지 않습니다.
2.  프로세스 활동이 작성되고 외주 작업 셀과 관련된 후에는 생산 흐름 버전을 활성화하기 전에 활동에 대한 서비스를 구성해야 합니다. **활동** **세부 정보** 페이지에서 이 단계를 완료합니다. 외주 작업 셀과 관련된 활동의 경우 **서비스 약관** 빠른 탭이 표시됩니다. 이 빠른 탭에서 모든 출력 항목에 유효한 기본 서비스를 추가합니다. 특정 출력 항목에 다른 서비스 또는 다른 서비스 계산 매개 변수가 필요한 경우(예: 다른 서비스 비율) 다른 서비스를 활동에 추가할 수 있습니다.

## <a name="subcontracted-transfer-activities"></a>하도급 전송 활동
전송 활동은 전송 활동의 **화물 전송** 설정에 따라 하도급 활동으로 구성됩니다. 다음 옵션을 사용할 수 있습니다.

-   **배송업체** – 창고에서 이전이 공급업체에 의해 관리되는 경우 활동은 외주됩니다(창고의 속성에 따라 정의됨). 서비스에 대해 선택한 모든 구매 계약에는 창고와 동일한 공급업체 ID가 있어야 합니다.
-   **수신자** – 창고로의 이전이 공급업체에 의해 관리되는 경우 활동은 외주됩니다(창고의 속성에 따라 정의됨). 서비스에 대해 선택한 모든 구매 계약에는 창고와 동일한 공급업체 ID가 있어야 합니다.
-   **운송업체** - 활동은 서비스를 제공하는 모든 공급업체에 하도급됩니다. 유효하려면 창고 관리를 위해 운송업체를 생성해야 하고 할당된 공급업체 계정이 있어야 합니다.

프로세스 활동의 경우 **활동** **세부 정보** 페이지의 **서비스 약관** 빠른 탭에서 하도급 이전 활동에 대한 기본 서비스를 구성해야 합니다.

## <a name="service-quantity-calculation"></a>서비스 수량 계산
전체 구매 프로세스는 서비스에 대한 항목 참조를 기반으로 합니다. 이 항목 참조는 서비스 측정 단위로 측정됩니다. 서비스는 일반적으로 서비스 수(단위) 또는 시간으로 측정됩니다. 칸반 작업의 등록 완료를 기반으로 서비스 수량을 계산하려면 다음 방법을 사용할 수 있습니다.

-   **작업 수를 기반으로 한 계산** – 하나의 칸반 작업은 서비스 *n* 개와 같으며, 공급되는 제품 수량과 관계없습니다. 린 제고에서 하나의 작업은 하나의 처리 장치에 해당합니다. 이 계산 방법은 처리 단위당 고정 가격이 있는 모든 서비스에 적용됩니다. 따라서 이 방법은 일반적으로 이전 활동에 적용됩니다. 그러나 전체 처리 단위를 처리하는 프로세스 활동에도 적용될 수 있습니다.
-   **제품 수량을 기반으로 한 계산** – 서비스 수량은 예정/공급되는 제품 수량에 상대적입니다. 공급된 제품 수량을 계산할 때 오류 수량을 포함하거나 제외할 수 있습니다. 이 계산 방법은 가공 제품의 단위당 서비스 가격이 합의된 모든 경우에 적용됩니다.
-   **활동 시간을 기반으로 한 계산** – 이론적인 활동 시간은 활동의 처리 시간, 총 처리 수량 및 처리된 제품의 처리 비율을 기반으로 계산됩니다. 이 계산 방법은 시간당 지급되는 서비스에 적용되며, 처리된 제품별로 시간차가 있습니다.

## <a name="cost-accounting-of-subcontracted-services"></a>하도급 용역의 원가회계
생산 흐름을 위해 생성된 구매 주문(즉, 외주 활동에 대한 칸반 작업을 기반으로 생성된 구매 주문)에 대한 입고 권고 또는 공급업체 포장 전표가 전기되면 입고 금액이 생산 흐름의 WIP 계정에 전기됩니다. 송장의 편차도 생산 흐름에 반영됩니다. 하도급 작업에 대한 비용 범주가 도입되었습니다. 이 비용 범주를 통해 WIP에 할당되고 기간별로 소비되는 외주 작업의 가치를 투명하게 추적할 수 있습니다.  

원가 계산 기간 종료 시 린 제고에 대한 역산 원가 계산은 원가 계산 기간 동안 생산 흐름에서 생산된 제품의 실제 차이를 계산합니다.

## <a name="modeling-transfers-as-subcontracted-activities"></a>이전을 외주 활동으로 모델링
사람들은 종종 운송이 비생산적이라고 생각하고 가치가 없다고 생각합니다. 그러나 하도급 비용을 내부 생산 비용과 비교할 때 추가 운송 활동 비용을 고려해야 합니다. 여러 위치에 걸쳐 있고 운송 서비스가 필요한 생산 흐름은 고객에게 제품을 공급하는 비용의 일부로 운송 비용을 모델링해야 합니다. 

린 제고의 활동 기반 하도급을 사용하면 생산 흐름의 위치 간에 자재와 제품을 이동하는 운송업체와 운송 공급업체를 통합할 수 있습니다. 이전 활동을 모델링하여 운송업체 또는 공급업체를 지정할 수 있습니다. 이전 활동/작업은 서비스 및 구매 계약을 기반으로 하며 실제 이전 작업을 기반으로 구매 주문 및 입고 안내를 생성할 수 있습니다. 이 기능은 외주 프로세스 활동에 대한 기능과 동일합니다.  

이제 Supply Chain Management는 운송 서비스, 관련 구매 주문 생성, 통합 영수증 등록 및 생산 흐름 원가 계산에 운송 서비스 비용 통합을 포함하는 BOM 계산을 지원합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]