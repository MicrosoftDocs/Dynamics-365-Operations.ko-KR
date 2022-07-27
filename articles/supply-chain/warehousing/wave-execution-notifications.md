---
title: 웨이브 실행 알림
description: 이 토픽에서는 웨이브 실행 알림을 설명하고 설정 방법을 설명합니다.
author: mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: af3983db1a96116a88914411a26f1ac5d4857ae9
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8449971"
---
# <a name="wave-execution-notifications"></a>웨이브 실행 알림

[!include [banner](../includes/banner.md)]

*웨이브 실행 알림* 기능은 비즈니스 이벤트와 작업 센터를 사용하여 웨이브 실행과 관련된 알림을 전달합니다. 알림을 생성하는 이벤트 유형, 알림을 생성하는 창고 및 알림을 받는 사용자를 지정할 수 있습니다.

탐색 모음 오른쪽에 있는 **메시지 표시** 버튼(종 모양 기호)은 현재 사용자가 알림 센터 메시지를 사용할 수 있음을 나타냅니다. 사용자는 **메시지 표시** 단추를 선택하여 알림 센터를 열고 메시지를 검토합니다.

비즈니스 이벤트는 비즈니스 프로세스가 실행될 때 발생합니다. 비즈니스 프로세스는 작업으로 구성됩니다. 비즈니스 프로세스 중에 여기에 참여하는 사용자는 비즈니스 작업을 수행하여 해당 작업을 완료합니다. 비즈니스 이벤트는 외부 시스템이 금융 및 운영 애플리케이션에서 알림을 받을 수 있도록 하는 메커니즘을 제공합니다. 이러한 방식으로 시스템은 비즈니스 이벤트에 대한 응답으로 비즈니스 작업을 수행할 수 있습니다. 자세한 내용은 [비즈니스 이벤트 개요](../../fin-ops-core/dev-itpro/business-events/home-page.md)를 참조하세요.

## <a name="turn-the-wave-execution-notifications-feature-on-or-off"></a>웨이브 실행 알림 기능 켜기 또는 끄기

Supply Chain Management 버전 10.0.25부터 이 기능은 기본적으로 켜져 있습니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 공간에서 *웨이브 실행 알림* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a>시나리오: 관리 센터에 웨이브 배치 실행 알림 보내기

이 시나리오는 관리 센터를 통해 웨이브 배치 실행 오류에 대한 알림을 특정 역할에 보내는 엔드투엔드 흐름을 보여줍니다.

### <a name="make-demo-data-available"></a>데모 데이터 사용 가능

이 시나리오를 따르려면 데모 데이터가 설치되어 있어야 하고 **USMF** 법인을 선택해야 합니다.

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a>웨이브가 배치 모드에서 실행되는지 확인

1. **Warehouse Management \> 설정 \> Warehouse Management 매개 변수** 로 이동합니다.
1. **웨이브 처리** 빠른 탭에서 **웨이브 일괄 처리** 를 *예* 로 설정합니다.

> [!NOTE]
> 웨이브 일괄 실행 알림을 비활성화하려면 **웨이브 처리 일괄 알림 비활성화** 옵션을 *예* 로 설정합니다.

### <a name="configure-a-wave-notification-policy"></a>웨이브 알림 정책 구성

웨이브 알림 정책은 전송되는 알림 유형과 알림을 받는 사용자를 정의합니다.

1. **창고 관리 \> 설정 \> 웨이브 \> 웨이브 알림 정책** 으로 이동합니다.
1. 다음 설정이 있는 레코드를 만듭니다.

    - **웨이브 알림 정책:** *24BatchError*
    - **설명:** *창고 24 웨이브 배치 오류*
    - **알림 보내기:** *오류만*
    - **역할:** *시스템 관리자*

        > [!NOTE]
        > 이 시나리오는 데모 데이터를 사용하므로 단순화를 위해 *시스템 관리자* 역할이 선택됩니다. 따라서 시스템 관리자로 로그인했기 때문에 알림을 받게 됩니다. 그러나 실제로는 일반적으로 *창고 관리자* 와 같은 웨이브 배치 실행 오류에 대해 알리기 위해 보다 구체적인 역할을 선택해야 합니다.

