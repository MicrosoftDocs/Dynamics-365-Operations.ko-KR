---
title: 적치 클러스터
description: 적치 클러스터는 동시에 여러 번호판을 선택한 다음 다른 위치에 보관할 수 있는 방법을 제공합니다. 번호판은 일반적으로 인벤토리의 전체 팔레트가 아닌 소매 비즈니스에 매우 유용할 수 있습니다.
author: Mirzaab
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: d5aa579394a0e3bd4c27cd44c9ff98951b3bfe1c
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450019"
---
# <a name="putaway-clusters"></a>적치 클러스터

[!include [banner](../includes/banner.md)]

적치 클러스터는 동시에 여러 번호판을 선택한 다음 다른 위치에 보관할 수 있는 방법을 제공합니다. 이 과정을 흔히 *밀크런(milk run)* 이라고 합니다. 적치 클러스터는 일반적으로 인벤토리의 전체 팔레트가 아닌 소매 비즈니스에 매우 유용할 수 있습니다. 

## <a name="turn-the-cluster-putaway-feature-on-or-off"></a>클러스터 적치 기능 켜기 또는 끄기

이 항목에서 설명하는 기능을 사용하려면 *클러스터 적치 기능* 이 시스템에 대해 켜져 있어야 합니다. Supply Chain Management 10.0.25부터 이 기능은 필수이며 끌 수 없습니다. 10.0.25 이전 버전을 실행 중인 경우 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *클러스터 적치* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

## <a name="setup-for-the-example-scenario"></a>예제 시나리오 설정

### <a name="cluster-profiles"></a>클러스터 프로필

적치 클러스터 프로필은 수령 시점에 항목에 할당된 위치를 기반으로 항목이 갈 위치를 결정합니다. 다른 클러스터가 필요한 경우 각 모바일 디바이스 메뉴 항목에 대해 다른 적치 클러스터를 만들어야 합니다.

1. **창고 관리 \> 설정 \> 모바일 디바이스 \> 클러스터 프로파일** 로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **헤더** 보기에서 다음 값을 설정합니다.

    - **적치 클러스터 프로필 ID:** *클러스터 적치*
    - **적치 클러스터 프로필 ID 이름:** *클러스터 적치*
    - **클러스터 유형:** *적치*
    - **시퀀스 번호**: 기본값을 수락합니다.

1. **저장** 을 선택하여 **일반** 빠른 탭에서 필요한 필드를 사용할 수 있게 만듭니다.
1. **일반** 빠른 탭에서 다음 값을 설정합니다.

    - **클러스터 할당 타이밍:** *수령 시*

        이 필드는 적치 클러스터를 인벤토리가 수신되는 즉시 할당해야 하는지 또는 나중에 정렬해야 하는지 여부를 정의합니다.

    - **클러스터 할당 규칙:** *수동*

        이 필드는 클러스터 할당이 시스템에 의해 자동으로 결정되어야 하는지 아니면 사용자에 의해 수동으로 결정되어야 하는지를 정의합니다.

    - **지시 코드:** 이 필드를 비워 둡니다.
    - **적치 클러스터 위치:** *수령*

        다음 값을 사용할 수 있습니다.

        - **수령** – 수령하는 즉시 위치를 찾습니다.
        - **클러스터 닫기** – 클러스터가 닫힐 때 위치가 발견됩니다.
        - **사용자 지시** – 적치를 위해 클러스터에서 번호판을 선택하면 위치가 검색됩니다. 이 경우 적치 작업이 생성될 때 위치를 지정하지 않습니다. 적치하는 동안 사용자는 번호판이나 직장 ID를 스캔하여 보관 단계를 시작해야 합니다. 그런 다음 시스템은 보관 위치를 다시 찾고 사용자에게 불출된 수량을 보관할 위치를 알려줍니다.

    - **사용자별 적치 클러스터:** *아니요*

        이 필드는 클러스터가 자동으로 할당될 때 각 클러스터가 사용자별로 고유해야 하는지 여부를 정의합니다. **클러스터 할당 규칙** 필드가 *자동* 으로 설정된 경우에만 사용할 수 있습니다.

    - **단위 제한:** 이 필드를 비워 둡니다.

        이 필드는 프로필이 유효하기 위해 수신되어야 하는 단위를 정의합니다. 공백으로 두면 모든 단위가 유효합니다.

    - **작업 단위 나누기:** *개인*

        이 필드는 클러스터가 닫힐 때 모든 인벤토리를 하나의 번호판에 통합해야 하는지(클러스터 ID와 번호판을 사용하여), 단일 번호판으로 적치해야 하는지 아니면 이전에 받은 번호판에 별도로 적치해야 하는지를 정의합니다. 이 필드는 **적치 클러스터 찾기** 필드가 *수령* 으로 설정된 경우 사용할 수 없습니다.

    - **클러스터가 상위 번호판으로 유지됨:** *아니요*

        이 옵션을 *예* 로 설정하면 보관 단계가 완료되면 클러스터 ID가 상위 번호판이 되고 클러스터 ID의 모든 항목이 해당 상위 번호판에 연결됩니다.

