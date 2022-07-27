---
title: 서비스 주문 단계
description: 서비스 주문의 단계를 정의하고 작업자에게 할당하여 서비스 조직에서 다양한 사람들이 수행하는 작업을 통해 서비스 주문의 흐름을 제어합니다.
author: kamaybac
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a43cbe0cf5993a305ff500f34f0da5d3763084c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448897"
---
# <a name="service-order-stages"></a>서비스 주문 단계   

[!include [banner](../includes/banner.md)]


서비스 주문에 대한 단계를 설정하여 완료해야 하는 작업, 완료되는 순서 및 완료를 책임지는 작업자를 정의할 수 있습니다. 서비스 주문의 단계를 정의하고 작업자에게 할당하여 서비스 조직에서 다양한 사람들이 수행하는 작업을 통해 서비스 주문의 흐름을 제어할 수 있습니다. 단계의 순서에는 초기 단계가 포함되어야 합니다.

또한 각 단계에서 허용되는 작업을 정의할 수 있습니다. 예를 들어, 최종 단계를 제외한 모든 단계에 대해 **게시** 확인란의 선택을 취소하면 전체 단계 시퀀스를 통해 서비스 주문이 처리되기 전에 서비스 주문이 게시되지 않습니다.

## <a name="branching-in-service-order-stages"></a>서비스 주문 단계에서 분기

서비스 단계를 설정할 때 다음 서비스 단계에서 선택할 여러 옵션 또는 분기를 만들 수 있습니다. 생성한 모든 분기는 초기 단계가 완료되면 선택할 수 있습니다. 예를 들어 **계획** 을 초기 단계로 설정합니다. **처리 중** 및 **취소** 라는 두 단계를 생성한 다음 **계획** 을 상위 단계로 선택합니다. 판매 주문에 **계획** 단계를 지정합니다. 판매 주문에 대한 계획 단계가 완료된 경우 판매 주문이 작업할 준비가 되었으면 **진행 중** 단계를 선택하고 판매 주문이 취소된 경우 **취소** 단계를 선택할 수 있습니다.

## <a name="see-also"></a>참고 항목

[서비스 주문 단계 설정](set-up-service-order-stages.md)

[서비스 주문 단계 변경](change-service-order-stage.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]