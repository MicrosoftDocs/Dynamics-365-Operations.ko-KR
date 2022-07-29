---
title: 작업에서 작업 풀 변경
description: 이 항목에서는 작업 항목에 대한 작업 풀 변경 버튼을 사용하여 기존 작업의 작업 풀을 변경하는 방법에 대해 설명합니다.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9255b7d2eaf030592207b557b3b6567a1a5bda98
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449932"
---
# <a name="change-work-pool-on-work"></a>작업에서 작업 풀 변경

[!include [banner](../includes/banner.md)]

작업 풀을 사용하여 작업을 그룹으로 구성할 수 있습니다. 예를 들어, 특정 창고 위치에서 발생하는 작업을 분류하기 위해 작업 풀을 생성할 수 있습니다.

*작업에서 작업 풀 변경* 기능은 작업 항목의 작업 창에 **작업 풀 변경** 버튼을 추가합니다. 따라서 창고 관리자는 기존 작업의 작업 풀을 쉽게 변경할 수 있습니다. 이 기능을 통해 관리자는 창고 작업 현장의 변경 사항에 신속하게 대응할 수 있으며 변화하는 상황에 적응하고 작업을 다른 작업 풀로 이전해야 하는 필요성에 적응하는 능력을 향상시킬 수 있습니다.

## <a name="turn-the-change-work-pool-on-work-feature-on-or-off"></a>작업 기능의 작업 풀 변경 기능을 켜거나 끕니다

Supply Chain Management 10.0.25부터 이 기능은 필수이며 끌 수 없습니다. 10.0.25 이전 버전을 실행 중인 경우 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *작업에서 작업 풀 변경* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

## <a name="set-up-the-change-work-pool-on-work-feature"></a>작업 기능의 작업 풀 변경 기능 설정

이 기능을 사용하려면 일부 작업 풀이 설정되어 있어야 합니다. 풀을 자동으로 할당하도록 작업 템플릿을 설정할 수도 있습니다. 이 항목의 뒷부분에서 제공되는 예제 시나리오를 통해 작업하려면 이 섹션에 설명된 대로 시스템을 설정합니다.

### <a name="set-up-work-pools"></a>작업 풀 설정

작업 풀을 사용하면 작업 항목을 유형별로 구성할 수 있습니다. *직장에서 작업 풀 변경* 기능으로 작업하려면 사용 가능한 작업 풀이 두 개 이상 있어야 합니다. 작업 풀을 보고 추가하려면 다음 단계를 따르세요.

1. **Warehouse Management \> 설정 \> 작업 \> 작업 풀** 로 이동합니다.
1. **USMF** 회사의 데모 데이터로 작업하고 있으며 이 항목의 뒷부분에 나오는 예제 시나리오를 통해 작업하려는 경우 다음 설정이 있는 두 개의 작업 풀을 추가합니다.

    - 작업 풀 1:

        - **작업 풀 ID:** *Webshop*
        - **설명:** *웹 샵*

    - 작업 풀 2:

        - **작업 풀 ID:** *CallCenter*
        - **설명:** *콜 센터*

1. 작업 창에서 **저장** 을 선택합니다.

### <a name="set-up-work-templates"></a>작업 템플릿 설정

각 작업 템플릿에 대해 필요에 따라 기본 작업 풀을 설정할 수 있습니다. 각 관련 템플릿에 대해 **작업 풀 ID** 열에서 작업 풀을 할당합니다. 이 경우 지정된 템플릿을 사용하여 생성된 모든 작업 항목은 할당된 작업 풀을 자동으로 상속합니다. **USMF** 회사의 데모 데이터로 작업하고 있으며 이 항목의 뒷부분에 나오는 예제 시나리오를 통해 작업하려는 경우 이러한 단계를 따릅니다.

1. **창고 관리 \> 설정 \> 작업 \> 작업 템플릿** 으로 이동합니다.
1. 작업 창에서 **편집** 을 선택하여 페이지를 편집 모드로 전환합니다.
1. 다음 값을 설정하여 템플릿을 편집합니다.

    - **작업 템플릿:** *62 픽 투 팩*
    - **작업 풀 ID:** *Webshop*

1. **저장** 을 선택합니다.

## <a name="example-scenario"></a>예시 시나리오

이 시나리오는 작업 풀을 변경하여 기존 작업 항목의 처리 스트림을 변경하는 방법을 보여줍니다. **USMF** 회사의 데모 데이터 및 이 항목의 앞부분에서 제안된 설정을 사용합니다.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>판매 주문을 생성하고 창고로 릴리스

