---
title: 서비스 주문 취소
description: 서비스 주문 자체에서 서비스 주문 또는 서비스 주문 라인을 취소하거나 정기 작업을 실행하여 여러 서비스 주문을 취소할 수 있습니다.
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
ms.openlocfilehash: cca6c34bb43702e2c33935a73dc24f1a630065c0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448429"
---
# <a name="cancel-service-orders"></a>서비스 주문 취소   

[!include [banner](../includes/banner.md)]


서비스 주문 자체에서 서비스 주문 또는 서비스 주문 라인을 취소하거나 정기 작업을 실행하여 여러 서비스 주문을 취소할 수 있습니다.


> [!NOTE]
> <P>서비스 주문 단계에서 취소가 허용되지 않거나 서비스 주문에 품목 요구 사항이 있거나 서비스 주문이 이미 게시된 경우 서비스 주문을 취소할 수 없습니다.</P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a>서비스 주문 양식에서 서비스 주문 취소

1.  **서비스 관리** \> **공통** \> **서비스 주문** \> **서비스 주문** 을 클릭합니다. 서비스 주문을 선택하고 작업 창에서 **주문 취소** 를 클릭합니다.

## <a name="cancel-a-service-order-line"></a>서비스 주문 라인 취소

1.  **서비스 관리** \> **공통** \> **서비스 주문** \> **서비스 주문** 을 클릭합니다. 취소할 라인이 포함된 서비스 주문을 두 번 클릭합니다.

2.  취소할 서비스 주문 라인을 선택한 다음 **주문 라인 취소** 를 클릭하여 라인 상태를 **취소됨** 으로 변경합니다.


> [!TIP]
> <P>서비스 주문 라인 취소를 취소하고 상태를 다시 <STRONG>생성됨</STRONG>으로 변경하려면 <STRONG>취소 되돌리기</STRONG>를 클릭합니다.</P>


## <a name="cancel-multiple-service-orders"></a>여러 서비스 주문 취소

1.  **서비스 관리** \> **정기** \> **서비스 주문** \> **서비스 주문 취소** 를 클릭합니다.

2.  **선택** 단추를 클릭합니다.

3.  **문의** 양식의 **기준** 열에서 취소하려는 서비스 주문을 선택합니다.

4.  **확인** 을 클릭하여 **문의** 양식을 닫습니다.

5.  **정보 로그 표시** 확인란을 선택하여 취소된 서비스 주문을 나열하는 정보 로그를 생성합니다.

6.  **취소됨** 상태의 서비스 주문을 되돌리려면 **취소 되돌리기** 확인란을 선택합니다.

7.  **확인** 을 클릭합니다.

선택한 서비스 주문이 취소되었거나 **최소됨** 의 진행 상태가 **진행 중** 으로 되돌려진 것입니다.


> [!NOTE]
> <P><STRONG>취소 되돌리기</STRONG> 확인란을 선택하면 <STRONG>취소됨</STRONG> 진행 상태의 서비스 주문이 되돌려지고 <STRONG>진행 중</STRONG> 진행 상태의 서비스 주문이 취소되지 않습니다.</P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]