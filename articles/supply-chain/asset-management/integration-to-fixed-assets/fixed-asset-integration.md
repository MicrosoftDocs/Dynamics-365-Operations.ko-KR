---
title: 고정 자산과 자산 관리 통합
description: 이 토픽에서는 고정 자산을 유지 관리 자산과 연결할 수 있도록 자산 관리 및 고정 자산 모듈을 통합하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 40e4fdce50b335668a53d2efe53b7cf6c66f364f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448027"
---
# <a name="integrate-asset-management-with-fixed-assets"></a>고정 자산과 자산 관리 통합

[!include [banner](../../includes/banner.md)]

**자산 관리** 및 **고정 자산** 모듈을 통합하여 고정 자산을 유지 관리 자산과 연결할 수 있습니다. 그런 다음 고정 자산 사용자는 신규 또는 기존 고정 자산에서 유지 관리 자산을 생성할 수 있고 자산 관리 사용자는 유지 관리 자산을 기존 고정 자산과 연결할 수 있습니다. 또한 이 기능을 사용하면 고정 자산 사용자가 관련 유지 관리 자산에 대한 작업 주문에서 게시된 비용을 쉽게 볼 수 있습니다.

> [!NOTE]
> 이 토픽에서 *유지 관리 자산* 은 **자산 관리** 모듈의 자산을 참조하고 *고정 자산* 은 **고정 자산** 모듈의 자산을 참조합니다.

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a>고정 자산에서 생성된 새 유지 관리 자산의 기본 위치 설정(선택 사항)

이 선택적 구성을 사용하면 고정 자산에서 생성된 새 유지 관리 자산의 기본 기능 위치를 설정할 수 있습니다. 일반적으로 이 구성을 완료하는 경우 한 번만 완료합니다.

구성을 완료하려면 다음 단계를 따르세요.

1. **자산 관리 \> 설정 \> 자산 관리 매개 변수** 로 이동합니다.
1. **고정 자산** 탭의 **기능 위치** 필드에서 기본 위치를 선택하세요.
1. 작업 창에서 **저장** 을 선택합니다.

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a>통합 유지 관리 자산 및 고정 자산 작업

이 섹션에서는 통합 자산 관리 및 고정 자산 기능으로 작업할 수 있는 다양한 방법을 보여주는 절차 모음을 제공합니다.

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a>기존 유지 관리 자산을 고정 자산과 연결

기존 유지 관리 자산을 고정 자산과 연결하려면 다음 단계를 따르십시오.

1. **자산 관리\> 자산 \>모든 자산**(또는 **활성 자산**)으로 이동합니다.
1. 자산을 선택합니다.
1. **고정 자산** 빠른 탭의 **고정 자산 번호** 필드에서 기존 고정 자산을 선택합니다.
1. 작업 창에서 **저장** 을 선택합니다.

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a>선택한 유지 관리 자산과 연결된 고정 자산 보기

선택한 유지 관리 자산과 연결된 고정 자산을 보려면 다음 단계를 따르세요.

1. **자산 관리\> 자산 \>모든 자산**(또는 **활성 자산**)으로 이동합니다.
1. 자산을 선택합니다.
1. **고정 자산** 빠른 탭의 **고정 자산 번호** 필드에서 링크를 선택합니다.

    선택한 자산에 대한 **고정 자산** 페이지가 열립니다. (일반적으로 이 페이지는 **고정 자산 \> 고정 자산 \> 고정 자산** 에서 찾을 수 있습니다.)

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a>선택한 고정 자산과 연결된 유지 관리 자산 보기

선택한 고정 자산과 연결된 유지 관리 자산을 보려면 다음 단계를 따르세요.

1. **고정 자산 \> 고정 자산 \> 고정 자산** 으로 이동합니다.
1. 자산을 선택합니다.
1. 작업 창의 **자산 관리** 탭에 있는 **보기** 그룹에서 **유지 관리 자산** 을 선택합니다.

    선택한 고정 자산과 연결된 자산의 **유지 관리 자산** 페이지가 열립니다. (일반적으로 이 페이지는 **자산 관리 \> 자산 \> 모든 자산** 에서 찾을 수 있습니다.)

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a>고정 자산과 관련된 유지 관리 비용 보기

자산 관리 작업 주문은 유지 관리 자산에 대해 전기될 수 있으며 이러한 각 작업 주문에는 일반적으로 비용이 있습니다. 고정 자산이 유지 관리 자산과 연결되면 고정 자산에서 직접 관련 비용을 볼 수 있습니다.

고정 자산과 관련된 유지 관리 비용을 보려면 다음 단계를 따르세요.

1. **고정 자산 \> 고정 자산 \> 고정 자산** 으로 이동합니다.
1. 자산을 선택합니다.
1. 작업 창의 **자산 관리** 탭에 있는 **보기** 그룹에서 **유지 관리 비용** 을 선택합니다.

    **유지 관리 비용** 페이지가 열리고 관련 비용이 표시됩니다.

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a>기존 고정 자산에 대한 새 유지 관리 자산 생성

기존 고정 자산에 대한 새 유지 관리 자산을 생성하려면 다음 단계를 따르세요.

1. **고정 자산 \> 고정 자산 \> 고정 자산** 으로 이동합니다.
1. 자산을 선택합니다.
1. 작업 창의 **자산 관리** 탭에 있는 **신규** 그룹에서 **유지 관리 자산 만들기** 를 선택합니다. (이 옵션을 사용할 수 없는 경우 유지 관리 자산이 선택한 고정 자산과 이미 연결되어 있을 수 있습니다.)
1. 자산 생성에 설명된 대로 [자산 생성](../objects/create-an-object.md)을 완료합니다.

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a>새 고정 자산을 만들고 새 유지 관리 자산 추가

새 고정 자산을 만들고 새 유지 관리 자산을 추가하려면 다음 단계를 따르세요.

1. **고정 자산 \> 고정 자산 \> 고정 자산** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택합니다.
1. 고정 자산 생성에 설명된 대로 [고정 자산 생성](../../../finance/fixed-assets/tasks/create-fixed-asset.md)을 완료합니다.
1. 작업 창의 **자산 관리** 탭에 있는 **신규** 그룹에서 **유지 관리 자산 만들기** 를 선택합니다.
1. 자산 생성에 설명된 대로 [자산 생성](../objects/create-an-object.md)을 완료합니다.

### <a name="remove-the-association-between-two-assets"></a>두 자산 간의 연결 제거

경우에 따라 고정 자산에서 유지 관리 자산의 연결을 해제해야 할 수 있습니다. 예를 들어 고정 자산에서 [새 유지 관리 자산을 생성](#new-maintenance-from-fixed)하려면 먼저 기존 연결을 제거해야 합니다.

유지 관리 자산과 고정 자산 간의 기존 연결을 제거하려면 다음 단계를 따르세요.

1. **자산 관리\> 자산 \>모든 자산**(또는 **활성 자산**)으로 이동합니다.
1. 고정 자산을 찾아 엽니다.
1. **고정 자산** 빠른 탭의 **기능 위치** 필드에서 값을 지웁니다.
1. 작업 창에서 **저장** 을 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]