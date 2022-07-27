---
title: 품질 관리 테스트 도구
description: 이번에는 Microsoft Dynamics 365 Supply Chain Management에서 품질 주문에 대한 테스트에 사용할 수 있는 테스트 도구를 만드는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d80a4f784a43e0d83d1f5b42f6740ef6da3add1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447868"
---
# <a name="quality-management-test-instruments"></a>품질 관리 테스트 도구

[!include [banner](../includes/banner.md)]

이번에는 Microsoft Dynamics 365 Supply Chain Management에서 품질 주문에 대한 테스트에 사용할 수 있는 테스트 도구를 만드는 방법에 대해 설명합니다.

**테스트 도구** 페이지를 사용하여 품질 주문에 대한 테스트를 수행하는 데 사용되는 장치에 대한 세부 정보를 정의하고 볼 수 있습니다. 테스트 도구는 선택 사항입니다. 그러나 품질 작업자가 특정 테스트를 수행하는 데 사용해야 하는 장치 또는 도구를 알 수 있도록 도울 수 있습니다.

## <a name="test-instrument-example"></a>테스트 장치 예시

전기 부품에 대한 다양한 테스트를 수행하고 있습니다. 일부 테스트는 부품의 전압 출력에 대한 것이고, 하나의 테스트는 온도에 대한 것이고, 하나의 테스트는 중량에 대한 것입니다. 각 테스트를 수행하기 위해 다양한 도구, 장치 또는 장비가 사용됩니다. 예를 들어, 전압계는 전압을 측정하는 데 사용하고, 온도계는 온도를 측정하는 데 사용되며 저울은 무게를 측정하는 데 사용됩니다. 이러한 각 장치를 테스트 장비로 구성하고 테스트 결과를 기록해야 하는 측정 단위를 지정할 수 있습니다. 예를 들어, 전압계의 결과는 볼트로, 온도계의 결과는 화씨 또는 섭씨로, 저울의 결과는 파운드 또는 킬로그램으로 기록됩니다.

## <a name="create-a-test-instrument"></a>테스트 도구 만들기

1. **재고 관리 \> 설정 \> 품질 관리 \> 테스트 장치** 로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 이후 새 행에 대해 다음 필드를 설정합니다.

    - **테스트 장치** – 테스트 장치의 고유 ID 또는 이름을 입력합니다.
    - **설명** – 테스트 장치에 대한 자세한 설명을 입력합니다.
    - **단위** – 장치가 측정한 결과의 단위를 선택합니다. **정밀도** 필드는 선택한 단위에 따라 자동으로 설정됩니다.

1. 페이지를 닫습니다.

## <a name="additional-resources"></a>추가 리소스

- [품질 관리 테스트](quality-tests.md)
- [품질 관리 테스트 그룹](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
