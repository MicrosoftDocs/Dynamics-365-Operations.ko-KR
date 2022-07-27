---
title: 서비스 주문에 주소 추가
description: 이 항목에서는 서비스 주문에 고객 주소를 추가하는 방법에 대해 설명합니다.
author: kamaybac
ms.date: 05/02/2018
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
ms.openlocfilehash: 055903628b2d72f420415bae5c72d0c7d9d57cba
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448609"
---
# <a name="add-an-address-to-a-service-order"></a>서비스 주문에 주소 추가    

[!include [banner](../includes/banner.md)]


이 항목에서는 서비스 주문에 고객 주소를 추가하는 방법에 대해 설명합니다. 서비스 주문을 생성하면 서비스 주문이 첨부된 프로젝트에서 주소 정보가 전송됩니다. 그러나 고객, 공급업체, 사이트, 창고, 서비스 주문 및 프로젝트에 대해 Microsoft Dynamics AX에 이미 입력된 주소에서 대체 위치를 선택할 수 있습니다.

새 주소를 만들 수도 있습니다. 기본적으로 새 주소는 프로젝트로 전송됩니다. 그러나 새 주소가 이 서비스 인스턴스에만 관련되도록 지정할 수 있습니다. 그렇게 하면 새 주소가 프로젝트로 전송되지 않습니다.

## <a name="create-a-customer-address-for-a-service-order"></a>서비스 주문에 대한 고객 주소 생성

서비스 주문에 주소를 추가하려면 다음 단계를 따르세요.

1.  **서비스 관리** \> **공통** \> **서비스 주문** \> **서비스 주문** 을 클릭합니다.

2.  주소를 생성할 서비스 주문을 엽니다.

3.  **작업 창** 에서 **편집** 을 클릭한 다음 **헤더 보기** 를 클릭합니다.

4.  **주소** 빠른 탭에서 **주소 추가** 를 클릭합니다.

5.  **새 주소** 양식에서 주소의 고유한 이름을 입력하고 나머지 필드를 작성합니다. 
    

    > [!WARNING]
    > <P>기존 주소와 동일한 이름을 입력하면 나머지 필드에 입력한 정보가 기존 주소에 대한 정보를 덮어씁니다.</P>


6.  **확인** 을 클릭하여 새 주소를 서비스 주문에 복사합니다.

## <a name="specify-an-alternative-address-on-a-service-order"></a>서비스 주문에 대체 주소 지정

서비스 주문에 대체 주소를 추가하려면 다음 단계를 따르세요.

1.  **서비스 관리** \> **공통** \> **서비스 주문** \> **서비스 주문** 을 클릭합니다.

2.  대체 주소를 입력할 서비스 주문을 엽니다.

3.  **작업 창** 에서 **편집** 을 클릭한 다음 **헤더 보기** 를 클릭합니다.

4.  **주소** 빠른 탭에서 **다른 주소** 를 클릭합니다.

5.  **주소 선택** 양식에서 **레코드 유형** 필드의 **서비스 주문** 을 선택합니다.

6.  주소를 선택한 다음 **확인** 을 클릭하여 서비스 주문에 복사합니다.


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]