1. **클러스터 정렬** 빠른 탭에서는 적치 정렬 기준을 정의할 수 있습니다. 도구 모음에서 **새로 만들기** 를 선택하여 라인을 추가하고 다음 값을 설정합니다.

    - **시퀀스 번호**: 기본값을 수락합니다.
    - **필드 이름:** *WMSLocationId*

        이 필드는 이 행이 정렬 기준으로 사용해야 하는 필드를 정의합니다.

    - **정렬:** *오름차순*

        이 필드는 정렬이 오름차순 또는 내림차순으로 수행되어야 하는지 여부를 정의합니다.

1. **클러스터 작업 템플릿** 빠른 탭에서 도구 모음에서 **새로 만들기** 를 선택하여 라인을 추가하고 다음 값을 설정합니다.

    - **작업 주문 유형:** *구매 주문*
    - **작업 템플릿:** *61 PO 다이렉트*

1. 작업 창에서 **저장** 을 선택한 다음 **쿼리 편집** 을 선택합니다.
1. **클러스터 적치** 대화 상자의 **범위** 탭에서 **추가** 를 선택하여 쿼리에 두 번째 줄을 추가합니다. 그런 다음 다음 표와 같이 쿼리 라인을 업데이트합니다.

    | 테이블 | 파생 테이블 | 필드 | 기준 |
    |---|---|---|---|
    | 작업 | 작업 | 창고 | *61* |
    | 작업 | 작업 | 작업 ID | 이 필드를 비워 둡니다. |

1. **확인** 을 선택하여 쿼리를 저장하고 대화 상자를 닫습니다.
1. 작업 창에서 **저장** 을 선택하고 페이지를 닫습니다.

> [!IMPORTANT]
> **클러스터 ID 생성** 이 *예* 로 설정된 경우 흐리게 표시되는 클러스터 프로필의 필드는 사용할 수 없으며 이 기능을 사용할 때 고려되지 않습니다.

### <a name="mobile-device-menu-items"></a>모바일 디바이스 메뉴 항목

이 기능에 대해 두 가지 새로운 모바일 디바이스 메뉴 항목을 사용할 수 있습니다. **클러스터 수신 및 정렬** 메뉴 항목은 수령한 인벤토리를 수령 시 적치 클러스터로 분류하는 데 사용됩니다. **클러스터 적치** 메뉴 항목은 클러스터가 할당된 후 제거하는 데 사용됩니다.

#### <a name="receive-and-sort-cluster"></a>클러스터 수신 및 정렬

인벤토리를 수신하고 클러스터로 정렬하기 위한 새 모바일 디바이스 메뉴 항목을 만듭니다. 이 메뉴 항목은 재고가 수신된 후 인바운드 작업을 생성하며, 이는 수신 메뉴 항목이 적치 클러스터에 사용됨을 나타냅니다.

> [!NOTE]
> **클러스터 수신 및 정렬** 메뉴 항목은 다음 수신 메뉴 항목과 함께 사용할 수 있습니다.
>
> - 구매 주문 라인 수신
> - 구매 주문 품목 수신
> - 적재 항목 입고

1. **창고 관리 \> 설정 \> 모바일 디바이스 \> 모바일 디바이스 메뉴 항목** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **헤더** 보기에서 다음 값을 설정합니다.

    - **메뉴 항목 이름:** *클러스터 수신 및 정렬*
    - **제목:** *클러스터 수신 및 정렬*
    - **모드:** *작업*
    - **기존 작업 사용:** *아니요*

