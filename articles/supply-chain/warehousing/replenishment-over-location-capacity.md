---
title: 위치 용량에 대한 보충
description: 이번에는 위치 능력 이상의 보충 기능에 대한 정보를 제공합니다. 이 기능은 생성되는 날에 필요한 모든 보충 작업을 가능하게 하고 해당 보충 작업의 가용성을 관리하여 선택 위치가 재고가 부족하거나 용량을 초과하지 않도록 합니다.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 6ff9f133010ec4370a99c585259aece4e279f801
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "8449437"
---
# <a name="replenishment-over-location-capacity"></a>위치 용량에 대한 보충

[!include [banner](../includes/banner.md)]

일부 대량 또는 공간 제약이 있는 창고는 선택 위치에 맞는 것보다 더 많은 양의 품목을 하루에 배송해야 합니다. *위치 역량 이상의 보충* 기능을 사용하면 당일에 필요한 모든 보충 작업을 생성하고 해당 보충 작업의 가용성을 관리하여 선택 위치가 재고가 부족하거나 역량을 초과하지 않도록 합니다.

이 기능은 한 위치에 들어갈 수 있는 것보다 더 많은 보충 작업을 생성할 수 있게 하고, 위치가 찼을 때 완료되는 보충 작업을 차단합니다. 선택 위치의 재고가 구성 가능한 임계값 아래로 떨어지면 더 많은 보충 작업을 사용할 수 있습니다.

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a>위치 용량에 대한 보충 기능을 켜십시오.

이 기능을 사용 가능하게 하려면 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)에서 다음 기능을 순서대로 켜십시오.

1. 조직 전체 작업 차단(Supply Chain Management 버전 10.0.21부터 이 기능은 필수이므로 기본적으로 켜져 있으며 다시 끌 수 없습니다.)
1. 위치 용량에 대한 보충

## <a name="set-up-the-feature-for-the-example-scenario"></a>예시 시나리오에 대한 기능 설정

이 섹션에서는 이 기능을 설정하고 이 품목의 뒷부분에서 제공되는 예시 시나리오에 대한 샘플 데이터를 준비하는 방법을 보여주는 지침과 예시를 제공합니다.

### <a name="enable-sample-data"></a>샘플 데이터 활성화

