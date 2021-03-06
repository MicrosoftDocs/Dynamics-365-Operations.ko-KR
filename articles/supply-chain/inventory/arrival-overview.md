---
title: 도착 개요
description: 이 항목에서는 도착 개요 기능에 대한 정보를 제공합니다. 도착 개요 페이지는 이 기능의 일부이며 들어오는 항목으로 도착할 것으로 예상되는 모든 항목에 대한 개요를 제공합니다.
author: yufeihuang
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview, WMSArrivalOverviewProfile, WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "274363"
- intro-internal
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 1248156ba9081fe4afbffd480b45cf9326d14a6c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448012"
---
# <a name="arrival-overview"></a>도착 개요

[!include [banner](../includes/banner.md)]

이 항목에서는 도착 개요 기능에 대한 정보를 제공합니다. 도착 개요 페이지는 이 기능의 일부이며 들어오는 항목으로 도착할 것으로 예상되는 모든 항목에 대한 개요를 제공합니다.

**도착 개요** 페이지는 예상되는 모든 들어오는 항목의 개요를 제공합니다. 또한 개요를 기반으로 초기화할 수 있는 도착도 표시합니다. 이 항목은 수신 프로세스에 중점을 둡니다.

## <a name="business-scenario"></a>비즈니스 시나리오
인바운드 프로세스에서 다음 시나리오를 고려하세요.

[![비즈니스 시나리오.](./media/arrival-overview-scenario.png)](./media/arrival-overview-scenario.png)

접수 사무원인 Sammy는 당일 수령할 것으로 예상되는 항목을 알고 싶어합니다. **도착 개요** 페이지에서 Sammy는 현재 작업에 대한 개요와 수량, 부피, 무게, 다양한 주문 유형 등에 대한 대략적인 추정치를 얻을 수 있습니다. 나중에 배송이 인바운드 부두 중 하나에 도착하고 Sammy는 배송 목록을 받습니다. **도착 개요** 페이지에서 Sammy는 다음 작업을 수행할 수 있습니다.

-   일치하는 영수증 주문을 식별하고 영수증을 **진행 중** 으로 등록합니다. 등록에 필요한 라인은 자동으로 생성되며, 아직 거래가 **등록됨** 으로 전기되지 않은 경우에도 입고를 모니터링할 수 있습니다.
-   적절한 도착 저널 참조(즉, **상품 도착** 일지 또는 **생산 투입** 저널)에 액세스하고 제품 영수증 업데이트 준비가 된 저널을 식별합니다.

## <a name="arrival-overview-page"></a>도착 개요 페이지
**도착 개요** 페이지를 열려면 **재고 관리** &gt; **인바운드 주문** &gt; **도착 개요** 를 클릭합니다. 예상되는 주문 목록을 볼 수 있습니다. 개요는 헤더와 라인으로 구분됩니다. 헤더 정보는 주문 유형, 예상 입고 날짜 및 배송 목적지별로 그룹화됩니다. 도착을 위해 헤더 라인이 선택되면 페이지의 라인 세부사항 부분에서 영수증 참조와 관련된 모든 세부사항 라인이 도착을 위해 선택됩니다. 모든 관련 분개 라인이 전기되면 이 정보는 표시되지 않습니다.

### <a name="arrival-overview-profiles"></a>도착 개요 프로필

**도착 개요** 페이지는 도착할 것으로 예상되는 항목과 도착할 것으로 예상되는 날짜에 대한 개요를 제공합니다. 도착 프로세스의 일부로 여러 개인 설정 세트를 사용할 수 있습니다. 개별 사용자는 **도착 개요 프로필** 페이지에서 개인 설정을 정의할 수 있습니다.

### <a name="set-up-item-arrival"></a>항목 도착 설정

이 예에서 Sammy는 사이트 1에서 생산된 완제품을 받는 데 사용할 위치에 새 컴퓨터를 설치하려고 합니다. **도착 개요 프로필** 페이지에서 Sammy는 이름이 **사이트 1 생산** 으로 지정된 새 설정을 만들고 다음 설정을 지정합니다.