1. 작업 창에서 **저장** 을 선택합니다.

### <a name="configure-a-wave-template"></a>웨이브 템플릿 구성

웨이브 템플릿을 사용하면 웨이브 메서드의 특정 인스턴스를 해당 웨이브 레이블 템플릿에 연결할 수 있습니다.

1. **창고 관리 \> 설정 \> 웨이브 \> 웨이브 템플릿** 으로 이동합니다.
1. 목록 창에서 **웨이브 템플릿 유형** 필드를 *배송* 으로 설정한 다음 창고 24에 대한 *24 배송 기본* 웨이브 템플릿을 선택합니다.
1. **일반** 빠른 탭에서 **웨이브 알림 정책** 필드를 *24BatchError* 로 설정합니다.

### <a name="configure-a-work-template"></a>작업 템플릿 구성

작업 템플릿은 웨이브 실행 중에 작업을 생성하는 데 사용됩니다. 이 시나리오에서 웨이브 실행은 오류를 트리거해야 합니다. 존재하지 않는 창고를 사용하도록 작업 템플릿 쿼리를 설정하면 웨이브 실행이 실패하여 알림을 보냅니다.

1. **창고 관리 \> 설정 \> 작업 \> 작업 템플릿** 으로 이동합니다.
1. 목록 창에서 **웨이브 템플릿 유형** 필드를 *판매 주문* 으로 설정한 다음 창고 24에 대한 *24 SO 단계* 작업 템플릿을 선택합니다.
1. 작업 창에서 **쿼리 편집** 을 선택합니다.
1. 쿼리 편집기 대화 상자의 **범위** 탭에서 다음 행을 편집합니다(없는 경우 추가).

    - **표:** *임시 작업 거래*
    - **파생 테이블:** *임시 작업 트랜잭션*
    - **필드:** *창고*
    - **기준:** 값을 *24* 에서 *오류* 로 변경합니다.

1. **확인** 을 선택하여 변경을 확인합니다.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>판매 주문을 생성하고 창고로 릴리스

1. **영업 및 마케팅 \> 판매 주문 \> 모든 판매 주문** 으로 이동합니다.
1. 다음 설정이 있는 판매 주문을 만듭니다.

    - **고객 계정** *US-001*
    - **창고:** *24*

1. **판매 주문 라인** 빠른 탭에서 다음 설정이 있는 판매 주문 라인을 추가합니다.

    - **품목 번호:** *A0001*
    - **수량:** *10*

    > [!NOTE]
    > 이러한 항목과 수량은 예시일 뿐입니다. 지정된 창고에는 충분한 재고가 있어야 합니다.

1. **판매 주문 라인** 빠른 탭에서 새 라인이 계속 선택되어 있는 동안 도구 모음에서 **재고 \> 예약** 을 선택합니다.
1. **예약** 페이지의 작업 창에서 **로트 예약** 을 선택합니다. 페이지를 닫습니다.
1. 작업 창의 **창고** 탭에서 **창고로 릴리스** 를 선택합니다.

### <a name="notifications-from-wave-batch-job-execution"></a>웨이브 일괄 작업 실행 알림

비즈니스 이벤트 설정에 따라 결국 웨이브 실행 실패에 대한 알림을 받게 됩니다. 관리 센터 메시지는 다음 예와 유사하며 실패한 웨이브에 대한 링크를 포함합니다.

> **웨이브 실행 중 오류**  
> 웨이브 USMF-000000001을 실행하는 동안 오류가 발생했습니다.  
> 마지막 메시지: 웨이브 USMF-000000001에 대해 작업이 생성되지 않았습니다.
>
> **상태**  
> 활성
>
> 웨이브 세부정보 열기

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