여기에 지정된 샘플 기록 및 값을 사용하여 [예시 시나리오](#example-scenario)를 진행하려면 표준 [데모 데이터](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md)가 설치된 시스템에 있어야 합니다. 또한 시작하기 전에 **USMF** 법인을 선택해야 합니다.

### <a name="location-profile"></a>위치 프로필

위치 프로필에서 용량 초과 보충 기능을 활성화합니다.

1. **창고 관리 \> 설정 \> 창고 \> 위치 프로필** 로 이동하세요.
1. 왼쪽 창에서 **선택-06** 을 선택합니다.
1. 작업 창에서 **편집** 을 선택합니다.
1. **보충** 빠른 탭에서 다음 필드를 설정하세요.

    - **위치 용량 초과:** *예*

        활성화되면 보충 작업으로 위치의 최대 용량을 초과할 수 있습니다. 이렇게 하면 **보충** 빠른 탭의 다른 필드도 활성화됩니다.

    - **작업 가용성 임계값 유형:** *수량*

        이 필드는 더 많은 작업을 릴리스해야 하는 시기를 결정하는 데 사용되는 방법을 정의합니다. 수량 또는 백분율로 릴리스할 수 있습니다.

        - *백분율* – 재고 제한 또는 부피를 기반으로 하는 백분율 용량을 사용하려면 이 옵션을 선택합니다. 이 옵션을 선택하면 **오버플로 백분율** 필드가 활성화되고 두 개의 수량 관련 필드인 **오버플로 수량** 및 **오버플로 단위** 가 비활성화됩니다.

            선택 위치에서 체적 측정을 사용하는 경우 이 옵션을 사용할 수 있습니다.

            이 옵션을 선택하면 **오버플로 백분율** 필드를 더 많은 보충 작업을 사용할 수 있는 백분율로 설정합니다.

        - *수량* – 특정 수량 값을 사용하려면 이 옵션을 선택합니다. 이 옵션을 선택하면 **오버플로 백분율** 필드가 비활성화되고 **오버플로 수량** 및 **오버플로 단위** 필드가 활성화됩니다.

            보충되는 위치에 대해 체적 측정을 사용하지 않거나 해당 위치로 더 많은 재고를 가져오려는 일관된 수량이 있는 경우 이 옵션을 사용합니다.

           이 옵션을 선택하면 **오버플로 수량** 및 **오버플로 단위** 필드를 더 많은 보충 작업을 사용할 수 있는 수량 및 단위로 설정합니다.

    - **오버플로 수량:** *0.65*

        이 필드는 위치가 오버플로되는 수량을 정의합니다.

        해당 위치의 현 재고 수량과 작업 수량의 합계가 이 값 미만일 때마다 작업이 가능합니다. 이 값을 초과하는 보충 작업은 차단되며 수동으로 차단을 해제해야 합니다.

        작업 수량 계산 시 위치 재고 한도를 고려합니다.

    - **오버플로 단위:** *PL*

        이 필드는 오버플로 수량과 연결된 단위를 정의합니다.

        이 경우 위치가 0.65팔레트(PL) 아래로 내려가면 추가 보충 작업이 가능해집니다.

    - **오버플로 백분율**

        이 필드는 위치가 오버플로되는 백분율을 정의합니다.

        작업은 해당 위치의 현 재고 수량과 작업 수량의 합계가 이 퍼센트 미만일 때 사용할 수 있습니다. 이 값을 초과하는 보충 작업 수량 백분율은 차단되며 수동으로 차단을 해제해야 합니다.

        작업량 백분율을 계산할 때 위치 재고 한도를 고려합니다. 위치 재고 제한이 정의되지 않은 경우 위치 프로파일에 대해 볼륨 제약이 정의된 경우 작업 수량 백분율은 볼륨으로 계산됩니다.

> [!IMPORTANT]
> **USMF** 엔터티에 대한 데모 데이터를 사용하고 이전에 *위치 번호판 위치 지정* 기능을 켠 경우 **대량-06** 위치 프로필에 대한 **번호판 위치 지정 활성화** 설정을 꺼야 예시 시나리오의 모바일 단계를 완료할 수 있습니다.

### <a name="wave-step-code"></a>웨이브 단계 코드

> [!NOTE]
> 여기에 설명된 대로 웨이브 단계 코드를 설정하려면 먼저 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)를 사용하여 *조직 전체 웨이브 단계 코드* 라는 기능을 켜야 할 수 있습니다.

1. **창고 관리 \> 설정 \> 웨이브 \> 단계 코드** 로 이동합니다.
1. **새로 만들기** 를 선택하고 다음 값을 설정합니다.

    - **웨이브 단계 코드:** *보충*
    - **웨이브 단계 설명:** *보충*
    - **웨이브 단계 유형:** *보충*

1. **저장** 을 선택합니다.

### <a name="replenishment-template"></a>보충 템플릿

보충 템플릿은 위치가 보충되는 시기와 방법을 제어하는 ​​일련의 규칙입니다.

1. **창고 관리 \> 설정 \> 보충 \> 보충 템플릿** 으로 이동합니다.
1. 작업 창에서 **편집** 을 선택합니다.
1. **개요** 섹션에서 **보충 템플릿** 필드가 *수요 보충* 으로 설정된 라인을 선택합니다.
1. 다음 값을 설정합니다.

    - **웨이브 단계 코드:** *보충*
    - **웨이브 수요가 예약되지 않은 수량을 사용하도록 허용:** *예*

1. **저장** 을 선택합니다.

