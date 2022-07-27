---
title: 임대 그룹 만들기
description: 이 토픽에서는 임대 그룹을 설정하는 방법을 설명합니다. 새 임대를 만들려면 임대 그룹이 필요합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseGroupTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5ff4892408aa87214231762452c195274192447512525ae9c1f08dad8e318076
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450280"
---
# <a name="create-a-lease-group"></a>임대 그룹 만들기

[!include [banner](../includes/banner.md)]

이 토픽에서는 임대 그룹을 설정하는 방법을 설명합니다. 새 임대를 만들려면 임대 그룹이 필요합니다. 임대 장부는 각 임대 그룹과 연결됩니다. 임대 장부는 각 임대에 대해 생성해야 하는 기본 장부를 결정합니다. **임대 전기 매개 변수** 페이지에서 특정 계정을 임대 그룹에 할당할 수 있습니다.

## <a name="create-a-lease-book-and-add-a-lease-group"></a>임대 장부 생성 및 임대 그룹 추가

1. **자산 임대 \> 설정 \> 임대 그룹** 으로 이동합니다.
2. 작업 창에서 **새로 만들기** 를 선택하여 임대 그룹을 추가합니다. 라인이 그리드에 추가됩니다.
3. 새로운 라인의 **임대 그룹** 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다.

방금 입력한 정보가 **임대 추가** 페이지의 **임대 그룹** 필드에 추가됩니다.

## <a name="associate-a-book-with-a-lease-group"></a>장부를 임대 그룹과 연결

임대 그룹을 만든 후 각 그룹에 장부를 할당할 수 있습니다. 임대를 만들고 임대 그룹에 할당하면 시스템은 해당 임대 그룹과 연결된 각 장부에 대한 일정 집합을 만듭니다.

> [!NOTE]
> 장부를 임대 그룹에 할당하려면 먼저 장부를 설정해야 합니다.

1. **자산 임대 \> 설정 \> 임대 그룹** 으로 이동합니다.
2. 임대 그룹을 선택한 다음 **장부** 를 선택합니다.
3. **새로 만들기** 를 선택한 후 **장부 유형** 필드에서 임대 그룹에 할당할 장부를 선택합니다. 임대를 다양한 방식으로 회계처리해야 하는 경우 임대 그룹에 여러 장부를 할당할 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
