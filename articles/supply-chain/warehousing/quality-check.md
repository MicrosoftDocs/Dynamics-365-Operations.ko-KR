---
title: 품질 검사
description: 이 항목에서는 품질 검사 기능에 대한 정보를 제공합니다. 이 기능을 사용하면 창고 작업자가 인바운드 부두 영역으로 품목을 받는 동안 품질에 대한 빠른 현장 검사를 수행할 수 있습니다.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0848eeb2ad073915ad90d2fd2a4a91f0f420c0ab
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449980"
---
# <a name="quality-check"></a>품질 검사

[!include [banner](../includes/banner.md)]

*품질 검사* 기능을 사용하면 창고 작업자가 인바운드 부두 영역으로 품목을 받는 동안 품질에 대한 빠른 현장 검사를 수행할 수 있습니다. 이러한 현장 점검은 작업자가 품목의 포장 또는 기타 쉽게 알아볼 수 있는 부분을 검사할 때 유용합니다. 이 기능은 작업자가 보관 위치에 재고를 비축하기 전에 분명히 결함이 있거나 손상된 항목이 있는지 빠르게 살펴보도록 안내합니다.

이 기능은 표준 품질 검사 프로세스의 대안입니다. 더 많은 유연성과 더 빠른 처리를 제공합니다.

이 기능을 사용하면 도착 및 품질 검사는 다음과 같은 방식으로 이루어집니다.

1. 화물이 도착하면 창고 직원이 도착을 등록합니다. 작업자는 또한 위치를 등록하기 위해 번호판을 스캔합니다.
1. 작업자는 빠른 품질 검사를 수행하고 해당 번호판에 대한 결과(합격 또는 불합격)를 기록합니다.
1. 다음 작업 중 하나가 발생합니다.

    - 품질 검사를 통과하면 번호판을 수락하고 평소와 같이 수신 위치로 안내합니다.
    - 품질 검사에 실패하면 번호판은 거부되고 기존의 보관 작업은 추가 검사를 위해 대체 위치로 리디렉션됩니다. 새 품질 주문이 생성됩니다. 실패한 품질 검사에서 생성된 품질 주문을 보려면 **재고 관리 \> 정기 작업 \> 품질 관리 \> 품질 주문** 으로 이동합니다.

이 프로세스는 스캔한 모든 번호판이 즉시 품질 검사 위치로 전달되도록 설정할 수도 있습니다.

## <a name="turn-the-quality-check-feature-on-or-off"></a>품질 검사 기능 켜기 또는 끄기

이 항목에서 설명하는 기능을 사용하려면 *품질 검사* 기능이 시스템에 대해 켜져 있어야 합니다. Supply Chain Management 10.0.25부터 이 기능은 필수이며 끌 수 없습니다. 10.0.25 이전 버전을 실행 중인 경우 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *품질 검사* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

## <a name="set-up-the-feature-for-the-example-scenario"></a>예시 시나리오에 대한 기능 설정

이 섹션에서는 *품질 검사* 기능을 설정하고 이 품목의 뒷부분에서 제공되는 예시 시나리오에 대한 샘플 데이터를 준비하는 방법을 보여주는 지침과 예시를 제공합니다.

### <a name="make-sample-data-available"></a>샘플 데이터 사용 가능

