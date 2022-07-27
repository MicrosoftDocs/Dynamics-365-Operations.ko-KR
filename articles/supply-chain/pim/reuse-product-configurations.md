---
title: 제품 구성 재사용
description: 제품에 대한 기존 구성을 자동으로 재사용하도록 지정할 수 있습니다. 그런 다음 사용자가 구성 세션을 완료하면 시스템은 사용자의 선택과 일치하는 구성이 이미 존재하는지 확인합니다. 일치하는 구성이 발견되면 구성 ID, 해당 자재 명세서(BOM) 및 경로가 재사용됩니다.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0898bd1832fa7007fc3aa265beee2e930f157a39
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449011"
---
# <a name="reuse-product-configurations"></a>제품 구성 재사용

[!include [banner](../includes/banner.md)]

제품에 대한 기존 구성을 자동으로 재사용하도록 지정할 수 있습니다. 그런 다음 사용자가 구성 세션을 완료하면 시스템은 사용자의 선택과 일치하는 구성이 이미 존재하는지 확인합니다. 일치하는 구성이 발견되면 구성 ID, 해당 자재 명세서(BOM) 및 경로가 재사용됩니다.

## <a name="requirements-for-reusing-configurations"></a>구성 재사용 요구 사항

구성을 재사용하려면 **제품 구성 모델 세부 정보** 페이지에서 구성 요소 및 특성에 대해 다음 정보를 지정해야 합니다.

-   **구성 요소 및 하위 구성 요소** – **일반** 빠른 탭의 **구성 재사용** 필드에서 **예** 를 선택합니다.
-   **특성** – **특성** 빠른 탭에서 **재사용에 포함** 옵션을 선택합니다. 이 옵션은 관련 구성 요소를 재사용할 수 있는 경우에만 나타납니다. 재사용할 특성을 선택하지 않으면 구성 세션 중 사용자의 선택에 관계없이 구성이 항상 재사용됩니다. 기존 구성의 특성 값은 사용자의 선택과 일치해야 합니다. 예를 들어, 사용자가 구성 세션 중에 색상으로 **파란색** 을 선택하면 시스템은 구성 요소의 기존 구성에 파란색이 있는지 확인합니다.

## <a name="resetting-configuration-reuse"></a>구성 재사용 재설정
구성 재사용을 재설정하면 이전에 생성된 구성이 더 이상 고려되지 않습니다. BOM 또는 경로가 변경되었지만 관련 특성이 변경되지 않은 경우 구성 재사용을 재설정할 수 있습니다. 구성 요소에 대한 **일반** 빠른 탭에서 구성 재사용을 재설정합니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]