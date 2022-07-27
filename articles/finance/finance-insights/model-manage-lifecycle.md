---
title: 모델 관리 수명 주기
description: 이 항목에서는 조직의 기계 학습 모델이 생성하는 예측을 최적화하기 위한 유지 관리 방법에 관해 설명합니다.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 0b16cfdce801e8a63b47397526b47995018b99c9
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451003"
---
# <a name="model-management-lifecycle"></a>모델 관리 수명 주기

[!include [banner](../includes/banner.md)]

이 항목에서는 조직의 기계 학습 모델이 생성하는 예측을 최적화하기 위한 유지 관리 방법에 관해 설명합니다.

샌드박스 환경에서 AI 모델을 교육한 다음 관리형 솔루션을 사용하여 프로덕션 환경에 배포하는 것이 좋습니다. 이 접근 방식은 모델 수명 주기를 관리하기 위한 올바른 제어를 보장하는 데 도움이 됩니다.

AI 모델은 사용 가능한 송장 및 고객 데이터에 기반을 두기 때문에 샌드박스 환경에 프로덕션 데이터의 최신 복사본이 있어야 합니다. [고객 지불 예측 사용](use-customer-payment-predictions.md)의 단계에 따라 모델의 학습을 시작할 수 있습니다. 모델이 재학습된 후 [초기 고객 지불 예측 모델 평가](evaluate-payment-prediction.md)에 설명된 대로 결과를 평가합니다. [예측 모델 개선](improve-model.md)의 정보를 사용하여 모델 개선에 도움이 될 수 있는 기능 및 필터 조합을 실험해보세요.

학습 결과가 만족스러우면 [AI 모델 배포](/ai-builder/distribute-model)의 단계에 따라 모델을 프로덕션 환경으로 전환합니다.