1.  **도착 옵션** 빠른 탭의 **범위** 필드 그룹에서 개요에 포함할 일 간격 및 창고에 대한 정보를 입력합니다.
2.  **도착 옵션** 빠른 탭의 **저널** 필드 그룹에 입고 창고, 위치 및 분개 이름(품목 도착/생산 입력)을 입력합니다.
3.  **도착 쿼리 세부 정보** 빠른 탭의 **사이트** 필드 그룹에서 **사이트로 제한** 필드에 개요 영역에서 보기를 제한할 사이트를 입력합니다.
4.  **도착 쿼리 세부 정보** 빠른 탭의 **표시된 트랜잭션 유형** 필드 그룹에서 **생산 주문** 옵션을 **예** 로 설정합니다.
5.  보기가 시작 시 자동으로 업데이트되어야 한다면 **도착 쿼리 세부 정보** 빠른 탭의 **기타** 그룹에서 **시작 시 업데이트** 옵션을 **예** 로 설정합니다. 범위 값이 변경될 때 보기가 자동으로 업데이트되어야 한다면 **범위 변경에 대한 업데이트** 옵션을 **예** 로 설정합니다.

이 예의 경우 **도착 개요** 페이지의 **도착 옵션** 빠른 탭에 있는 **도착 개요 프로필 이름** 필드가 **사이트 1 생산** 으로 설정되어 있습니다.

### <a name="prerequisites-for-arrival-journals"></a>도착 저널의 전제 조건

**도착 개요** 페이지에서 자동으로 도착 분개장을 생성하려면 **도착 옵션** 빠른 탭의 **분개장** 필드 그룹에서 적절한 정보를 정의해야 합니다.

-   저널을 생성하려면 저널 이름을 지정해야 합니다.

[![저널 이름 지정.](./media/arrival-overview-journal.png)](./media/arrival-overview-journal.png)

-   **창고** 및 **위치** 필드에 값을 지정하는 경우 해당 값은 분개 라인에 적용됩니다. 값을 지정하지 않으면 시스템은 재고 트랜잭션에 지정된 차원의 값을 사용합니다.

#### <a name="items-that-are-received-from-one-expected-receipt-order"></a>하나의 예상 입고 주문에서 받은 항목

**영수증** 빠른 탭에서 Sammy는 라인을 선택한 다음 **도착 시작** 을 클릭합니다. 지정된 범위에 있고 등록할 수량이 있는 모든 관련 라인이 자동으로 선택됩니다. 예상 입고 주문과 저널이 일치하는 품목 도착 저널이 생성됩니다. 수량은 생성된 모든 라인에서 자동으로 초기화됩니다.

#### <a name="items-that-are-received-from-more-than-one-expected-receipt-order"></a>하나 이상의 예상 입고 주문에서 받은 항목

**영수증** 빠른 탭에서 Sammy는 여러 개의 라인을 선택한 다음 **도착 시작** 을 클릭합니다. 모든 예상 입고 주문과 저널이 일치하는 품목 도착 저널이 생성됩니다. 모든 라인은 하나의 품목 도착 분개 헤더에 생성되며 수량은 자동으로 초기화됩니다.

### <a name="receive-items-from-one-or-more-expected-receipt-orders"></a>하나 이상의 예상 입고 주문에서 항목 받기

#### <a name="view-information"></a>정보 보기

날짜 간격으로 예상되는 영수증의 개요를 보기 위해 Sammy는 **도착 개요** 페이지의 **도착 옵션** 빠른 탭에서 필드에 다음 정보를 입력한 다음 **업데이트** 를 클릭하여 보기를 업데이트합니다.

-   도착 개요 프로필 이름: **문의**
-   라인 표시: **모두**
-   이전 일: (공백)
-   앞으로 일: **0**
-   창고: **GW, MW**

Sammy는 다음 정보를 볼 수 있습니다.

