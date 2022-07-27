---
title: 예측 정확도 모니터링
description: 이 항목에서는 Dynamics 365 Supply Chain Management가 계산하는 예측 정확도의 유형을 설명하고 정확도 값을 보는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4246a277aa5d88193c18336cb1de69916ec2a3c2
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447856"
---
# <a name="monitor-forecast-accuracy"></a>예측 정확도 모니터링

[!include [banner](../includes/banner.md)]

이 항목에서는 Microsoft Dynamics 365 Supply Chain Management가 계산하는 예측 정확도의 유형을 설명하고 정확도 값을 보는 방법에 대해 설명합니다.

Supply Chain Management는 다음 유형의 예측 정확도를 계산합니다.

-   기준 계획에서 사용하는 과거 예측을 과거 수요와 비교하는 과거 예측 정확도. 과거 예측 정확도에 대한 값(절대값 및 백분율 값 모두)을 보려면 **수요 예측 세부 정보** 페이지에서 **정확도 표시** 를 클릭합니다.
-   예측을 생성하는 데 사용되는 예측 모델의 예상 정확도입니다. **수요 예측 세부 정보** 페이지의 **모델 세부 정보 - MAPE** 아래에서 정확도 백분율을 볼 수 있습니다. 

> [!NOTE]
> 수요 예측 Microsoft Azure 기계 학습을 사용하는 경우 내부 모델 정확도 계산은 테스트 데이터 세트를 기반으로 합니다. 테스트 데이터 세트의 크기를 지정하려면 **수요 예측 매개 변수** 페이지에서 **TEST\_SET\_SIZE\_PERCENT** 매개 변수를 설정합니다. 예를 들어 값을 **20** 으로 으로 설정하면 과거 데이터의 마지막 20%는 내부 모델 정확도를 계산하는 데 사용됩니다.


## <a name="additional-resources"></a>추가 리소스

[조정된 예측 승인](authorize-adjusted-forecast.md)

[수요 예측을 계산할 때 과거 거래 데이터에서 이상치 제거](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]