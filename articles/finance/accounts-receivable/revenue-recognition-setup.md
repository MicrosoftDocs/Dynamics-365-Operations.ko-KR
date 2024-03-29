---
title: 수익 인정 설정
description: 이 문서에서는 수익 인정을 위한 설정 옵션과 그러한 옵션의 함의에 대해 설명합니다.
author: bking
ms.date: 04/28/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: bking
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 00acb795b05d01136cc154f697e7c955b0c6b620
ms.sourcegitcommit: 1909d18a74cef85aad020a6a7473281e451f58c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2022
ms.locfileid: "9348415"
---
# <a name="revenue-recognition-setup"></a>수익 인정 설정
[!include [banner](../includes/banner.md)]

필요한 모든 설정에 대한 메뉴 항목을 포함하는 새 **수익 인정** 모듈이 추가되었습니다. 이 문서에서는 설정 옵션과 그러한 옵션의 함의에 대해 설명합니다.

> [!NOTE]
> 수익 인정 기능은 이제 기본 설정에 따라 기능 관리를 통해 사용할 수 있습니다. 조직에서 이 기능을 사용하지 않는 경우, **기능 관리** 작업 영역에서 이 기능을 끌 수 있습니다.
>
> 번들 기능을 포함한 수익 인정은 Commerce 채널(전자 상거래, POS 및 콜 센터)에서 지원되지 않습니다. 수익 인정을 위해 구성된 항목들은 Commerce 채널에서 생성된 주문 또는 거래에 추가하면 안 됩니다.

**수익 인정** 모듈에는 다음과 같은 설정 옵션들이 있습니다.

- 수익 인정 분개장
- 수익 인정을 위한 매개 변수
- 수익 일정 
- 재고 설정

    - 품목 그룹 및 출시된 제품
    - 수익 일정 정의
    - 수익 가격 정의
    - 재고 설정

        - 수익 일정 정의
        - 수익 가격 정의

    - 기장 프로필
    - 번들

        - 번들 구성 요소
        - 번들 항목

- 프로젝트 설정

## <a name="revenue-recognition-journals"></a>수익 인정 분개장

수익 인정을 위해 새 분개장 유형이 도입되었습니다. 분개장은 필수이며 두 가지 시나리오에서 사용됩니다.

첫 번째 시나리오는 모든 계약상 의무가 이행된 후 수익 일정의 세부 내역을 기초로 하는 수익 인정 분개장을 작성하여 이연 수익을 인정할 때 발생합니다. 분개장에는 이연 수익 원장 계정에서 수익 원장 계정으로 잔액을 이전하는 회계 기입이 포함되어 있습니다.

두 번째 시나리오는 재할당이 발생한 후 하나의 분개장이 작성될 때 발생합니다. 재할당은 판매 주문 라인이 이전에 송장 발행된 판매 주문 건에 추가되거나 원 계약의 일부에 속하는 라인을 포함하는 새 판매 주문이 생성될 때 발생합니다. 새 판매 주문 라인이 추가되기 전에 송장이 기장된 경우, 기장된 고객 송장에 대해 수정 회계 기입을 생성해야 합니다.

분개장은 **분개장 이름** 페이지(**수익 인정 \> 설정 \> 분개장 이름**)에 설정됩니다. 분개장 유형은 **수익 인정** 으로 설정해야 합니다. 

## <a name="parameters-for-revenue-recognition"></a>수익 인정을 위한 매개 변수

수익 인정 설정은 **총계정원장 매개 변수** 페이지의 **수익 인정** 탭에 구성됩니다(**수익 인정 \> 설정 \> 총계정원장 매개 변수**). 다음과 같은 설정을 사용할 수 있습니다.

