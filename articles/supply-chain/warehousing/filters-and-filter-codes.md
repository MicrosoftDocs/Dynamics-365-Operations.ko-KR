---
title: 창고 거래에 대한 제품 필터 구성
description: 이 토픽에서는 창고의 재고 항목을 분류하기 위해 제품 필터 및 필터 코드를 구성하는 방법에 대해 설명합니다. 필터를 사용하여 특정 항목을 주문할 수 있는 고객과 특정 공급업체에서 구매할 수 있는 항목을 지정할 수도 있습니다.
author: Mirzaab
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSFilters,WHSFilterGroupTable,EcoResProductDetailsExtended,WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 021ce940a4ea6d59719d1c6bc79532832cc2f3ff
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448030"
---
# <a name="configure-product-filters-for-warehouse-transactions"></a>창고 거래에 대한 제품 필터 구성

[!include [banner](../includes/banner.md)]

이 토픽에서는 창고의 재고 항목을 분류하기 위해 제품 필터 및 필터 코드를 구성하는 방법에 대해 설명합니다. 필터를 사용하여 특정 항목을 주문할 수 있는 고객과 특정 공급업체에서 구매할 수 있는 항목을 지정할 수도 있습니다.

또한 제품 필터를 설정 및 사용하여 창고의 재고 항목을 자동으로 구성하고 필터링된 품목을 필터 그룹으로 결합할 수 있습니다. 필터를 사용하여 항목을 취급, 구매 및 판매 프로세스의 범주로 분류할 수 있습니다. 취급 방법이 무게 또는 취급 제한 사항을 기반으로 하는 경우 항목을 함께 그룹화하거나 서로 분리할 수 있습니다. 또한 항목을 구매하거나 판매할 수 있는 고객 또는 공급업체를 지정할 수도 있습니다.

## <a name="prerequisites"></a>전제 조건

다음 테이블은 시작하기 전에 갖추어야 할 전제 조건을 보여줍니다.

| 전제 조건 | 지침 |
|---|---|
| **출시된 제품 세부 사항** 페이지에서 제품 구성을 시작하기 전에 제품의 재고 규모 그룹에 대해 창고 처리를 켜야 합니다. | **제품 정보 관리 \> 설정 \> 차원 및 변형 그룹 \> 재고 규모 그룹** 으로 이동하고 **Warehouse Management** 프로세스 사용 옵션이 *예* 로 설정된 저장소 차원 그룹을 선택하거나 생성합니다. |
| 고객 필터 및/또는 공급업체 필터를 사용하는 경우 Warehouse Management 매개 변수에서 사용을 활성화해야 합니다. | **Warehouse Management \> 설정 \> Warehouse Management 매개 변수** 로 이동합니다. **제품 필터** 탭에서 **고객 필터 사용** 및/또는 **공급업체 필터 사용** 옵션을 *예* 로 설정합니다. |

## <a name="set-up-product-filters"></a>제품 필터 설정

제품 필터는 열거(열거형) 값인 최대 10개의 **필터 제목** 특성을 제공합니다. 이러한 열거형 값은 제품 필터를 생성할 때 선택할 수 있습니다. *코드 1* 에서 *코드 10* 까지의 열거형 값은 시스템 정의이며 항목의 특정 특성 또는 속성을 나타냅니다. 예를 들어, *코드 1* 은 유해 물질 분류가 있는 항목을 나타낼 수 있습니다. *코드 2* 는 공급업체만 구매할 수 있는 항목을 나타낼 수 있습니다. 그런 다음 제품 필터는 **필터 제목** 값과 연결된 특정 **필터 코드** 값을 정의합니다.

1. **Warehouse Management \> 설정 \> 제품 필터 \> 제품 필터** 로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 제품 필터를 추가합니다.
1. **필터 제목** 필드에 값을 입력합니다.
1. **필터 코드** 필드에 값을 입력합니다.

    ![제품 필터를 설정합니다.](media/Product_Filters10.png "제품 필터 설정")

