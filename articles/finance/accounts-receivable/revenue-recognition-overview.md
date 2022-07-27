---
title: 수익 인식 개요(동영상 포함)
description: 이 항목에서는 수익 인식 기능에 관한 정보를 제공합니다. 이 기능은 다중 요소 주문에 대한 수익 가격과 수익 일정을 모두 인식하는 회사별 규칙을 정의할 수 있는 유연한 프레임워크를 제공합니다.
author: kweekley
ms.date: 03/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: aae46fa90d306355608200f96ae5cf10793c8464
ms.sourcegitcommit: 0925b9ee0cb0df93047681a243aacc2abd404dea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2022
ms.locfileid: "8451852"
---
# <a name="revenue-recognition-overview"></a>수익 인식 개요

[!include [banner](../includes/banner.md)]

제품, 서비스, 구독 등과 같은 여러 요소를 판매하는 업계의 회사는 회사별 및 산업별 지침 집합을 기반으로 수익을 인식할 수 있도록 다중 요소 주문을 분할할 수 있어야 합니다.

번들 기능을 포함한 수익 인식은 상거래 채널(전자 상거래, POS, 콜센터)에서 사용할 수 없습니다. 수익 인식으로 구성된 항목은 상거래 채널에서 생성된 주문 또는 거래에 추가하지 않아야 합니다.

일반적으로 수익 인식 프로세스를 사용하여 다음 작업을 수행할 수 있습니다.

* 다중 요소 주문의 구성 요소 가치를 기반으로 적절한 수익 가격이 인식되도록 수익을 할당합니다.
* 계약 기간을 나타내는 수익 일정과 시간 경과에 따른 수익 인식 비율을 기준으로 수익을 이연합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

[금융 및 운영 재생 목록](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW)에 포함된 [Dynamics 365 Finance에서 수익 인식을 사용하는 방법](https://youtu.be/v3amIsiqvoo) 비디오(위에 표시)는 YouTube에서 볼 수 있습니다.

수익 인식 기능은 다중 요소 주문에 대한 수익 가격과 수익 일정을 모두 인식하는 회사별 규칙을 정의할 수 있는 유연한 프레임워크를 제공합니다.

출시된 제품은 판매 주문 문서에 대한 수익 인식을 지원하는 데 사용됩니다. 출시된 제품에는 수익 가격 및 수익 일정을 결정하는 데 필요한 설정이 포함되어 있습니다. 판매 주문은 시간 및 자재 프로젝트에서 시작될 수 있습니다.

회사는 수익 가격 기능을 사용하지 않고 수익 일정 기능을 사용할 수 있습니다. 따라서 판매 주문 라인의 가격은 수익 또는 이연 수익으로 사용됩니다. 판매 주문 라인에 수익 일정이 있는 경우 판매 주문 라인의 가격이 이연됩니다. 판매 주문 라인에 수익 일정이 없는 경우 송장이 발행될 때 판매 주문 라인의 가격이 수익 계정에 게시됩니다.

수익 가격은 판매 주문이 확정되거나 송장이 게시될 때 계산됩니다. 송장이 게시되기 전에 수익 가격을 미리 보려면 판매 주문을 확정해야 합니다.

판매 주문이 확정되면 판매 주문 라인에 수익 일정이 있는 경우 예상 수익 일정도 생성됩니다. 판매 주문이 청구되면 예상 수익 일정이 삭제되고 예상 수익 일정이 실제 수익 인식 일정으로 대체됩니다.

수익 인식 일정의 세부 정보는 판매 주문 라인별로 관리됩니다. 따라서 수익 인식 관리자는 세부 정보를 조회할 수 있고 계약상의 의무가 완료되면 수익 라인을 해제할 수 있습니다. 각 기간이 끝나면 수익 인식 관리자는 수익 분개장을 만들어 정의된 날짜 또는 그 이전에 만기가 되는 일정 라인을 해제할 수 있습니다. 이 수익 분개장은 즉시 게시되지 않습니다. 따라서 수익 인식 관리자는 이연 수익에서 실제 수익으로 정확한 금액이 전달되고 있음을 확인할 수 있습니다.

계약상의 변경으로 신규 판매 주문 라인이 기존 판매 주문이나 신규 판매 주문에 추가되는 경우 재할당 프로세스를 실행하여 판매 주문의 모든 라인에서 수익 가격을 수정할 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
