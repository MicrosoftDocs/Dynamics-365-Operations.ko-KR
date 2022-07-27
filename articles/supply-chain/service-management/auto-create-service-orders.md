---
title: 자동으로 서비스 주문 생성하기
description: 서비스 계약의 유효 기간 동안 서비스 계약을 기반으로 하는 서비스 주문을 생성할 수 있습니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1acf4620556fe7ec5ae40f0a98b0a23602e2524a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447796"
---
# <a name="automatically-create-service-orders"></a>자동으로 서비스 주문 생성하기 

[!include [banner](../includes/banner.md)]


서비스 계약의 유효 기간 동안 서비스 계약을 기반으로 하는 서비스 주문을 생성할 수 있습니다.

서비스 계약에서 생성하는 서비스 주문은 모두 서비스 계약에 연결됩니다.

서비스 주문은 다음 설정에서 자동으로 생성됩니다.

  - 서비스 계약 라인에 설정된 서비스 계약 간격입니다. 서비스 계약 간격은 서비스 주문 라인이 생성되는 빈도를 나타냅니다. 자세한 내용은 [서비스 간격](service-intervals.md)을 참조하세요.

  - **서비스 주문 만들기** 양식의 **시작 날짜** 및 **종료 날짜** 필드에서 서비스 기간을 정의하는 기간. 자세한 내용은 [자동으로 서비스 주문 생성](create-service-orders-automatically.md)을 참조하세요.

  - 서비스 계약 헤더의 **서비스 주문 결합** 옵션. 이 옵션은 서비스 계약에서 생성된 서비스 주문 라인이 직원, 서비스 태스크, 서비스 객체 또는 서비스 계약에 따라 서비스 주문을 결합하는지 여부를 정의합니다. 자세한 내용은 [서비스 주문 결합](combine-service-orders.md)을 참조하세요.

  - 서비스 계약 라인의 **시간 창** 옵션. 시간 창은 계산된 날짜와 관련하여 서비스 주문 라인이 이동할 수 있는 정도를 정의합니다. 자세한 내용은 [시간 창](time-windows.md)을 참조하세요.


> [!NOTE]
> <P>서비스 주문에 대해 지정된 날짜가 <STRONG>서비스 관리 매개 변수</STRONG> 양식에서 선택한 달력에서 열리지 않는 경우 일정 충돌이 있음을 나타내는 메시지가 표시됩니다. 다음 메시지를 무시해도 됩니다. 달력에서 날짜가 닫혀 있어도 서비스 주문이 생성됩니다.</P>

## <a name="example-1"></a>예시 1

서비스 계약은 2012년 1월 1일부터 2012년 12월 31일까지 지속됩니다. **서비스 주문 생성** 양식에서 정의하는 서비스 기간이 2012년 11월 1일부터 2013년 2월 1일까지인 경우 서비스 주문은 2012년 11월 1일부터 2012년 12월 31일까지 생성됩니다.

## <a name="example-2"></a>예시 2

서비스 계약은 2012년 1월 1일부터 2012년 12월 31일까지 지속됩니다. 두 개의 서비스 계약 라인이 서비스 계약에 첨부됩니다. 첫 번째 서비스 계약 라인의 시작 날짜는 2012년 1월 2일이고 종료 날짜는 2012년 3월 1일입니다. 두 번째 서비스 계약 라인의 시작 날짜는 2012년 4월 1일이고 종료 날짜는 2012년 12월 31일입니다. **서비스 주문 생성** 양식에서 2012년 10월 1일부터 2012년 12월 31일까지의 기간을 지정합니다. 따라서 첫 번째 계약 라인의 시작 날짜와 종료 날짜가 서비스 주문에 대해 지정한 기간 이전이기 때문에 서비스 주문은 두 번째 계약 라인에 대해서만 생성됩니다.

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]