- **수익 인정 분개장 이름** – 수익 인정을 위해 생성된 분개장을 선택합니다. 분개장은 수익 일정에서 수익이 인정되거나 송장이 이미 발행된 판매 주문 건에 대해 재할당을 실시할 때 필요합니다.
- **할인 할당 방법 사용** – 출시된 각 제품의 수익 가격에 정의된 공정 시가를 할당함으로써 수익 가격을 결정하려면 이 옵션을 **예** 로 설정하십시오. 이 할당에는 해당 품목에 대한 모든 라인 할인의 할당이 포함됩니다. 이 옵션이 **아니요** 로 설정된 경우, 시스템은 출시된 각 제품의 수익 가격에 정의된 중간 가격을 사용합니다. 이 옵션이 **아니요** 로 설정되었지만 출시된 해당 제품에 대한 중간 가격이 설정되지 않은 경우, 수익 가격의 할당이 발생하지 않습니다.
- **헤더 할인 포함** – 제반 제품에 대해 헤더 할인을 할당하여 수익 가격을 결정하려면 이 옵션을 **예** 로 설정합니다. 이 옵션이 **아니요** 로 설정된 경우, 헤더 할인은 수익 가격 할당에 포함되지 않습니다.
- **계약 조건 사용 안 함** – **계약 후 지원** 의 수익 유형을 가진 제품이 계약 시작 및 종료 날짜가 정의되지 않은 경우에도 출시될 수 있는 경우, 이 옵션을 **예** 로 설정합니다. 일반적으로 계약 시작 날짜와 종료 날짜는 **계약 후 지원** 수익 유형에 속한 항목에 필요합니다. 계약 시작 날짜와 종료 날짜를 정의하지 않은 경우, 발생 횟수와 송장 날짜를 이용하여 기장 날짜의 수익 일정 세부 내역을 계산합니다.
- **재할당 시 수취 계정에 송장 수정 기장** – 이미 기장된 송장에 대해 재할당을 실시하는 경우, 기장된 송장에 대한 회계 기입을 수정해야 합니다. 이 옵션을 사용하여 수정을 진행하는 방법을 지정합니다.

    - 총계정원장에 대한 수정 거래의 기장을 제한하려면 이 옵션을 **아니요** 로 설정하십시오. 이 옵션이 **아니요** 로 설정되면 내부 회계 수정을 위한 수취 계정에서 추가 문서가 작성되지 않습니다. 송장 대금이 결제되면 정산 프로세스는 이전 회계 기입을 사용하여 현금 할인 또는 실현 손익의 내역을 기장합니다.
    - 이 옵션을 **예** 로 설정하면 수취 계정의 수정 거래에 대한 반대 기입 문서와 새 송장이 자동으로 생성됩니다. 이러한 수정은 내부 회계 수정이므로 새 문서가 고객에게 전송되거나 전달되지 않습니다. 반대 기입 문서는 송장 원본으로 정산되며 수정된 새 송장은 고객이 결제합니다. 3건의 문서는 모두 고객 명세서와 같은 보고서에 표시됩니다.

[![설정 정보.](./media/revenue-recognition-setup-info.png)](./media/revenue-recognition-setup-info.png)

## <a name="revenue-schedules"></a>수익 일정

수익을 이연할 수 있는 각 발생 건에 대해 수익 일정을 생성해야 합니다. 예를 들어, 조직에서 6개월, 12개월, 18개월, 24개월의 기간 동안 지원을 제공한다면 각 기간에 대한 수익 일정을 생성해야 합니다. 수익 일정의 설정에 따라 선택한 기간 동안 수익 가격이 할당되는 방식이 결정됩니다. 또한 송장이 기장될 때 작성되는 수익 일정에 대해 입력되는 기본 날짜도 결정됩니다.

마일스톤별로 수익을 인정하는 경우, 인식 날짜에 관계없이 마일스톤 수에 대한 수익 인식 일정을 작성하는 것이 좋습니다. 일정을 생성한 후에는 예상되는 마일스톤 날짜를 반영하도록 일정을 편집할 수 있습니다. 이러한 레코드는 마일스톤에 도달했으며 수익을 인정할 수 있다는 알림을 받을 때까지 보류할 수 있습니다.

수익 일정은 **수익 일정** 페이지(**수익 인정 \> 설정 \> 수익 일정**)에서 생성됩니다.

[![수익 일정.](./media/revenue-recognition-revenue-schedules.png)](./media/revenue-recognition-revenue-schedules.png)

**수익 일정** 및 **설명** 필드에 설명 값을 입력합니다. 다음 추가 설정은 송장이 기장될 때 수익 일정을 생성하는 데 사용됩니다.

