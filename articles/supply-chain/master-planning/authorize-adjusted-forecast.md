---
title: 조정된 예측 승인
description: 모든 예측 데이터를 즉시 승인해야 하는 것은 아닙니다. 이 문서에서는 예측이 승인된 기간을 지정하는 방법을 설명합니다. 또한 특정 회사 및 예측 모델에 대한 예측 권한을 부여하는 방법에 대해서도 설명합니다.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f9ceeb01675a44388862e1dede11551d3a60bdc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448138"
---
# <a name="authorize-an-adjusted-forecast"></a>조정된 예측 승인

[!include [banner](../includes/banner.md)]

모든 예측 데이터를 즉시 승인해야 하는 것은 아닙니다. 이 문서에서는 예측이 승인된 기간을 지정하는 방법을 설명합니다. 또한 특정 회사 및 예측 모델에 대한 예측 권한을 부여하는 방법에 대해서도 설명합니다.

모든 예측 데이터를 즉시 승인해야 하는 것은 아닙니다. 예측이 승인된 기간의 시작 날짜와 종료 날짜를 지정할 수 있습니다. 이 기능을 사용하면 특정 버킷을 고정할 수 있습니다. 

지정하는 시작 및 종료 날짜는 예측이 생성되는 버킷의 시작 및 종료 날짜와 일치해야 합니다. 시스템은 이 제한을 적용하고 조정이 필요한 경우 날짜를 자동으로 조정합니다. 

**인증** 페이지의 **세부 정보** 탭에서 가장 최근에 생성된 예측에 대한 세부 정보를 볼 수 있습니다. 

회사 및 예측 모델을 선택하여 예측을 사용할 수 있도록 승인할 수 있습니다. 기본적으로 그리드에는 수요 예측이 생성된 모든 회사가 포함됩니다. 각 회사에 대해 기준 계획 매개 변수에 설정된 현재 예측 계획에 해당하는 예측 모델이 미리 채워져 있습니다. 그러나 이 예측 모델을 해당 회사에 속한 모든 예측 모델로 변경할 수 있습니다. 선택한 회사에 대해 예측 수요 데이터가 생성되지 않은 경우 가져올 때 경고 메시지가 표시됩니다. 

**베이스라인 수요 예측에 대한 수동 조정 저장** 확인란이 작동하는 방법을 이해하는 것이 매우 중요합니다. 통계 기준선 예측을 수동으로 조정한 경우 이 확인란이 선택 취소된 경우에도 조정된 값을 사용할 수 있습니다. 그러나 승인 후 변경 사항은 폐기됩니다. 따라서 다음에 예측이 생성될 때 해당 예측은 통계적 예측일 뿐이며 **수요 예측으로 수동 조정 이전** 이 선택된 경우에도 수동 재정의가 없습니다. 따라서 **베이스라인 수요 예측에 대한 수동 조정 저장** 확인란을 선택하여 모든 수동 변경 사항을 유지하거나 취소할 수도 있습니다.

## <a name="additional-resources"></a>추가 리소스

[기준선 예측을 수동으로 조정](manual-adjustments-baseline-forecast.md)

[예측 정확도 모니터링](monitor-forecast-accuracy.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]