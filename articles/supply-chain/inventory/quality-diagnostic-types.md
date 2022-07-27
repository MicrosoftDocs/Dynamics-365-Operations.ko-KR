---
title: 부적합 진단 유형
description: 이 항목에서는 부적합에 사용할 수 있는 진단 유형을 사용하고 생성하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestDiagnosticType, InventTestCorrection
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: edaa3a8b5c6446f039f33589166d832dcd9d0b9a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449368"
---
# <a name="diagnostic-types-for-nonconformances"></a>부적합 진단 유형

[!include [banner](../includes/banner.md)]

이 항목에서는 부적합에 사용할 수 있는 진단 유형을 사용하고 생성하는 방법에 대해 설명합니다.

**진단 유형** 페이지를 사용하여 진단 작업의 분류를 정의합니다. 그런 다음 부적합에 대한 수정 사항을 생성할 때 진단을 선택합니다. 수정은 승인된 부적합에 대해 취해야 하는 진단 조치 유형과 해당 조치를 취해야 하는 사람을 지정합니다. 또한 요청된 완료 날짜와 계획된 완료 날짜를 지정합니다.

## <a name="examples-of-diagnostic-types"></a>진단 유형 예시

당신은 제조 회사에서 일하고 있으며 여러 품목이 품질 테스트에 실패했습니다. 해당 품목은 검역소로 이동되어 부적합품으로 표시됩니다. 문제 해결을 통해 세부 정보를 추적하기 위해 Microsoft Dynamics 365 Supply Chain Management에 부적합 레코드가 생성됩니다.

이 경우, 물품을 포장하는 기계의 베어링이 손상되어 과열되어 품질 문제가 발생합니다. 이 문제에 대한 수정은 기계의 부품을 교체하는 것입니다.

진단 유형을 구성할 때 여러 레코드를 생성할 수 있으며 각 레코드는 시스템에 발생할 수 있는 다른 유형의 문제를 나타냅니다. 또는 기계 수리를 나타내는 하나의 일반 진단 유형을 작성할 수 있습니다.

## <a name="create-a-diagnostic-type"></a>진단 유형 만들기

1. **재고 관리 \> 설정 \> 품질 관리 \> 진단 유형** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 이후 새 행에 대해 다음 필드를 설정합니다.

    - **진단** – 진단 유형의 고유 ID 또는 이름을 입력합니다.
    - **설명** – 진단 유형에 대한 자세한 설명을 입력합니다.

1. 페이지를 닫습니다

## <a name="additional-resources"></a>추가 리소스

- [품질 관리 개요](quality-management-processes.md)
- [품질 및 부적합 관리 활성화](enable-quality-management.md)
- [부적합 승인을 담당하는 작업자](quality-responsible-workers.md)
- [부적합 격리 구역](quality-quarantine-zones.md)
- [부적합 문제 유형](quality-problem-types.md)
- [부적합 품질 비용](quality-charges.md)
- [부적합 작업](quality-operations.md)
- [창고 공정을 위한 품질 관리](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
