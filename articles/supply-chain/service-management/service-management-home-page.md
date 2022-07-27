---
title: 서비스 관리 개요
description: 서비스 관리를 사용하여 서비스 계약 및 서비스 가입을 설정하고, 서비스 주문 및 고객 문의를 처리하고, 고객에 대한 서비스 제공을 관리 및 분석합니다.
author: kamaybac
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b9b8444c635fe08a224314d1b76de5ac8d9defbc
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449686"
---
# <a name="service-management-overview"></a>서비스 관리 개요

[!include [banner](../includes/banner.md)]


**서비스 관리** 를 사용하여 서비스 계약 및 서비스 구독을 설정하고, 서비스 주문 및 고객 문의를 처리하고, 고객에 대한 서비스 제공을 관리 및 분석합니다. 서비스 계약을 사용하여 일반적인 서비스 방문에 사용되는 리소스를 정의할 수 있습니다. 서비스 계약을 사용하여 해당 리소스가 고객에게 청구되는 방식을 볼 수도 있습니다. 서비스 계약에는 표준 응답 시간을 지정하고 실제 시간을 기록하는 도구를 제공하는 서비스 수준 계약도 포함될 수 있습니다.

서비스 주문을 생성하여 서비스 기술자가 고객 사이트를 방문하는 예약 및 예약되지 않은 방문에 대한 정보를 관리할 수 있습니다. 서비스 주문에는 다음과 같은 정보가 포함됩니다.

1.  서비스 기술자가 수행할 작업 시간

2.  서비스 또는 수리 유형입니다.

3.  증상 및 진단에 대한 세부 정보를 포함하여 수리할 항목

4.  서비스 또는 수리와 관련된 모든 비용 및 수수료

서비스 요청을 수신, 처리 및 발송할 수 있습니다. 서비스 주문을 생성한 후 서비스 단계를 사용하여 진행 상황을 모니터링하고 각 단계에서 활성화되는 작업을 제어하는 규칙을 지정할 수 있습니다. 서비스 주문이 완료되면 주문에 서명하여 완료되었는지 확인한 다음 주문을 게시하여 송장 프로세스를 시작할 수 있습니다.

보고 도구를 사용하여 서비스 주문 마진 및 구독 거래를 모니터링하고 작업 설명 및 작업 영수증을 인쇄합니다.

## <a name="business-processes"></a>비즈니스 프로세스

다음 다이어그램은 **서비스 관리** 를 위한 상위 수준 비즈니스 프로세스를 보여주고 서비스 프로세스가 다른 모듈과 통합되는 위치를 보여줍니다.

[![서비스 관리 비즈니스 프로세스 다이어그램.](./media/sm_home_page.gif)](./media/sm_home_page.gif)

## <a name="service-management-at-a-glance"></a>서비스 관리 한눈에 보기

|중요한 작업           | 기본 페이지                         |인기 있는 보고서              |
|--------------------------|---------------------------------------|-----------------------------|
|서비스 계약 이행|서비스 계약                     |서비스 주문 마진         |
|고객 문의 처리 |서비스 주문                         |작업 설명             |
|                          |디스패치 보드                         |거래 - 구독   |
|                          |                                       |구독료 거래|


## <a name="integration-of-service-management"></a>서비스 관리 통합

서비스 관리는 다음 모듈과 통합할 수 있습니다.

  - [영업 및 마케팅 개요](../sales-marketing/overview-sales-marketing.md)
  - [Human Resources](/dynamics365/unified-operations/talent/index)

  



[!INCLUDE[footer-include](../../includes/footer-banner.md)]