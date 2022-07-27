---
title: 작업 주문 및 고정 자산
description: 이 토픽에서는 자산 관리의 작업 주문 및 고정 자산에 대해 설명합니다.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ad4af6bb0df557314f844d3e7a6c5fb84a6331d86f16e1bc76150f78ce3039e4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447031"
---
# <a name="work-orders-and-fixed-assets"></a>작업 주문 및 고정 자산

[!include [banner](../../includes/banner.md)]


자산 관리에서 자산은 고정 자산과 관련될 수 있으며 해당 자산에 대한 작업 주문을 생성할 수 있습니다. 이 기능을 사용하면 Microsoft Dynamics 365 for Finance and Operations의 **프로젝트 관리 및 회계** 및 **고정 자산** 모듈에서 고정 자산, 관련 투자 프로젝트 및 투자 프로젝트에 등록된 비용에 대한 전체 개요를 얻을 수 있습니다.

>[!NOTE]
>작업 주문 작업 프로젝트의 **고정 자산 번호** 필드는 작업 주문 작업 프로젝트의 프로젝트 유형으로 **투자** 가 선택된 경우에만 설정됩니다.

아래 그림은 **프로젝트 관리 및 회계** 모듈의 투자 프로젝트와 작업 주문 작업 프로젝트 간의 관계를 보여줍니다.

![자료 1.](media/24-work-orders.png)

다음 절차에서는 자산, 작업 주문, 작업 주문 작업 프로젝트 및 고정 자산 간의 관계를 설명합니다.

1. 고정 자산과 관련된 자산을 생성합니다.

![자료 2.](media/25-work-orders.png)

2. **작업 주문 유형** 페이지(**자산 관리** > **설정** > **작업 주문** > **작업 주문 유형**)에서 작업 주문 유형을 설정할 때 투자 처리를 위한 작업 주문 유형을 생성합니다. [작업 주문 유형](../setup-for-work-orders/work-order-types.md)도 참조하세요.

![자료 3.](media/26-work-orders.png)

3. **작업 주문 프로젝트 설정** 페이지(**자산 관리** > **설정** > **작업 주문** > **프로젝트 설정**)의 **프로젝트 그룹** 탭에서 작업 주문 프로젝트 그룹을 설정할 때, **프로젝트 관리 및 회계** 모듈의 **프로젝트 그룹** 페이지에서 투자에 사용되는 작업 주문 유형과 투자에 대해 생성된 프로젝트 그룹 간의 관계를 생성합니다(**프로젝트 관리 및 회계** > **설정** > **전기** > **프로젝트 그룹**).

![그림 4.](media/27-work-orders.png)

4. 고정 자산과 관련된 작업 주문을 생성할 때 **투자** 와 같은 투자를 처리하는 데 사용되는 작업 주문 유형을 선택합니다.

5. 작업 주문이 생성되면 관련 작업 주문 유형이 **모든 작업 주문** 페이지에 표시됩니다.

![그림 5.](media/28-work-orders.png)

6. 작업 주문이 생성되면 **프로젝트 관리 및 회계** 모듈의 **모든 프로젝트** 페이지(**프로젝트 관리 및 회계** > **프로젝트** > **모든 프로젝트**)에 작업 주문과 관련된 프로젝트가 생성됩니다. 프로젝트 관련 정보를 보려면 **자산 관리** 모듈의 **모든 작업 주문** 페이지의 세부 정보 보기에서 **라인 세부 정보** 빠른 탭의 **일반** 탭에 있는 **프로젝트 ID** 필드에 있는 링크를 선택하세요(**자산 관리** > **일반** > **작업 주문** > **모든 작업 주문**).

![그림 6.](media/29-work-orders.png)

7. 고정 자산과 연결된 프로젝트의 개요를 보려면 **고정 자산** > **고정 자산** > **고정 자산** 을 선택한 다음 **고정 자산 번호** 필드에서 고정 자산에 대한 링크를 선택하여 세부 정보 보기를 엽니다. 페이지 오른쪽의 **관련 정보** 창을 확장하고 **연결된 프로젝트** 빠른 탭을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]