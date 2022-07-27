---
title: 품질 관리 테스트
description: 이번에는 Microsoft Dynamics 365 Supply Chain Management에서 품질 주문에 사용할 수 있는 테스트를 만드는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c10b67f86fc29b5e8c08081a9b789d4f42c24cf4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448663"
---
# <a name="quality-management-tests"></a>품질 관리 테스트

[!include [banner](../includes/banner.md)]

이번에는 Microsoft Dynamics 365 Supply Chain Management에서 품질 주문에 사용할 수 있는 테스트를 만드는 방법에 대해 설명합니다.

**테스트** 페이지를 사용하여 제품이 품질 사양을 충족하는지를 결정하는 개별 테스트를 정의하고 봅니다. 하나 이상의 개별 테스트를 테스트 그룹에 할당할 수 있습니다. 이 경우 허용 가능한 측정 값과 같은 테스트 관련 정보도 지정합니다. 측정값은 정량적 테스트에 사용됩니다. 질적 테스트의 경우 테스트 변수가 사용됩니다.

- 정량적 테스트의 경우 **유형** 필드가 *정수* 또는 *분수* 로 설정됩니다. 측정 단위도 지정됩니다. 품질 사양 및 테스트 결과는 번호로 표시됩니다.
- 질적 테스트의 경우 **유형** 필드가 *옵션* 으로 설정됩니다. 질적 테스트에는 측정되는 테스트 변수와 열거된 옵션에 대한 추가 정보가 필요합니다. 품질 사양 및 테스트 결과는 결과에 따라 표현됩니다.

선택적으로 테스트 장비를 테스트에 할당할 수 있습니다. 그러나 테스트 도구는 품질 주문으로 테스트를 만들고 사용하는 데 필요하지 않습니다. 자세한 내용은 [품질 관리](quality-test-instruments.md) 테스트 도구를 참조하세요.

또한, 선택적으로 테스트 단위를 지정하여 테스트 결과가 기록되는 측정 단위를 나타낼 수 있습니다. 예를 들어, 온도 테스트에는 화씨 또는 섭씨 단위가 포함될 수 있습니다.

## <a name="example-of-a-test"></a>테스트 예시

제조 업체는 구매한 원자재에 대해 원자재 품질에 대한 정량적 테스트와 소포 손상에 대한 질적 테스트라는 두 가지 테스트를 수행합니다. 업체는 테스트 변수(소포 손상 등) 및 그 결과를 정의하기 위해 질적 테스트에 대한 추가 정보를 지정합니다. 업체는 **테스트 그룹** 페이지를 사용하여 두 테스트를 테스트 그룹에 할당하고 테스트 관련 정보를 지정합니다. 테스트 그룹은 업체가 두 테스트에 대한 테스트 결과를 보고할 수 있도록 품질 주문에 할당됩니다.

## <a name="create-a-test"></a>테스트 만들기

테스트를 생성하려면 다음 단계를 따르십시오.

1. **재고 관리 \> 설정 \> 품질 관리 \> 테스트** 로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 이후 새 행에 대해 다음 필드를 설정합니다.

    - **테스트** – 테스트의 고유 ID 또는 이름을 입력합니다.
    - **설명** – 테스트에 대한 자세한 설명을 입력합니다.
    - **유형** – 테스트가 생성하는 결과 유형을 선택합니다. 정량적 테스트의 경우 *분수* 또는 *정수* 를 선택합니다. 질적 테스트의 경우 *옵션* 을 선택합니다.
    - **테스트 장치** – 테스트에 사용해야 하는 [테스트 장치](quality-test-instruments.md)를 선택합니다.
    - **단위** – **유형** 필드에서 *분수* 또는 *정수* 를 선택한 경우(즉, 테스트가 정량적 테스트인 경우) 테스트 결과를 기록해야 하는 측정 단위를 선택합니다.

1. 페이지를 닫습니다.

> [!NOTE]
> 테스트를 저장한 후에는 그리드에서 더 이상 **유형** 필드를 편집할 수 없습니다. 테스트에 대해 기록할 테스트 결과 유형을 변경해야 하는 경우 작업 창에서 **품질 테스트 유형 변경** 을 선택합니다. **품질 테스트 유형 변경** 대화 상자에서 **새 유형** 필드를 원하는 유형으로 설정한 후, **확인** 을 선택하여 대화 상자를 닫습니다.

## <a name="additional-resources"></a>추가 리소스

- [품질 관리 테스트 도구](quality-test-instruments.md)
- [품질 관리 테스트 그룹](quality-test-groups.md)
- [품질 관리 테스트 변수](quality-test-variables.md)
- [품질 협회](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
