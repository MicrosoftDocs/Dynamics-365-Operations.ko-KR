---
title: 추가 위치 영역
description: 이 항목에서는 Microsoft Dynamics 365 Supply Chain Management에 추가된 새 위치 영역에 대한 개요를 제공합니다.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: dd9e97cabe5e3d3bdc261a7280930b73eb8e1419
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450040"
---
# <a name="additional-location-zones"></a>추가 위치 영역

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management에서 세 가지 새로운 영역 필드를 사용할 수 있습니다. 창고 관리자는 이를 사용하여 추가 창고 조직 또는 레이아웃을 정의할 수 있습니다. 새 영역 필드는 수동으로 또는 **위치 설정** 마법사를 사용하여 설정할 수 있습니다. 위치 테이블을 사용하는 모든 쿼리 또는 필터링에서 사용할 수 있습니다.

영역 필드를 사용하기 위해 추가 설정이 필요하지 않습니다.

## <a name="turn-the-additional-location-zone-feature-on-or-off"></a>추가 위치 영역 기능 켜기 또는 끄기

Supply Chain Management 버전 10.0.25부터 이 기능은 기본적으로 켜져 있습니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *추가 위치 영역* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

## <a name="use-location-zones"></a>위치 영역 사용

1. **창고 관리\> 설정 \> 창고 \> 위치 설정 마법사** 로 이동합니다.
2. 다음 값을 설정합니다.

    - **창고** 필드에서 _62_ 를 선택합니다.
    - **영역 ID** 필드에서 _FLOOR_ 를 선택합니다.
    - **추각 영역 1** 필드에서 _PICKZONE1_ 을 선택합니다.
    - **추각 영역 2** 필드에서 _WEBSHOP1_ 을 선택합니다.
    - **위치 프로필 ID** 필드에서 _FLOOR_ 를 선택합니다.

3. **플로어** 라인을 선택합니다.
4. **시작 번호** 필드에 _1_ 을 입력합니다. **끝 번호** 필드에 _3_ 을 입력합니다.
5. **통로** 라인을 선택합니다.
6. **시작 번호** 필드에 _1_ 을 입력합니다. **끝 번호** 필드에 _5_ 를 입력합니다.
7. **만들기** 를 선택합니다.
8. 새 위치가 추가되었다는 메시지를 받습니다. **메시지 표시** 버튼을 선택하여 메시지를 봅니다.
9. **창고 관리 \> 설정 \> 창고 \> 위치** 로 이동합니다. 새 위치가 목록에 나타나고 모든 구역 필드를 사용할 수 있습니다(즉, 기존 구역 필드와 새 추가 구역 필드).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]