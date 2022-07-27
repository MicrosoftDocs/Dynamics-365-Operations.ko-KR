---
title: 부적합 승인을 담당하는 작업자
description: 이번에는 부적합 승인을 담당하는 작업자를 구성하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: 5fd1c7c86ac8627bd332bc578e98b4d7f091cdc8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448855"
---
# <a name="workers-responsible-for-approving-nonconformances"></a>부적합 승인을 담당하는 작업자

[!include [banner](../includes/banner.md)]

이번에는 부적합 승인을 담당하는 작업자를 구성하는 방법에 대해 설명합니다.

사용자가 수정 또는 작업과 같은 세부 정보 입력을 시작하려면 먼저 부적합을 승인해야 합니다. 사용자가 부적합을 승인하거나 거부하려면 먼저 사용자 ID(사용자 기록)가 작업자 기록에 연결되어야 합니다. 선택적으로 품질을 담당하는 작업자를 구성한 후, 한 작업자가 다른 작업자를 대신하여 작업을 승인하도록 허용할 수 있습니다.

## <a name="enable-a-user-for-nonconformance-processing"></a>부적합 처리를 위해 사용자 활성화

사용자가 부적합을 승인하거나 거부하려면 먼저 사용자 기록을 작업자 기록에 연결해야 합니다. 그러면 승인 필드가 자동으로 설정되고 현재 사용자가 작업표에 대해 자동으로 채워질 수 있습니다. 사용자가 문서 메모를 사용하려면 먼저 사용자 옵션에서 문서 처리를 활성화해야 합니다.

1. **시스템 관리 \> 사용자 \> 사용자** 로 이동합니다.
1. 부적합을 승인하거나 거부할 수 있는 사용자를 찾아 엽니다.
1. **사람** 필드를 현재 사용자 기록와 관련된 작업자의 이름으로 설정합니다.
1. 작업 창에서 **사용자 옵션** 을 선택합니다.
1. 현재 사용자 기록에 대한 **옵션** 페이지의 **환경 설정** 탭에서 **문서 처리 사용** 옵션을 *예* 로 설정합니다.
1. 페이지를 닫습니다.

## <a name="define-workers-that-are-responsible-for-quality"></a>품질을 책임지는 작업자 정의

1. **재고 관리 \> 설정 \> 품질 관리 \> 품질을 담당하는 작업자** 로 이동합니다.
2. 작업 창에서 **새로 만들기** 를 선택합니다.
3. **작업자** 필드에서 품질 데이터를 입력하는 작업자를 선택합니다.
4. **작업자 책임** 필드에서 선택한 작업자가 대신 작업에 입력하는 작업자를 선택합니다. 부적합이 생성 및 업데이트되면 이 작업자는 기본적으로 **작업자** 필드에 입력됩니다.

## <a name="additional-resources"></a>추가 리소스

- [품질 관리 개요](quality-management-processes.md)
- [품질 및 부적합 관리 활성화](enable-quality-management.md)
- [품질 요금](quality-charges.md)
- [부적합 격리 구역](quality-quarantine-zones.md)
- [부적합 진단 유형](quality-diagnostic-types.md)
- [부적합 품질 비용](quality-charges.md)
- [부적합 작업](quality-operations.md)
- [창고 공정을 위한 품질 관리](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
