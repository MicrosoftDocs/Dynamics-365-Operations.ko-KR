---
title: 신용 카드 설정, 승인 및 캡처
description: 이 문서에서는 Microsoft Dynamics 365 Finance의 신용 카드 승인에 대한 개요를 제공합니다. 여기에는 지불 서비스를 설정하고 판매 주문에 신용 카드를 추가하고 승인을 무효화하는 방법에 대한 정보가 포함됩니다.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 932949f31cbc4e4e8c07a2e489b8a0848843c54ad8d27d5d77f2b7031c68c30a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450742"
---
# <a name="credit-card-setup-authorization-and-capture"></a>신용 카드 설정, 승인 및 캡처

[!include [banner](../includes/banner.md)]

이 문서에서는 Microsoft Dynamics 365 Finance의 신용 카드 승인에 대한 개요를 제공합니다. 여기에는 지불 서비스를 설정하고 판매 주문에 신용 카드를 추가하고 승인을 무효화하는 방법에 대한 정보가 포함됩니다.

## <a name="setting-up-the-credit-card-payment-service"></a>신용 카드 지불 서비스 설정

신용 카드를 사용하려면 지불 서비스 페이지에서 지불 서비스를 설정하고 활성화해야 합니다. 지불 서비스는 법인과 고객의 신용 카드 요금을 처리하는 은행 간의 다리 역할을 합니다. 지불 커넥터 필드에 나열된 신용 카드 제공업체와 협력하고 해당 제공업체에 계정을 설정해야 합니다. 그런 다음 지불 서비스 페이지에서 다른 옵션을 설정하고 신용 카드 유형 페이지에서 American Express, Discover, MasterCard 및 Discover에 대한 신용 카드 유형을 설정하고 공급자를 기본 공급자로 활성화해야 합니다. 또한 설정을 완료하려면 다음 단계를 따라야 합니다.
-   수취 계정 매개 변수 페이지에서 신용 카드 승인을 사용하기 위한 매개 변수를 지정합니다.
-   지불 조건 페이지에서 신용 카드 지불 조건을 설정합니다. 지불 유형 필드에서 신용 카드를 선택하십시오.
-   고객 신용 카드 페이지에서 고객의 신용 카드 정보를 입력합니다.

## <a name="adding-a-new-credit-card"></a>새 신용 카드 추가
고객, 설정, 신용 카드를 사용하여 고객 페이지에서 새 신용 카드 레코드를 만들 수 있습니다. 관리, 고객, 신용카드, 등록을 사용하여 판매 주문 페이지에서 판매 주문을 입력할 때 신용 카드 레코드를 만들 수도 있습니다.

## <a name="adding-a-credit-card-to-a-sales-order"></a>판매 주문에 신용 카드 추가

판매 주문 페이지의 가격 및 할인 빠른 탭에서 신용 카드 조회의 신용 카드를 선택하여 판매 주문에 신용 카드를 추가할 수 있습니다. 인증 프로세스를 시작하려면 작업 창의 관리 탭에서 신용 카드 및 인증를 선택합니다.

## <a name="authorizing-a-credit-card"></a>신용 카드 인증

신용 카드가 인증되면 카드 번호와 카드 소지자의 이름을 확인하고 사용 가능한 신용 잔액을 확인합니다. 선택적으로 카드 인증 값(CVV)과 카드 소지자의 주소가 검증됩니다. 그러면 고객의 사용 가능한 신용 잔액이 송장 금액만큼 줄어듭니다. 지불 서비스는 신용 카드가 승인 또는 거부되었다는 정보를 보냅니다. 판매 주문이 송장 처리되면 송장 금액이 신용 카드로 청구(캡처)됩니다.

### <a name="card-verification-value"></a>카드 인증 값(CVV)

카드의 보안 코드라고도 하는 카드 인증 값을 요구할 수 있습니다. American Express의 경우 이는 4자리 값입니다. Discover, MasterCard 및 Visa의 경우 세 자리 값입니다.

### <a name="address-verification"></a>주소 확인

주소 확인 정보는 항상 지불 제공자에게 전송됩니다. 거래를 수락하는 데 필요한 정보의 양을 결정할 수 있습니다. 이 정보를 수락하는지 여부를 확인하려면 공급자에게 확인하십시오. 주소 확인 옵션은 다음과 같습니다.
-   **항상 거래 수락** – 주소 확인 결과와 상관없이 거래를 수락합니다.
-   **계정 소유자** – 거래에서 카드 소지자의 이름과 신용 카드 회사의 정보를 비교합니다.
-   **청구 주소** – 거래에서 카드 소지자의 이름과 청구 주소를 신용 카드 회사의 정보와 비교합니다.
-   **청구 우편번호** – 거래에서 카드 소지자의 이름, 청구 주소 및 우편번호를 신용 카드 회사의 정보와 비교합니다.

## <a name="data-support"></a>데이터 지원
지원되는 각 신용 카드 유형에 대해 데이터 지원 레벨을 지정할 수 있습니다. 레벨은 거래에 대한 정보가 지불 서비스로 전송되는 양을 제어합니다. 공급자에게 이 정보를 제공할 수 있는지 확인하십시오. 데이터 지원 레벨에 대한 옵션은 다음과 같습니다.
-   **레벨 1** – 거래 일자, 거래 금액, 내용을 전송합니다.
-   **레벨 2** – 레벨 1 정보, 배송 및 판매자 주소, 세금 정보를 전송합니다.
-   **레벨 3** – 레벨 2 정보와 주문 라인 정보를 전송합니다.

## <a name="partial-payments"></a>부분 지불
주문의 일부를 배송하는 경우 부분 주문 금액이 캡처되고 전체 주문 금액에 대한 승인이 닫힙니다. 그런 다음 배송되지 않은 주문의 나머지 금액에 대해 새로운 인증이 제출됩니다.

## <a name="voiding-an-authorization"></a>인증 무효화
신용 카드 인증을 무효화하려면 지불 방법을 신용 카드 유형이 없는 다른 방법으로 변경할 수 있습니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]