1. 창고 *62* 에 항목 *A0001* 및 *A0002* 에 대한 충분한 보유 재고가 있는지 확인합니다. **재고 관리 \> 문의 및 보고 \> 보유 목록** 으로 이동하고 다음과 같이 필터를 편집합니다.

    - **창고** 값은 *62* 로 시작합니다.
    - **품목 번호** 값은 *A001* 또는 *A002* 입니다.

    데모 데이터의 수량은 각각 10개여야 합니다.

    다음으로 판매 주문을 생성해야 합니다.

1. **영업 및 마케팅 \> 판매 주문 \> 모든 판매 주문** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **판매 주문 만들기** 대화 상자에서 다음 값을 설정합니다.

    - **고객 계정:** *US-007*
    - **창고:** *62*

1. **확인** 을 선택하여 판매 주문을 생성하고 대화 상자를 닫습니다.
1. 새 판매 주문이 열립니다. **판매 주문 라인** 빠른 탭의 그리드에 새로운 빈 라인을 포함해야 합니다. 이 라인에서 다음 값을 설정합니다.

    - **품목 번호:** *A0001*
    - **수량:** *2*

1. 그리드 위의 **인벤토리** 메뉴에서 **예약** 을 선택합니다.
1. **예약** 페이지의 작업 창에서 **로트 예약** 을 선택하고 재고를 예약합니다.
1. 페이지를 닫습니다.
1. **판매 주문 라인** 빠른 탭에서 **라인 추가** 를 선택하여 판매 주문에 다른 라인을 추가합니다. 이 라인에서 다음 값을 설정합니다.

    - **품목 번호:** *A0002*
    - **수량:** *2*

1. 그리드 위의 **인벤토리** 메뉴에서 **예약** 을 선택합니다.
1. **예약** 페이지의 작업 창에서 **로트 예약** 을 선택하고 재고를 예약합니다.
1. 페이지를 닫습니다.
1. 작업 창의 **창고** 탭에서 **창고로 릴리스** 를 선택합니다.
1. 릴리스에서 생성된 웨이브 ID 및 배송 ID를 보여주는 정보 메시지를 받습니다. 웨이브 ID를 기록해 둡니다.

### <a name="review-the-outbound-wave"></a>아웃바운드 웨이브 검토

1. **창고 관리 \> 아웃바운드 웨이브 \> 배송 웨이브 \> 모든 웨이브** 로 이동합니다.
1. 그리드에서 판매 주문 릴리스에서 생성된 웨이브 ID를 검색합니다.
1. 세부 정보를 보려면 웨이브 ID를 선택하세요.
1. **웨이브 라인** 빠른 탭에서 판매 주문에 대한 배송 ID가 표시되는지 확인합니다.

    > [!TIP]
    > 배송 웨이브 템플릿의 설정에서 **창고로 출고 시 프로세스 웨이브** 옵션이 *아니요* 로 설정되어 있으면 작업 창의 **웨이브** 탭에서 **프로세스** 를 선택하여 웨이브를 수동으로 처리해야 합니다.

1. 웨이브가 처리되었는지 확인합니다. 이 처리로 필요한 작업이 생성됩니다.

### <a name="view-work-details-and-change-the-work-pool"></a>작업 세부 정보 보기 및 작업 풀 변경

**작업 세부 정보** 페이지를 사용하여 생성된 작업을 확인하고 작업 풀을 관리할 수 있습니다.

1. **창고 관리 \> 작업 \> 작업 세부 정보** 로 이동합니다.
1. 방금 만든 작업에 대한 행을 선택합니다. **주문 번호** 열에는 판매 주문 번호가 표시됩니다.

    **작업 풀 ID** 필드는 작업 템플릿에 설정된 작업 풀 ID로 설정됩니다.

    > [!TIP]
    > **작업 풀 ID** 필드가 보이지 않으면 그리드에 열을 추가한 다음 페이지를 새로 고칩니다.

1. 작업 ID와 연결된 작업 풀을 변경하려면 작업 창의 **작업** 탭에서 **작업 풀 ID 변경** 을 선택합니다.
1. **작업 풀 변경** 대화 상자의 **매개 변수** 빠른 탭에서 **작업 풀 ID** 필드에 *CallCenter* 를 선택합니다.
1. **확인** 을 선택하여 변경 사항을 적용합니다.
1. **작업 풀 ID** 필드의 값이 이제 *CallCenter* 로 변경된 것을 볼 수 있습니다.

> [!IMPORTANT]
> **작업 풀 변경** 대화 상자가 나타나면 **작업 풀 ID** 필드는 기본적으로 비어 있을 수 있습니다. **확인** 을 선택하여 변경 사항을 적용할 때 필드가 비어 있으면 작업 풀을 작업에서 완전히 제거합니다.
>
> 작업 풀을 전환하는 것 외에도 이 절차를 사용하여 작업 풀이 없는 작업 항목에 작업 풀을 추가하거나 작업 풀이 있는 작업 항목에서 작업 풀을 제거할 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]