- **발생** – 수익 이연 기간의 개월 수 또는 발생 횟수를 입력합니다.
- **자동 보류** – 송장이 기장될 때 수익 일정의 모든 라인이 자동으로 보류되어야 하는 경우, 이 확인란을 선택합니다. 해당 라인의 이연 수익을 인정하려면 먼저 해당 일정의 각 라인에서 보류 건을 수동으로 제거해야 합니다.
- **자동 계약 조건** – 계약 시작 날짜와 종료 날짜를 자동으로 설정해야 하는 경우, 이 확인란을 선택합니다. 이 날짜는 **계약 후 지원** 수익 유형의 출시된 제품에 대해서만 자동으로 설정됩니다. 계약 시작 날짜는 판매 주문 라인의 요청된 배송 날짜로 자동 설정되며 계약 종료 날짜는 수익 일정의 설정 시 정의된 개월 수 또는 발생 횟수를 시작 날짜와 합산한 값으로 자동 설정됩니다. 예를 들어, 판매 주문 라인의 제품에 대해서는 1년간 보증이 제공됩니다. 기본 수익 일정은 **12M**(12개월)으로 설정되며 이 수익 일정에 대해서는 **자동 계약 조건** 확인란이 선택되어 있습니다. 판매 주문 라인의 요청된 배송 날짜가 2019년 12월 16일인 경우, 기본 계약 시작 날짜는 2019년 12월 16일이며 기본 계약 종료 날짜는 2020년 12월 15일입니다.
- **인정 기준** – 인정 기준은 수익 가격이 전체 발생 건에 걸쳐 할당되는 방식을 결정합니다.

    - **월별 일수 기준** – 금액은 매월 실제 날짜를 기준으로 할당됩니다.
    - **매월** – 금액은 해당 발생 건에서 정의된 개월 수에 걸쳐 균등하게 할당됩니다.
    - **발생** – 금액은 전체 발생 건에 걸쳐 균등하게 할당되며 다만 **실제 시작 날짜** 를 수익 인정 규칙으로 선택하는 경우에는 추가 기간이 포함될 수 있습니다.
    - **회계 기간 일수 기준** – 금액은 각 회계 기간 중 실제 날짜를 기준으로 할당됩니다. 

         - 회계 기간이 역월 다음에 오는 경우, **월별 일수** 및 **회계 기간 일수** 의 결과는 동일합니다. 유일한 예외 조건은 수익 인정 규칙이 **월말/기말** 로 설정된 경우 그리고 판매 주문 라인에서 **계약 시작 날짜** 와 **종료 날짜** 필드가 비어 있는 경우입니다.

- **인정 규칙** – 인정 규칙은 해당 송장에 대한 수익 일정에 설정되는 날짜를 결정합니다.

    - **실제 시작 날짜** – 일정은 계약 시작 날짜 (계약 후 지원 \[PCS\] 항목) 또는 송장 날짜(필수 항목 및 비필수 항목의 경우) 중 하나를 사용하여 생성됩니다.
    - **매월/매 기간의 초일** – 첫 일정 라인의 날짜는 계약 시작 날짜(또는 송장 날짜)에 해당됩니다. 그러나 모든 후속 일정 라인은 해당 월 또는 회계 기간의 초일에 대해 생성됩니다.
    - **월중 분할** – 첫 일정 라인의 날짜는 송장 날짜에 따라 달라집니다. 송장이 매월 1일부터 15일까지의 기간에 기장되는 경우, 해당 월의 초일을 적용하여 수익 일정이 생성됩니다. 송장이 매월 16일 또는 그 이후의 날짜에 기장되는 경우, 익월의 초일을 적용하여 수익 일정이 생성됩니다.

        - 인정 기준이 **회계 기간 일수 기준** 으로 설정되어 있는 경우, **월중 분할** 은 선택할 수 없습니다.

    - **익월/차기의 초일** – 일정이 시작되는 날짜는 다음 달 또는 다음 회계 기간의 첫째 날입니다.
    - **매월/매 기간의 말일** – 첫 일정 라인의 날짜는 계약 시작 날짜(또는 송장 날짜)에 해당됩니다. 그러나 모든 후속 일정 라인은 해당 월 또는 회계 기간의 말일에 대해 생성됩니다. 

