---
title: 재고 위치
description: 재고 위치는 기본 창고(WMS I)와 함께 사용되어 WMS I 창고에서 항목이 저장되는 위치와 항목이 불출되는 위치를 결정합니다.
author: yufeihuang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSLocation, WMSBlockingCause, WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c202a679e992c562772cbf6da6e17c4b8149760f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448675"
---
# <a name="inventory-locations"></a>재고 위치

[!include [banner](../includes/banner.md)]

재고 위치는 기본 창고(WMS I)와 함께 사용되어 WMS I 창고에서 항목이 저장되는 위치와 항목이 불출되는 위치를 결정합니다.

이 토픽은 재고 관리 모듈의 기능에 적용됩니다. 창고 관리 모듈의 기능에는 적용되지 않습니다.

위치라는 용어는 항목을 저장하고 가져오는 장소를 나타냅니다.

각 위치에 대해 항목이 삽입되는 위치도 지정할 수 있습니다. 기본적으로 동일합니다. 항목은 일반적으로 위치의 같은 면에서 삽입되고 그려지지만 항상 그런 것은 아닙니다. 예를 들어, 라이브 스토리지 랙에 보관된 항목은 한 통로에서 삽입되고 다른 통로에서 꺼집니다. 주요 입력은 위치 이름으로 주어지며 일반적으로 창고, 통로, 선반, 선반 및 빈과 같은 좌표에 의해 결정됩니다. 이 이름 또는 ID는 수동으로 입력하거나 위치 좌표에서 생성할 수 있습니다(예: 재고 위치 페이지의 통로 1, 랙 2, 선반 3, 빈 4의 경우 01-02-03-4).
위치 속성

위치에는 다음과 같은 특성이 있습니다.
-   크기(높이, 너비, 깊이 및 그에 따른 볼륨)
-   창고, 통로, 랙, 선반 및 빈 위치
-   위치 유형(대량 위치, 불출 위치, 인바운드 도크, 아웃바운드 도크, 생산 입력 위치, 검사 위치 또는 칸반 슈퍼마켓)

검사 텍스트는 운영자가 특정 항목에 대한 올바른 위치를 선택했는지 확인하기 위해 온라인 시스템에서 사용할 수 있습니다. 이 검사 텍스트는 수동으로 생성하거나 기본적으로 생성할 수 있습니다.

## <a name="sort-codes"></a>정렬 코드
정렬 코드를 사용하여 피킹 주문을 포함하여 재고에서 항목을 피킹하는 데 필요한 정보를 설명하는 피킹 라인 처리를 최적화합니다. 정렬 코드는 통로 및 기타 좌표로 지정하거나 위치에 대해 수동으로 지정할 수 있습니다.

## <a name="blocked-locations"></a>차단된 위치
경우에 따라 예를 들어 수리를 허용하기 위해 일정 기간 동안 위치가 차단되었음을 나타낼 수 있습니다. 다른 경우에는 입력만 차단하거나 출력만 차단하도록 표시할 수 있습니다.

## <a name="tree-structure"></a>트리 구조

재고 위치 페이지에서 정의된 표시 형식으로 재고 위치 좌표를 기반으로 하는 트리 구조의 창고 레이아웃을 볼 수 있습니다.

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a>창고 양식을 통해 재고 위치 유지

한 창고에서 다른 창고로 위치를 복사하고 마법사를 통해 위치를 생성할 수 있습니다. 마법사를 실행하기 전에 웨어하우스 페이지에서 기본 위치 이름을 정의했는지 확인해야 합니다.



## <a name="additional-resources"></a>추가 리소스

[새 창고 레이아웃 만들기](tasks/create-new-warehouse-layout.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]