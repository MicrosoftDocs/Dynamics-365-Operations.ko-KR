---
title: 부적합 작업
description: 이번에는 부적합 작업을 만들고 사용하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestOperations, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35619454af8b1cb1b7d383d393362f58d9dd0ea6
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448666"
---
# <a name="operations-for-nonconformances"></a>부적합 작업

[!include [banner](../includes/banner.md)]

이번에는 부적합 작업을 만들고 사용하는 방법에 대해 설명합니다.

**작업** 페이지를 사용하여 승인된 부적합에 대해 수행할 수 있는 작업의 분류를 정의할 수 있습니다. 관련 작업을 부적합에 할당할 때 작업을 수행하는 데 필요한 관련 원자재, 노동 시간 및 요금과 같은 세부 정보를 제공할 수 있습니다. 시스템에서는 이 정보를 사용하여 작업에 대한 예상 비용을 계산합니다. 자세한 정보 및 예상 비용은 참고용입니다. 품질 관련 작업은 생산 경로에 대해 정의할 수 있는 작업과 다릅니다.

> [!NOTE]
> 비용, 시간 및 부적합과 관련된 작업에 사용되는 품목을 추적할 수 있지만 입력하는 데이터는 정보 제공용일 뿐입니다. 총 계정 원장, 재고 보조 원장 또는 **근태** 모듈과 자동으로 통합되지 않습니다.

## <a name="examples-of-operations"></a>작업 예시

귀하는 제조 업체에서 일하고 있습니다. 품질 테스트에 실패한 품목에 대해 부적합이 생성되고 승인되었습니다. 문제가 기계의 베어링 불량과 관련되어 있음을 나타내기 위해 수정 사항이 작성되었습니다. 베어링을 교체하려면 여러 단계가 필요하며 각 작업에 대한 책임이 추적됩니다. 예를 들어 다음 단계가 필요할 수 있습니다.

1. 생산 라인이 중지되고 청소 루틴이 수행됩니다.
1. 유지 보수 직원이 베어링을 교체합니다.
1. 품질 보증 담당자는 전원을 다시 켜기 전에 기계를 검사합니다.

이 예시에서는 수행해야 하는 작업을 나타내기 위해 다음 작업을 만들 수 있습니다.

- 생산 라인을 중지합니다.
- 생산 라인을 청소합니다.
- 기계 유지 보수를 수행합니다.
- 기계를 검사합니다.

## <a name="create-an-operation"></a>작업 만들기

1. **재고 관리 \> 설정 \> 품질 관리 \> 작업** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 이후 새 행에 대해 다음 필드를 설정합니다.

    - **작업** – 작업의 고유 ID 또는 이름을 입력합니다.
    - **설명** – 작업에 대한 자세한 설명을 입력합니다.
    - **유형** – 특정 유형의 주문과 관련된 부적합에만 작업을 사용할 수 있는 경우 주문 유형(*구매 주문* 또는 *판매 주문*)을 선택합니다.

1. 페이지를 닫습니다.

## <a name="additional-resources"></a>추가 리소스

- [품질 관리 개요](quality-management-processes.md)
- [품질 및 부적합 관리 활성화](enable-quality-management.md)
- [부적합 사항 생성 및 처리](tasks/create-process-non-conformance.md)
- [부적합 승인을 담당하는 작업자](quality-responsible-workers.md)
- [부적합 격리 구역](quality-quarantine-zones.md)
- [부적합 진단 유형](quality-diagnostic-types.md)
- [부적합 품질 비용](quality-charges.md)
- [부적합 문제 유형](quality-operations.md)
- [창고 공정을 위한 품질 관리](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
