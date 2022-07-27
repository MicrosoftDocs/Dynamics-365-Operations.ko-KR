---
title: 수요 예측을 위한 과거 데이터 가져오기
description: 정확한 수요 예측을 위해서는 품목별 또는 품목 할당 키별 과거 수요 데이터가 필요합니다. 이 토픽에서는 데이터 엔터티를 사용하여 모든 시스템에서 과거 수요 데이터를 가져오는 방법에 대해 설명하므로 수요 예측 데이터의 더 긴 기록이 있습니다.
author: ChristianRytt
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6dba31279541c20949dd1e86236103045c48b701
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449239"
---
# <a name="import-historical-data-for-demand-forecasts"></a>수요 예측을 위한 과거 데이터 가져오기

[!include [banner](../includes/banner.md)]

수요 예측의 정확성을 보장하려면 항목 또는 항목 할당 키별로 얻을 수 있는 만큼의 과거 수요 데이터가 있어야 합니다. 과거 수요 데이터를 아직 가져오지 않은 경우 Dynamics 365 Supply Chain Management의 **과거 외부 수요**(ReqDemPlanHistoricalExternalDemandEntity) 데이터 엔터티를 사용하여 가져옵니다.

**데이터 관리** 작업 영역에서 엔터티의 모든 필드에 대한 개요를 볼 수 있습니다.

1. **데이터 관리** 작업 영역을 엽니다.
2. **데이터 엔터티** 타일을 선택합니다.
3. **과거 외부 수요** 에 대한 엔터티 목록을 검색합니다.
4. **대상 필드** 를 선택합니다. 다음 엔터티 필드는 필수 항목입니다. 사이트(**DeliveringSiteId**), 날짜(**DemandDate**), 수량(**DemandQuantity**), 품목 번호(**ItemNumber**) 또는 항목 할당 키(**ProductAllocationKeyId**).

데이터 엔터티를 사용하려면 과거 수요 데이터가 포함된 Microsoft Excel 파일 또는 CSV(쉼표로 구분된 값) 파일이 있어야 합니다. 다음 예는 CSV 파일에서 데이터를 가져오는 방법을 보여줍니다.

가져온 후 데이터를 정리하는 방법을 포함하여 데이터를 가져오는 방법에 대한 자세한 내용은 [데이터 가져오기 및 내보내기 작업 개요](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) 및 관련 토픽을 참조하세요.

[통계 기준선 예측 생성](generate-statistical-baseline-forecast.md)도 참조하세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]