1. **일반** 빠른 탭에서 다음 값을 설정합니다.

    - **작업 생성 프로세스:** *구매 주문 품목 입고*
    - **번호판 생성:** *예*
    - **적치 클러스터 할당:** *예*

        > [!NOTE]
        > **적치 클러스터 할당** 옵션은 수신을 위한 1단계 *작업 생성 프로세스* 활동에만 사용할 수 있습니다.

    나머지 필드에 대한 기본값을 승인합니다.

1. 작업 창에서 **저장** 을 선택합니다.

#### <a name="cluster-putaway"></a>클러스터 적치

할당된 클러스터를 제거하기 위해 새 모바일 디바이스 메뉴 항목을 만듭니다.

1. **창고 관리 \> 설정 \> 모바일 디바이스 \> 모바일 디바이스 메뉴 항목** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **헤더** 보기에서 다음 값을 설정합니다.

    - **메뉴 항목 이름:** *클러스터 적치*
    - **제목:** *클러스터 적치*
    - **모드:** *작업*
    - **기존 작업 사용:** *예*

1. **일반** 빠른 탭에서 **감독** 필드를 *클러스터 적치* 로 설정합니다. 나머지 필드에 대한 기본값을 승인합니다.
1. **작업 클래스** 빠른 탭에서 이 모바일 디바이스 메뉴 항목에 대해 유효한 작업 클래스를 설정합니다.

    - **작업 클래스 ID:** *구매*
    - **작업 주문 유형:** *구매 주문*

1. 작업 창에서 **저장** 을 선택합니다.

### <a name="mobile-device-menu"></a>모바일 디바이스 메뉴

방금 생성한 메뉴 항목을 모바일 앱의 인바운드 메뉴에 추가합니다.

1. **Warehouse Management \> 설정 \> 모바일 디바이스 \> 모바일 디바이스 메뉴** 로 이동합니다.
1. 작업 창에서 **편집** 을 선택합니다.
1. 메뉴 목록에서 **인바운드** 를 선택합니다.
1. **사용 가능한 메뉴 및 메뉴 항목** 목록에서 **클러스터 수신 및 정렬** 을 찾아 선택합니다.
1. 오른쪽 화살표 버튼을 선택하여 선택한 메뉴 항목을 **메뉴 구조** 목록으로 이동합니다.
1. 위쪽 화살표 및 아래쪽 화살표 버튼을 사용하여 메뉴 항목을 메뉴에서 원하는 위치로 이동합니다.
1. 작업 창에서 **저장** 을 선택합니다.
1. 나머지 메뉴 항목을 추가하려면 4~7단계를 반복합니다.

    - 클러스터 할당
    - 클러스터 적치

## <a name="example-scenario"></a>예시 시나리오

이 시나리오는 적치 클러스터 처리를 시뮬레이션합니다.

### <a name="create-a-purchase-order"></a>구매 주문 만들기

1. **지급 계정 \> 구매 주문 \> 모든 구매 주문** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **구매 주문 만들기** 대화 상자에서 다음 값을 설정합니다.

    - **공급 업체 계정:** *1001*
    - **창고:** *61*

1. **확인** 을 선택합니다.

    **모든 구매 주문** 페이지가 나타납니다.

1. **모든 구매 주문** 페이지의 **구매 주문 라인** 빠른 탭에서 **라인 추가** 버튼을 사용하여 다음 라인을 추가합니다.

    - 구매 주문 라인 1:

        - **품목 번호:** *A0001*
        - **수량:** *10*

    - 구매 주문 라인 2:

        - **품목 번호:** *A0002*
        - **수량:** *20*

    - 구매 주문 라인 3:

        - **품목 번호:** *M9215*
        - **수량:** *30*

1. 작업 창에서 **저장** 을 선택합니다.
1. 구매 주문 번호를 기록해 둡니다.

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a>인벤토리를 받고 모바일 디바이스에서 떨어진 곳에 적치

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a>인벤토리를 수신하고 클러스터로 정렬

1. 창고 *61* 에 대해 설정된 사용자로 Warehouse Management 모바일 앱에 로그인합니다.
1. 주 메뉴에서 **인바운드** 를 선택합니다.
1. **인바운드** 메뉴에서 **클러스터 수신 및 정렬** 을 선택합니다.
1. **Ponum** 필드에 구매 주문 번호를 입력합니다.
1. **확인**(확인 표시 단추)을 선택합니다.
1. **항목** 필드를 선택하고 품목 번호로 *A0001* 을 입력하고 **확인** 을 선택합니다.
1. **수량** 필드를 선택하고 숫자 패드를 사용하여 *10* 을 입력한 다음 확인 표시 버튼을 선택합니다.
1. **수량** 작업 페이지에서 **확인**(확인 표시 버튼)을 선택하여 입력한 수량을 확인합니다.
1. **항목** 작업 페이지에서 **확인** 을 선택하여 *A0001* 항목이 입력되었는지 확인합니다.
1. **클러스터 ID** 필드를 선택하고 값을 입력하여 생성 중인 클러스터의 ID를 할당합니다.

    여기에 입력한 ID는 구매 주문의 나머지 2개 품목을 수령할 때 사용됩니다.

