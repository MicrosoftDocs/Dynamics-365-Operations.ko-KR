---
title: 경고 개요(비디오 포함)
description: 이번에는 경고에 대한 일반 정보를 제공합니다. 경고를 사용하여 근무 시간 동안 추적하려는 이벤트에 대한 정보를 받을 수 있습니다.
author: RichdiMSFT
ms.date: 09/04/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: c3332bdf7f2edb693c95a4d5a6f95906e14c0a42
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8460695"
---
# <a name="alerts-overview"></a>경고 개요

[!include [banner](../includes/banner.md)]

## <a name="about-alerts"></a>알림 정보
경고는 시스템의 중요한 이벤트에 대한 알림 시스템을 형성합니다. 경고를 사용하여 근무 시간 동안 추적하려는 이벤트에 대한 정보를 받을 수 있습니다. 기한이 지난 배송, 삭제된 주문, 가격 변경 또는 응답해야 하는 기타 이벤트에 대해 알림을 받도록 고유한 경고 규칙 집합을 쉽게 만들 수 있습니다.

ERP(전사적 자원 관리)에는 경고 기능을 사용할 수 있는 몇 가지 일반적인 시나리오가 있습니다. 여기 예시들이 있습니다 :

### <a name="scenario-1-create-an-alert-rule-for-new-sales-orders"></a>시나리오 1: 새 판매 주문에 대한 경고 규칙 만들기

1. **모든 판매 주문** 페이지를 엽니다.
2. 작업 창의 **옵션** 탭에 있는 **공유** 그룹에서 **사용자 지정 경고 만들기** 를 선택합니다.
3. **경고 규칙 만들기** 대화 상자의 FastTab 시 **경고 표시** 에 있는 **이벤트** 필드에서 **기록이 생성되었음** 을 선택합니다.

### <a name="scenario-2-create-an-alert-rule-for-postponement-of-a-delivery-date"></a>시나리오 2: 배달 날짜 연기에 대한 경고 규칙 만들기

1. **모든 구매 주문** 페이지를 엽니다.
2. 구매 주문 세부 정보에 액세스하려면 구매 주문 ID를 선택합니다.
3. **구매 주문 헤더** FastTab을 확장합니다.
4. 작업 창의 **옵션** 탭에 있는 **공유** 그룹에서 **사용자 지정 경고 만들기** 를 선택합니다.
5. **알림 규칙 만들기** 대화 상자의 FastTab **알림 시** **필드** 필드에서 **배달 날짜** 를 선택합니다.
6. **이벤트** 필드에서 **선택이 연기되었습니다**.
    
**경고 규칙 만들기** 대화 상자를 닫으면 **경고 규칙 관리** 페이지에 규칙이 나타납니다. **경고 규칙 관리** 페이지를 사용하여 기존 경고 규칙을 업데이트할 수 있습니다. 예를 들어, 이벤트 트리거를 수정하고, 이벤트 알림을 업데이트하고, 만료 날짜를 업데이트할 수 있습니다. **알림 규칙 관리** 페이지를 열려면 작업 창의 **옵션** 탭에서 **알림** 버튼을 사용합니다.

## <a name="what-occurs-when-an-alert-rule-is-created"></a>경고 규칙이 생성되면 어떻게 됩니까?

경고 규칙을 생성할 때 미리 정의된 이벤트를 특정 필드와 연결할 수 있습니다. 예를 들어, 필드에 지정된 날짜가 도착하거나 필드의 내용이 변경됩니다. 또는 이벤트를 특정 페이지의 기록와 연결할 수 있습니다. 예를 들어, 기록이 생성되거나 기록이 삭제됩니다.

필드 또는 페이지의 기록에 대해 선택한 이벤트가 발생하면 경고가 전송됩니다. 예를 들어 특정 구매 주문 라인의 **배달 날짜** 필드를 **이 시간 전 이벤트와 연결하는 규칙** 을 생성합니다. 기간을 5일로 설정했습니다. 이 경우 해당 구매 발주 라인의 배송 날짜로부터 5일 후에 경고가 전송됩니다.

또한 조건을 설정하여 경고 규칙을 구체화할 수 있습니다. 예를 들어 특정 공급 업체 계정에 대해 생성된 새 구매 주문에 대해 경고를 받을 수 있습니다.

## <a name="preparing-for-an-alert"></a>경고 준비

경고 규칙을 설정하기 전에 경고를 수신할 시기 또는 상황을 결정하십시오. 어떤 이벤트에 대해 알림을 받고 싶은지 알면 해당 이벤트의 원인이 되는 데이터가 표시되는 페이지를 찾습니다. 이벤트는 도착 날짜 또는 발생하는 특정 변경일 수 있습니다. 따라서 날짜가 지정되어 있는 페이지, 변경되는 필드 또는 새로 생성되는 기록이 나타나는 페이지를 찾아야 합니다. 이 정보가 있으면 경고 규칙을 만들 수 있습니다.

## <a name="components-of-an-alert-rule"></a>경고 규칙의 구성 요소

경고 규칙에는 5가지 구성 요소가 있습니다.

- **이벤트** – 경고 규칙을 트리거하는 이벤트는 도착 날짜 또는 발생한 특정 변경일 수 있습니다. **경고 규칙 만들기** 대화 상자의 **작업 상태 변경에 대한 전자 메일 경고 보내기** FastTab에서 이벤트를 정의합니다.
- **조건** – **경고 규칙 만들기** 대화 상자의 FastTab에 대한 **알림** 에서 조건 범위를 선택하여 이벤트에 대한 알림을 받는 시기를 제어할 수 있습니다. 현재 기록에만 규칙을 적용하거나 페이지에 표시되는 모든 기록에 규칙을 적용할 수 있습니다. 규칙이 **법인 전체** 에 적용되는 경우 조직 전체 옵션을 **예** 로 설정할 수 있습니다.
- **규칙 만료** – **알림 규칙 만들기** 대화 상자의 FastTab **까지 알림** 에서 알림 규칙이 활성화되어야 하는 기간을 지정할 수 있습니다.
- **내용** – **경고 규칙 생성** 대화 상자의 FastTab **으로 경고** 메시지에서 경고 메시지가 사용해야 하는 제목 텍스트와 메시지 텍스트를 지정할 수 있습니다.
- **사용자** – **경고 규칙 생성** 대화 상자의 **경고 대상** FastTab에서 경고 메시지를 수신해야 하는 사용자를 지정할 수 있습니다. 기본적으로 사용자 ID가 선택됩니다.

    > [!NOTE]
    > 이 옵션은 조직 관리자로 제한됩니다.

## <a name="videos"></a>비디오

### <a name="how-to-use-alerts-to-monitor-filtered-data"></a>경고를 사용하여 필터링된 데이터를 모니터링하는 방법

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3DWZ3]

[경고를 사용하여 필터링된 데이터 비디오를 모니터링하는 방법](https://youtu.be/ZYKMcv6kl9s)(위에 표시됨)은 YouTube에서 제공되는 [재무 및 운영 재생 목록](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)에 포함되어 있습니다.

### <a name="alert-rule-options"></a>경고 규칙 옵션

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E4PV]

[경고 규칙 옵션](https://youtu.be/cpzimwOjicM) 비디오(위에 표시됨)는 YouTube에서 사용할 수 있는 [재무 및 운영 재생 목록](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)에 포함되어 있습니다.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]