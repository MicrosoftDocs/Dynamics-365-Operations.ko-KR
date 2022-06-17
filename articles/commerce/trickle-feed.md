---
title: 소매점 거래를 위한 지속적인 피드 기반 주문 생성
description: 이 항목에서는 Microsoft Dynamics 365 Commerce에서 매장 거래에 대한 지속적인 피드 기반 주문 생성에 대해 설명합니다.
author: analpert
ms.date: 01/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 67b66cd4bf2a77f3ab7f33f691156e38cc13770a
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2022
ms.locfileid: "8452935"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>소매점 거래를 위한 지속적인 피드 기반 주문 생성

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Commerce 버전 10.0.5 이상에서는 모든 명세서 게시 프로세스를 지속적인 피드 기반 명세서 게시 프로세스로 전환하는 것이 좋습니다. 지속적인 피드 기능을 사용하면 상당한 성능과 비즈니스 이점을 얻을 수 있습니다. 판매 거래는 하루 종일 처리됩니다. 입찰 및 현금 관리 거래는 하루가 끝날 때 재무제표에서 처리됩니다. 지속적인 피드 기능을 사용하면 판매 주문, 송장, 지불을 지속적으로 처리할 수 있습니다. 따라서 재고, 수익, 지불이 거의 실시간으로 업데이트되고 인정됩니다.

## <a name="use-trickle-feed-based-posting"></a>지속적인 피드 기반 게시 사용

> [!IMPORTANT]
> 지속적인 피드 기반 게시를 사용하기 전에 계산된 명세서와 게시되지 않은 명세서가 없는지 확인해야 합니다. 기능을 사용하기 전에 모든 명세서를 게시합니다. **매장 재무** 작업 영역에서 미결산 명세서가 있는지 확인할 수 있습니다.

소매 거래의 지속적인 피드 기반 게시를 사용하려면 **기능 관리** 작업 영역에서 **소매 명세서 - 지속적인 피드** 기능을 사용하도록 설정합니다. 명세서는 거래 명세서와 재무제표의 두 가지 유형으로 나뉩니다.

### <a name="transactional-statements"></a>거래 명세서

거래 명세서 처리는 거래가 Commerce Headquarters에 업로드될 때 문서가 생성되도록 하루 종일 높은 빈도로 실행됩니다. **P-Job** 을 실행하면 거래가 매장에서 Commerce Headquarters로 로드됩니다. 거래 명세서에서 거래가 선별되도록 **매장 거래 확인** 작업을 실행해 거래를 확인합니다.

다음 작업을 높은 빈도로 실행하도록 예약합니다.

- 거래 명세서를 계산하려면 **거래 명세서 일괄 계산** 작업을 실행합니다(**Retail 및 Commerce \> Retail 및 Commerce IT \> POS 게시 \> 거래 명세서 일괄 계산**). 이 작업은 게시되지 않고 확인된 모든 거래를 선별해 새 거래 명세서에 추가합니다.
- 거래 명세서를 일괄 게시하려면 **거래 명세서 일괄 게시** 작업을 실행합니다(**Retail 및 Commerce \> Retail 및 Commerce IT \> POS 게시 \> 거래 명세서 일괄 게시**). 이 작업은 게시 프로세스를 실행하고 오류가 포함되지 않은 게시되지 않은 명세서에 대한 판매 주문, 판매 송장, 지불 분개장, 할인 분개장, 소득 비용 거래를 생성합니다. 

### <a name="financial-statements"></a>재무제표

재무제표 처리는 최종 프로세스로 고안되었습니다. 이러한 유형의 명세서 처리는 **교대** 결산 방법이며 결산된 교대만 선별합니다. 명세서는 재정 조정으로 제한됩니다. 계산된 금액과 입찰 거래 금액 간의 차액에 대한 분개장과 기타 현금 관리 거래에 대한 분개장만 생성합니다.

재무제표를 통해 입찰 신고 거래, 지불 거래, 은행 입찰 거래, 안전 입찰 거래 등의 거래를 검토할 수도 있습니다. 입찰 세부 정보 페이지는 재무제표를 선택한 경우에만 표시됩니다.

![재무제표를 선택한 경우에만 게시된 명세서 양식의 입찰 세부 내역 섹션을 보여 주는 이미지.](./media/Trickle-feed-posted-statements-transaction-view.png)

예상되는 하루의 끝을 기준으로 다음 재무제표 작업의 시작 및 종료 시간을 예약합니다.

- 재무제표를 계산하려면 **재무제표 일괄 계산** 작업을 실행합니다(**Retail 및 Commerce \> Retail 및 Commerce IT \> POS 게시 \> 재무제표 일괄 계산**). 이 작업은 게시되지 않은 모든 재무 거래를 수집하여 새 재무제표에 추가합니다.
- 재무제표를 일괄 게시하려면 **재무제표 일괄 게시** 작업을 실행합니다(**Retail 및 Commerce \> Retail 및 Commerce IT \> POS 게시 \> 재무제표 일괄 게시**).

### <a name="manually-create-statements"></a>수동으로 명세서 생성

거래 명세서와 재무제표 유형을 수동으로 만들 수도 있습니다. 

1. **Retail 및 Commerce \> 채널 \> 매장** 으로 이동한 뒤 **명세서** 를 선택합니다. 
2. **새로 만들기** 를 선택한 후 만들려는 명세서 유형을 선택합니다. **명세서** 페이지의 필드에는 **명세서 그룹** 아래에 선택한 명세서 유형과 관련된 데이터와 작업이 표시됩니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
