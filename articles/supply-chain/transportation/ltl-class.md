---
title: 트럭 적재량(LTL) 등급 미만
description: 이 토픽에서는 LTL(적은 화물) 클래스가 무엇인지 설명하고 Microsoft Dynamics 365 Supply Chain Management에서 이를 설정하는 방법을 설명합니다.
author: Henrikan
ms.date: 04/05/2021
ms.topic: article
ms.search.form: WHSLTLClass
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 4349e649e48e5103a53a5e6ab332d127fd1de27aa7b06953533198d3928d250a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447343"
---
# <a name="less-than-truckload-ltl-classes"></a>트럭 적재량(LTL) 등급 미만

[!include [banner](../includes/banner.md)]

LTL(미량 화물 운송) 등급은 배송할 수 있는 품목을 분류하는 데 사용되는 화물 운송 등급입니다. 일반적으로 모든 유형의 제품 또는 상품에는 LTL 배송에 대한 특정 화물 등급 번호에 해당하는 NMFC(National Motor Freight Classification) 코드가 있습니다. LTL 화물 등급은 항목 범주를 나타내는 반면 NMFC 코드는 18개 화물 등급 각각의 특정 상품과 관련됩니다.

이 기능을 사용하면 시스템을 사용하여 다음 작업을 수행할 수 있습니다.

- 회사에서 사용되는 LTL 화물 등급을 정의합니다.
- **NMFC 코드** 페이지에서 각 LTL 클래스를 NMFC 코드에 할당합니다. 자세한 내용은 [NMFC(National Motor Freight Classification) 코드](nmfc-codes.md)를 참조하세요.
- **제품** 페이지에서 각 제품에 NMFC 코드(및 관련 LTL 코드)를 할당합니다.
- NMFC 코드가 할당된 각 제품의 LTL 클래스를 정확하게 평가합니다.
- 국제 LTL 표준을 확인하여 각 LTL 클래스에 대한 포장 요구 사항을 결정합니다. 이러한 방식으로 제품을 잘 보호하고 안전하게 배송할 수 있습니다.
- 각 제품의 LTL 화물 등급을 기반으로 정확한 배송 견적을 받으세요.

이 항목에서는 Microsoft Dynamics 365 Supply Chain Management에서 LTL 클래스를 만드는 방법에 대해 설명합니다.

## <a name="create-an-ltl-class"></a>LTL 클래스 생성

LTL 클래스를 만들려면 다음 단계를 따르세요.

1. 다음 단계 중 하나를 따르십시오.

    - **창고 관리 \> 설정 \> 재고 \> LTL 클래스** 로 이동합니다.
    - **운송 관리 \> 설정 \> 운송 기준 \> LTL 클래스** 로 이동합니다.

2. 작업 창에서 **새로 만들기** 를 선택하여 LTL 클래스를 생성합니다. 그런 후에 다음 필드를 설정합니다.

    - **LTL 클래스** – 상품 유형에 대한 회사의 내부 LTL 클래스 식별자(ID)를 입력합니다. 대부분의 회사는 국제 표준을 사용합니다. 이 경우 이 필드의 값은 **클래스** 필드의 값과 일치합니다. 그러나 회사에서 자체 표준을 사용하는 경우 해당 표준을 준수하는 코드를 입력합니다.
    - **이름** – 귀하와 다른 사용자가 각 NMFC 코드에 대한 올바른 LTL 클래스를 선택하는 데 도움이 되는 설명적인 이름을 입력합니다.
    - **클래스** – 상품 유형에 대한 국제 표준 LTL 클래스 ID를 입력합니다. 여기에 입력하는 코드는 공식 표준을 준수해야 합니다.

## <a name="example-set-up-ltl-classes"></a>예: LTL 클래스 설정

다음 예는 서로 다른 유형의 제품에 사용할 수 있는 두 개의 서로 다른 LTL 클래스를 설정하는 방법을 보여줍니다.

1. **창고 관리 \> 설정 \> 재고 \> LTL 클래스** 로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. 새 줄에서 다음 값을 설정합니다.

    - **LTL 클래스:** *92.5*
    - **이름:** *컴퓨터, 모니터, 냉장고*
    - **클래스:** *92.5*

1. 작업 창에서 **저장** 을 선택합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. 새 줄에서 다음 값을 설정합니다.

    - **LTL 클래스:** *125*
    - **이름:** *소형 가전*
    - **클래스:** *125*

1. 작업 창에서 **저장** 을 선택합니다.

## <a name="additional-resources"></a>추가 리소스

- [NMFC(National Motor Freight Classification) 코드](nmfc-codes.md)
- [선하 증권 만들기](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
