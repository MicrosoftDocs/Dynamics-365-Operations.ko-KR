---
title: 측정 단위 및 재고 정책
description: 이 문서에서는 창고 프로세스에서 기본 단위, 단위 순서 및 단위 변환이 사용되는 방법을 설명합니다.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetails, EcoResProductDetailsExtended, EcoResStorageDimensionGroup, InventItemOrderSetup, UnitOfMeasureConversion, WHSRFMenuItem, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 29611
ms.assetid: 4b5ca875-9a06-416d-9ac0-cc3ab8f7338e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0de12620bca54c7e43713138d7a152c2bd6edff3453f81cf779f9b875cf77eb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446644"
---
# <a name="unit-of-measure-and-stocking-policies"></a>측정 단위 및 재고 정책

[!include [banner](../includes/banner.md)]

이 문서에서는 창고 프로세스에서 기본 단위, 단위 순서 및 단위 변환이 사용되는 방법을 설명합니다.

단위 시퀀스 그룹은 창고 작업에 사용할 수 있는 단위 시퀀스를 정의합니다. **단위 시퀀스 그룹** 페이지에서 생성됩니다. 시퀀스는 다양한 단위의 관계를 보여줍니다. 예를 들어, 개별 품목이 들어 있는 상자가 들어 있는 팔레트를 보관합니다. 이 경우 세 가지 다른 단위와 계층의 논리적 순서를 제공해야 합니다. 단위 시퀀스 그룹을 사용하면 번호판 그룹화에 대한 정책과 다양한 창고 프로세스에 사용해야 하는 기본 단위를 정의할 수 있습니다. 이 문서는 창고 관리에서 사용할 수 있는 고급 창고 솔루션과 재고 관리에서 사용할 수 있는 보다 기본적인 창고 솔루션 모두에 적용됩니다.

## <a name="unit-sequence-groups-for-released-products"></a>출시 제품의 단위 시퀀스 그룹
출시된 제품을 창고 작업 프로세스에서 사용하려면 해당 제품에 단위 시퀀스 그룹을 지정해야 합니다. 재고 규모 그룹과 연결된 제품의 유효성을 검사하고 재고 규모 그룹에 대한 **창고 관리 프로세스 사용** 옵션이 **예** 로 설정된 경우 제품에 대해 단위 시퀀스 그룹 ID가 정의되지 않은 경우 오류 메시지가 수신됩니다. 사용하는 단위 시퀀스 그룹에 여러 줄(따라서 여러 단위)이 포함된 경우 단위 간에 단위 변환을 설정해야 합니다. **단위 변환** 페이지에서 이 설정을 완료합니다. 릴리스된 제품과 연결하는 시퀀스 그룹의 가장 작은 단위는 해당 제품에 대해 정의된 재고 단위와 일치해야 합니다. 재고 단위는 현재고의 기본 계산에 사용되는 단위입니다. **측정 단위 변환 활성화** 옵션을 사용하여 제품 마스터의 제품 변형에 대한 측정 단위 변환을 설정할 수도 있습니다.

## <a name="license-plate-grouping"></a>번호판 그룹
하나보다 적거나 많은 특정 단위의 영수증을 하나의 번호판으로 그룹화해야 하는지 아니면 각 장치에 대한 번호판으로 나누어야 하는지 지정할 수 있습니다. 이 동작을 설정하려면 **단위 시퀀스 그룹** 페이지의 **라인 세부 정보** 탭에서 **번호판 그룹화** 옵션을 사용합니다. 모바일 디바이스로 작업을 처리할 때 번호판 그룹화를 사용하려면 **모바일 디바이스** 메뉴 항목에서 **번호판 그룹화** 옵션을 선택해야 합니다. 예를 들어, 모바일 디바이스를 사용하여 두 줄이 있는 단위 시퀀스 그룹과 연결된 항목을 등록합니다. 첫 번째 줄은 조각용이고 **번호판 그룹화** 옵션은 **예** 로 설정되어 있습니다. 두 번째 줄은 팔레트 단위이고 **번호판 그룹화** 옵션은 **아니요** 로 설정되어 있습니다. 이 경우 시스템은 100개당 번호판 분할 및 생성을 자동으로 안내할 수 있습니다.

## <a name="units-for-cycle-counting"></a>순환 재고 단위
주기 실사 프로세스의 일부로 사용할 단위를 정의하려면 **단위 시퀀스 그룹** 페이지에서 **순환 재고에 단위 사용** 옵션을 선택합니다. 시퀀스 그룹에서 최대 4가지 단위를 선택할 수 있습니다. 단위를 4가지 이상 선택하면 추가 단위가 모바일 디바이스에 표시되지 않습니다.

## <a name="default-units-for-mobile-device-receiving-processes"></a>모바일 디바이스 수신 프로세스의 기본 단위
모바일 디바이스에서 프로세스를 수신하는 데 사용해야 하는 기본 단위를 설정하려면 **단위 시퀀스 그룹** 페이지에서 **구매 및 양도를 위한 기본 단위** 와 **생산을 위한 기본 단위** 옵션을 활성화합니다. 예를 들어 모바일 디바이스를 사용하여 구매 주문 현재고를 수신할 때 기본적으로 시스템에서 팔레트 수량을 사용하도록 지정할 수 있지만 재고 보관 단위는 조각이어야 합니다. 각 팔레트에 포함된 조각 수에 대한 변환을 얻으려면 100 Pcs = 1 PL과 같이 단위 변환을 정의해야 합니다.

## <a name="default-order-settings"></a>기본 주문 설정
출시된 제품 생성의 일부로 구매, 판매 및 재고에 대한 기본 단위를 선택하여 다양한 주문을 처리해야 합니다. **기본 주문 설정** 및 **사이트별 주문 설정** 페이지를 사용하여 다양한 소스 문서에 대한 기본 단위 및 수량을 설정할 수 있습니다. **출시된 제품** 페이지에서 이 페이지에 액세스할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]