**수익 일정 세부 정보** 버튼을 선택하면 일반 기간과 각 기간에 인식되는 백분율을 볼 수 있습니다. 기본적으로 **인식 백분율** 값은 전체 기간 수에 걸쳐 균등하게 나뉩니다. 인정 기준이 **매월** 로 설정된 경우, 인식 백분율을 변경할 수 있습니다. 인식 백분율을 변경하면 합계가 100%가 아님을 알리는 경고 메시지가 나타납니다. 해당 메시지를 수신하면 라인을 계속 편집할 수 있습니다. 그러나 페이지를 닫기 전 총 백분율은 100이어야 합니다.

[![수익 일정 세부 정보.](./media/revenue-schedule-details-2nd-scrn.png)](./media/revenue-schedule-details-2nd-scrn.png)

## <a name="inventory-setup"></a>재고 설정

판매 주문 건에서 출시된 제품에 대한 수익을 인정할 수 있으며 다만 해당 문서에 아무런 항목도 포함되지 않은 경우, 판매 주문 건의 판매 범주나 무료 문자 송장으로는 수익을 인정할 수 없습니다. 출시된 제품을 설정할 때 선택하는 사항에 따라 해당 항목의 수익을 인정하는 방식이 결정됩니다. 예를 들어, 수익 가격이 할당되는지 여부와 수익 일정을 사용하여 수익이 이연되는지 여부는 선택 사항에 따라 결정됩니다.

해당 설정은 **항목 그룹** 페이지의 **수익 인정** 빠른 탭에서 시작할 수 있습니다(**수익 인정 \> 설정 \> 재고 및 제품 설정 \> 항목 그룹**). 이 페이지에는 여러 설정 필드가 포함되어 있습니다. 이들 필드는 시스템 내에서 생성되는 신규 출시 제품에 대해서만 기본값을 설정하는 데 사용됩니다. 새 제품이 생성되면 여기에 설정한 값이 해당 항목 그룹에 대해 기본적으로 입력됩니다. **출시된 제품** 페이지에서 출시된 제품의 기본값을 재정의할 수 있습니다(**수익 인정 \> 설정 \> 재고 및 제품 설정 \> 출시된 제품**). 그러면 출시된 제품에 대해 설정된 기본값이 판매 주문 건으로 이월됩니다.

## <a name="item-groups-and-released-products"></a>품목 그룹 및 출시된 제품

### <a name="define-the-revenue-schedule"></a>수익 일정 정의

출시된 제품에 대해 수익 일정이 정의되고 이 일정이 판매 주문 라인에서 기본적으로 사용되는 경우, 판매 주문 라인의 수익은 이연됩니다. 해당 제품에 대해 기본적으로 설정을 사용해야 하는 경우, **항목 그룹** 페이지의 **수익 인정** 빠른 탭에서 수익 일정을 정의할 수 있습니다(**수익 인정 \> 설정 \> 재고 및 제품 설정 \> 항목 그룹**). **출시된 제품** 페이지의 **수익 인정** 빠른 탭에서 출시된 제품에 대한 설정을 정의할 수도 있습니다(**수익 인정 \> 설정 \> 재고 설정 \> 출시된 제품**).

**수익 일정** 필드에서 수익을 이연해야 하는 기간을 나타내는 수익 일정을 선택합니다. 수익 일정은 판매 주문 라인에 자동으로 입력되며, 판매 주문 송장이 기장될 때 수익 일정의 세부 정보가 생성됩니다.

### <a name="define-the-revenue-price"></a>수익 가격 정의

항목 그룹 및 출시된 제품은 중간 가격 방식 또는 할인 할당 방식을 사용하여 설정할 수 있습니다. **출시된 제품** 페이지에서 이러한 두 가지 방법은 모두 다음과 같이 다양한 설정이 필요합니다.

