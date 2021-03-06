---
title: 공급업체 리베이트
description: 이 토픽에서는 공급업체 리베이트를 사용할 때 수행할 수 있는 가장 일반적인 작업에 대한 개요를 제공합니다. 공급업체 리베이트는 획득한 리베이트를 관리, 추적 및 청구하는 데 필요한 작업을 자동화하여 회사가 공급업체 리베이트 프로그램을 더 잘 관리할 수 있도록 도와줍니다.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMVendRebateAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 2012
ms.openlocfilehash: ec8d054d023b7e3f6611199e60f661c480d44d57
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447958"
---
# <a name="vendor-rebates"></a>공급업체 리베이트

[!include [banner](../includes/banner.md)]

공급업체 리베이트는 획득한 리베이트를 관리, 추적 및 청구하는 데 필요한 작업을 자동화하여 회사가 공급업체 리베이트 프로그램을 더 잘 관리할 수 있도록 도와줍니다.

이 토픽에서는 공급업체 리베이트를 사용할 때 수행할 수 있는 가장 일반적인 작업에 대한 개요를 제공합니다. 개요에서는 다음 작업을 다룹니다.

- 리베이트 계약의 세부사항을 검토합니다.
- 리베이트 자격이 있는 주문을 식별하고 리베이트 청구를 생성합니다.
- 청구를 검토하고 승인합니다.

## <a name="audience-and-purpose"></a>대상 그룹 및 목적

이 토픽의 정보는 구매 관리자, CFO(최고 재무 책임자) 및 회계 관리자와 같은 직책에 있는 기업 회사의 비즈니스 의사 결정권자를 위해 작성되었으며 이들은 다음과 같은 책임을 집니다.

- 공급업체 가격, 할인 및 리베이트 계약을 협상합니다.
- 리베이트 청구를 처리하고 지불금을 징수하는 직원을 관리합니다.
- 최상의 가격으로 재고를 주문하세요.

이러한 직책을 맡은 사람들은 다양한 목표를 달성하기 위한 방법을 찾고 있습니다. 여기 예시들이 있습니다 :

- 다양한 유형의 공급업체 판촉 프로그램 및 리베이트 조건을 유연하게 수용합니다.
- 프로모션 성과 모니터링 및 클레임 처리와 관련된 관리 부담과 오류를 줄이기.
- 미래 미수금을 발생시켜 현금 흐름 예측 개선하기.
- 리베이트에 대한 공급업체와의 진행 중 및 향후 협상을 위한 정량화된 기반 확보.

## <a name="review-details-of-a-vendor-rebate-agreement"></a>공급업체 리베이트 계약의 세부사항을 검토합니다.

공급업체 리베이트 계약은 회사가 사전 설정된 구매 목표를 달성하는 대가로 금전적 보상을 받을 자격이 있는 협상된 조건을 지정하는 공급업체와의 계약 기록입니다. 공급업체 리베이트 계약은 **리베이트 계약** 페이지에 기록됩니다.

**공급업체 리베이트 계약** 페이지를 열려면 **조달 및 소싱** &gt; **공급업체 리베이트** &gt; **리베이트 계약** 을 선택합니다.

![구매 계약](media/purchase-agreement.PNG)

**공급업체 리베이트 계약** 페이지에서 공급업체 계약의 협상된 조건에 대한 세부 정보를 볼 수 있습니다.

계약의 헤더는 회사가 리베이트를 받을 수 있는 일반 조건을 지정합니다. 실제로 헤더 정보는 특정 제품이 특정 수량으로 구매될 때 공급업체가 리베이트를 부여하도록 지정합니다. 헤더에서 측정 단위 리베이트 옵션과 계산 날짜 유형도 지정합니다.