-   시스템 날짜에 대한 모든 관련 입고 주문과 그로부터 무한한 일수(**InventTrans.StatusDate** 간격) 및 상태에 관계없이 창고 GW 및 MW에 대한 영수증.
-   하나 이상의 주문에 대한 자세한 라인 정보. Sammy는 개요에서 여러 헤더 행을 선택한 다음 **선택한 모든 항목 표시** 를 클릭하여 선택한 모든 주문에 대한 모든 해당 라인 세부 정보를 볼 수 있습니다.
-   특정 구매 주문에 대한 정보입니다. 개요에서 특정 참조 번호와 관련된 정보만 표시하기 위해 Sammy는 **계정 번호** 필드에 계정 번호를 입력하고 **참조 번호** 필드에 주문 번호를 입력할 수 있습니다.
-   품목 도착 분개가 생성되었지만 아직 전기되지 않은 모든 주문 라인에 대한 등록 태스크의 개요입니다. 이 정보를 보기 위해 Sammy는 **라인 표시** 필드에서 **진행 중** 을 선택할 수 있습니다.

### <a name="update-journals"></a>분개장 업데이트

처리될 하나 이상의 주문 라인을 등록하기 위해 Sammy는 개요 그리드 또는 라인 그리드에서 라인을 선택한 다음 **분개장** &gt; **영수증에서 도착 표시** 를 클릭할 수 있습니다. 라인과 일치하는 품목 도착 헤더가 표시됩니다. 등록된 품목에 대한 구매 주문 제품 영수증을 업데이트하기 위해 Sammy는 업데이트할 준비가 된 품목 도착 저널 헤더에 액세스할 수 있습니다. 이러한 품목 도착 분개 헤더에 액세스하기 위해 **저널** &gt; **제품 수령 준비 일지** 를 클릭합니다. 지정된 창고 범위에서 제품 입고 업데이트가 준비된 모든 헤더 라인이 표시됩니다. (표시되는 헤더 행은 일 간격과 관련이 없습니다).

### <a name="start-an-arrival-registration"></a>도착 등록 시작

**도착 개요** 페이지에서 여러 라인을 선택하여 Sammy는 하나 이상의 영수증 참조 도착을 시작할 수 있습니다. 입고 개요에서 라인을 선택하면 해당 라인 상세내역이 선택됩니다. 등록할 수 있는 수량이 있는 경우 **도착 시작** 버튼을 사용할 수 있습니다. Sammy는 두 가지 방법을 사용하여 도착 등록을 시작할 수 있습니다.

-   특정 기준을 충족하는 레코드만 표시하도록 페이지를 필터링하려면 **공급업체 참조** 필드에서 배달 메모의 바코드와 같은 공급업체의 참조 번호를 스캔합니다.
-   **도착 개요** 페이지의 개요 부분 또는 세부 사항 부분에서 도착 등록을 위한 기록 선택을 수동으로 선택하거나 취소합니다. 그런 다음 Sammy가 **도착 시작** 을 클릭하면 선택한 레코드는 항목 도착 일지에 자동으로 생성됩니다. 레코드에는 라인 정보가 포함되며 모든 고유한 필드 정보가 할당됩니다.

## <a name="update-arrival-information-and-process-a-product-receipt"></a>도착 정보 업데이트 및 제품 영수증 처리
모든 상품이 등록되면 창고 관리자 또는 구매 관리자는 입고된 항목을 제품 영수증으로 업데이트하여 실제 비용을 추가할 수 있습니다. 도착 정보를 업데이트하고 제품 영수증을 게시하려면 다음 단계를 따르세요.

1.  **재고 관리** &gt; **인바운드 주문** &gt; **도착 개요** 를 클릭합니다.
2.  **도착 개요** 페이지에서 **저널** &gt; **제품 수령 준비 일지** 를 클릭하여 제품 수령 업데이트를 위해 준비된 저널 목록을 표시합니다.
3.  업데이트해야 하는 저널을 선택한 다음 **기능** &gt; **제품 영수증** 을 클릭합니다.
4.  **전기** 페이지에서 제품 영수증 번호를 입력하고 저널에 아직 없는 경우 제품 영수증 번호를 입력한 다음 **확인** 을 클릭하여 제품 영수증을 처리합니다.

## <a name="summary"></a>요약
**도착 개요** 페이지는 창고 관리자와 창고 작업자가 인바운드 프로세스의 일부로 수행해야 하는 예상 작업의 개요를 얻는 데 도움이 될 수 있습니다. 이 페이지는 또한 상품 도착 프로세스를 시작하는 데 사용할 수 있으며, 이는 창고에 처음 들어갈 때 상품이 추적되도록 보장하는 데 도움이 됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]