### <a name="wave-template"></a>웨이브 템플릿

1. **창고 관리 \> 설정 \> 웨이브 \> 웨이브 템플릿** 으로 이동합니다.
1. 왼쪽 창에서 **웨이브 템플릿 유형** 필드를 *배송 중* 으로 설정합니다.
1. 목록에서 템플릿 **61 배송** 을 선택합니다.
1. 작업 창에서 **편집** 을 선택합니다.
1. **일반** 빠른 탭에서 **보충 작업 릴리스 자동화** 옵션을 *예* 로 설정합니다.

    수요 기반 보충 작업을 생성하고 자동으로 릴리스하려면 이 옵션을 *예* 로 설정합니다. 웨이브 템플릿에 보충 웨이브 방식을 추가하고 **웨이브 수요** 유형의 보충 템플릿을 생성해야 합니다. **보충 템플릿** 페이지에서 보충 템플릿을 설정합니다. 보충 템플릿을 설정하려면 웨이브 템플릿에 보충 방법을 추가해야 합니다.

1. **선택한 메서드** 열의 **메서드** 빠른 탭에서 다음 줄을 찾습니다.

    - **메서드 이름:** *보충*
    - **이름:** *보충*

1. 이 라인의 **웨이브 단계 코드** 필드를 *보충* 으로 설정합니다.
1. **저장** 을 선택합니다.

## <a name="example-scenario"></a>예시 시나리오

앞에서 설명한 모든 샘플 데이터를 사용 가능하게 만들고 설정한 후에는 이 시나리오를 통해 *위치 용량에 대한 보충* 기능을 사용해 볼 수 있습니다. 이 시나리오에 표시된 값은 표준 데모 데이터로 작업 중이고 **USMF** 엔터티를 선택했으며 이 품목의 앞부분에서 설명한 샘플 레코드를 준비했다고 가정합니다. 이 시나리오는 생산 환경에서 기능을 사용하는 방법을 보여주는 예이기도 합니다.

### <a name="create-replenishment-work"></a>보충 작업 생성

#### <a name="create-sales-order-1"></a>판매 주문 1 생성

1. **영업 및 마케팅 \> 판매 주문 \> 모든 판매 주문** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 새 판매 주문을 생성하기 위한 대화 상자를 엽니다.
1. 대화 상자에서 다음 값을 설정합니다.

    - **고객 계정** *US-007*
    - **창고:** *61*

1. **확인** 을 선택하여 판매 주문을 생성하고 대화 상자를 닫습니다.
1. 새 판매 주문이 열립니다. 여기에는 **판매 주문 라인** 빠른 탭에 비어 있는 새 라인이 포함됩니다. 이 라인에서 다음 값을 설정합니다.

    - **품목 번호:** *T0100*
    - **수량:** *40*

1. **판매 주문 라인** 빠른 탭에서 **재고 \> 예약** 을 선택합니다.
1. **예약** 페이지에서 **부지 확보** 를 선택합니다.
1. 페이지를 닫습니다.
1. 작업 창의 **창고** 탭에서 **창고로 릴리스** 를 선택합니다.

    생성된 웨이브 및 배송 ID를 보여주는 정보 메시지를 수신합니다. 보충 웨이브도 생성됩니다.

    또한 '완료되지 않은 보충 작업이 있으므로 작업 ID XXXX을(를) 차단 해제할 수 없습니다.'라는 경고 메시지가 나타납니다.

#### <a name="create-sales-order-2"></a>판매 주문 2 생성

1. **모든 판매 주문** 페이지의 작업 창에서 **새로 만들기** 를 선택하여 새 판매 주문을 만들기 위한 대화 상자를 엽니다.
1. 대화 상자에서 다음 값을 설정합니다.

    - **고객 계정** *US-001*
    - **창고:** *61*

