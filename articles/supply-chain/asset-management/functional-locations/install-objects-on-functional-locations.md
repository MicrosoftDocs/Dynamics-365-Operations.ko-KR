---
title: 기능적 위치에 자산 설치
description: 이 토픽에서는 자산 관리의 기능 위치에 자산을 설치하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationObjectChange, EntAssetFunctionalLocationObjectInstall, EntAssetFunctionalLocationObject
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc278564b02335b44a0b35d6a3a981125e6f456b08893be2b5886f0a55396d52
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447265"
---
# <a name="install-assets-on-functional-locations"></a>기능적 위치에 자산 설치

[!include [banner](../../includes/banner.md)]

 

기능적 위치 구조를 만든 후 다음 단계는 관련 기능적 위치에 자산을 설치하는 것입니다. 이 토픽에서는 자산 관리의 해당 기능 위치에 자산을 설치하는 방법에 대해 설명합니다. 자산을 만드는 방법에 대한 자세한 내용은 [자산 소개](../objects/introduction-to-objects.md)를 참조하세요.

자산 구조를 생성한 경우 전체 자산 구조가 기능 위치에 설치되어야 합니다. 따라서 기능 위치에서 상위 자산(상위 자산이 없는 최상위 자산)만 선택할 수 있습니다. 관련된 모든 하위 자산(하위 자산)도 기능 위치에 설치됩니다. 기능 위치에 자산을 설치할 때 기능 위치에 대해 선택한 기능 위치 유형 설정에 따라 기능 위치의 재무 차원이 자동으로 자산으로 이전될 수 있습니다. 기능적 위치 유형을 설정하는 방법에 대한 자세한 내용은 [기능적 위치 유형](../setup-for-functional-locations/functional-location-types.md)을 참조하세요.

> [!NOTE]
> 기능적 위치에 사용되는 기능적 위치 유형에 자산 유형을 설정할 수 있습니다. 이 경우 기능 위치에 자산을 설치할 때 동일한 자산 유형을 가진 상위 자산만 기능 위치에 설치할 수 있는 자산 목록에 표시됩니다.

기능적 위치에 자산을 설치한 후 필요에 따라 상위 자산 또는 자산 구조를 바꿀 수 있습니다. 자산을 설치할 때와 마찬가지로 교체할 상위 자산을 선택합니다. 관련된 모든 하위 자산도 대체됩니다. 


## <a name="install-an-asset-structure-on-a-functional-location"></a>기능 위치에 자산 구조 설치

1. **자산 관리** \> **공통** \> **기능 위치** \> **모든 기능 위치** 또는 **활성 기능 위치** 를 선택합니다.
2. 자산을 설치할 기능 위치를 선택합니다.
3. **자산 설치** 를 선택합니다.

    **특성** 섹션에는 기능 위치에 대해 선택된 기능 위치 유형에 설정된 자산 특성 요구 사항 목록이 표시됩니다. 특성은 정보 제공용입니다. 시스템은 설치 중인 자산에 설정된 자산 특성에 대해 특성의 유효성을 검사하지 않습니다. **자산** 필드에서 자산을 선택한 후 검증을 수행해야 합니다.

4. **자산** 필드에서 설치할 상위 자산을 선택합니다. 관련된 모든 하위 자산이 자동으로 설치에 포함됩니다.

    자산 목록 오른쪽의 **자산 특성** 섹션에는 선택한 자산과 관련된 자산 특성이 표시됩니다.

5. **유효** 필드에서 자산 설치가 유효한 날짜와 시간을 선택합니다. 해당 날짜 및 시간 이후에는 자산 및 관련 하위 자산에 대한 비용이 기능적 위치와 관련됩니다.

    > [!NOTE]
    > 자산에 설정된 자산 특성이 **특성** 섹션에 추가됩니다. 예를 들어 **무게** 특성 요구 사항은 자산과 기능 위치 모두에 대한 요구 사항으로 추가되었습니다. 자산에 기능 위치와 동일한 유형의 특성 요구 사항이 있는 경우 자산의 속성 요구 사항 값이 **값** 필드에 입력됩니다. 따라서 기능 위치에 설정된 특성 요구 사항에 대해 자산 값을 확인할 수 있습니다. 기능 위치에 설정된 특성 요구 사항은 확인 표시로 표시됩니다.

6. **확인** 을 선택합니다.

    > [!NOTE]
    > 자산을 새 기능 위치에 설치하여 설치를 변경하려면 이 절차의 1-6단계를 따르세요. 새 기능 위치에 자산을 설치하면 자산이 이전 기능 위치에서 자동으로 제거됩니다. 새 기능 위치에 설치하기 전에 자산에 생성된 활성 유지 관리 요청 또는 작업 주문은 새 기능 위치로 자동 전송되지 **않습니다**. 자산에 이러한 유지 관리 요청 및 작업 주문이 여전히 필요한 경우 자산을 새 위치에 설치한 후 수동으로 다시 생성해야 합니다.

7. 하위 자산을 포함하여 기능 위치에 설치된 모든 자산 목록을 보려면 **모든 기능 위치** 페이지에서 기능 위치를 선택한 다음 **자산** 을 선택합니다.
8. 기능 위치에 설치된 자산과 관련된 활성 유지 관리 요청, 활성 작업 주문 또는 오류 등록 목록을 보려면 **모든 기능 위치** 페이지에서 기능 위치를 선택한 다음 **요청**, **작업 주문** 또는 **오류** 를 선택합니다.

> [!NOTE]
> 자산 관련 데이터가 변경되면 자산이 설치된 기능 위치에 자동으로 업데이트됩니다. 이 자동 업데이트는 유지 관리 요청, 작업 주문, 자산 결함 등록, 유지 관리 중단 시간 등록 및 자산 측정 등록에 대한 변경과 관련됩니다.

## <a name="automatically-create-one-asset-on-a-functional-location"></a>기능 위치에 하나의 자산을 자동으로 생성

기능 위치 단계 및 기능 위치 유형을 설정하여 기능 위치에서 *하나* 의 자산 자동 생성을 처리할 수 있습니다. 자산은 기능 위치와 동일한 ID 및 이름을 갖습니다. 이 기능은 건물과 같은 대규모 정적 자산의 유지 관리를 처리할 때 유용할 수 있습니다.

기능 위치에 자산을 자동으로 생성하려면 먼저 다음 설정 데이터를 사용할 수 있어야 합니다.

- 자산의 자동 생성을 처리하는 기능적 위치 유형을 생성합니다. **자산 유형** 필드에 자산 유형을 선택합니다. 자세한 내용은 [기능적 위치 유형](../setup-for-functional-locations/functional-location-types.md)을 참조하세요.
- 자산의 자동 생성을 처리하기 위해 기능적 위치 수명 주기 상태를 생성합니다. **자산 생성** 옵션을 **예** 로 설정합니다. 자세한 내용은 [기능 위치 수명 주기 상태](../setup-for-functional-locations/functional-location-stages.md)를 참조하세요.

설정 데이터를 사용할 수 있게 되면 자산을 만들 준비가 된 것입니다.

1. **모든 기능 위치** 페이지에서 자산을 자동으로 생성하려는 기능 위치가 이 목적으로 생성한 기능 위치 유형을 사용하는지 확인합니다.
2. 목록에서 기능 위치를 선택합니다.
3. **기능 위치 상태 업데이트** 를 선택한 다음 이 용도로 생성한 수명 주기 상태를 선택합니다. 이제 하나의 자산이 기능 위치에 자동으로 설치됩니다. 이 자산은 기능 위치와 동일한 ID 및 이름을 갖습니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]