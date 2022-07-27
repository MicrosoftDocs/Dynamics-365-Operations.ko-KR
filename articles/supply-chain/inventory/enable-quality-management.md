---
title: 품질 및 부적합 관리 활성화
description: 이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management에서 품질 및 부적합 관리 기능을 설정하고 구성하는 프로세스에 대한 개요를 제공합니다.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c2c8b7e9a1a8d7692e1d2215e38de1b0f4d2d82
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448009"
---
# <a name="enable-quality-and-nonconformance-management"></a>품질 및 부적합 관리 활성화

[!include [banner](../includes/banner.md)]

이 토픽에서는 Microsoft Dynamics 365 Supply Chain Management에서 품질 및 부적합 관리 기능을 설정하고 구성하는 프로세스에 대한 개요를 제공합니다.

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a>품질 및 부적합 관리 활성화

다음 단계에 따라 시스템에서 품질 관리를 활성화하세요.

1. **재고 관리 \> 설정 \> 재고 및 창고 관리 매개 변수** 로 이동합니다.
1. **품질 관리** 탭에서 **품질 관리 사용** 옵션을 *예* 로 설정합니다.
1. **시간당 요금** 필드에 현지 통화로 시간당 노동 요금을 입력합니다. 시간당 요금은 부적합과 관련된 작업에 대한 비용을 계산하는 데 사용됩니다. 시간당 요금과 계산된 비용은 부적합에 대한 참조 정보를 제공합니다. 다른 기능과 상호 작용하지 않습니다.
1. **보고서 설정** 을 선택합니다.
1. 다양한 보고서 유형에 대한 새 줄을 추가하고 각 보고서에 사용할 문서 유형을 선택합니다.
1. 페이지를 닫습니다.
1. 페이지를 닫습니다.

## <a name="quality-management-configuration-process"></a>품질 관리 구성 프로세스

품질 관리 기능을 사용하고 품질 주문을 생성하려면 먼저 시스템과 전제 조건을 구성해야 합니다. 다음은 품질 관리를 구성하는 데 필요한 단계 목록입니다.

1. [품질 및 부적합 관리를 활성화](#enable-qm)합니다.
1. 선택 사항: [테스트 도구를 구성](quality-test-instruments.md)합니다.
1. [테스트를 구성](quality-tests.md)합니다.
1. [테스트 변수 및 결과를 구성](quality-test-variables.md)합니다.
1. [테스트 그룹을 구성](quality-test-groups.md)합니다.
1. 선택 사항: [품질 그룹을 구성하고 제품에 연결](quality-groups.md)합니다.
1. 선택 사항: [품질 연결을 구성](quality-associations.md)합니다.

구성이 완료되면 품질 주문 생성 및 처리를 시작할 수 있습니다. 품질 주문을 만들고 작업하는 방법에 대한 자세한 내용은 [품질 주문](quality-orders.md)을 참조하세요.

## <a name="nonconformance-management-configuration-process"></a>부적합 관리 구성 프로세스

부적합 관리 기능을 사용하고 부적합을 생성하려면 먼저 시스템과 전제 조건을 구성해야 합니다. 다음은 부적합 관리를 구성하는 데 필요한 단계 목록입니다.

1. [품질 및 부적합 관리를 활성화](#enable-qm)합니다.
1. [부적합 승인을 담당하는 작업자를 구성](quality-responsible-workers.md)합니다.
1. [문제 유형을 구성](quality-problem-types.md)합니다.
1. [격리 구역을 구성](quality-quarantine-zones.md)합니다.
1. [진단 유형을 구성](quality-diagnostic-types.md)합니다.
1. [작업을 구성](quality-operations.md)합니다.
1. 선택 사항: [품질 요금을 구성](quality-charges.md)합니다.

구성이 완료되면 부적합 생성 및 처리를 시작할 수 있습니다. 부적합을 생성하고 작업하는 방법에 대한 자세한 내용은 [부적합 생성 및 처리](tasks/create-process-non-conformance.md)를 참조하세요.

## <a name="additional-resources"></a>추가 리소스

- [품질 관리 개요](quality-management-processes.md)
- [품질 및 부적합 관리 활성화](enable-quality-management.md)
- [창고 공정을 위한 품질 관리](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