1. **확인** 을 선택하여 판매 주문을 생성하고 대화 상자를 닫습니다.
1. 새 판매 주문이 열립니다. 여기에는 **판매 주문 라인** 빠른 탭에 비어 있는 새 라인이 포함됩니다. 이 라인에서 다음 값을 설정합니다.

    - **품목 번호:** *T0100*
    - **수량:** *60*

1. **판매 주문 라인** 빠른 탭에서 **재고 \> 예약** 을 선택합니다.
1. **예약** 페이지에서 **부지 확보** 를 선택합니다.
1. 페이지를 닫습니다.
1. 작업 창의 **창고** 탭에서 **창고로 릴리스** 를 선택합니다.

    생성된 웨이브 및 배송 ID를 보여주는 정보 메시지를 수신합니다. 보충 웨이브도 생성됩니다.

    또한 '완료되지 않은 보충 작업이 있으므로 작업 ID XXXX을(를) 차단 해제할 수 없습니다.'라는 경고 메시지가 나타납니다.

#### <a name="create-sales-order-3"></a>판매 주문 3 생성

1. **모든 판매 주문** 페이지의 작업 창에서 **새로 만들기** 를 선택하여 새 판매 주문을 만들기 위한 대화 상자를 엽니다.
1. 대화 상자에서 다음 값을 설정합니다.

    - **고객 계정** *US-004*
    - **창고:** *61*

1. **확인** 을 선택하여 판매 주문을 생성하고 대화 상자를 닫습니다.
1. 새 판매 주문이 열립니다. 여기에는 **판매 주문 라인** 빠른 탭에 비어 있는 새 라인이 포함됩니다. 이 라인에서 다음 값을 설정합니다.

    - **품목 번호:** *T0100*
    - **수량:** *30*

1. **판매 주문 라인** 빠른 탭에서 **재고 \> 예약** 을 선택합니다.
1. **예약** 페이지에서 **부지 확보** 를 선택합니다.
1. 페이지를 닫습니다.
1. 작업 창의 **창고** 탭에서 **창고로 릴리스** 를 선택합니다.

    생성된 웨이브 및 배송 ID를 보여주는 정보 메시지를 수신합니다. 보충 웨이브도 생성됩니다.

    또한 '완료되지 않은 보충 작업이 있으므로 작업 ID XXXX을(를) 차단 해제할 수 없습니다.'라는 경고 메시지가 나타납니다.

#### <a name="view-work-details"></a>작업 세부 정보 보기

1. **창고 관리 \> 작업 \> 작업 세부 정보** 로 이동합니다.
1. **개요** 섹션에서 **창고** *61* 에 대한 창고 열을 필터링하세요.
1. 3개의 수요 판매 주문에 대해 7개의 작업 ID가 생성되었음을 확인해야 합니다.

    - 7개의 작업 ID 중 3개의 **작업 주문 유형** 값은 *보충* 이고 4개의 **작업 주문 유형** 값은 *판매 주문* 입니다.
    - **작업 주문 유형** 값이 *보충* 인 세 가지 작업 ID 모두 **라인** 섹션에서 동일한 *선택* 및 *배치* 위치를 가집니다.

        - **선택:** *02A01R5S1B*
        - **배치:** *06A01R2S1B*

    - 판매 주문 1에 대해 두 개의 작업 ID가 생성되었습니다.

1. 판매 주문의 작업 ID를 기록해 둡니다.

현 재고 수량에 따라 생성되는 작업 수량은 약간 다를 수 있습니다. 그러나 전반적으로 생성되는 작업 헤더는 이 시나리오 예시와 일치해야 합니다.

#### <a name="on-hand-inventory-license-plate-id"></a>보유 재고 번호판 ID

이 시나리오의 뒷부분에서 Warehouse Management mobile app(또는 에뮬레이터)을 사용하게 되며, 여기서 픽업 및 보충 시나리오를 완료하기 위해 번호판을 식별해야 합니다.

나중에 필요한 번호판 ID를 찾으려면 다음 단계를 따르십시오.

