---
title: 표준 비용에 대한 원가 계산 버전에 대한 제한 사항
description: 이 토픽에서는 표준 비용에 대한 원가 계산 버전에 적용되는 제한 사항에 대해 설명합니다.
author: AndersGirke
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2028cdabde3d01de16050b38893ec9e42353ae542be7a0cd7362cf62e9315170
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446965"
---
#  <a name="restrictions-on-costing-versions-for-standard-costs"></a>표준 비용에 대한 원가 계산 버전에 대한 제한 사항

[!include [banner](../includes/banner.md)]

이 토픽에서는 표준 비용에 대한 원가 계산 버전에 적용되는 제한 사항에 대해 설명합니다. 

다음 제한 사항은 표준 원가 계산 원칙을 준수하는 데 도움이 됩니다.

-  비용은 항목 비용에 포함되어야 합니다. 제조 항목에 대한 비용은 BOM(자재 명세서) 및 경로 정보의 상각 불변 비용을 나타냅니다. 따라서 비용은 단가에 포함되어야 합니다. 구매한 항목에 대한 비용도 항목의 단가에 포함됩니다.

-  제조 품목의 표준 비용 계산은 표준 비용에 대한 원가 계산 버전의 원가 기록을 기반으로 해야 합니다. 비용 데이터의 대체 소스는 구매 항목에 대한 구매 가격 거래 계약과 같은 계획된 비용에 대한 원가 계산 버전에서만 사용할 수 있습니다. 비용 데이터의 대체 소스는 BOM 계산 그룹에서 정의합니다.

-  BOM 계산은 단일 수준 분해 모드에서 수행해야 합니다.

표준 비용에 대한 항목 비용 데이터는 표준 비용 또는 계획 비용이 포함된 다른 원가 계산 버전으로 복사할 수 있습니다. 그러나 이 항목의 앞부분에 나열된 제한 사항이 계획 비용에 적용되지 않기 때문에 계획 비용에 대한 항목 비용 데이터는 표준 비용이 포함된 비용 버전으로 복사할 수 없습니다.

## <a name="related-topics"></a>관련 토픽

[원가 계산 버전 개요](costing-versions.md)

[비제조 환경에서 표준 비용 업데이트](update-standard-costs-non-manufacturing-environment.md)

[제조 항목에 대한 표준 원가 유지 준비](update-standard-costs-manufacturing-environment.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]