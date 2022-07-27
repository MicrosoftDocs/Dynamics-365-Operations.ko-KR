---
title: 고객 소유 자산에 대한 유지 관리 청구서
description: 이 토픽에서는 고객이 소유한 자산에 대해 수행되는 유지 관리 작업을 생성, 처리 및 청구하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a48e681da1801ef3c0d1c9c03cebaa5eecd37d76349a7b1c3cfe53e892fae489
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447256"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a>고객 소유 자산에 대한 유지 관리 청구서

[!include [banner](../../includes/banner.md)]

*작업 주문 청구* 기능을 사용하면 고객이 소유한 자산에 대해 수행되는 유지 관리 작업을 생성, 처리 및 청구할 수 있습니다. 이 기능을 사용하면 다음 작업을 수행할 수 있습니다.

- 고객을 소유한 자산에 연결합니다.
- 고객을 선택하고 작업 주문을 생성할 때 고객이 소유한 자산을 봅니다.
- 각 고객에 대해 상위 프로젝트를 설정합니다.
- 작업 주문에 대해 시간, 항목, 비용 및 수수료를 등록하고 나중에 고객을 위한 송장 제안서를 작성합니다.

또한 이 기능은 다음 기능을 제공합니다.

- 고객의 상위 프로젝트에서 프로젝트 계약이 관련 작업 주문 프로젝트에 자동으로 복사됩니다.
- 자산 관리는 이제 작업 주문 예측과 작업 주문 분개장 모두에서 *수수료* 프로젝트 트랜잭션 유형을 사용할 수 있습니다.

## <a name="turn-on-the-customer-billing-feature"></a>고객 청구 기능 켜기

