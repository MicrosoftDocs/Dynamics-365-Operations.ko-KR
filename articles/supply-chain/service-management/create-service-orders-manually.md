---
title: 수동으로 서비스 주문 만들기
description: 서비스 계약을 사용하거나 서비스 주문 양식을 사용하여 **서비스 주문** 을 수동으로 만들 수 있습니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1fad4abcf39021f94db50c07a39803af31f85c2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449152"
---
# <a name="create-service-orders-manually"></a>수동으로 서비스 주문 만들기    

[!include [banner](../includes/banner.md)]


서비스 계약을 사용하거나 서비스 주문 양식을 사용하여 **서비스 주문** 을 수동으로 만들 수 있습니다. 프로젝트에서 서비스 주문을 생성할 수도 있습니다.

> [!TIP]
> <P>자동화된 절차를 사용하여 서비스 주문을 생성할 수 있습니다. 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a>서비스 계약에서 수동으로 서비스 주문 만들기

1.  **서비스 관리** \> **공통** \> **서비스 계약** \> **서비스 계약** 을 선택합니다.

2.  서비스 계약을 선택하거나 새 서비스 계약을 생성합니다.

3.  **배달** 탭을 선택하고 **만들기** 그룹에서 **계획된 서비스 주문** 을 선택하여 **서비스 주문 만들기** 양식을 엽니다.

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a>서비스 주문 양식에서 수동으로 서비스 주문 만들기

1.  **서비스 관리** \> **공통** \> **서비스 주문** \> **서비스 주문** 을 선택합니다.

2.  **새로 만들기** 를 선택하여 새 서비스 주문을 만듭니다.

3.  서비스 주문에 대한 서비스 주문 라인을 생성합니다.

> [!NOTE]
> <P><STRONG>서비스 관리 매개 변수</STRONG> 양식에서 <STRONG>서비스 계약 없이 허용</STRONG> 체크박스를 선택한 경우 서비스 계약에 서비스 주문을 첨부하지 않고 서비스 주문 라인에서 트랜잭션을 게시할 수 있습니다. 체크박스가 선택 취소된 경우 서비스 주문 라인을 전기하기 전에 수동으로 생성된 서비스 주문을 프로젝트에 첨부해야 합니다.</P>

## <a name="create-a-service-order-from-a-project"></a>프로젝트에서 서비스 주문 만들기

1.  **프로젝트 관리 및 회계** \> **공통** \> **프로젝트** \> **모든 프로젝트** 로 이동합니다.

2.  **프로젝트** 양식에서, **작업** 창에서, **관리** 탭 \> **서비스** \> **서비스 주문** 을 클릭합니다.

3.  **서비스 주문** 양식에서 서비스 주문을 수동으로 생성하려면 이전 절차를 따르세요. **프로젝트 ID** 필드에는 프로젝트 참조가 표시됩니다.

> [!NOTE]
> <P><STRONG>서비스 관리 매개 변수</STRONG> 양식에서 <STRONG>서비스 계약 없이 허용</STRONG> 체크박스를 선택한 경우 서비스 계약에 서비스 주문을 첨부하지 않고 서비스 주문 라인에서 트랜잭션을 게시할 수 있습니다. 체크박스가 선택 취소된 경우 서비스 주문 라인을 전기하기 전에 수동으로 생성된 서비스 주문을 프로젝트에 첨부해야 합니다.</P>

## <a name="create-a-service-order-from-the-sales-order-form"></a>판매 주문 양식에서 서비스 주문 만들기

**판매 주문을 기반으로 새 서비스 주문 만들기** 마법사를 사용하여 **판매 주문** 양식에서 서비스 주문을 생성할 수 있습니다.

1.  **영업 및 마케팅** \> **공통** \> **판매 주문** \> **모든 판매 주문** 으로 이동합니다.

2.  관련 판매 주문을 엽니다.

3.  **판매 주문** 탭에서 **서비스 주문** 을 선택하여 **판매 주문을 기반으로 새 서비스 주문 만들기** 마법사를 시작합니다.

4.  **다음 \>을 선택** 한 후 **서비스 주문에 대한 계약 선택** 페이지에서 다음 단계를 완료합니다.
    
      - **서비스 계약** 필드를 사용하여 새 서비스 주문을 연결해야 하는 서비스 계약을 선택합니다.
    
      - 선택 사항: **프로젝트 ID** 필드를 사용하여 이 서비스 주문을 특정 프로젝트와 연결합니다.

5.  **다음 \>을 선택** 한 후 **서비스 주문 만들기** 페이지에서 다음 단계를 완료합니다.
    
      - **기본 서비스 시간** 필드에 서비스 호출을 시작할 날짜와 시간을 입력합니다.
    
      - 선택 사항: **설명** 필드의 텍스트를 수정합니다. 기본적으로 이 필드에는 이전 페이지에서 선택한 서비스 계약에 대한 설명이 포함됩니다.
    
      - **담당** 필드에서 계약을 담당하는 직원의 ID를 선택하고, 그것이 무엇인지 알고 있는 경우 서비스 호출에 대해 고객이 선호하는 기술자의 ID를 입력합니다.
    
      - **연락처 ID** 필드에서 이 서비스 주문과 관련하여 연락해야 하는 고객 회사의 사람을 선택합니다.

6.  **다음 \>을 선택** 한 후 **마침** 을 선택합니다.


## <a name="see-also"></a>참고 항목

[서비스 주문](service-orders.md)

[자동으로 서비스 주문 생성하기](create-service-orders-automatically.md)

[서비스 주문 생성하기(기존 양식)](https://technet.microsoft.com/library/aa553901\(v=ax.60\)) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]