1. **재고 관리 \> 문의 및 보고 \> 보유 목록** 으로 이동합니다.
1. **필터 표시** 버튼을 선택하여 필터 창을 엽니다.
1. 시나리오에 대한 번호판을 가져오려면 다음 필터링 기준을 입력하세요. *시작 방법* 필터를 사용합니다.

    - **품목 번호:** *T0100*
    - **창고:** *61*

1. **적용** 을 선택합니다.
1. **작업 창** 에서 차원을 선택합니다.
1. **치수 표시** 대화 상자의 **창고 치수** 섹션에서 모든 값을 선택합니다.
1. **트랜잭션** 섹션에서 **품목 번호** 와 **수량 \<\> 0** 을 선택합니다.
1. 완료되면 **확인** 을 선택하여 대화 상자를 닫습니다.
1. **재고** 그리드는 각 위치의 품목 *T0100* 에 대한 번호판 번호를 보여줍니다. 이 정보는 나중에 필요하므로 각 위치에 있는 번호판을 기록해 두십시오.
1. 페이지를 닫습니다.

### <a name="process-steps"></a>절차 단계

처음 두 작업 ID에 대해 창고 위치 보충을 수행합니다. 3차 보충 작업은 선택 위치의 재고 수준이 임계값 아래로 떨어질 때까지 차단됩니다.

#### <a name="replenishment"></a>보충

1. 창고 *61* 에서 사용자로 Warehouse Management mobile app에 로그인하세요. (사용자 ID는 *61*, 비밀번호는 *1* 을 입력하세요.)
1. **인벤토리 \> 보충** 으로 이동합니다.

    첫 번째 보충 작업을 완료하라는 메시지가 표시됩니다. 선택할 품목 번호, 수량 및 위치가 표시됩니다.

1. **LP** 필드에 표시된 위치에 있는 품목의 번호판 번호를 입력합니다.
1. **확인** 버튼(확인 표시 기호)을 선택합니다.

    시스템은 선택한 품목의 새 번호판에 대한 대상 번호판 번호를 생성합니다.

1. **확인** 을 선택하여 값을 확인합니다.

    사용자에게 대상 번호판을 보충 위치에 넣으라고 지시하는 작업 넣기가 표시됩니다. *배치* 위치는 **06A01R2S1B** 여야 합니다.

1. 입력 내용을 확인하고 **확인** 을 선택합니다.

    작업 완료 메시지가 수신되고 다음 보충 선택 태스크의 세부사항이 표시됩니다: 품목 번호, 수량 및 선택 위치 선택 위치는 첫 번째 보충 위치와 동일합니다. 따라서 번호판은 첫 번째 보충 작업에 사용된 것과 동일한 번호판 ID를 갖게 됩니다.

1. 이전 단계를 반복하여 두 번째 작업 작업에 대한 보충 작업을 완료합니다. 수량 및 대상 번호판은 첫 번째 작업 작업의 수량 및 대상 번호판과 다릅니다.

2차 보충 작업이 완료되면 '작업 완료' 메시지가 나타납니다. 모바일 디바이스는 또한 일부 보충 작업이 남아 있지만 사용 가능한 작업이 없음을 알려줍니다. 이 문제는 보충 작업의 가용성 상태가 *보류* 중이므로 **차단됨** 으로 표시되기 때문에 발생합니다.

작업이 지정되는 선택 위치에 대한 위치 프로파일의 **오버플로 수량** 값이 *0.65 PL* 이기 때문에 *보류* 상태가 트리거되었습니다. 이전의 두 가지 보충 작업 작업은 품목 *T0100* 에 대한 오버플로 한도까지 위치를 거의 채웠습니다. (품목의 단위 환산은 *1 PL = 100개* 입니다.) 따라서 나머지 보충 작업으로 인해 위치가 오버플로 제한을 초과하게 됩니다.