- **개요** 탭에서 품목을 지정하기 위해 **품목 코드** 가 *테이블* 로 설정된 라인이 있는 경우 해당 특정 품목에 대한 계약입니다. 품목을 지정하기 위해 **품목 코드** 가 *그룹* 또는 *모두* 로 설정된 라인이 있는 경우 품목 코드에 적합한 모든 품목이 아니라 품목 코드에 적합한 품목별로 공급업체 리베이트 계약이 개별적으로 처리됩니다.

- **일반** 탭의 **측정 단위 리베이트 옵션** 필드에서 측정 단위가 구매 주문 라인의 조건이 되어야 리베이트 청구 자격을 얻을 수 있는지 여부를 정의할 수 있습니다.

    - **전환** – 구매 주문 라인은 리베이트 계약에 따라 벤더 리베이트 자격이 있습니다. 라인에 적용된 측정 단위와 상관없이 리베이트를 받게 됩니다.
    - **정확히 일치** – 리베이트를 받으려면 구매 라인에 계약서에 명시된 것과 동일한 측정 단위가 있어야 합니다.

- **일반** 탭의 **계산 날짜 유형** 필드에서 구매가 리베이트 계약의 유효 기간에 발생하는지 여부를 결정하는 데 사용되는 날짜를 선택합니다.

    - **생성됨** – 구매 주문의 생성 날짜를 사용합니다.
    - **요청된 배송** - 요청한 배송 날짜를 사용합니다.

계약 라인에서 공급업체 리베이트 계약을 더 자세히 지정할 수 있습니다.

- **누적 구매 기준** 필드에서 리베이트 청구 계산을 설정할 수 있습니다. 기간(주, 월, 년, 평생 또는 사용자 지정 기간)에 따라 금액을 설정할 수 있습니다. **송장** 값은 구매 주문 라인에 송장이 발행될 때마다 리베이트 청구가 결정됨을 나타냅니다.
- **출처** 필드에서 리베이트 계산의 기준을 지정할 수 있습니다.

    - **총합** - 리베이트는 품목의 총 가격을 기준으로 계산됩니다.
    - **순** – 리베이트는 상품의 순가(기타 할인 적용 후 가격)를 기준으로 산정됩니다.

- **리베이트 프로그램 미지급 계정** 및 **리베이트 프로그램 비용 계정** 필드는 승인과 처리 사이의 중간 단계에서 미지급 리베이트 금액을 받을 계정 번호를 지정합니다.
- **승인 필수** 옵션이 **예** 로 설정된 경우 리베이트 청구가 승인되어야 적립 또는 지급될 수 있습니다.
- **리베이트 줄 바꿈 유형** 필드는 리베이트의 기준을 지정합니다.

    - **수량** – 리베이트는 볼륨 기반입니다.
    - **금액** – 리베이트는 금액 기준입니다.

- **라인** 빠른 탭에서 다양한 리베이트를 부여하기 위해 다양한 수량 계층을 설정하는 방법을 볼 수 있습니다. 예를 들어, 이전 그림에서 **시작 값** 및 **종료 값** 필드는 10개에서 19개 단위 사이의 제품 수량이 단위당 USD 15의 리베이트 대상임을 나타냅니다.

    > [!NOTE]
    > **시작 값** 값은 포함되는 반면 **종료 값** 값은 제외됩니다. 예를 들어, **리베이트 줄 바꿈 유형** 필드가 **수량** 으로 설정되고 **시작 값** 필드에 **1** 을 입력하고 **종료 값** 필드에 **3** 을 입력합니다. 이 경우 리베이트 금액은 1~2개 구매 시 적용되며, 3개 구매 시에는 적용되지 않습니다.

- **워크플로 승인 상태** 필드에서 **승인됨** 값은 계약 조건을 충족하는 구매 주문에 계약을 적용할 수 있음을 나타냅니다.

## <a name="identify-orders-that-qualify-for-rebates-and-generate-rebate-claims"></a>리베이트 자격이 있는 주문을 식별하고 리베이트 청구를 생성합니다.

