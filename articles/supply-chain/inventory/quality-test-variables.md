---
title: 품질 관리 테스트 변수
description: 이번에는 Microsoft Dynamics 365 Supply Chain Management에서 품질 주문에 대한 질적 테스트에 사용할 수 있는 테스트 변수를 만드는 방법에 대해 설명합니다.
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
ms.openlocfilehash: 4495c3d3f8df9f07ec079d8e497a17979abbe3ee
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448852"
---
# <a name="quality-management-test-variables"></a>품질 관리 테스트 변수

[!include [banner](../includes/banner.md)]

이번에는 Microsoft Dynamics 365 Supply Chain Management에서 품질 주문에 대한 질적 테스트에 사용할 수 있는 테스트 변수를 만드는 방법에 대해 설명합니다.

**테스트** 페이지에 정의된 모든 질적 테스트에 대해 테스트 변수와 가능한 결과를 정의해야 합니다. (질적 테스트의 경우 **테스트** 페이지의 **유형** 필드가 *옵션* 으로 설정됩니다.)

**테스트 변수** 페이지를 사용하여 질적 테스트와 연결된 테스트 변수에 대한 가능한 결과를 설정, 편집하고 볼 수 있습니다. 각 결과에 대해 *통과* 또는 *실패* 의 결과 상태를 할당하여 해당 결과가 테스트 결과로 선택될 때 테스트가 통과 또는 실패했는지를 나타냅니다. **테스트 그룹** 페이지를 사용하여 테스트 변수와 이에 대한 기본 결과를 개별 질적 테스트에 할당합니다.

모든 테스트 변수에 대해 결과 상태가 *통과* 인 것과 결과 상태가 *실패* 인 두 가지 이상의 결과를 정의하는 것이 좋습니다. 정의할 수 있는 변수 또는 결과의 총 수에는 제한이 없습니다. 또한, 여러 테스트에서 동일한 테스트 변수를 사용하여 결과를 기록할 수 있습니다.

## <a name="examples-of-test-variables"></a>테스트 변수 예시

### <a name="example-1"></a>예시 1

제조 업체는 제조된 원자재에 대해 두 가지 테스트를 수행합니다. 한 테스트에서 pH 수준은 컬러 스트립과 관련이 있습니다. 허용 가능한 pH 수준은 더 밝은 색상으로 표시되고 허용되지 않는 pH 수준은 더 어두운 색상으로 표시됩니다. 또 다른 테스트에서는 여러 번 육안 검사를 수행하고 품질 작업자가 판단을 사용하여 품목이 육안 검사에 통과했는지를 결정합니다.

### <a name="example-2"></a>예시 2

쿠키를 생산하는 제조 업체는 완제품에 대한 검사 테스트를 사용합니다. 이 검사 테스트에는 여러 변수가 있습니다. 한 가지 변수는 맛과 좋고 나쁨에 대한 가능한 결과입니다. 두 번째 변수는 색상이며 가능한 결과는 너무 어둡고, 너무 밝거나 정확한 것이 있습니다.

## <a name="create-a-test-variable"></a>테스트 변수 만들기

테스트 변수를 생성하려면 다음 단계를 따르십시오.

1. **재고 관리 \> 설정 \> 품질 관리 \> 테스트 매개 변수** 로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 이후 새 행에 대해 다음 필드를 설정합니다.

    - **변수** – 변수의 고유 ID 또는 이름을 입력합니다.
    - **설명** – 변수에 대한 자세한 설명을 입력합니다.

1. 새 행이 선택된 상태에서 작업 창에서 **결과** 를 선택합니다.
1. **테스트 변수 결과** 페이지의 작업 창에서 **새로 만들기** 를 선택하여 표에 행을 추가합니다. 이후 새 행에 대해 다음 필드를 설정합니다.

    - **결과** – 결과에 대한 고유 ID 또는 이름을 입력합니다.
    - **설명** – 결과에 대한 자세한 설명을 입력합니다.
    - **결과 상태** – *통과* 또는 *실패* 를 선택하여 결과가 테스트 결과로 선택되었을 때 테스트의 통과 또는 실패 여부를 나타냅니다.

1. 각 추가 결과에 대해 이전 단계를 반복합니다. 하나 이상의 결과 상태가 *통과* 이고 하나 이상의 결과 상태가 *실패* 인지 확인합니다.
1. 페이지를 닫습니다.

## <a name="additional-resources"></a>추가 리소스

- [품질 관리 테스트 도구](quality-test-instruments.md)
- [품질 관리 테스트](quality-tests.md)
- [품질 관리 테스트 그룹](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
