---
title: 수요 예측을 계산할 때 과거 거래 데이터에서 이상치 제거
description: 이번에는 수요 예측을 계산하는 데 사용되는 과거 데이터에서 이상치를 제외하는 방법을 설명합니다. 이상치를 제외하면 예측 정확도를 높일 수 있습니다.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastParameters, ReqDemPlanOutlierQuerySetup, ReqDemPlanOutlierQueryPreview
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72621
ms.assetid: 88a964af-14eb-4c5c-945b-388e5908362c
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc0826d3a0dd8ded19590867e9a8138bb772c89a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448132"
---
# <a name="remove-outliers-from-historical-transaction-data-when-calculating-a-demand-forecast"></a>수요 예측을 계산할 때 과거 거래 데이터에서 이상치 제거

[!include [banner](../includes/banner.md)]

이번에는 수요 예측을 계산하는 데 사용되는 과거 데이터에서 이상치를 제외하는 방법을 설명합니다. 이상치를 제외하면 예측 정확도를 높일 수 있습니다.

예측 정확도를 향상시키기 위해 이상치를 제외할 수 있습니다. 이는 선택적 작업입니다. 다음은 절차의 개요입니다.

1.  **기준 계획** &gt; **설치** &gt; **수요 예측** &gt; **이상치 제거** 를 클릭하여 쿼리를 사용하여 제외할 트랜잭션을 선택할 수 있는 **이상치 제거** 페이지를 엽니다.
2.  쿼리가 적용되는 회사를 선택한 다음 이름과 설명을 입력합니다. **쿼리 날짜** 필드는 자동으로 현재 날짜로 설정됩니다.
3.  쿼리가 기록 데이터에서 찾은 트랜잭션을 제외하려면 **활성** 확인란을 선택합니다. 이 설정은 기준 예측을 생성할 때 적용됩니다.
4.  **이상치 제거 쿼리** 페이지에서 기준 예측을 계산할 때 제외할 트랜잭션을 정의하는 기준을 추가, 제거 및 선택할 수 있습니다. 예를 들어 제외할 특정 품목이나 주문 거래를 선택합니다.
5.  **트랜잭션 표시** 를 클릭합니다. **이상치 트랜잭션** 페이지에는 쿼리에 정의한 기준을 충족하고 수요 예측이 계산될 때 기록 데이터에서 제외되는 트랜잭션이 나열됩니다.

**참고:** 기존 쿼리를 기반으로 하는 쿼리를 만들 수도 있습니다. 복사할 쿼리를 선택한 다음 **복제** 를 클릭합니다. **쿼리 날짜** 필드는 버전을 식별합니다. 쿼리를 그대로 사용하거나 **쿼리 편집** 을 클릭하여 기준을 수정할 수 있습니다. 선택적으로 새 쿼리의 이름과 설명을 수정할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

[수요 예측 개요](introduction-demand-forecasting.md)

[예측 정확도 모니터링](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]