모바일 디바이스 메뉴 품목의 작업 릴리스 임계값 아래로 가져오기 위해 위치에서 충분한 재고가 선택될 때까지 이 보충 작업은 차단된 상태로 유지됩니다.

#### <a name="sales-order-pick"></a>판매 주문 선택

남은 보충 작업을 완료하기 전에 선택 위치의 재고가 남아 있는 보충 작업을 차단 해제할 수 있는 수준으로 고갈되어야 합니다. 즉, 해당 위치의 현 재고 수량과 보충 수량의 합이 **오버플로 수량** 값을 초과할 수 없습니다. 이 합계가 오버플로 수량보다 적으면 나머지 보충 작업이 차단 해제됩니다.

1. 창고 *61* 에서 사용자로 Warehouse Management mobile app에 로그인하세요. (사용자 ID는 *61*, 비밀번호는 *1* 을 입력하세요.)
1. **아웃바운드 \> 판매 피킹** 으로 이동합니다.
1. 판매 주문 1의 첫 번째 작업 ID를 입력합니다.

    **작업 세부 사항** 페이지에서 이전에 메모한 판매 주문에 대한 작업 ID를 참조하세요. 여기에 입력하는 작업 ID는 두 개의 개별 위치에서 10개 수량의 작업을 선택합니다.

1. **확인** 을 선택합니다.

    **판매 주문: 작업 선택** 페이지에는 첫 번째 위치에서 선택할 품목 번호, 수량 및 위치가 표시됩니다.

1. **LP** 필드에 표시된 위치에 있는 품목의 번호판 번호를 입력합니다.
1. **확인** 버튼(확인 표시 기호)을 선택합니다.

    **판매 주문: 작업 선택** 페이지에는 다음 위치에서 선택할 품목 번호, 수량 및 위치가 표시됩니다.

1. **LP** 필드에 표시된 위치에 있는 품목의 번호판 번호를 입력합니다.
1. **확인** 버튼(확인 표시 기호)을 선택합니다.

    **판매 주문: 배치** 페이지에서는 완료된 선택 작업을 모두 아웃바운드 스테이징 위치로 치워야 한다고 지시합니다.

1. **확인** 을 선택합니다.

    "작업 완료" 메시지가 표시됩니다.

1. 판매 주문 1의 두 번째 작업 ID를 입력합니다.

    이 작업 ID에는 하나의 선택 작업만 있습니다.

1. **확인** 을 선택합니다.

    **판매 주문: 작업 선택** 페이지에는 선택할 품목 번호, 수량 및 위치가 표시됩니다.

1. **LP** 필드에 표시된 위치에 있는 품목의 번호판 번호를 입력합니다.

    지정하는 번호판은 보충 작업 작업에서 시스템 생성 번호판 중 하나가 됩니다. 올바른 번호판 ID를 캡처했는지 확인하려면 **재고 목록** 페이지에서 품목, 위치 및 수량에 대한 재고를 확인하세요.

1. **확인** 버튼(확인 표시 기호)을 선택합니다.
1. 아웃바운드 스테이징 위치에 대한 넣기 작업에 대한 지침을 확인합니다.
1. **확인** 을 선택합니다.

    "작업 완료" 메시지가 표시됩니다.

판매 주문 2는 연결된 보충 작업이 완료되지 않았기 때문에 선택이 차단되었습니다. 현재 선택 위치에 30개 수량 남아 있으며 판매 주문 2에 대한 보충 수량은 60개입니다. 현 재고와 보충재고(90개)의 합계가 0.65PL(또는 65개)의 오버플로 수량을 초과합니다. 보충 작업을 완료하려면 먼저 판매 주문 3을 선택해야 합니다.

1. 판매 주문 3의 작업 ID를 입력합니다.

    이 작업 ID에는 하나의 선택 작업만 있습니다.

1. **확인** 을 선택합니다.

    **판매 주문: 작업 선택** 페이지에는 선택할 품목 번호, 수량 및 위치가 표시됩니다.

