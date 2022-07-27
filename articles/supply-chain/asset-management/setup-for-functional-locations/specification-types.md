---
title: 유지 관리 특성 유형
description: 이 토픽에서는 자산 관리에서 특성 유형을 만드는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec5552d96473403931bbd513ae68ef0fe3069209f52e813963914417ad41b88a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446872"
---
# <a name="maintenance-attribute-types"></a>유지 관리 특성 유형

[!include [banner](../../includes/banner.md)]

 

이 토픽에서는 자산 관리에서 특성 유형을 만드는 방법에 대해 설명합니다. 특성은 다양한 요소의 속성을 설명하는 데 사용됩니다. 다음 요소에 특성을 설정할 수 있습니다.

- [기능 위치 유형](../setup-for-functional-locations/functional-location-types.md)
- [기능적 위치 생성](../functional-locations/create-functional-locations.md)
- [자산 유형](../setup-for-objects/object-types.md)
- 자산

설정할 수 있는 특성은 요소에 따라 다릅니다. 예를 들어 기능 위치의 경우 위치의 구성 및 물리적 크기에 대한 특성을 설정할 수 있습니다. 자산 유형 또는 자산에 대해 다양한 조건에서 엔진 볼륨, 전력 소비 및 최대 부하 용량에 대한 특성을 설정할 수 있습니다.

## <a name="create-attribute-types"></a>특성 유형 생성

고유한 특성 유형을 생성할 수 있습니다. 또한 제품 차원을 **특성 유형** 페이지로 전송할 수 있습니다.

1. **자산 관리** \> **설정** \> **특성 유형** 을 선택합니다.
2. 특성 유형을 처음 설정할 때 **제품 차원 생성** 을 선택하여 표준 제품 차원을 자동으로 전송합니다.
3. **새로 만들기** 를 선택하여 새 특성 유형을 만듭니다.
4. **특성 형식** 필드에서 특성 형식의 이름을 입력합니다.
5. **설명** 필드에 설명을 입력합니다.
6. **단위** 필드에서 필요에 따라 관련 특성 단위를 선택합니다.
7. **데이터 형식** 필드에서 단위의 데이터 형식을 선택합니다.
8. 데이터 유형으로 **문자열** 을 선택한 경우 다음 단계에 따라 특성 유형에 대한 값을 생성합니다.

    1. 특성 유형을 선택한 다음 **값** 을 선택합니다.
    2. **특성 값** 필드에서 **새로 만들기** 를 선택합니다.
    3. **특성 유형** 필드에서 특성 유형(차원)을 선택합니다.
    4. **값** 필드에 관련 값을 입력합니다.
    5. **설명** 필드에 설명을 입력합니다.
    6. 레코드를 저장합니다.
    7. **특성 유형** 페이지로 돌아갑니다.

9. 레코드를 저장합니다.

    **기능 위치 유형** 필드는 특성 유형을 사용하는 기능 위치의 수를 표시합니다. **자산 유형** 필드는 이를 사용하는 자산 유형의 수를 표시합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]