---
title: 부적합 격리 구역
description: 이번에는 부적합에 대한 격리 영역을 만들고 사용하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQuarantineZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 207950a2ff4057853488f75d0e302a049d228b76
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449116"
---
# <a name="quarantine-zones-for-nonconformances"></a>부적합 격리 구역

[!include [banner](../includes/banner.md)]

이번에는 부적합에 대한 격리 영역을 만들고 사용하는 방법에 대해 설명합니다.

**격리 구역** 페이지를 사용하여 부적합에 할당할 수 있는 구역을 정의합니다. 부적합을 생성할 때 **부적합** 페이지의 **일반** 탭에서 **격리 구역** 및 **격리 유형** 필드를 설정할 수 있습니다. **격리 구역** 필드는 일반적으로 품목이 있는 지역 또는 위치를 나타냅니다. **격리 유형** 필드는 품목을 *제한된 사용* 또는 *사용할 수 없음* 으로 정의합니다.

부적합 또는 부적합에 대한 수정 보고서를 인쇄할 때 품목이 있는 격리 구역을 볼 수 있습니다.

부적합에 대한 부적합 태그를 인쇄할 수도 있습니다. 이 보고서에서는 할당된 격리 구역과 사용에 대한 정보를 표시하여 결함 있는 원자재를 처리하는 방법에 대한 지침을 제공합니다. 격리 구역은 재고 위치 또는 작업 리소스에 해당할 수 있습니다.

## <a name="examples-of-quarantine-zones"></a>격리 구역 예시

### <a name="example-1"></a>예시 1

귀하는 텔레비전, 스피커 및 미디어 플레이어를 생산 및 유통하는 전자 제품 제조 업체에서 일하고 있습니다. 이 경우 각 제품 유형을 나타내도록 격리 구역을 구성할 수 있습니다.

### <a name="example-2"></a>예시 2

3개의 빈과 2개의 랙은 부적합 품목을 보관하는 데 사용됩니다. 이 경우 각 빈과 랙에 대해 각각 5개의 격리 영역을 구성할 수 있습니다.

## <a name="create-a-quarantine-zone"></a>격리 구역 생성

1. **재고 관리 \> 설정 \> 품질 관리 \> 격리 구역** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 이후 새 행에 대해 다음 필드를 설정합니다.

    - **격리 구역** – 격리 구역의 고유 ID 또는 이름을 입력합니다.
    - **설명** – 격리 구역에 대한 자세한 설명을 입력합니다.

1. 페이지를 닫습니다.

## <a name="additional-resources"></a>추가 리소스

- [품질 관리 개요](quality-management-processes.md)
- [품질 및 부적합 관리 활성화](enable-quality-management.md)
- [부적합 승인을 담당하는 작업자](quality-responsible-workers.md)
- [부적합 문제 유형](quality-quarantine-zones.md)
- [부적합 진단 유형](quality-diagnostic-types.md)
- [부적합 품질 비용](quality-charges.md)
- [부적합 작업](quality-operations.md)
- [창고 공정을 위한 품질 관리](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