회사가 리베이트 계약을 체결한 공급업체와 구매 주문을 하면 프로그램은 향후 공급업체 신용 지불을 식별합니다. 구매 주문이 리베이트에 해당하는 경우 구매 송장이 전기되는 즉시 모든 주문 라인에 대해 리베이트 청구가 생성됩니다. 이 프로세스는 자동입니다. 나중에 예상 리베이트를 검토하고 해당 리베이트가 제품의 비용 및 이익률에 미치는 영향을 확인할 수 있습니다.

### <a name="view-details-of-rebates-that-are-applied-to-a-purchase-order-line-per-the-vendor-rebate-agreement"></a>공급업체 리베이트 계약에 따라 구매 발주 라인에 적용된 리베이트 상세내역 조회

1. **구매 주문** 페이지에서 주문 라인을 선택한 다음 **구매 주문 라인** &gt; **보기** &gt; **가격 세부 정보** 를 선택합니다.
2. **가격 세부 정보** 페이지에서 **리베이트** 빠른 탭을 선택합니다.

리베이트 정보는 **가격 세부 정보** 페이지의 **마진 추정** 섹션에 있는 **공급업체 리베이트** 필드에도 표시됩니다.

> [!NOTE]
> **조달 및 소싱 매개 변수** 페이지의 **가격** 탭에서 **가격 세부 정보 사용** 옵션이 **예** 로 설정되어 있는지 확인합니다. 옵션이 **아니요** 로 설정되어 있으면 리베이트를 볼 수 없습니다.

## <a name="review-and-approve-claims"></a>청구 검토 및 승인

생성된 리베이트 청구는 공급업체로부터 기대할 수 있는 미래의 지불을 나타냅니다. 신용 메모가 공급업체에 발행되기 전에 계약 담당자는 일반적으로 청구를 검토하고 승인하기를 원합니다. 그러나 클레임의 상태에 따라 클레임이 승인 프로세스를 거칠 준비가 되었는지 여부가 결정됩니다.

### <a name="the-status-of-claims-and-the-effect-on-the-approval-process"></a>클레임 현황 및 승인 절차에 미치는 영향

청구가 생성되면 리베이트가 누적 기준으로 부여된 경우 해당 상태가 **계산 예정** 으로 설정되고 리베이트가 송장별로 부여된 경우 **계산됨** 으로 설정됩니다. 청구 상태가 **계산 예정** 인 경우 청구는 누적 기능에서 처리하는 계산 프로세스를 거쳐야 합니다. 상태가 **계산됨** 인 클레임만 승인 프로세스에 포함될 수 있습니다.

> [!NOTE]
> 공급업체 리베이트 계약의 **승인 필수** 옵션이 **아니요** 로 설정된 경우 생성된 모든 청구는 **승인됨** 상태가 됩니다. 승인은 누적 기준으로 부여된 클레임에 대해 필수입니다.

### <a name="approve-claims-and-view-postings-and-invoice-details"></a>청구 승인, 전기 및 송장 세부 정보 보기

청구가 승인되면 지급 계정(A/P)에서 처리할 수 있습니다. 리베이트 청구 금액에 대한 대변 메모(공급업체 송장)가 자동으로 생성됩니다. 그런 다음 크레딧을 공급업체 잔액에 추가할 수 있으며 A/P 팀은 이를 일반 결제 프로세스에 포함할 수 있습니다.

1. **조달 및 소싱** &gt; **공급업체 리베이트** &gt; **리베이트 청구** 를 선택하여 리베이트 청구를 엽니다.
2. 리베이트 청구를 종료합니다.
3. 클레임을 표시한 다음 작업 창에서 **승인** 을 선택합니다.
4. 요청 페이지의 **공급업체** 필드에서 리베이트를 받을 권한이 있는 공급업체를 선택한 다음 **확인** 을 선택합니다.

    청구 금액에 대해 환불 발생 분개장이 전기됩니다. 이 전기는 예상 공급업체 대변에 대한 미지급 공급업체 리베이트 미지급 계정에서 차변에 기입하고 예상 이익에 대해 중간 미지급 공급업체 리베이트 수령 계정을 대변에 기입합니다.

    ![메시지.](media/message.png)

