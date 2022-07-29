---
title: 교차 도킹을 위한 자동 릴리스 선적
description: 이 항목에서는 수요 수량을 공급하는 생산 주문이 완료된 것으로 보고될 때 자동으로 수요 주문을 창고로 릴리즈하여 수량을 생산 출력 위치에서 아웃바운드 위치로 직접 이동할 수 있는 교차 도킹 전략에 대해 설명합니다.
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 1315bda1fd284eb326d4f08bf36bfea59074fde3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449056"
---
# <a name="auto-release-shipment-for-cross-docking"></a>교차 도킹을 위한 자동 릴리스 선적

[!include [banner](../includes/banner.md)]

이 항목에서는 수요 수량을 공급하는 생산 주문이 완료된 것으로 보고될 때 수요 주문을 창고로 자동 릴리즈할 수 있는 교차 도킹 전략에 대해 설명합니다. 이러한 방식으로 수요 주문을 이행하는 데 필요한 수량이 생산 출력 위치에서 아웃바운드 위치로 직접 이동됩니다.

교차 도킹은 아웃바운드 주문을 이행하는 데 필요한 수량을 인바운드 주문이 접수된 위치에서 주문의 아웃바운드 도크 또는 스테이징 영역으로 보내는 창고 처리 흐름입니다. (인바운드 주문은 구매 주문더, 이전 주문 또는 생산 주문이 될 수 있습니다.) 고급 크로스 도킹 기능은 모든 공급 및 수요 주문을 지원하며 크로스 도킹 기회가 종료되기 전에 아웃바운드 수요가 릴리즈되어야 합니다. 식별된 경우 자동 릴리스 배송 기능에는 다음과 같은 특성이 있습니다.

- 생산 주문만 공급으로 지원하고 판매 주문과 이전 주문만 수요로 지원합니다.
- 공급 입고가 등록되기 전(즉, 생산이 완료된 것으로 보고되기 전)에 수요 주문이 창고로 출고되지 않은 경우에도 교차 도킹 작업을 시작할 수 있습니다.

이 교차 도킹 기능에는 두 가지 이점이 있습니다.

- 창고 운영은 아웃바운드 주문을 이행하기 위해 해당 수량을 다시 픽업하는 경우 완제품 수량을 일반 창고 보관 영역에 보관하는 단계를 건너뛸 수 있습니다. 대신 수량을 출력 위치에서 포장/배송 위치로 한 번만 이동할 수 있습니다. 이러한 방식으로 기능은 재고 처리 횟수를 최소화하고 궁극적으로 창고 작업 현장에서 시간과 공간 절약을 최대화하는 데 도움이 됩니다.
- 창고 작업은 연결된 생산 주문에 대한 완제품의 출력이 완료된 것으로 보고될 때까지 판매 주문 릴리스 및 창고로 주문 이전을 연기할 수 있습니다. 이 이점은 제조 리드 타임이 재고 제작 환경의 리드 타임보다 긴 경향이 있는 주문 제작 생산 환경에서 특히 관련이 있을 수 있습니다.

## <a name="prerequisites"></a>전제 조건

| 전제 조건 | 설명 |
|---|---|
| 항목 | 항목은 창고 관리 프로세스에 대해 활성화되어야 합니다.<p>**메모:** 캐치 웨이트가 활성화된 항목은 교차 도킹 프로세스에 포함될 수 없습니다.</p> |
| 창고 | 창고 관리 프로세스에 대해 창고를 활성화해야 합니다. |
| 크로스 도킹 템플릿 | **공급 수령 시** 수요 릴리스 정책을 사용하는 하나 이상의 교차 도킹 템플릿이 지정된 창고에 대해 설정되어야 합니다. |
| 작업 클래스 | 교차 도킹 작업 클래스 ID가 **크로스 도킹** 작업 주문 유형에 대해 생성되어야 합니다. |
| 작업 템플릿 | 교차 도킹 픽 앤 풋 작업을 생성하려면 **크로스 도킹** 작업 주문 유형의 작업 템플릿이 필요합니다. |
| 위치 지시문 | 판매 주문 수량을 포장 및 배송할 위치에서 작업을 안내하려면 **크로스 도킹** 작업 주문 유형의 위치 지시문이 필요합니다. |
| 수요 주문과 생산 주문 사이의 마킹 | 창고 시스템은 판매 주문 및 이전 주문이 예약되고 생산 주문에 대해 표시된 경우에만 아웃바운드 주문 선적의 자동 릴리스를 트리거하고 완료로 보고 조치의 출력 위치에서 교차 도킹 작업을 생성할 수 있습니다. |