이 기능을 사용하려면 먼저 시스템에서 켜져 있어야 합니다. 관리자는 [기능 관리](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 설정을 사용하여 기능의 상태를 확인하고 켤 수 있습니다. **기능 관리** 작업 영역에서 기능은 다음과 같은 방식으로 나열됩니다.

- **모듈**: *프로젝트 관리 및 회계*
- **기능 이름:** *작업 주문 청구*

## <a name="example-scenario"></a>예시 시나리오

이 기능의 작동 방식을 알아보려면 다음 예시 시나리오를 통해 작동하세요.

여기에 지정된 샘플 레코드 및 값을 사용하여 이 시나리오를 진행하려면 표준 [데모 데이터](../../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md)가 설치된 시스템에 있어야 합니다. 시작하기 전에 **USMF** 법인을 선택해야 합니다.

프로덕션 시스템에서 작업할 때 기능을 사용하기 위한 지침으로 이 시나리오를 사용할 수도 있습니다. 그러나 이 경우 고유한 값으로 대체해야 하며 표준 데모 데이터에서 제공하는 일부 유형의 필수 레코드가 누락될 수 있습니다.

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a>1단계: 고객을 위한 새 프로젝트 계약 만들기

1. **프로젝트 관리 및 회계 \> 프로젝트 \> 프로젝트 계약** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **새 프로젝트 계약** 대화 상자에서 다음 값을 설정합니다.

    - **이름:** *Pelican Wholesales*
    - **자금 유형:** *고객*
    - **자금 출처:** *US-013*(*Pelican Wholesales*)

1. **확인** 을 선택합니다.

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a>2단계: 고객을 위한 새 상위 프로젝트 만들기

여기에서 생성하는 상위 프로젝트는 고객에 대한 작업 주문이 생성될 때 사용됩니다.

1. **프로젝트 관리 및 회계 \> 프로젝트 \> 모든 프로젝트** 로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **새 프로젝트** 대화 상자에서 다음 값을 설정합니다.

    - **프로젝트 유형:** *시간 및 자재*
    - **프로젝트 이름:** *Pelican Wholesales 작업 주문*
    - **프로젝트 그룹:** *TM*
    - **프로젝트 계약 ID:** *Pelican Wholesales*(이전에 만든 계약)
    - **시작 날짜:** 오늘 날짜를 선택합니다.

1. **프로젝트 만들기** 를 선택합니다.
1. 새 프로젝트가 열려 있습니다. **프로젝트 ID** 값을 기록해 둡니다. 나중에 입력해야 합니다.

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a>3단계: 자산 관리에서 새 작업 주문 유형 만들기

1. **자산 관리 \> 설정 \> 작업 주문 \> 작업 주문 유형** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. 새 레코드가 목록에 추가됩니다. 다음 값을 설정합니다.

    - **작업 주문 유형:** *서비스*
    - **이름**: *서비스 작업 주문*
    - **작업 주문 수명 주기 상태:** *표준*

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a>4단계: 고객 계정을 상위 프로젝트에 연결하기

이제 자산 관리의 프로젝트 설정에서 고객 계정을 상위 프로젝트에 연결해야 합니다.

1. **자산 관리 \> 설정 \> 작업 주문 \> 프로젝트 설정** 으로 이동합니다.
1. **상위 프로젝트** 탭에서 **추가** 를 선택하여 라인을 추가합니다.
1. 새 줄에서 다음 값을 설정합니다.

    - **고객 계정**: *US-013*(*Pelican Wholesales*)
    - **프로젝트 ID:** 이전에 기록해 둔 프로젝트 ID를 입력합니다.

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a>5단계: 프로젝트 그룹을 연결하고 작업 주문 프로젝트에 입력하기

여전히 **프로젝트 설정** 페이지에 있어야 합니다(**자산 관리 \> 설정 \> 작업 주문 \> 프로젝트 설정**).

1. **프로젝트 그룹** 탭에서 **추가** 를 선택하여 라인을 추가합니다.
1. 새 줄에서 다음 값을 설정합니다.

    - **작업 주문 유형**: *서비스*(이전에 생성한 작업 주문 유형)
    - **프로젝트 그룹:** *TM*

> [!NOTE]
> 작업 주문 프로젝트의 프로젝트 계약은 항상 상위 프로젝트에서 상속됩니다.

### <a name="step-6-link-an-asset-to-the-customer-id"></a>6단계: 고객 ID에 자산 연결하기

1. **자산 관리 \> 자산 \> 활성 자산** 으로 이동합니다.
1. **필터** 필드에 *VE-102* 를 입력하고 **자산** 별로 필터링하도록 선택합니다.
1. 자산을 선택하여 설정을 엽니다.
1. **고객** 빠른 탭에서 **고객 계정** 필드를 *US-013*(*Pelican Wholesales*)로 설정합니다.

    **이름** 필드는 자동으로 *Pelican Wholesales* 로 업데이트됩니다.

### <a name="step-7-create-a-new-work-order-on-the-asset"></a>7단계: 자산에서 새 작업 주문 만들기

1. **자산 관리 \> 작업 주문 \> 활성 작업 주문** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. **작업 주문 만들기** 대화 상자에서 다음 값을 설정합니다.

    - **작업 주문 유형:** *서비스*
    - **설명:** *수리 트럭*
    - **고객 계정**: *US-013*(*Pelican Wholesales*)
    - **자산:** *VE-102*

        > [!NOTE]
        > 조회는 선택한 고객 계정에 연결된 자산만 표시합니다.

    - **유지 관리 작업 유형:** *수리*
    - **거래:** *정비공*
    - **서비스 수준:** *4*

1. **확인** 을 선택합니다.

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a>8단계: 작업 주문 검토 및 작업 시작하기

이 섹션에서는 이전 섹션에서 생성한 작업 주문에 대해 작업합니다.

1. 상위 프로젝트가 *Pelican wholesales 작업 주문* 프로젝트인지 확인하려면 다음 단계를 따르세요.

    1. **작업 주문 유지 관리 작업** 섹션에서 라인을 선택합니다.
    1. **라인 세부 정보** 빠른 탭에서 **프로젝트 ID** 값을 검사합니다. = *\<Parent-Project-ID\>-\<Project-ID\>* 형식의 하이픈으로 연결된 숫자여야 합니다. 이 값은 링크입니다.
    1. 프로젝트 ID 링크를 선택하여 상위 프로젝트 및 프로젝트 이름을 볼 수 있는 페이지를 엽니다.

1. 작업 창의 **작업 주문** 탭에 있는 **수명 주기 상태** 그룹에서 **작업 주문 상태 업데이트** 를 선택합니다.
1. **작업 주문 상태 업데이트** 대화 상자의 **선택** 열에서 **수명 주기 상태** 필드가 *진행 중* 으로 설정된 행의 확인란을 선택합니다.
1. **확인** 을 선택합니다.
1. **수명 주기 상태: 진행 중** 대화 상자에서 **확인** 을 선택합니다.

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a>9단계: 작업 주문에 소요된 시간 게시 및 새 송장 제안 만들기

이 섹션에서는 이전 섹션에서 작업한 작업 순서에 대해 계속 작업합니다.

1. 작업 창의 **작업 주문** 탭에 있는 **프로젝트** 그룹에서 **분개장** 을 선택합니다.

    **작업 주문 분개장** 페이지가 나타납니다. 여기에서 작업 주문에 소요한 시간을 등록할 수 있습니다.

1. **시간** 빠른 탭에서 **라인 추가** 를 선택합니다.
1. 새 줄에서 **시간** 필드를 *4* 로 설정합니다.
1. 작업 창에서 **분개장 게시** 를 선택합니다.
1. **작업 주문 분개장** 페이지를 닫고 작업 주문으로 돌아갑니다.
1. 작업 창의 **송장 발행** 탭에서 **새 송장 제안** 을 선택합니다.
1. **송장 제안 만들기** 대화 상자의 **프로젝트 트랜잭션** 섹션에서 송장을 발행할 모든 라인에 대해 **선택** 확인란을 선택합니다.
1. **확인** 을 선택하여 대화 상자를 닫고 새 송장 제안을 봅니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]