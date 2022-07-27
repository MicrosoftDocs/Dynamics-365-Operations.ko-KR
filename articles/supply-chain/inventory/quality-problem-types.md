---
title: 부적합 문제 유형
description: 이번에는 부적합 문제 유형을 생성하고 사용하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 26705dd12f478f4ca6046c7265d4ae3cb1d08c69
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448150"
---
# <a name="problem-types-for-nonconformances"></a>부적합 문제 유형

[!include [banner](../includes/banner.md)]

이번에는 부적합 문제 유형을 생성하고 사용하는 방법에 대해 설명합니다.

**문제 유형** 페이지를 사용하여 다양한 부적합 유형에 대해 발생할 수 있는 품질 문제의 분류를 정의합니다. 생성한 각 문제 유형에 대해 문제 유형을 사용할 수 있는 부적합 유형을 지정해야 합니다. 다음과 같은 부적합 유형을 설정할 수 있습니다.

- **내부** – 이 유형의 부적합은 현 재고와 관련이 있습니다(품질 주문 또는 격리 주문 등).
- **고객** – 이 유형의 부적합은 판매 주문과 관련이 있습니다.
- **공급 업체** – 이 유형의 부적합은 구매 주문과 관련이 있습니다.
- **서비스 요청** – 이 유형의 부적합은 서비스 주문과 관련이 있습니다.
- **생산** – 이 유형의 부적합은 일괄 주문 또는 생산 주문과 관련이 있습니다.
- **부산물 생산** – 이 유형의 부적합은 부산물에 대한 일괄 주문과 관련이 있습니다.

새 문제 유형을 생성할 때 작업 창에서 **비준수 유형** 을 선택하여 문제 유형에 대해 승인된 하나 이상의 비준수 유형 목록을 생성합니다. 예를 들어, 결함 코드와 관련된 문제 유형은 모든 부적합 유형에 적용될 수 있습니다. 단, 고객 불만과 관련된 문제 유형은 **고객** 및 **서비스 요청** 부적합 유형에만 해당될 수 있습니다.

## <a name="examples-of-problem-types"></a>문제 유형 예시

다음은 다양한 부적합 유형에 사용할 수 있는 문제 유형에 대한 시나리오의 몇 가지 예시입니다.

- **고객:** 고객이 불만을 제기했거나 고객이 반품했거나 품질 사양이 충족되지 않았습니다.
- **공급 업체:** 제품이 훼손되었거나, 품질 사양에 맞지 않거나, 잘못된 제품을 받았습니다.
- **서비스 요청:** 품질 사양이 충족되지 않았거나 고객이 불만을 제기했거나 기계 유지 보수가 필요합니다.
- **생산:** 품질 사양이 충족되지 않았거나 기계 유지 보수가 필요하거나 제품이 손상되었습니다.
- **부산물 생산:** 품질 사양이 충족되지 않았거나 기계 유지 보수가 필요하거나 제품이 손상되었습니다.

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a>문제 유형을 생성하고 부적합 유형에 할당

1. **재고 관리 \> 설정 \> 품질 관리 \> 문제 유형** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 이후 새 행에 대해 다음 필드를 설정합니다.

    - **문제 유형** – 문제 유형의 고유 ID 또는 이름을 입력합니다.
    - **설명** – 문제 유형에 대한 자세한 설명을 입력합니다.

1. 새 행이 선택된 상태에서 작업 창에서 **비준수 유형** 을 선택합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 이후 새 행에 대해 비준수 유형 필드를 문제 유형에 허용하려는 **비준수 유형** 으로 설정합니다.
1. 문제 유형에 대해 승인하려는 각 추가 부적합 유형에 대해 이전 단계를 반복합니다.
1. 페이지를 닫습니다.

## <a name="additional-resources"></a>추가 리소스

- [품질 관리 개요](quality-management-processes.md)
- [품질 및 부적합 관리 활성화](enable-quality-management.md)
- [부적합 승인을 담당하는 작업자](quality-responsible-workers.md)
- [부적합 격리 구역](quality-quarantine-zones.md)
- [부적합 진단 유형](quality-diagnostic-types.md)
- [부적합 품질 비용](quality-charges.md)
- [부적합 작업](quality-operations.md)
- [창고 공정을 위한 품질 관리](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