## <a name="example-cross-docking-flow"></a>크로스 도킹 흐름의 예

일반적인 크로스 도킹 흐름은 다음과 같은 주요 단계로 구성됩니다.

1. 판매 주문 접수자는 주문 제작 제품에 대한 판매 주문을 생성합니다. 일반적으로 요청된 수량은 현재 보유하고 있지 않으며 먼저 생산되어야 합니다.
2. 판매 주문 수령자는 판매 주문 라인에서 직접 생산 주문을 생성합니다. 이러한 방식으로 판매 주문 수령자는 생산 주문 수량에 대해 판매 주문 수량을 예약하고 표시합니다. 

    또는 생산 계획자가 계획 주문이 확정될 때 표시를 업데이트해야 한다고 지정합니다.

3. 생산 주문은 다음 단계를 거칩니다.

    1. 생산 계획자는 생산 주문을 추정하고 릴리스합니다. (추정에는 원자재 예약이 포함되며 출고에는 창고로 출고가 포함됩니다.)
    2. 창고 작업자는 생산 피킹 작업에 따라 저장 위치에서 생산 입력 위치까지 원자재 피킹을 시작하고 완료합니다.
    3. 작업 현장 작업자가 생산 주문을 시작합니다.
    4. 마지막 작업에서 기계 운영자는 모바일 디바이스를 사용하여 생산 주문이 완료된 것으로 보고합니다.

4. 시스템은 설정을 사용하여 연결된 두 주문에 대한 교차 도킹 이벤트를 식별한 다음 다음 작업을 완료합니다.

    1. 관련 판매 주문을 창고로 자동 릴리즈하여 선적을 생성합니다.
    2. 출력 위치에서 완제품을 선택하고 교차 도킹 위치가 판매 주문에 할당한 아웃바운드 위치로 이동하라는 지침이 있는 교차 도킹 작업을 자동으로 생성합니다.
    3. 생산 주문이 완료된 것으로 보고된 후 즉시 교차 도킹 작업을 완료하도록 기계 작업자에게 프롬프트를 표시합니다.

5. 크로스 도킹 작업이 완료되고 수량을 차량에 싣고 나면 아웃바운드 창고 계획자가 판매 선적을 확인합니다.

## <a name="example-scenario"></a>예시 시나리오

이 시나리오의 경우 데모 데이터가 설치되어 있어야 하며 **USMF** 데모 데이터 회사를 사용해야 합니다.

### <a name="set-up-cross-docking-that-uses-the-auto-release-shipment-feature"></a>자동 출시 배송 기능을 사용하는 교차 도킹 설정

#### <a name="cross-docking-template"></a>크로스 도킹 템플릿

1. **창고 관리** \> **설정** \> **작업** \> **크로스 도킹 템플릿** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **시퀀스 번호** 필드에 **1** 을 입력합니다.
4. **크로스 도킹 템플릿 ID** 필드에 **XDock\_RAF** 와 같은 이름을 입력합니다.
5. **수요 릴리스 정책** 필드에서 **공급 수령 시** 를 선택합니다.
6. **창고** 필드에 크로스 도킹 프로세스를 설정할 창고 번호를 입력합니다. 이 예에서는 **51** 을 선택합니다.

    > [!NOTE]
    > **공급 수령 시** 를 템플릿에 대한 수요 릴리스 정책으로 선택하는 즉시 페이지의 다른 모든 필드를 사용할 수 없게 됩니다. 마찬가지로, 공급 소스를 정의할 수 없습니다. 이 동작은 자동 출고 배송 기능을 사용하는 크로스 도킹이 공급 소스로 생산 주문만 지원하고 판매 주문과 생산 주문 사이에 표시가 있어야 하기 때문에 발생합니다. **공급 수령 전** 을 수요 릴리스 정책으로 선택하면 **계획** 및 **공급원** 탭의 필드를 사용할 수 있으며 편집할 수 있습니다.

