---
title: NMFC(National Motor Freight Classification) 코드
description: 이 항목에서는 Microsoft Dynamics 365 Supply Chain Management에서 NMFC(National Motor Freight Classification) 코드를 사용하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 04/22/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 8e6aac6b3a8b730b6adc5c3d4410b98c3e8d5090eac866c337ed1d03409ba765
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446791"
---
# <a name="national-motor-freight-classification-nmfc-codes"></a>NMFC(National Motor Freight Classification) 코드

[!include [banner](../includes/banner.md)]

NMFC(National Motor Freight Classification) 코드는 배송 가능한 항목을 분류하는 데 도움이 됩니다. NMFC 코드는 상품을 그룹화하는 데 사용되는 지정입니다. 이를 통해 운송 회사는 트럭 적합성, 적재 문제, 취급 문제 및 부패 가능성과 같은 고려 사항을 기반으로 항목을 분류하여 선적할 상품을 평가할 수 있습니다. 상품은 50에서 500까지의 숫자 범위를 사용하여 18개의 화물 등급 중 하나로 그룹화됩니다. 상품이 그룹화되는 클래스는 밀도, 적재 가능성, 취급 및 책임의 네 가지 운송 특성 평가를 기반으로 합니다. 그와 함께 이러한 특성은 상품의 운송성을 설정합니다.

NMFC 코드는 모든 LTL(적재량 미만) 배송 항목과 연결됩니다. 예를 들어 랩톱에는 2.5로 분류된 NMFC가 할당되고 전기 코드에는 65로 분류되는 NMFC가 할당될 수 있습니다.

이 기능은 작업자가 NMFC 코드를 사용하여 LTL 배송 항목을 분류하는 데 도움이 될 수 있습니다. 여기 예시들이 있습니다 :

- 회사가 선하증권(BOL)에 화물 설명을 포함하는 경우 운송업체는 화물이 무엇인지 알 수 있습니다. 많은 운송 회사가 운송하는 화물 유형에 전체 비즈니스 모델을 기반으로 하기 때문에 화물은 중요한 분류입니다.
- 이 분류는 주어진 부하의 비용을 결정하는 데 사용되기 때문에 회사에 필수적일 수 있습니다.
- 회사는 LTL 물류 및 운송 회사의 수익성을 파악할 수 있습니다.

이 항목에서는 Microsoft Dynamics 365 Supply Chain Management에서 NMFC 코드를 사용하는 방법에 대해 설명합니다.

## <a name="prerequisites"></a>전제 조건

NMFC 코드를 생성하기 전에 매핑해야 하는 모든 LTL 화물 클래스를 설정해야 합니다. LTL 화물 등급은 항목 범주를 나타내는 반면 NMFC 코드는 18개 화물 등급 각각의 특정 상품과 관련됩니다. LTL 클래스로 작업하는 방법에 대한 자세한 내용은 [트럭 적재량(LTL) 등급 미만](ltl-class.md)을 참조하세요.

## <a name="create-an-nmfc-code"></a>NMFC 코드 생성

NMFC 코드를 생성하려면 다음 단계를 따르십시오.

1. 다음 단계 중 하나를 따르십시오.

    - **창고 관리 \> 설정 \> 재고 \> NMFC 코드** 로 이동합니다.
    - **운송 관리 \> 설정 \> 운송 기준 \> NMFC 코드** 로 이동합니다.

1. **새로 만들기** 를 선택하여 NMFC 코드를 생성합니다. 그런 후에 다음 필드를 설정합니다.

    - **NMFC 코드** – 상품 유형에 대한 NMFC 코드를 입력합니다.
    - **이름** - NMFC 코드에 대한 이름을 입력합니다.
    - **LTL 클래스** – NMFC 코드와 연결된 LTL 클래스를 선택합니다.
    - **BOL 취급 단위** – 배송의 기본 취급 유형을 정의합니다.

## <a name="example-set-up-nmfc-codes"></a>예: NMFC 코드 설정

다음 예는 서로 다른 제품에 사용할 수 있는 두 개의 서로 다른 NMFC 코드를 설정하는 방법을 보여줍니다.

1. **창고 관리 \> 설정 \> 재고 \> NMFC 코드** 로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. 새 줄에서 다음 값을 설정합니다.

    - **NMFC 코드:** *92.5*
    - **이름:** *컴퓨터*
    - **LTL 클래스:** *92.5*
    - **BOL 취급 단위:** *단위*

1. 작업 창에서 **저장** 을 선택합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. 새 줄에서 다음 값을 설정합니다.

    - **NMFC 코드:** *125*
    - **이름:** *전화*
    - **LTL 클래스:** *125*
    - **BOL 취급 단위:** *단위*

1. 작업 창에서 **저장** 을 선택합니다.

## <a name="additional-resources"></a>추가 리소스

- [트럭 적재량(LTL) 등급 미만](ltl-class.md)
- [선하증권 작성](create-bill-of-lading.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
