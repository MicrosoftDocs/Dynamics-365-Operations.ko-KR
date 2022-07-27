---
title: 반품 접수증 등록
description: 도착 개요 양식 또는 등록 양식을 사용하여 반품된 품목의 영수증을 등록할 수 있습니다.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3a1dc18e50dd10568c719c4f87d805be526d6746
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448906"
---
# <a name="register-the-receipt-of-returned-items"></a>반품 접수증 등록 

[!include [banner](../includes/banner.md)]


반품 접수는 2가지 방법이 있습니다. 첫 번째 방법은 **도착 개요** 양식을 사용하는 창고 입고 절차입니다. 두 번째는 **등록** 양식을 사용합니다.

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a>도착 개요 양식에 반품 영수증을 등록하세요.

**도착 개요** 양식을 사용하여 RMA(반품 원자재 승인) 번호로 반품 발송물을 식별할 수 있습니다. **설정** 탭에서 분개 이름을 정의하고 **도착 개요** 양식에서 선택한 라인에 해당하는 분개 라인이 있는 경우 **도착 시작** 을 클릭하면 새 분개 머리글이 생성됩니다.

1.  **재고 관리** \> **정기** \> **도착 개요** 를 클릭합니다.

2.  **설정 이름** 필드에서 **반품 주문** 을 선택한 다음 **업데이트** 를 클릭합니다.
    

    > [!TIP]
    > <P><STRONG>범위</STRONG> 필드를 사용하여 검색 결과를 좁힐 수 있습니다. 정확한 결과를 보려면 <STRONG>RMA 번호</STRONG> 필드에 RMA 번호를 입력하거나 선택할 수 있습니다. 표시되는 수신 도착을 제한하는 필터 세트를 정의하고 저장하려면 <STRONG>설정</STRONG> 탭을 클릭하세요. 사용 가능한 필터에는 유형, 창고 및 선착장이 포함됩니다.</P>

    

    > [!WARNING]
    > <P>반품 주문은 <STRONG>도착 개요</STRONG> 양식에서 다른 도착 유형과 혼합할 수 없습니다. 따라서 참조는 항상 판매 주문이지만 분개 헤더에는 판매 주문 ID가 지정되지 않습니다.</P>



3.  **수신** 그리드에서 반환되는 품목과 일치하는 라인을 찾은 다음 **도착 선택** 열에서 확인란을 선택합니다.

4.  반품 배송에 포함되지 않은 원래 주문 품목과 같이 반품 영수증에서 특정 라인을 제외하려면 양식 하단의 **라인** 테이블에서 연관된 **도착 선택** 확인란을 선택 취소합니다.

5.  **도착 시작** 버튼을 클릭하여 도착 분개를 생성합니다.
    

    > [!NOTE]
    > <P>여러 반품 주문을 선택하고 단일 도착 절차에 모두 포함할 수 있습니다. 각 반품 주문 라인은 해당 품목 도착 분개 라인으로 복사됩니다.</P>

    

    > [!NOTE]
    > <P>품목 도착 양식을 사용하여 수동으로 <STRONG>도착 분개</STRONG>를 작성할 수도 있습니다. 



6.  **재고 관리** \> **분개** \> **품목 도착** \> **품목 도착** 을 클릭합니다.

7.  방금 생성한 도착 분개를 선택한 다음 **라인** 을 눌러 **분개 라인, 위치** 양식을 엽니다.

8.  **일반** 탭에서 필요한 경우 **수량** 필드의 숫자를 조정한 다음 **처분 코드** 필드에 처분 코드를 지정합니다.
    
    또는 **격리 관리** 확인란을 선택하여 격리 명령의 컨텍스트에서 검사 절차를 통해 반품된 품목을 보낼 수 있습니다.
    

    > [!NOTE]
    > <P>격리를 통해 반품된 제품을 보내는 경우 폐기 코드를 지정할 수 없습니다.</P>



9.  **검증** 버튼을 클릭합니다.

10. 검증 절차에 오류가 없으면 **전기** 를 클릭합니다.

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a>반품 접수증을 등록 양식에 등록

**도착 개요** 양식을 사용하는 대신 **등록** 양식을 사용하여 반품된 품목의 도착을 등록할 수 있습니다.

1.  **영업 및 마케팅** \> **공통** \> **반품 주문** \> **모든 반품 주문** 을 클릭합니다. 새 반품 주문을 생성하거나 목록에서 반품 주문을 엽니다. **라인** 빠른 탭에서 반품 주문 라인을 선택합니다. **업데이트 라인** 을 클릭한 다음 **등록** 을 클릭합니다.

2.  **처분 코드** 필드에 처분 코드를 할당한 다음 **확인** 을 클릭합니다.
    

    > [!NOTE]
    > <P><STRONG>등록</STRONG> 양식을 사용하여 격리 명령으로 검사 품목을 보낼 수 없습니다.</P>



3.  **트랜잭션** 그리드에서 등록할 트랜잭션을 선택합니다.

4.  **지금 등록** 그리드에서 **추가** 를 클릭합니다. 반환된 모든 품목이 **지금 등록** 그리드에 나타날 때까지 이전 두 단계를 반복합니다.

5.  **모두 전기** 를 클릭합니다.

## <a name="see-also"></a>참고 항목

[도착 개요(양식)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]