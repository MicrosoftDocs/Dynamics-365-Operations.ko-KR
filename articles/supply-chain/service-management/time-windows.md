---
title: 기간
description: 기간을 사용하여 서비스 주문 라인의 스케줄링을 최적화할 수 있습니다.
author: kamaybac
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a0ac2c038b76d64ff8d55708e57f7c3b88c3393
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448774"
---
# <a name="time-windows"></a>기간  

[!include [banner](../includes/banner.md)]

기간을 사용하여 서비스 주문 라인의 스케줄링을 최적화할 수 있습니다. 서비스 주문을 자동으로 생성하도록 시스템을 설정할 수 있습니다. 기간에서 지정한 기준에 따라 가능한 한 적은 서비스 주문에 최대한 많은 서비스 주문 라인을 연결할 수 있습니다.

기간은 서비스 주문 라인이 계산된 날짜에서 이동할 수 있는 거리를 지정합니다. 계산된 날짜는 서비스 주문 라인이 발생하도록 스케줄링된 날짜입니다. 날짜는 **서비스 주문 생성** 페이지에서 정의한 서비스 기간 및 간격 설정을 기반으로 합니다. 다음 표의 값을 사용하여 기간을 정의합니다.

| 메서드 | 설명                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 주   | 서비스 주문 라인을 초기 계산 일자와 같은 주의 개설 일자로 이동할 수 있는 일자입니다.                                                                                                                                                                                    |
| 개월  | 서비스 주문 라인을 초기 계산 일자와 같은 월의 개설 일자로 이동할 수 있는 일자입니다. 예를 들어 서비스 주문 라인의 계산 날짜는 2017년 2월 15일입니다. 서비스 주문 라인은 2017년 2월 1일에서 2월 28일 사이의 평일에 스케줄링할 수 있습니다. |
| 수동 | 서비스 주문 라인을 이동할 수 있는 최초 계산 일자 전후의 최대 일수를 정의합니다.                                                                                                                                                                           |

서비스 계약 라인에 대한 기간을 지정하지 않으면 서비스 계약에서 파생된 서비스 주문 라인은 원래 스케줄링된 정확한 일자에 있어야 합니다.

## <a name="related-topics"></a>관련 토픽

[기간 만들기](create-time-windows.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]