#### <a name="work-classes"></a>작업 클래스

1. **창고 관리** \> **설정** \> **작업** \> **작업 클래스** 로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **작업 클래스 ID** 필드에 **CrossDock** 과 같은 이름을 입력합니다.
4. **작업 주문 유형** 필드에서 **크로스 도킹** 을 선택합니다.

교차 도킹된 완제품을 넣을 수 있는 위치 유형을 제한하려면 하나 이상의 유효한 위치 유형을 지정할 수 있습니다.

#### <a name="work-templates"></a>작업 템플릿

1. **창고 관리** \> **설정** \> **작업** \> **작업 템플릿** 으로 이동합니다.
2. **작업 주문 유형** 필드에서 **크로스 도킹** 을 선택합니다.
3. **새로 만들기** 를 선택합니다.
4. **시퀀스 번호** 필드에 **1** 을 입력합니다.
5. **작업 템플릿** 필드에 **CrossDock\_51** 과 같은 이름을 입력합니다.
6. **저장** 을 선택합니다.
7. **작업 템플릿 세부 정보** 섹션에서 **새로 만들기** 를 선택합니다.
8. 새로운 라인의 경우 **작업 유형** 필드에서 **픽** 을 선택합니다. **작업 클래스 ID** 필드에서 **CrossDock** 를 선택합니다.
9. **새로 만들기** 를 선택합니다.
10. 새로운 라인의 경우 **작업 유형** 필드에서 **풋** 을 선택합니다. **작업 클래스 ID** 필드에서 **CrossDock** 를 선택합니다.

#### <a name="location-directives"></a>위치 지시문

완제품에 대한 표준 폐기 프로세스에는 피킹된 생산 수량을 일반 보관 공간으로 이동하도록 안내하는 **풋** 위치 지시문이 필요합니다. 마찬가지로 크로스 도킹 **풋** 위치 지시문을 설정하여 관련 판매 주문의 배송을 서비스하는 지정된 아웃바운드 위치에 완성 수량을 두도록 작업에 지시해야 합니다.

크로스 도킹의 경우 정기적인 완제품 반입과 같이 출력 위치가 제공되므로 피킹 작업에 대한 위치 지시문을 만들 필요가 없습니다. 또한 이 출력 위치는 자원 관련 레코드(즉, 자원, 자원 그룹 관계 또는 자원 그룹) 중 하나의 기본 출력 위치로 설정되거나 기본 생산 완제품 위치로 설정됩니다.

1. **창고 관리** \> **설정** \> **위치 지시문** 으로 이동합니다.
2. **작업 주문 유형** 필드에서 **크로스 도킹** 을 선택합니다.
3. **새로 만들기** 를 선택합니다.
4. **시퀀스 번호** 필드에 **1** 을 입력합니다.
5. **이름** 필드에 **Baydoor** 와 같은 이름을 입력합니다.
6. **작업 유형** 필드에서 **풋** 을 선택합니다.
7. **사이트** 필드에서 **5** 을 선택합니다.
8. **창고** 필드에서 **51** 을 선택합니다.
9. **라인** 빠른 탭에서 **새로 만들기** 를 선택합니다.
10. **도착 수량** 필드에 **1000000** 과 같은 범위의 최대 수량을 입력합니다.
11. **저장** 을 선택합니다.
12. **위치 지시문 조치** 빠른 탭에서 **새로 만들기** 를 선택합니다.
13. **이름** 필드에 **Baydoor** 와 같은 이름을 입력합니다.
14. **저장** 을 선택합니다.
15. 표준 쿼리 기능을 사용하여 넣기 위치를 하나 이상의 특정 위치로 제한할 수 있습니다. **쿼리 편집** 을 선택하고 **위치** 테이블의 **창고** 필드에 대한 기준으로 **51** 을 선택합니다.

### <a name="cross-dock-finished-goods-to-the-outbound-location"></a>완제품을 아웃바운드 위치로 교차 도킹

관련 판매 주문의 아웃바운드 위치에 완제품 수량을 교차 도킹하려면 다음 단계를 따르세요.

