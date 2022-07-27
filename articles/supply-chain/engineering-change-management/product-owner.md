---
title: 제품 소유자
description: 이 토픽에서는 제품 소유자에 대한 정보를 제공합니다. 제품 소유자는 특정 제품을 담당하는 사용자 그룹입니다. 그룹의 구성원만 해당 제품을 출시할 수 있습니다. 제품 소유자는 승인 워크플로에서도 사용할 수 있습니다.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a29ab169e9b24826fbe69fbc316040d4618750ee
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448021"
---
# <a name="product-owners"></a>제품 소유자

[!include [banner](../includes/banner.md)]

제품 소유자는 특정 제품을 담당하는 사용자 그룹입니다. 제품 소유자 그룹이 제품에 할당되면 해당 그룹의 구성원만 제품을 출시할 수 있습니다. 제품 소유자는 엔지니어링 변경 관리의 승인 워크플로에서도 사용할 수 있습니다.

제품 소유자는 전역 설정입니다. 따라서 모든 법인이 사용할 수 있습니다.

## <a name="create-a-product-owner-group"></a>제품 소유자 그룹 만들기

제품 소유자 그룹을 만들고 구성원을 추가하려면 다음 단계를 따르세요.

1. **엔지니어링 변경 관리 \> 설정 \> 제품 소유자** 로 이동합니다.
2. 작업 창에서 **새로 만들기** 를 선택합니다.
3. **제품 소유자** 필드에 그룹에 대한 이름을 입력합니다.
4. **이름** 필드에 그룹에 대한 설명을 입력합니다.
5. **구성원** 빠른 탭에서 그룹의 구성원이어야 하는 작업자를 추가합니다.

## <a name="assign-a-product-owner-to-a-product"></a>제품에 제품 소유자 할당

제품 소유자를 제품에 할당하려면 다음 단계를 따르십시오.

1. 관련 제품 또는 제품 마스터에 대한 **제품 세부정보** 페이지를 엽니다.
1. **일반** 빠른 탭에서 **제품 소유자** 필드를 관련 제품 소유자 그룹의 이름으로 설정합니다.

제품 소유자가 제품에 할당되는 동안 제품 소유자 그룹의 구성원만 **제품 소유자** 설정을 편집할 수 있습니다.

제품 소유자는 **출시된 제품** 페이지에서도 볼 수 있습니다.

## <a name="product-owners-and-product-releases"></a>제품 소유자 및 제품 릴리스

제품의 제품 소유자 그룹에 속한 사용자만 해당 제품을 출시할 수 있습니다. 그러나 제품이 하위 항목이고 상위 항목이 상위 항목의 소유자에 의해 해제된 경우에는 예외가 있습니다. 즉, 제품이 다른 제품의 BOM의 일부인 경우 시스템은 BOM에 있는 각 항목의 제품 소유자를 확인하지 않습니다. 상위 항목의 제품 소유자만 확인합니다.

예를 들어 제품 X는 *디자인* 캐비닛 제품 소유자 그룹에 할당됩니다. 제품 X는 또한 *디자인 스피커* 제품 소유자 그룹에 할당된 제품 Y의 BOM의 일부입니다. *디자인 스피커* 제품 소유자 그룹의 사용자가 제품 Y 및 해당 BOM을 출시하면 제품 X는 제품 Y와 함께 출시됩니다.

## <a name="product-owners-and-approvals"></a>제품 소유자 및 승인

제품 소유자는 특정 엔지니어링 변경이 제품에 도움이 될 것인지 여부를 알고 있으므로 엔지니어링 변경 관리에서 승인 프로세스의 일부로 이를 포함하는 것이 타당합니다. 엔지니어링 변경 관리에 사용되는 워크플로에서 제품 소유자를 참여 공급자로 설정하여 이 접근 방식을 구현할 수 있습니다. 그런 다음 시스템은 엔지니어링 변경 요청 및 엔지니어링 변경 주문에 있는 제품을 기반으로 워크플로에서 승인 작업을 할당합니다. 자세한 내용은 [엔지니어링 제품의 변경 사항 관리](engineering-change-management.md)를 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]