1. **LP** 필드에 표시된 위치에 있는 품목의 번호판 번호를 입력합니다.

    지정하는 번호판은 보충 작업 작업에서 시스템 생성 번호판 중 하나가 됩니다. 올바른 번호판 ID를 캡처했는지 확인하려면 **재고 목록** 페이지에서 품목, 위치 및 수량에 대한 재고를 확인하세요.

1. **확인** 버튼(확인 표시 기호)을 선택합니다.
1. 아웃바운드 스테이징 위치에 대한 넣기 작업에 대한 지침을 확인합니다.
1. **확인** 을 선택합니다.

    "작업 완료" 메시지가 표시됩니다.

선택 위치의 현 재고 수량과 보충 수량의 합계가 임계값 미만인 즉시 나머지 보충 작업을 처리할 수 있습니다.

**작업 세부 사항** 페이지로 돌아가서 최종 보충 조각(판매 주문 2의 경우)에 대한 보충 작업 가용성이 *열림* 임을 확인합니다. 이제 위치에 보충을 수락할 충분한 공간이 있기 때문입니다.

이제 모바일 디바이스를 통해 이 보충 작업을 처리할 수 있습니다.

1. **인벤토리 \> 보충** 으로 이동합니다.

    나머지 보충 작업을 완료하라는 메시지가 표시됩니다. 선택할 품목 번호, 수량 및 위치가 표시됩니다.

1. **LP** 필드에 표시된 위치에 있는 품목의 번호판 번호를 입력합니다.
1. **확인** 버튼(확인 표시 기호)을 선택합니다.

    시스템은 선택한 품목의 새 번호판에 대한 대상 번호판 번호를 생성합니다.

1. **확인** 을 선택하여 값을 확인합니다.

    사용자에게 대상 번호판을 보충 위치에 넣으라고 지시하는 작업 넣기가 표시됩니다. *배치* 위치는 **06A01R2S1B** 여야 합니다.

1. 입력 내용을 확인하고 **확인** 을 선택합니다.

    작업 완료 및 '사용 가능한 작업 없음' 메시지가 나타납니다.

이제 판매 주문 2를 선택할 수 있습니다. 판매 주문과 연결된 보충 작업이 완료되면 차단 해제되었습니다.

1. 판매 주문 2의 작업 ID를 입력합니다.

    이 작업 ID에는 하나의 선택 작업만 있습니다.

1. **확인** 을 선택합니다.

    **판매 주문: 작업 선택** 페이지에는 선택할 품목 번호, 수량 및 위치가 표시됩니다.

1. **LP** 필드에 표시된 위치에 있는 품목의 번호판 번호를 입력합니다.

    지정하는 번호판은 보충 작업 작업에서 시스템 생성 번호판이 됩니다. 올바른 번호판 ID를 캡처했는지 확인하려면 **재고 목록** 페이지에서 품목, 위치 및 수량에 대한 재고를 확인하세요.

1. **확인** 버튼(확인 표시 기호)을 선택합니다.
1. 아웃바운드 스테이징 위치에 대한 넣기 작업에 대한 지침을 확인합니다.
1. **확인** 을 선택합니다.

    "작업 완료" 메시지가 표시됩니다.

## <a name="notes-and-tips"></a>참고 사항 및 팁

- 이 기능은 웨이브 수요, 최소/최대, 부하 수요 및 슬롯과 같은 모든 유형의 보충과 함께 작동합니다.
- 원하는 경우 **작업 세부 사항** 페이지에서 각 작업 헤더에 대한 보충 작업 가용성을 수동으로 무시할 수 있습니다.
- 시스템이 보충 작업 가용성을 설정할 때 작업이 완료되기 전에 해당 위치에 이미 있는 모든 재고를 고려합니다.
- 각 판매 주문 작업은 특정 보충 작업과 연결됩니다. 해당하는 영업 작업 가용성 기능이 없습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]