- **수익 할당이 활성화되어 있습니까?** – 출시된 제품을 수익 할당 계산에 포함시키려면 이 옵션을 **예** 로 설정하십시오. 이 옵션이 **아니요** 로 설정된 경우, 중간 가격이 정의되어 있다면 출시된 제품에서는 중간 가격 방식을 사용합니다. 중간 가격이 정의되지 않은 경우, 판매 주문 라인의 단가는 수익 또는 이연 수익으로 기장하는 데 사용됩니다.
- **수익 유형** – 출시된 제품을 정의하는 수익 유형을 선택합니다.

    - **필수** – 해당 항목은 조직의 주요 수익원에 속합니다. 이 값은 기본 설정에 해당됩니다.
    - **비필수** – 해당 항목은 조직의 주요 수익원에 속하지 않습니다. 중간 가격 설정을 사용하는 경우, 가격은 중간 가격으로 '분리'된 후 할당됩니다. 예를 들어, 필수 항목에는 수익으로 인정해야 하는 고정 가격이 있습니다. 할인이 있는 경우, 필수 항목 수익에서 할인이 분리될 수 있으며 다만 고정 가격의 금액 한도 **내에서만** 분리됩니다. 나머지 할인 부분은 비필수 항목에 대한 수익에서 제외됩니다. 또는 필수 항목 수익에서 할인을 분리하지 못할 수도 있습니다.
    - **계약 후 지원** – 해당 항목은 고객에 대한 판매에 포함된 그 밖의 요소들을 지원합니다. 수익 가격은 판매에 포함된 필수 제품과 비필수 제품에 걸쳐 배분됩니다. 설정에 따라 PCS 항목은 판매 주문 라인에서 계약 시작 및 종료 날짜를 정의할 필요가 없습니다.

- **분리에서 제외** – 해당 항목의 중간 가격이 정의된 최소 백분율보다 낮거나 최대 백분율보다 높게 조정할 수 없음을 나타내려면 이 옵션을 **예** 로 설정하십시오. 모든 수익 가격은 판매 주문 건에 포함된 다른 출시 제품의 수익 가격에서 파생됩니다. 이 옵션이 **아니요** 로 설정된 경우, 해당 항목의 중간 가격은 조정되거나 분리될 수 있습니다. 중간 가격으로 설정된 항목을 두 개 이상 판매하는 경우, **분리에서 제외** 옵션이 **아니요** 로 설정되어 있는 조건 하에서 출시된 제품을 적어도 한 개 이상 설정해야 합니다. 이렇게 하면 수익 가격의 차이를 할당할 수 있는 항목이 적어도 한 개 이상 존재합니다.
- **중간 가격** – 이 옵션을 **예** 로 설정하면 해당 항목의 수익 가격이 지정된 최소 허용 범위보다 낮거나 최대 허용 범위보다 높은 경우 중간 가격과 일치하도록 수익 가격을 조정해야 하며, **분리에서 제외** 옵션이 **아니요** 로 설정된 조건 하에서 여러 제품이 있는 라인에 분리 금액을 할당해야 한다고 알릴 수 있습니다.

    - **최대 허용 범위** – 허용되는 중간 가격을 상회하는 백분율을 입력합니다.
    - **최소 허용 범위** – 허용되는 중간 가격을 하회하는 백분율을 입력합니다.

출시된 제품에 대한 설정 구성을 완료한 후 **수익 가격** 페이지에서 적정 가격 또는 중간 가격을 입력(중간 가격 방식을 사용하는 경우)하여 수익 가격을 수동으로 정의해야 합니다(**수익 인정 \> 설정 \> 재고 설정 \> 출시된 제품** 으로 이동한 다음, 작업 창의 **판매** 탭에 있는 **수익 인정** 그룹 내에서 **수익 가격** 을 선택할 것).

[![수익 가격.](./media/revenue-recognition-revenue-prices.png)](./media/revenue-recognition-revenue-prices.png)

이 페이지에서 수동으로 정의된 수익 가격은 정의된 제반 기준에 따라 각 판매 주문 건에 대한 수익 가격 할당을 결정하는 데 사용됩니다. 각 기준은 판매 주문 라인과 매칭되어 할당 프로세스에서 사용할 수익 가격을 결정합니다.