1. **영업 및 마케팅** \> **판매 주문** \> **모든 판매 주문** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. 판매 주문 헤더의 경우 고객 계정 **US-001** 및 자동 출고 배송 기능을 사용하는 교차 도킹을 위해 설정된 창고를 선택합니다.
4. 완제품에 대한 라인을 추가하고 수량으로 **10** 을 입력합니다.
5. **판매 주문 라인** 섹션에서 **제품 및 공급** \> **생산 주문** 을 선택합니다.
6. **생산 주문 생성** 대화 상자에서 기본값을 검토한 다음 **만들기** 를 선택합니다. 새 생산 주문이 생성되어 판매 주문에 연결됩니다(즉, 예약 및 표시됨).
7. 선택 사항: **수량** 필드의 값을 변경하여 판매 주문을 이행하는 데 필요한 값보다 크도록 합니다. 생산 수량이 완성된 것으로 보고되면, 시스템은 완제품의 반출 처리를 위한 정규 절차에 따라 표시된 수량에 대해 교차 입하 작업을 생성하고 나머지 수량에 대해 반출 작업을 생성합니다.

    앞서 언급했듯이 판매 주문과 생산 주문 사이에 마킹이 있어야 합니다. 그렇지 않으면 크로스 도킹이 작동하지 않습니다. 다음과 같은 여러 방법으로 표시를 만들 수 있습니다.

    - 시스템은 다음과 같은 상황에서 자동으로 마킹을 생성할 수 있습니다.

        - 판매 주문은 판매 주문 라인에서 직접 수동으로 생성됩니다(6단계 참조).
        - 계획된 생산 주문이 확정되고 **업데이트 표시** 필드가 **표준** 으로 설정됩니다.

    - 사용자는 수요 주문 라인에서 **마킹** 페이지를 열어 수동으로 마킹을 만들 수 있습니다.

    > [!NOTE]
    > 표준 및 가중 평균을 인벤토리 모델로 사용하도록 설정된 항목에 대해서는 표시를 수동으로 생성할 수 없습니다.

8. **생산 주문** 페이지의 작업 창에서 **생산 주문** 탭의 **프로세스** 그룹에서 **추정** 을 선택한 다음 **확인** 을 선택합니다. 주문이 예상되고 원자재 수량이 생산을 위해 예약됩니다.
9. 작업 창의 **생산 주문** 탭에 있는 **프로세스** 그룹에서 **릴리스** 를 선택한 다음 **확인** 을 선택합니다. 창고 피킹 작업이 원자재에 대해 생성됩니다.
10. 작업을 열고 검토합니다. 작업 창의 **창고** 탭에 있는 **일반** 그룹에서 **작업 세부 정보** 를 선택합니다. 작업 ID를 기록해 둡니다.
11. Warehouse Management 모바일 앱에 로그인하여 창고 51의 작업을 실행합니다.
12. **생산** \> **생산 픽** 으로 이동합니다.
13. 작업 ID를 입력하여 원료 피킹을 시작하고 완료합니다. 

    작업이 완료된 것으로 보고된 후 생산 입력 위치에서 원자재 수량을 사용할 수 있으며(USMF 데모 데이터의 **005**), 생산 주문 실행을 시작할 수 있습니다.

14. **생산 주문** 페이지의 작업 창에서 **생산 주문** 탭의 **프로세스** 그룹에서 **시작** 을 선택한 다음 **확인** 을 선택합니다.
15. 앱에서 **생산** \> **RAF 및 풋 어웨이** 로 이동합니다.
16. **생산 ID** 필드에 생산 주문 번호 및 기타 필수 세부 정보를 입력한 다음 **확인** 을 선택합니다.

다음 이벤트가 발생합니다.

- 연결된 판매 주문에 대해 창고로의 릴리즈가 트리거됩니다.
- 출시를 기준으로 선적 및 교차 도킹 작업이 생성됩니다. 이 작업은 창고 운영자에게 판매 주문 라인을 이행하는 데 필요한 수량을 선택하고 교차 도킹 위치 지시문에 지정된 아웃바운드 위치에 두도록 지시합니다.
- 생산 주문 수량이 판매 주문에 필요한 수량보다 많을 경우 정기적인 배치 작업이 생성됩니다. 이 작업은 창고 운영자에게 위치 지시에 따라 크로스 도킹 후 남은 완제품의 수량을 선택하고 일반 보관소로 이동하도록 지시합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]