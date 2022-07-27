---
title: 부적합 작업에 대한 요금
description: 이 주제에서는 부적합 작업에 사용할 수 있는 품질 요금을 생성하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestMiscCharges
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac3306f3f9215ab03f408b8026f335dcf496515a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449371"
---
# <a name="charges-for-nonconformance-operations"></a>부적합 작업에 대한 요금

[!include [banner](../includes/banner.md)]

이 주제에서는 부적합 작업에 사용할 수 있는 품질 요금을 생성하는 방법에 대해 설명합니다.

**품질 요금** 페이지를 사용하여 부적합 작업에 추가할 수 있는 요금 유형을 정의합니다. 요금을 사용하면 부적합 제품에 대해 고객에게 지불해야 하는 수수료 또는 청구 또는 귀하가 받은 부적합 제품에 대해 공급업체가 귀하에게 지불해야 하는 요금에 대한 세부 정보를 추적할 수 있습니다. 비용을 사용하여 외부 공급업체 또는 서비스가 작업을 수행하는 데 필요한 비용을 추적할 수도 있습니다.

## <a name="examples-of-quality-charges"></a>품질 요금의 예

귀하는 제조 업체에서 일하고 있습니다. 귀하의 회사는 여러 공급업체와 계약을 맺고 있습니다. 이러한 계약은 정시 선적, 손상 및 품목의 제품 품질에 대한 표준을 설명합니다. 마찬가지로 여러 고객이 반품, 손상 및 제품 품질에 대해 회사와 계약을 맺었습니다.

수수료 구조는 각 상황에 대해 정의되고 계약에 명시됩니다. *손상*, *지연 배송* 및 *품질* 과 같은 다양한 유형의 비용을 설명하도록 품질 비용을 구성할 수 있습니다. 그런 다음 부적합을 생성할 때 하나 이상의 작업을 추가합니다. 각 작업에 대해 **요금** 을 선택하여 요금에 대한 세부 정보를 정의합니다.

## <a name="create-a-quality-charge"></a>품질 요금 생성

1. **재고 관리 \> 설정 \> 품질 관리 \> 픔질 요금** 으로 이동합니다.
1. 작업 창에서 **새로 만들기** 를 선택하여 그리드에 행을 추가합니다. 이후 새 행에 대해 다음 필드를 설정합니다.

    - **요금 코드** – 품질 요금에 대한 고유 ID 또는 이름을 입력합니다.
    - **설명** – 품질 요금에 대한 자세한 설명을 입력합니다.

1. 페이지를 닫습니다

## <a name="add-a-quality-charge-to-an-operation-for-a-nonconformance"></a>부적합에 대한 작업에 품질 비용 추가

부적합에 작업을 추가하고 요금을 부과하는 방법에 대한 자세한 내용은 [부적합에 대한 작업](quality-operations.md)을 참조하세요.

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