- **항목 코드** 와 **항목 관계** – 개별 제품 또는 제품 그룹에 대해 수익 가격을 정의할 수 있습니다. **항목 코드** 필드에서 **테이블** 을 선택하는 경우, **항목 관계** 필드에서 출시된 제품을 선택합니다. **항목 코드** 필드에서 **그룹** 을 선택하는 경우, **항목 관계** 필드에서 해당 항목 그룹을 선택합니다.
- **계정 코드** 와 **계정/그룹 번호** – 수익 가격은 모든 고객, 개별 고객 또는 고객 그룹에 대해 정의할 수 있습니다. **계정 코드** 필드에서 **모두** 를 선택하면 가격은 모든 고객을 대상으로 적용됩니다. **계정 코드** 필드에서 **테이블** 을 선택하는 경우, **계정/그룹 번호** 필드에서 고객을 선택합니다. **계정 코드** 필드에서 **그룹** 을 선택하는 경우, **계정/그룹 번호** 필드에서 고객 그룹을 선택합니다.
- **통화** – 판매 주문 건을 기입 시 적용되는 각 통화에 대해 별도의 수익 가격을 입력해야 합니다. 예를 들어 현재 미국 달러, 캐나다 달러 및 유로로 판매하는 경우 이 세 가지 통화를 모두 사용하여 수익 가격을 정의해야 합니다. 수익 가격은 하나의 통화(예: 회계 통화)에서 현재 사용 중인 다른 거래 통화로 환산되지 않습니다.
- **금액 또는 정가 비율** – 수익 가격을 금액으로 설정할지 아니면 정가 비율로 설정할지 여부를 지정합니다. **정가의 비율** 을 선택하면 사용자는 금액 대신 정가 비율로 중간 가격을 기입할 수 있습니다. **정가 비율** 값은 PCS 항목으로 설정된 출시 제품에만 적용됩니다.
- **수익 할당 가격** – **금액 또는 정가 비율** 필드에서 선택한 값에 따라 해당 판매 주문 건의 제반 요소에 걸쳐 수익을 할당하는 데 사용되는 수익 가격을 나타내도록 금액 또는 백분율을 입력합니다.
- **시작 날짜** 와 **종료 날짜** – 수익 가격이 활성화된 날짜 범위를 입력합니다. 이들 필드는 선택 사항입니다.

**총계정원장 매개 변수** 페이지의 **할인 할당 방법 사용** 옵션이 **예** 로 설정되어 있고 출시된 제품에 대한 **수익 유형** 필드가 **계약 후 지원** 으로 설정된 경우, 출시된 제품에서 지원 중인 항목들도 기입해야 합니다. 이 설정은 **설정 기준** 페이지에서 수행됩니다(**수익 인정 \> 설정 \> 재고 설정 \> 출시된 제품** 으로 이동한 다음, 작업 창의 **판매** 탭에 있는 **수익 인정** 그룹에서 **설정 기준** 을 선택할 것).

**설정 기준** 페이지에서 해당 항목이 지원하는 각 항목 그룹에 대한 레코드를 추가합니다. 수익 할당이 발생하면 수익 가격은 PCS 항목의 필수 부분과 비필수 부분에 걸쳐 배분됩니다.

### <a name="posting-profiles"></a>기장 프로필

수익 이연 기능을 지원하는 추가 기장 유형으로는 세 가지가 있습니다. 이러한 기장 유형들은 **기장** 페이지의 **판매 주문** 탭에서 설정됩니다(**수익 인정 \> 설정 \> 재고 및 제품 설정 \> 기장**).

- **이연 수익** – 수익 대신 이연 수익에 기장되는 수익 가격의 주 계정을 입력합니다. 판매 주문 라인에 수익 일정이 있는 경우, 수익 가격은 이연됩니다.
- **이연된 판매 제품 원가** – 수익도 이연된 경우, 이연된 판매 제품 원가에 기장되는 판매 제품 원가의 주 계정을 입력합니다.
- **부분 송장 수익 정산** – 판매 주문이 일부 청구되거나 수익 재할당이 발생할 때 사용되는 정산 계정의 주 계정을 입력합니다. 판매 주문 건이 전액 청구되면 이 계정의 잔액은 다시 0(영)이 됩니다.