5. 리베이트 목록에서 라인을 선택한 다음 작업 창에서 **트랜잭션 리베이트** 를 선택하여 이 리베이트 발생 전기에 대한 분개장 배치 번호를 보고 탐색합니다.

    클레임을 일반 A/P 프로세스로 이동하려면 이제 A/P 서기가 프로세스 기능을 실행하여 리베이트 클레임 처리를 완료해야 합니다.

6. 작업 창에서 **프로세스** 를 선택한 다음 **필터** 를 선택합니다. **공급업체 계정** 필드의 **기준** 필드에서 리베이트 청구를 처리할 공급업체를 선택하고 다른 관련 필터를 선택한 다음 **확인** 을 선택합니다.

    메시지 표시줄과 상태가 **완료됨** 으로 변경되었다는 사실은 다음 이벤트가 발생했음을 나타냅니다.

    - 리베이트 발생 분개장 전기가 미지급 채권 및 비용 계정의 이전 중간 금액을 취소했습니다.
    - 리베이트 금액에 대한 공급업체 송장(대변 메모)이 생성되었습니다.

        > [!NOTE]
        > **조달 및 소싱 매개 변수** 페이지의 **리베이트 프로그램** 탭에 있는 **수동 송장 전기** 옵션 설정에 따라 공급업체 송장이 청구 처리의 일부로 수동으로 전기될지 자동으로 전기될지가 결정됩니다.

    - 공급업체 송장이 자동 또는 수동으로 전기되면 공급업체의 지불 가능 계정이 차변에 기입되고 할인 및 수당 수령 계정이 대변에 기입됩니다.

        > [!NOTE] 
        > 할인 및 수당 수령 계정 번호는 리베이트에 대한 구매 송장 라인에 사용되는 조달 범주에 대해 지정됩니다. 그러면 조달 범주는 **조달 및 소싱 매개 변수** 페이지의 **리베이트 프로그램** 탭에서 설정됩니다.

7. 리베이트 목록에서 라인을 선택한 다음 작업 창에서 **리베이트 거래** 를 선택하여 이 리베이트 발생 전기에 대한 분개장 배치 번호와 공급업체 송장 번호를 확인하고 탐색합니다.
8. 공급업체 송장 거래에 대한 라인을 선택한 다음 작업 창에서 **공급업체 송장** 을 선택합니다. 공급업체 송장이 전기된 경우 송장 분개장이 표시됩니다. 그렇지 않으면 공급업체 송장이 수동 전기가 필요한 보류 중인 공급업체 송장으로 표시됩니다.

    송장 라인은 **커미션 및 리베이트** 조달 범주에 대한 공급업체 송장의 상세내역을 지정합니다.

9. **모든 공급업체** 페이지에서 리베이트를 받을 공급업체를 선택한 다음 작업 창에서 **트랜잭션** 을 선택합니다. 송장에 대한 라인을 찾습니다. 리베이트 금액이 이제 공급업체 잔액에 추가되었습니다.

## <a name="summary"></a>요약

공급업체 리베이트를 처리하는 프로세스에는 종종 지루한 여러 수동 추적 작업이 포함됩니다. 이러한 작업을 자동화함으로써 공급업체 리베이트 관리 기능을 통해 다음 프로세스를 진행할 수 있습니다.

- 정확한 리베이트 청구 생성
- 총계정원장에서 예상 채권 및 중간 이익 발생
- 공급업체 잔액 및 손익계산서를 만기 수당으로 업데이트


[!INCLUDE[footer-include](../../includes/footer-banner.md)]