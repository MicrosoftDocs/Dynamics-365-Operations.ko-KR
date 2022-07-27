---
title: 비용 요소 차원 구성원을 차원 구성원의 공통 집합에 매핑
description: 다른 비용 요소 차원 구성원을 공통 비용 요소 차원 구성원 집합에 매핑하여 데이터를 분석 목적의 공통 형식으로 병합할 수 있습니다.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMDimensionMember, CAMDimensionMapping
audience: Application User
ms.reviewer: roschlom
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b9ac59f305afd55edfcfb3b47bf38ddd44d92a706904f55a069a6a9fc9050825
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450274"
---
# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a>비용 요소 차원 구성원을 차원 구성원의 공통 집합에 매핑

[!include [banner](../includes/banner.md)]

다른 비용 요소 차원 구성원을 공통 비용 요소 차원 구성원 집합에 매핑하여 데이터를 분석 목적의 공통 형식으로 병합할 수 있습니다.

글로벌 기업에서 법정 회계 요구 사항을 준수하는 경우 여러 계정 차트를 사용할 수 있습니다. 다른 계정 차트에서 비용 요소 차원 구성원을 가져오면 계정이 혼합될 수 있습니다. 그러나 이러한 계정은 실제로는 동일한 특성을 가질 수 있고 공통 형식을 사용하여 해당 계정에 대한 비용을 분석하고 할당할 수 있습니다.

## <a name="map-cost-element-dimension-members-to-a-common-format"></a>비용 요소 차원 구성원을 공통 형식에 매핑
다음 예는 비용 관리자가 미국 계정 차트 구조와 프랑스 계정 차트 구조의 비용 요소 차원 구성원을 공통 비용 요소 차원 구성원 집합에 매핑하는 비용 요소 차원 구성원을 새로 만드는 방법을 보여 줍니다. 그런 다음 비용 요소 차원 구성원의 공통 집합을 사용하여 비용 회계 원장의 두 법인에서 비용 데이터를 분석할 수 있습니다.

| 원본: 미국 계정 차트                                          | 원본: 프랑스 계정 차트                                          | 비용 요소 차원 구성원의 새로운 공통 집합                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| 미국 계정 차트에서 가져온 비용 요소 차원 구성원 | 프랑스 계정 차트에서 가져온 비용 요소 차원 구성원 | 공통 집합에 대한 미국 및 프랑스 비용 요소 차원 구성원 매핑 |
| 5001: 영업                                                           | 5001: 영업 및 광고                                               | 5000: 영업 및 광고                                             |
| 5030: 광고                                                     | 6390: 주식 매수\*                                                    | 7000: 청소 경비                                                 |
| 7001: 청소 경비                                               | 7001: 출장 경비                                                      | 7001: 출장 경비                                                   |

\*주식 매수 프랑스 비용 요소 차원 구성원이 매핑되지 않았습니다.

## <a name="currency-conversion"></a>통화 환산
사용하는 다양한 계정 차트는 다른 통화를 사용하도록 설정될 수 있습니다. 이 경우 원가 요소 차원 구성원이 사용되는 원가 회계 원장에 정의된 대로 원가 데이터가 올바른 통화를 사용하여 처리되도록 통화 환산을 지정해야 합니다. 앞의 예에서 원가 회계 원장에 미국 달러(USD)가 사용되는 경우 매핑된 원가 요소 차원 구성원에 대한 거래를 처리하려면 USD에서 유로(EUR)로의 통화 환산을 만들어야 합니다.

## <a name="update-mappings-at-any-time"></a>언제든지 매핑 업데이트
비용 요소 차원에 대한 매핑 정의는 언제든지 업데이트할 수 있습니다. 매핑은 날짜가 적용되지 않으므로 다음에 비용 거래를 처리하거나 비용 계산을 실행할 때 변경이 적용됩니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]