### <a name="bundles"></a>번들

번들 항목은 출시된 고유 제품으로서 구성 요소를 포함하도록 설정되어 있습니다. 이 설정은 자재 명세서(BOM) 기능을 사용하여 수행됩니다. 번들 항목이 판매 주문 건에 입력되면 개별 구성 요소를 사용하여 수익 가격과 수익 일정을 결정합니다. 그러나 판매 주문 및 송장과 같은 고객용 인쇄 문서에는 번들 항목이 반영됩니다.

#### <a name="bundle-components"></a>번들 구성 요소

번들에 포함된 구성 요소들은 **출시된 제품** 페이지에서 설정해야 합니다(**수익 인정 \> 설정 \> 재고 및 제품 설정 \> 출시된 제품**). 이러한 구성 요소들은 출시된 제품에 속하며 BOM에 포함된 제품과 동일한 방식으로 설정해야 합니다. 예를 들어 출시된 제품은 **항목** 유형 또는 **서비스** 유형 중 하나에 속한 항목일 수 있으며 다만 **재고 제품** 옵션이 **예** 로 설정된 경우에는 하나의 항목 모델 그룹에 할당되어야 합니다. 자세한 내용은 BOM 항목에 대한 설정 설명서를 참조하십시오.

구성 요소는 판매 주문에서 개별적으로 판매할 수 있는 제품과 마찬가지로 수익 인정에 대해서도 설정해야 합니다. 예를 들어, 각 구성 요소에 대해 정확한 수익 가격이 정의되어 있고 PCS 항목에 대해 가격 기준이 설정되어 있는지 확인하십시오.

#### <a name="bundle-items"></a>번들 항목

하나의 번들 항목을 설정할 때에는 **출시된 제품** 페이지에서 다음과 같이 두 개의 필드를 설정해야 합니다(**수익 인정 \> 설정 \> 재고 및 제품 설정 \> 출시된 제품**).

- **엔지니어** 빠른 탭의 **생산 유형** 필드에서 해당 항목은 BOM 항목으로 설정되어야 합니다.
- **일반** 빠른 탭의 **번들** 필드에서 해당 항목은 번들 항목으로 표시되어야 합니다.

그런 다음, 구성 요소를 **BOM 버전** 페이지의 번들/BOM 부모 항목에 할당해야 합니다(**수익 인정 \> 설정 \> 재고 및 제품 설정 \> 출시된 제품** 으로 이동한 다음, 작업 창의 **엔지니어** 탭에 있는 **BOM** 그룹에서 **BOM 버전** 을 선택할 것). 자세한 내용은 BOM에 대한 설정 설명서를 참조하십시오.

[![출시된 제품, BOM 일정.](./media/revenue-recognition-bom-scheduleds.jpg)](./media/revenue-recognition-bom-scheduleds.jpg)

번들 부모 항목 및 번들 구성 요소를 할당하도록 설정한 경우, 번들 수익 가격은 수익 기여율(%)에 따라 해당 구성 요소에 배분됩니다.

## <a name="project-setup"></a>프로젝트 설정

수익 인정은 시간 및 자재 프로젝트를 통해 생성된 판매 주문 건에도 사용할 수 있습니다. 프로젝트에서 시작된 판매 주문 건의 경우, 프로젝트 송장을 기장하는 데 사용되는 프로젝트 기장 프로필에서 주 계정을 정의하기만 하면 됩니다. 주 계정은 **원장 기장 설정** 페이지에서 정의됩니다(**수익 인정 \> 설정 \> 프로젝트 설정 \> 원장 기장 설정**).

- **이연 송장 수익**(**수익 계정** 아래의) – 수익 대신 이연 수익에 기장되는 수익 가격의 주 계정을 입력합니다. 판매 주문 라인에 수익 일정이 있는 경우, 수익 가격은 이연됩니다.
- **이연된 원가**(**원가 계정** 아래의) – 수익도 이연된 경우, 이연된 판매 제품 원가에 기장되는 판매 제품 원가의 주 계정을 입력합니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