1. **설명** 필드에 코드에 대한 이름을 입력합니다. 예를 들어, *코드 2* 는 공급업체를 나타낼 수 있습니다. 그런 다음 특정 공급업체 또는 공급업체 그룹에 대한 제품 필터를 생성할 수 있습니다. 자세한 내용은 이 토픽 뒷부분의 [공급업체 필터 코드 설정](#vendor-product-filters) 섹션을 참조하세요.

    ![제품 필터 집합](media/Product_Filters.png "제품 필터 집합")

## <a name="set-up-product-filter-groups"></a>제품 필터 그룹 설정

필터 그룹을 사용하여 필터 코드를 그룹으로 묶을 수 있습니다. 이 기능은 위치 지시문의 쿼리에서 그룹을 사용하고 일련의 코드 대신 그룹을 검색하려는 경우에 유용합니다. 각 필터 그룹은 항목 그룹과 연결됩니다.

> [!IMPORTANT]
> *코드 4* 보다 높은 필터 코드(즉, *코드 5* 에서 *코드 10*)에 대해 모든 제품 필터 그룹을 사용할 수 있는 것은 아닙니다. 예를 들어 출시된 제품의 경우 모든 제품 필터 코드가 추가되지만 필터 코드 그룹은 업데이트되지 않습니다. 이 동작은 이후 릴리스에서 업데이트될 수 있습니다.

가격 그룹을 설정하려면 다음 단계를 따르세요.

1. **Warehouse Management \> 설정 \> 제품 필터 \> 제품 필터 그룹** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **그룹 1** 및 **그룹 2** 필드에 항목을 분류하는 데 사용할 이름을 입력합니다.
1. **세부 정보** 빠른 탭에서 **새로 만들기** 를 선택하여 라인을 추가합니다.
1. **시작 날짜/시간** 및 **종료 날짜/시간** 필드에 필터 그룹의 시작 및 종료 날짜를 입력합니다.
1. **항목 그룹** 필드에서 제품 필터가 적용되어야 하는 항목 그룹을 선택합니다.
1. **코드 1**~**코드 10** 필드에서 필요에 따라 그룹에 포함할 필터 코드를 선택합니다.

    ![항목 그룹.](media/ProdFilterGroup.png "항목 그룹")

> [!NOTE]
> 페이지를 닫을 때 오류 메시지가 표시되면 코드 설정이 누락되었을 수 있습니다. **항목 그룹** 페이지에서 **항목 그룹에 필터 코드 1 할당**, **항목 그룹에 필터 코드 2 할당** 등 확인란을 선택하여 항목 그룹에 대한 코드를 필수로 만들 수 있습니다.

## <a name="set-up-filter-codes-on-item-groups"></a>항목 그룹에 필터 코드 설정

항목 그룹에 필터 코드를 설정하여 해당 항목 그룹에 부착된 제품에 필요한 코드를 만들 수 있습니다.

항목 그룹에 필터 코드를 설정하려면 다음 단계를 따르세요.

1. **재고 관리 \> 설정 \> 재고 \> 항목 그룹** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 항목 그룹을 생성합니다.
1. **항목 그룹** 필드에 이름을 입력합니다.
1. **이름** 필드에 설명을 입력합니다.
1. **창고** 빠른 탭의 **필수 필터** 섹션에서 항목 그룹과 연결된 제품에 대해 지정해야 하는 필터 코드의 확인란을 선택합니다.

    출시된 제품을 업데이트하려면 **출시된 제품 세부 정보** 페이지를 연 다음 작업 창에서 **편집** 을 선택합니다. 코드와 연결된 필터는 **창고** 빠른 탭에서 사용할 수 있습니다.

    ![항목 그룹.](media/ItemGroup10.png "항목 그룹")

1. **항목 그룹 필터** 섹션에서 필터 그룹이 항목의 기본 필터 그룹이 되기 위해 일치해야 하는 필터의 확인란을 선택합니다.

    예를 들어 필터 **코드 1 사용** 및 필터 **코드 2 사용** 확인란을 선택한 경우 항목의 필터 코드 1과 필터 코드 2가 모두 항목 그룹에 대한 필터 그룹 설정과 일치해야 필터 그룹을 선택할 수 있습니다. 새 항목을 만들 때 선택한 필터 그룹은 **출시된 제품 세부 정보** 페이지의 **창고** 빠른 탭에 있는 **그룹 1** 및 **그룹 2** 필드의 기본 필터 그룹이 됩니다.

> [!IMPORTANT]
> 제품 필터 코드는 고급 창고 관리를 사용하는 품목에 대해서만 활성화됩니다.

## <a name="specify-filter-codes-for-released-products"></a>출시된 제품에 대한 필터 코드 지정

출시된 제품에 대한 필터 코드를 지정하려면 다음 단계를 따르십시오. 예를 들어 필터 코드를 사용하여 특정 공급업체에서 구매하는 위험 제품을 그룹화할 수 있습니다.

1. **제품 정보 관리 \> 제품 \> 릴리스된 제품** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 제품을 만듭니다.
1. **새 출시 제품** 대화 상자에서 새 제품의 기반을 만드는 데 필요한 데이터를 입력한 다음 **확인** 을 선택합니다.

    제품에 연결된 항목 그룹이 필터 코드에 대해 구성되어 있지 않으면 제품 필터 코드를 사용할 수 없습니다.

    자세한 내용은 [새 제품 만들기](../pim/tasks/create-new-product.md)를 참조하세요.

1. **창고** 빠른 탭의 **제품 필터 코드** 섹션에서 필요에 따라 **코드 1** 에서 **코드 10** 필드에 대한 필터 코드를 선택하여 제품에 대한 필터 코드를 지정합니다.

## <a name="set-up-generally-available-items"></a>일반적으로 사용 가능한 항목 설정

특정 인벤토리 항목을 고객, 공급업체 또는 고객과 공급업체 모두가 사용할 수 있도록 설정할 수 있습니다.

> [!NOTE]
> 고객 및 공급업체 필터는 일반적으로 사용 가능한 것으로 설정된 항목에 적용되지 않습니다.

일반적으로 사용 가능한 항목을 설정하려면 다음 단계를 따르세요.

1. **Warehouse Management \> 설정 \> 제품 필터 \> 일반적으로 사용 가능한 제품** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 레코드를 생성합니다.
1. **고객 또는 공급업체** 필드에서 *고객*, *공급업체* 또는 *모두* 를 선택하여 고객, 공급업체 또는 둘 다에 대해 항목을 사용할 수 있도록 합니다.
1. **시작 날짜/시간** 필드에 항목을 사용할 수 있게 되는 날짜와 시간을 입력합니다.
1. **항목 그룹** 필드에서 항목 그룹을 선택합니다.
1. **코드 1**~**코드 10** 필드에서 필터 코드를 선택하여 일반적으로 사용 가능한 항목을 제한합니다.

    항목 그룹을 선택하면 해당 항목 그룹을 일반적으로 사용 가능한 것으로 설정합니다. 이 필드에서 필터 코드를 선택하여 사용 가능한 항목을 제한합니다.

## <a name="set-up-customer-product-filters"></a>고객 제품 필터 설정

이 선택적 절차를 사용하여 **일반적으로 사용 가능한 항목** 페이지의 필터 설정을 통해 사용할 수 있는 항목 외에 고객이 사용할 수 있어야 하는 항목을 지정할 수 있습니다. 단일 고객에 대해 여러 필터를 설정할 수 있습니다.

고객 필터 코드를 설정하려면 다음 단계를 따르세요.

1. **영업 및 마케팅 \> 고객 \> 모든 고객** 으로 이동합니다.
1. 고객을 선택합니다.
1. 작업 창의 **고객** 탭에 있는 **설정** 그룹에서 **제품 필터** 를 선택합니다.
1. **제품 필터 코드** 페이지의 작업 창에서 **새로 만들기** 를 선택합니다.
1. **시작 날짜/시간** 및 **종료 날짜/시간** 필드에 선택한 항목 그룹의 시작 및 종료 날짜를 입력합니다.
1. **항목 그룹** 필드에서 항목 그룹을 선택합니다.
1. **코드 1** 에서 **코드 10** 필드에서 선택한 항목 그룹의 고객이 사용할 수 있는 항목을 제한하는 기준으로 사용할 필터 코드를 선택합니다. 항목 그룹에 대해 설정된 모든 필터 코드에 대해 선택해야 합니다.

## <a name="set-up-vendor-product-filters"></a><a name="vendor-product-filters"></a>공급업체 제품 필터 설정

이 선택적 절차를 사용하여 **일반적으로 사용 가능한 항목** 페이지의 필터 설정을 통해 사용할 수 있는 항목 외에 공급업체가 사용할 수 있어야 하는 항목을 지정할 수 있습니다. 단일 공급업체에 대해 여러 필터를 설정할 수 있습니다.

공급업체 필터 코드를 설정하려면 다음 단계를 따르세요.

1. **조달 및 소싱 \> 공급업체 \> 공급업체 검색** 으로 이동합니다.
1. 공급업체를 선택하세요.
1. 작업 창의 **공급업체** 탭에 있는 **설정** 그룹에서 **제품 필터** 를 선택합니다.
1. **필터 코드** 페이지의 작업 창에서 **새로 만들기** 를 선택합니다.
1. **시작 날짜/시간** 및 **종료 날짜/시간** 필드에 선택한 항목 그룹의 시작 및 종료 날짜를 입력합니다.
1. **항목 그룹** 필드에서 항목 그룹을 선택합니다.
1. **코드 1** 에서 **코드 10** 필드에서 선택한 항목 그룹의 공급업체가 사용할 수 있는 항목을 제한하는 기준으로 사용할 필터 코드를 선택합니다. 항목 그룹에 대해 설정된 모든 필터 코드에 대해 선택해야 합니다.

> [!NOTE]
> 공급업체 제품 필터 설정은 연결된 저장소 차원 그룹에 대해 Warehouse Management 프로세스가 활성화된 릴리스된 제품에 적용됩니다. 필터 코드는 시스템에서 사용자가 구매 주문 라인을 생성할 때 주어진 공급업체로부터 주어진 항목을 구매하도록 허용할지 여부를 결정하는 데 사용됩니다. Microsoft Dynamics 365 Supply Chain Management에는 공급업체 승인을 처리하는 두 가지 방법이 있습니다. **승인된 공급업체 확인 방법** 필드가 *경고만* 또는 *허용되지 않음* 으로 설정된 릴리스된 제품이 하나 이상 있는 경우 해당 항목에 대해 두 공급업체 승인 방법을 모두 사용할 수 있습니다. 이 상황은 사용자가 판매 주문 라인을 생성할 때 문제를 일으킬 수 있습니다.

## <a name="see-also"></a>참고 항목

[자세한 내용은 블로그 게시물 WMS-Warehouse 필터 코드를 참조하세요.](http://blog.dynamics-for-operations.com/2017/09/26/wms-warehouse-filter-codes/)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]