여기에 지정된 샘플 기록 및 값을 사용하여 [예시 시나리오](#example-scenario)를 진행하려면 표준 [데모 데이터](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md)가 설치된 시스템에 있어야 합니다. 또한 시작하기 전에 **USMF** 법인을 선택해야 합니다.

### <a name="quality-check-template"></a><a name="quality-template"></a>품질 검사 템플릿

품질 검사 템플릿은 수신 시 품질에 대한 빠른 현장 검사를 수행하기 위한 규칙을 정의합니다.

1. **창고 관리 \> 설정 \> 작업 \> 품질 검사 템플릿** 으로 이동합니다.
1. **새로 만들기** 를 선택하여 그리드에 템플릿을 추가합니다.
1. 다음 값을 설정하여 새 템플릿을 정의합니다.

    - **품질 검사 템플릿 이름:** *도크 검사*

        이 템플릿에 적용된 정책을 식별하는 이름을 입력합니다.

    - **수락 정책:** *사용자에게 확인*

        사용자가 작업을 처리하는 동안 인벤토리 품질을 수락 또는 거부할지 또는 품질이 자동으로 거부되어야 하는지 여부를 지정합니다. 사용 가능한 옵션은 *자동 거부* 및 *사용자에게 확인* 입니다.

    - **품질 처리 정책:** *품질 주문 생성*

        재고 품질이 거부될 때 사용해야 하는 정책을 선택합니다. 다음 옵션을 사용할 수 있습니다.

        - *작업만 생성* – 재고 이동을 용이하게 하는 작업을 생성하기만 하면 됩니다.
        - *품질 주문 생성* – 품질 테스트를 용이하게 하기 위해 품질 주문을 생성합니다.

    - **테스트 그룹:** *인클로저*

        생성된 품질 순서에 사용해야 하는 테스트 그룹을 지정합니다. 테스트 그룹은 **재고 관리** 모듈에서 설정됩니다.

        테스트 그룹에 대해 **파괴적인 텍스트** 옵션이 꺼져 있습니다. 이 옵션은 샘플이 테스트 그룹에서 테스트의 일부로 파괴되는지 여부를 정의합니다. 파괴 테스트가 사용되는 경우 시스템은 품목에 대한 품질 주문이 생성될 때 재고 트랜잭션을 생성합니다. 새 재고 거래는 테스트 수량에 대한 재고 감소를 예측합니다. 재고 감소는 검증 단계를 통해 품질 주문이 완료될 때 발생합니다. 재고 거래는 품질 주문으로 식별됩니다.

### <a name="work-class--quality-check"></a><a name="work-class"></a>작업 클래스 – 품질 검사

작업 클래스는 창고 작업자가 모바일 디바이스에서 처리할 수 있는 작업 주문 라인의 유형을 지시 및/또는 제한하는 데 사용됩니다.

1. **창고 관리 \> 설정 \> 작업 \> 작업 클래스** 로 이동합니다.
1. **새로 만들기** 를 선택하여 작업 클래스를 생성합니다.
1. 헤더에서 다음 값을 설정합니다.

    - **작업 클래스 ID:** *QC 검사*

        작업 클래스를 식별하는 이름을 입력합니다.

    - **설명:** *QC 검사*

        작업 클래스의 용도를 나타내는 간단한 설명을 입력합니다.

    - **작업 주문 유형:** *품질 검사의 품질*

        작업 클래스에 의해 생성되는 작업 주문 유형을 선택합니다. 품질 관리 작업을 설정할 때 항상 *품질 검사의 품질* 을 선택합니다.

1. **유효한 위치 유형 입력** 빠른 탭에서 **위치 유형** 필드를 비워 둡니다.

    위치 유형을 선택하면 항목을 선택한 후 넣을 수 있는 위치가 제한됩니다. 이 필드는 위치 지시문이 위치를 확인하려고 하거나 창고 작업자가 모바일 디바이스 메뉴 항목의 위치를 수동으로 지정하는 경우에 사용됩니다.

작업 클래스 및 작성 방법에 대한 자세한 정보는 [작업 클래스 만들기](tasks/create-work-class.md) 참조하세요.

### <a name="work-template"></a>작업 템플릿

작업 템플릿에서는 창고에서 수행해야 하는 작업 작업을 정의할 수 있습니다. 일반적으로 창고 작업 작업은 한 쌍의 작업으로 구성됩니다. 창고 작업자는 한 위치에서 현 재고를 집어들고 피킹된 인벤토리를 다른 위치에 보관합니다. 품질 관리를 위한 작업 템플릿은 품질 검사를 수행하기 위한 작업을 정의합니다.

#### <a name="purchase-orders"></a>구매 주문

1. **창고 관리 \> 설정 \> 작업 \> 작업 템플릿** 으로 이동합니다.
1. 헤더에서 **작업 주문 유형** 필드를 *구매 주문* 으로 설정합니다.
1. 작업 창에서 **편집** 을 선택합니다.
1. 품질 검사 단계를 포함해야 하는 작업 템플릿을 선택합니다. **개요** 섹션의 **작업 템플릿** 필드에서 *51 PO 영수증* 을 선택합니다.
1. **작업 템플릿 세부 정보** 섹션에서 그리드에 기존의 두 라인이 있습니다. 하나는 *불출* 이고 다른 하나는 *배치* 입니다.
1. **작업 템플릿 세부 정보** 섹션에서 **신규** 를 선택하여 그리드에 품질 관리를 위한 행을 추가합니다. 새 라인의 **라인 번호** 필드가 *3* 으로 설정되어 있습니다.
1. 새 줄에서 다음 값을 설정합니다. 나머지 필드에 대한 기본값을 승인합니다.

    - **작업 유형:** *품질 검사*
    - **작업 클래스 ID:** *구매*
    - **품질 검사 템플릿 이름:** *도크 검사*

        작업 클래스의 고유 ID를 선택합니다. 이 값을 사용하여 모바일 디바이스의 메뉴 항목과 해당 메뉴 항목이 처리할 수 있는 작업 유형을 구성합니다.

1. 작업 창에서 **저장** 을 선택하여 지금까지의 작업을 저장합니다.

    "잘못됨 - 품질 검사는 불출 직후에 실행해야 합니다."라는 정보 메시지를 받습니다. 따라서 방금 추가한 라인의 **라인 번호** 값을 변경해야 합니다.

1. 새 라인의 **라인 번호** 값을 변경하려면 다음 단계를 따르십시오.

    1. **작업 템플릿 세부 정보** 섹션에서 **작업 유형** 필드가 *품질 검사* 로 설정된 라인을 선택합니다.
    2. **위로 이동** 또는 **아래로 이동** 버튼을 선택하여 *불출* 라인 뒤에 오도록 *품질 검사* 라인으로 이동합니다.

1. 작업 창에서 **저장** 을 선택합니다.

#### <a name="quality-in-quality-check"></a>품질 검사의 품질

다음으로 품질 검사를 위한 작업 템플릿을 만듭니다.

1. **작업 템플릿** 페이지 헤더에서 **작업 주문 유형** 필드 값을 *품질 검사 품질* 로 변경합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 **개요** 섹션의 그리드에 행을 추가합니다.
1. 신규 행에서 다음 값을 설정합니다.

    - **작업 템플릿:** *51 품질 검사*

        템플릿 이름을 입력합니다.

    - **작업 템플릿 설명:** *51 품질 검사*

1. 작업 창에서 **저장** 을 선택하여 **작업 템플릿 세부 정보** 섹션을 사용할 수 있도록 합니다.
1. **개요** 섹션에서 새 템플릿이 선택된 상태에서 **작업 템플릿 세부 정보** 섹션에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다.
1. 신규 행에서 다음 값을 설정합니다.

    - **작업 유형:** *픽*
    - **작업 클래스 ID:** *QC 검사*

        이전에 품질 관리 작업을 위해 생성한 [작업 클래스](#work-class)의 이름을 선택합니다.

1. **작업 템플릿 세부 정보** 섹션에서 **새로 만들기** 를 다시 선택하여 다른 행을 추가합니다.
1. 신규 행에서 다음 값을 설정합니다.

    - **작업 유형:** *풋*
    - **작업 클래스 ID:** *QC 검사*

        이전에 품질 관리 작업을 위해 생성한 [작업 클래스](#work-class)의 이름을 선택합니다.

1. 작업 창에서 **저장** 을 선택합니다.

작업 템플릿에 대한 자세한 내용은 [작업 템플릿 및 위치 지침을 사용하여 창고 작업 제어](control-warehouse-location-directives.md)를 참조하세요.

### <a name="location-directive--quality-failures"></a>위치 지시문 – 품질 실패

위치 지시문은 재고 이동을 위한 픽 앤 풋 위치를 식별하는 데 도움이 되는 규칙입니다. 예를 들어, 판매 주문 거래에서 위치 지시문은 항목을 선택하고 선택한 항목을 넣을 위치를 결정합니다. 실패한 품질 검사를 처리하는 방법을 정의하려면 위치 지시문 규칙을 구성해야 합니다.

1. **창고 관리 \> 설정 \> 위치 지시문** 으로 이동합니다.
1. 왼쪽 창에서 **작업 주문 유형** 필드를 *구매 주문* 으로 설정하여 해당 유형의 위치 지시문을 사용합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 품질 검사를 위한 위치 지시문을 만듭니다.
1. 헤더에서 다음 값을 설정합니다.

    - **시퀀스 번호**: 기본값을 수락합니다.
    - **이름:** *품질 51*

1. **위치 지시문** 빠른 탭에서 다음 필드를 설정합니다. 나머지 필드에 대한 기본값을 승인합니다.

    - **작업 유형:** *풋*
    - **사이트:** *5*
    - **창고:** *51*

1. 작업 창에서 **저장** 을 선택하여 지시문을 저장하고 **라인** 빠른 탭을 사용할 수 있도록 합니다.
1. **라인** 빠른 탭에서 **새로 만들기** 를 선택하여 라인을 그리드에 추가합니다.
1. 새 줄에서 다음 값을 설정합니다. 나머지 필드에 대한 기본값을 승인합니다.

    - **시작 수량:** *1*
    - **종료 수량:** *1,000,000*

1. 작업 창에서 **저장** 을 선택하여 새 줄을 저장하고 **위치 지시문 작업** 빠른 탭을 사용할 수 있도록 합니다.
1. **라인** 빠른 탭에서 새 라인이 선택되어 있는 동안 **위치 지시문 작업** 빠른 탭에서 **새로 만들기** 를 선택하여 그리드에 행을 추가하면 라인에 대한 작업을 설정할 수 있습니다.
1. 새 행에서 **이름** 필드를 *품질* 로 설정합니다. 나머지 필드에 대한 기본값을 승인합니다.
1. 작업 창에서 **저장** 을 선택하여 **위치 지시문 작업** 빠른 탭의 **쿼리 수정** 버튼을 사용할 수 있도록 합니다.
1. 방금 추가한 라인이 **위치 지시문 작업** 빠른 탭에서 선택된 상태에서 **쿼리 편집** 을 선택하여 작업에 대한 쿼리를 편집할 수 있는 대화 상자를 엽니다.
1. **범위** 탭에서 **추가** 를 선택하여 쿼리에 행을 추가합니다.
1. 신규 행에서 다음 값을 설정합니다.

    - **테이블:** *위치*
    - **파생 테이블:** *위치*
    - **필드:** *위치*
    - **기준:** *QMS*

    *QMS* 위치는 품질을 위한 창고 위치입니다.

1. **확인** 을 선택하여 대화 상자를 닫습니다.
1. 이제 창고 *51* 에 대한 구매 주문서 위치 지시의 순서를 변경해야 합니다. 새로운 *품질 51* 위치 지시문을 저장하고 페이지를 새로 고친 다음 목록에서 위치 지시문을 선택합니다. 그런 다음 작업 창에서 **위로 이동** 및 **아래로 이동** 버튼을 사용하여 창고 *51* 에 대한 위치 지시문을 다음 순서로 배치합니다. (**위로 이동** 또는 **아래로 이동** 을 선택하기 전에 목록에서 위치 지시문을 선택해야 합니다.)

    1. 품질 51
    2. 51 PO 다이렉트
    3. 51 QMS

### <a name="mobile-device-menu-items"></a>모바일 디바이스 메뉴 항목

모바일 디바이스에서 **품질 확인** 기능을 수행할 수 있도록 메뉴 항목을 구성합니다.

#### <a name="purchase-putaway"></a>구매 처리

1. **창고 관리 \> 설정 \> 모바일 디바이스 \> 모바일 디바이스 메뉴 항목** 으로 이동합니다.
1. 목록에서 **구매 처리** 메뉴 항목을 선택합니다.
1. 작업 창에서 **편집** 을 선택합니다.
1. **작업 클래스** 섹션에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다.
1. 신규 행에서 다음 값을 설정합니다.

    - **작업 클래스 ID:** *QC 검사*

        이전에 품질 관리 작업을 위해 생성한 [작업 클래스](#work-class)의 이름을 입력합니다.

    - **작업 주문 유형:** *품질 검사의 품질*

1. 작업 창에서 **저장** 을 선택합니다.

#### <a name="purchase-order-line-receiving"></a>구매 주문 라인 수신

1. **창고 관리 \> 설정 \> 모바일 디바이스 \> 모바일 디바이스 메뉴 항목** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. 헤더에서 다음 값을 설정합니다.

    - **메뉴 항목 이름:** *PO 라인 수신*
    - **제목:** *PO 라인 수신*
    - **모드:** *작업*
    - **기존 작업 사용:** *아니요*

1. **일반** 빠른 탭에서 다음 값을 설정합니다. 나머지 필드에 대한 기본값을 승인합니다.

    - **작업 생성 프로세스**: *구매 주문 라인 입고 및 보관*
    - **번호판 생성:** *예*
    - **작업 템플릿:** *51 PO 영수증*

1. 작업 창에서 **저장** 을 선택합니다.

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a>모바일 디바이스 메뉴에 메뉴 항목 추가

1. **Warehouse Management \> 설정 \> 모바일 디바이스 \> 모바일 디바이스 메뉴** 로 이동합니다.
1. 왼쪽 창에서 **인바운드** 메뉴를 선택합니다.
1. 작업 창에서 **편집** 을 선택합니다.
1. **사용 가능한 메뉴 및 메뉴 항목** 열에서 새 **PO 라인 수신** 메뉴 항목을 선택합니다.
1. 오른쪽 화살표 버튼을 선택하여 **PO 라인 수신** 을 **메뉴 구조** 열로 이동합니다.
1. **메뉴 구조** 열에서 **PO 라인 수신** 을 선택한 다음 위쪽 화살표 또는 아래쪽 화살표 버튼을 선택하여 메뉴 항목을 모바일 디바이스 메뉴의 원하는 위치로 이동합니다.
1. 작업 창에서 **저장** 을 선택합니다.

## <a name="example-scenario"></a><a name="example-scenario"></a>예시 시나리오

앞에서 설명한 모든 샘플 데이터를 사용 가능하게 만들고 설정한 후에는 이 시나리오를 통해 *품질 검사* 기능을 사용해 볼 수 있습니다. 이 시나리오에 표시된 값은 표준 데모 데이터로 작업 중이고 **USMF** 엔터티를 선택했으며 이 품목의 앞부분에서 설명한 샘플 레코드를 준비했다고 가정합니다. 이 시나리오는 생산 환경에서 기능을 사용하는 방법을 보여주는 예이기도 합니다.

### <a name="create-a-purchase-order"></a>구매 주문 만들기

1. **조달 및 소싱 \> 구매 주문 \> 모든 구매 주문** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **구매 주문 만들기** 대화 상자에서 다음 값을 설정합니다.

    - **공급 업체 계정:** *104*
    - **창고:** *51*

1. **확인** 을 선택하여 대화 상자를 닫고 새 구매 주문을 엽니다.
1. **구매 주문 라인** 빠른 탭에 그리드에 새 빈 라인이 포함되어 있습니다. 이 라인에서 다음 값을 설정합니다.

    - **품목 번호:** *M9203*
    - **수량:** *3*
    - **단위:** *PL*

1. 작업 창에서 **저장** 을 선택합니다.

### <a name="process-quality-check-receiving"></a>공정 품질 검사 접수

구매 주문이 생성된 후 **PO 라인 수신** 메뉴 항목과 *품질 검사* 기능을 이용하여 구매 주문을 수신할 수 있습니다.

#### <a name="receive-pallet-1"></a>팔레트 1 받기

1. 창고 *51* 에서 사용자로 Warehouse Management 모바일 앱에 로그인합니다. (사용자 ID는 *51*, 비밀번호는 *1* 을 입력하세요.)
1. **인바운드 \> PO 라인 수신** 으로 이동합니다.
1. **PONUM** 필드에 구매 주문 번호를 입력합니다.
1. 구매 주문 번호를 확인합니다.
1. **LINENUM** 필드에 수신 중인 구매 주문 라인의 번호를 입력합니다. 이 시나리오에서는 주문에 라인이 하나만 있기 때문에 각 입고 단계에 대해 **LINENUM** 필드에 *1* 을 입력합니다.
1. 라인 번호를 확인합니다.
1. **QTY** 필드에 수신할 수량을 입력합니다. 이 시나리오에서 구매 주문은 3개의 팔레트(*PL*)에 대한 것이고 3개의 입고 단계가 있으므로 각 수신 단계에 대한 **QTY** 필드에 *1* 을 입력합니다.
1. 수량을 확인합니다.

    표시되는 **품질 검사** 페이지에는 입력 필드가 없습니다. 하단에는 확인(확인 표시) 버튼, 상단에는 메뉴 버튼(**≡**)만 있습니다. (메뉴 버튼을 햄버거 또는 햄버거 버튼이라고도 합니다.) 신속한 품질 검사를 위해 팔레트가 품질 검사를 통과하면 사용자가 **품질 검사** 페이지를 확인하기만 하면 됩니다.

    ![품질 검사 페이지.](media/quality-check.png "품질 검사 페이지")

1. 확인 버튼을 선택하여 1행의 팔레트 1에 대한 품질 검사를 통과합니다.

    풋 작업에 대한 세부 정보를 보여주는 **구매 주문: 풋** 페이지:

    - **위치:** 시스템 결정 위치

        이 위치는 구매 주문 수신을 위해 지정된 보관 위치입니다.

    - **LP:** 시스템 생성 번호판 ID
    - **항목:** *M9203*
    - **수량:** *1 PL: 100개*

    항목 설명도 표시됩니다.

1. 처리 작업을 확인합니다.

    구매 주문 라인 수신을 위한 **작업** 페이지에서 "작업 완료" 메시지를 받습니다. **LINENUM** 필드를 사용할 수 있으므로 다음 팔레트를 받을 수 있습니다.

#### <a name="receive-pallet-2"></a>팔레트 2 받기

이 시나리오에서는 팔레트 2가 거부됩니다.

1. **LINENUM** 필드에 *1* 을 입력하고 라인 번호를 확인합니다.
1. **QTY** 필드를 이제 사용할 수 있습니다. *1* 을 입력하고 수량을 확인합니다.

    **품질 검사** 페이지가 나타납니다. 이 영수증의 경우 팔레트는 품질에 대해 거부되고 *QMS* 품질 위치에 배치됩니다.

1. 페이지 상단의 메뉴 버튼(**≡**)을 선택한 후 메뉴에서 **거부** 를 선택합니다.
1. 표시되는 **작업** 페이지에서 추가 검사를 위해 팔레트를 보낼 *풋* 위치로 **QMS** 를 입력합니다.

    풋 작업에 대한 세부 정보를 보여주는 **품질 검사의 품질: 풋** 페이지:

    - **위치:** *QMS*

        이 위치는 거부된 품질 수신을 위해 지정된 보관 위치입니다.

    - **LP:** 시스템 생성 번호판 ID
    - **항목:** *M9203*
    - **수량:** *1 PL: 100개*

    항목 설명도 표시됩니다.

1. 처리 작업을 확인합니다.

    구매 주문 라인 수신을 위한 **작업** 페이지에서 "작업 완료" 메시지를 받습니다. **LINENUM** 필드를 사용할 수 있으므로 다음 팔레트를 받을 수 있습니다.

이제 품질 검사를 완료하고 거부된 팔레트에 대한 품질 주문을 생성했습니다. 생성된 주문을 보려면 **재고 관리 \> 정기 작업 \> 품질 관리 \> 품질 주문** 으로 이동합니다.

이제 품질 주문 테스트를 처리할 수 있습니다. 품질 테스트는 이 항목에서 다루지 않습니다.

품질 관리에 대한 자세한 내용은 [품질 관리 개요](../inventory/enable-quality-management.md)를 참조하세요.

#### <a name="receive-pallet-3"></a>팔레트 3 받기

이 시나리오에서는 팔레트 3이 수락됩니다.

1. **LINENUM** 필드에 *1* 을 입력하고 라인 번호를 확인합니다.
1. **QTY** 필드를 이제 사용할 수 있습니다. *1* 을 입력하고 수량을 확인합니다.

    **품질 검사** 페이지가 나타납니다. 이 영수증의 경우 팔레트는 품질이 인정되며 대량 보관 장소에 보관됩니다.

1. 확인 버튼을 선택하여 품질 검사를 통과합니다.

    풋 작업에 대한 세부 정보를 보여주는 **구매 주문: 풋** 페이지:

    - **위치:** 시스템 결정 위치

        이 위치는 구매 주문 수신을 위해 지정된 보관 위치입니다.

    - **LP:** 시스템 생성 번호판 ID
    - **항목:** *M9203*
    - **수량:** *1 PL: 100개*

    항목 설명도 표시됩니다.

1. 처리 작업을 확인합니다.

    구매 주문 라인 수신을 위한 **작업** 페이지에서 "작업 완료" 메시지를 받습니다. **LINENUM** 필드를 사용할 수 있으므로 다음 팔레트를 받을 수 있습니다.

1. 페이지 상단의 메뉴 버튼(**≡**)을 선택한 후 메뉴에서 **취소** 를 선택하여 메뉴로 돌아갑니다.

이제 모바일 앱을 닫을 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]