1. **확인** 을 선택합니다.

    **Ponum** 작업 페이지가 나타나고 "작업 완료됨" 메시지가 표시됩니다.

    *A0001* 항목이 이제 *RECV* 위치로 수신되었으며 10단계에서 입력한 클러스터 ID에 할당되었습니다.

1. 4~11단계를 반복하여 구매 주문에서 나머지 두 항목을 수신하고 클러스터 ID에 할당합니다.

    - 항목 *A0002* 에 대해 수량 *20*
    - 항목 *M9215* 에 대해 수량 *30*

#### <a name="close-the-cluster"></a>클러스터 닫기

클러스터의 항목을 적치하기 전에 클러스터를 닫아야 합니다.

1. Supply Chain Management에서 **창고 관리 \> 작업 \> 아웃바운드 \> 작업 클러스터** 로 이동합니다.
1. **작업 클러스터** 페이지의 **작업 클러스터** 섹션에서 이전에 입력한 클러스터 ID에 대한 **클러스터 ID** 필드를 검색합니다.
1. 클러스터가 표시되지 않으면 이미 닫혀 있을 수 있습니다. 클러스터가 닫혔는지 확인하려면 **닫힌 작업 표시** 확인란을 선택하고 이전에 입력한 클러스터 ID를 검색합니다. 그런 다음 다음 단계 중 하나를 따릅니다.

    - 클러스터가 닫혀 있는 경우 이 절차의 나머지 단계를 건너뛰고 다음 절차인 [클러스터 적치](#put-the-cluster-away)로 이동합니다.
    - 클러스터가 닫히지 않은 경우 이 절차의 나머지 단계에 따라 클러스터를 수동으로 닫습니다. 그런 후 다음 절차로 이동합니다.

1. **작업 클러스터** 섹션에서 이전에 입력한 클러스터 ID를 선택합니다.
1. 작업 창에서 **클러스터 닫기** 를 선택합니다.

    클러스터가 닫힌 후에는 더 이상 **작업 클러스터** 섹션에 표시되지 않습니다(**닫힌 작업 표시** 확인란이 선택되지 않은 경우).

#### <a name="put-the-cluster-away"></a>클러스터 적치

1. 창고 *61* 에 대해 설정된 사용자로 Warehouse Management 모바일 앱에 로그인합니다.
1. 주 메뉴에서 **인바운드** 를 선택합니다.
1. **인바운드** 메뉴에서 **클러스터 적치** 를 선택합니다.
1. **클러스터 ID** 를 선택하고 닫힌 클러스터에 대해 이전에 입력한 클러스터 ID를 입력합니다.
1. **확인** 을 선택합니다.

    **클러스터 적치: 불출** 페이지가 나타납니다. 클러스터 ID, 불출 위치, 항목(값 *여러 개* 이 표시됨) 및 클러스터에서 불출해야 하는 총 수량을 보여줍니다.

1. **확인** 을 선택합니다.

    **클러스터 적치: 보관** 페이지가 나타납니다. **보관** 지침은 클러스터 ID, 보관 위치, 품목, 총 수량 및 클러스터에서 받은 품목에 대한 번호판 ID를 식별합니다.

    이 단계를 무시하거나 통과할 수 있는 표준 옵션이 있습니다.

    ![클러스터 적치: 보관 페이지.](media/Cluster_putaway-Put.png "클러스터 적치: 보관 페이지")

1. **확인** 을 선택하여 클러스터의 적치를 확인합니다.

    "클러스터 완료" 메시지가 나타납니다.

## <a name="notes-and-tips"></a>참고 사항 및 팁

클러스터 ID가 중첩 팔레트의 상위 번호판이 되는 경우 클러스터 ID를 스캔할 때 보관 위치가 자동으로 제공됩니다. 번호판 생성이 수동으로 설정되어 있어도 더 이상 번호판을 스캔할 필요가 없습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]