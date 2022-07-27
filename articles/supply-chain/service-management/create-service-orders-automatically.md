---
title: 자동으로 서비스 주문 생성하기
description: 하나의 서비스 계약 또는 여러 서비스 계약에 대한 서비스 주문을 생성할 수 있습니다.
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
ms.openlocfilehash: 8fc63a720dd06c85be17ca61de1fe7c25f1cf3f7
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448426"
---
# <a name="create-service-orders-automatically"></a>자동으로 서비스 주문 생성하기    

[!include [banner](../includes/banner.md)]


하나의 서비스 계약 또는 여러 서비스 계약에 대한 서비스 주문을 생성할 수 있습니다. 생성되면 서비스 주문 양식에서 **서비스 주문** 을 볼 수 있습니다.

서비스 주문은 서비스 계약의 유효 기간 동안만 생성됩니다. **서비스 주문 생성** 양식에 지정하는 간격이 서비스 계약의 시작 날짜 이전 또는 종료 날짜 이후인 경우 서비스 계약 날짜 내에 있는 간격 부분에 대해서만 서비스 주문이 생성됩니다.

서비스 계약 라인에서 서비스 주문을 수동 또는 자동으로 생성할 때 라인에 종료 일자를 지정하지 않는 한 서비스 주문은 라인의 시작 및 종료 일자로 정의된 시간 간격에 있어야 합니다.

## <a name="create-service-orders-automatically-for-a-service-agreement"></a>서비스 계약에 대한 서비스 주문 자동 생성

1.  **서비스 관리** \> **공통** \> **서비스 계약** \> **서비스 계약** 을 클릭합니다.

2.  서비스 계약을 선택합니다.

3.  **배달** 탭을 클릭한 다음 **계획된 서비스 주문** 을 클릭합니다.

4.  서비스 기간을 정의하려면 **시작 날짜** 및 **종료 날짜** 필드에 날짜를 지정합니다.

5.  **정보 로그 표시** 확인란을 선택하여 생성된 서비스 주문 목록을 표시합니다.

6.  **트랜잭션 유형 포함** 필드 그룹에서 트랜잭션 유형을 선택합니다. 트랜잭션 유형은 서비스 계약에 생성된 라인을 나타내며, 선택한 각 트랜잭션 유형은 서비스 계약 라인에 지정된 서비스 간격에 따라 여러 서비스 주문을 생성합니다.

7.  연속 서비스 주문에서 누락된 서비스 주문을 생성하려면 **연속** 확인란을 선택합니다.

8.  **확인** 을 클릭합니다.

## <a name="create-service-orders-automatically-for-several-service-agreements"></a>여러 서비스 계약에 대해 자동으로 서비스 주문 생성

1.  **서비스 관리** \> **정기** \> **서비스 주문** \> **서비스 주문 생성** 을 클릭합니다.

2.  서비스 주문을 생성하는 데 사용할 기준을 추가하거나 제거하려면 **선택** 을 클릭합니다.

3.  **확인** 을 클릭합니다.

## <a name="see-also"></a>참고 항목

[서비스 주문](service-orders.md)

[자동으로 서비스 주문 생성하기](auto-create-service-orders.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]