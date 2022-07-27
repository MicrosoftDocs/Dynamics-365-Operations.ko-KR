---
title: 재고 에이징 보고서 스토리지
description: 이 토픽에서는 재고 에이징 보고서를 실행하고 출력을 양식 및 차트로 사용할 수 있도록 하는 기능에 대해 설명합니다.
author: AndersGirke
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2019-01-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2ddddb0b1e377ed525b7c17fec5a4b3305573d0eba551bc03f075109a2ed769b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447331"
---
# <a name="inventory-aging-report-storage"></a>재고 에이징 보고서 스토리지

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management에서 **재고 에이징 보고서 스토리지** 보고서를 실행하고 출력을 양식 및 차트로 사용할 수 있도록 만들 수 있습니다. 양식에서 열 및 총 잔액은 구성된 레이아웃에 따라 동적으로 조정됩니다. 차트는 필터링을 지원하고 세부 정보로 드릴다운할 수 있는 시각적 개요를 제공합니다. 또한 **인벤토리 에이징 보고서** 라는 데이터 엔터티를 사용하면 **인벤토리 에이징 보고서 스토리지** 보고서 실행 결과를 Microsoft Excel 파일이나 PDF 파일과 같은 형식으로 내보낼 수 있습니다.

**인벤토리 에이징 보고서 스토리지** 보고서를 실행하는 이 방법은 출력에 많은 줄이 포함된 경우에 유용합니다. 예를 들어, 창고로 생성된 50,000개의 품목과 300개의 상점이 있고 품목, 사이트 및 창고별로 재고 에이징을 요청하는 경우 출력에는 많은 라인이 포함됩니다.

## <a name="enable-the-inventory-value-storage-report-feature"></a>재고 가치 저장 보고서 기능 활성화

이 기능을 사용하려면 먼저 시스템에서 활성화해야 합니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 설정을 사용하여 기능 상태를 확인하고 필요한 경우 활성화할 수 있습니다. 여기에서 기능은 다음과 같이 나열됩니다.

- **모듈** - 자산 관리
- **기능 이름** - 재고 에이징 보고서 스토리지

## <a name="run-an-inventory-aging-report-storage"></a>재고 에이징 보고서 스토리지 실행

1. **Cost Management \> 문의 및 보고 \> 재고 에이징 보고서 스토리지** 로 이동합니다.
1. **새로 만들기** 를 선택합니다.
1. **프로세스 식별자 – 이름** 필드에 보고서의 고유한 이름을 입력합니다.
1. **식별 – ID** 보고서를 선택하고 필요에 따라 필터링합니다.

    보고서 실행은 항상 일괄 작업으로 수행됩니다.

1. 일괄 작업이 완료되면 출력이 **재고 에이징 보고서 스토리지** 페이지에 표시됩니다.
1. 출력을 기존 그리드 레이아웃이 있는 양식으로 보려면 **세부 정보 보기** 를 선택합니다. 결과를 집계 차트로 보려면 **차트 보기** 를 선택합니다.

    > [!NOTE]
    > 양식에는 보고서 레이아웃에 정의된 부분합이 포함되지 않습니다.

**재고 에이징 보고서** 데이터 엔터티를 사용하면 **프로세스 식별자 - 이름** 필드에 대한 필터를 데이터 관리가 지원하는 형식으로 적용하여 **인벤토리 에이징 보고서 스토리지** 보고서의 출력을 내보낼 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]