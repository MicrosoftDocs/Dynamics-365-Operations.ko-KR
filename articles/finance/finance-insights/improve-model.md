---
title: 예측 모델 개선
description: 이 항목에서는 예측 모델의 성능을 개선하는 데 사용할 수 있는 기능에 관해 설명합니다.
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
ms.openlocfilehash: 804c18c1b165fff99390db1fda22da0137249373
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8451012"
---
# <a name="improve-the-prediction-model"></a>예측 모델 개선

[!include [banner](../includes/banner.md)]

이 항목에서는 예측 모델의 성능을 개선하는 데 사용할 수 있는 기능에 관해 설명합니다. Microsoft Dynamics 365 Finance의 **고객 지불 예측** 작업 영역에서 모델 개선을 시작합니다. 개선 단계는 AI Builder에서 완료됩니다.

## <a name="select-historical-outcomes"></a>기록 결과 선택

먼저 송장에 대해 가능한 세 가지 결과 **정시**, **늦음**, **매우 늦음** 중 하나 이상을 선택합니다. 세 가지 결과를 모두 선택해야 합니다. 결과 선택을 취소하면 학급 프로세스에서 송장이 필터링되고 예측의 정확도가 낮아집니다.

[![결과 확인.](./media/confirm-3-outcomes.png)](./media/confirm-3-outcomes.png)

조직에 두 가지 결과만 필요한 경우 **늦음** 및 **매우 늦음** 임계값을 0일로 변경합니다. 이렇게 하면 예측을 **정시** 또는 **늦음** 의 이진 상태로 사실상 축소합니다.

## <a name="select-fields"></a>필드 선택

모델에 포함할 필드를 선택할 때 목록에는 Azure Data Lake의 데이터에 매핑되는 Microsoft Dataverse 테이블의 사용 가능한 모든 필드가 포함됩니다. 이러한 필드 중 일부는 선택하지 **않아야 합니다**. 선택하지 않아야 하는 필드는 다음 세 가지 범주 중 하나에 속합니다.

- 이 필드는 Dataverse 테이블에 필요하지만 Data Lake에 이를 뒷받침하는 데이터가 없습니다.
- 필드는 ID이므로 기계 학습 기능에 적합하지 않습니다.
- 필드는 예측 중에 사용할 수 없는 정보를 나타냅니다.

다음 섹션에서는 송장 및 고객 엔터티에 사용할 수 있는 필드를 보여주고 학습을 위해 선택하지 **않아야 하는** 필드를 나열합니다. 각 필드에 대해 지정된 범주는 이전 목록의 범주를 참조합니다.
 
### <a name="invoice-dataverse-table"></a>송장 Dataverse 테이블

다음 그림은 송장 테이블에 사용할 수 있는 필드를 보여줍니다.

[![송장 테이블에 사용할 수 있는 필드.](./media/available-fields.png)](./media/available-fields.png)

다음 필드는 학습을 위해 선택하면 안 됩니다.

- **송장 계정**(카테고리 2)
- **마감됨**(카테고리 3) – 이 필드는 송장을 학습(마감됨) 및 예측(마감되지 않음)으로 필터링하는 데 사용됩니다.
- **이름**(카테고리 1)
- **원본 ID**(카테고리 2)
- **원본 레코드**(카테고리 2)
- **원본 테이블**(카테고리 2)

### <a name="customer-dataverse-table"></a>고객 Dataverse 테이블

다음 그림은 고객 테이블에 사용할 수 있는 필드를 보여줍니다.

[![고객 테이블에 사용할 수 있는 필드.](./media/related-entities.png)](./media/related-entities.png)

다음 필드는 학습을 위해 선택하면 안 됩니다.

- **행 고유 키**(카테고리 2)

## <a name="filters"></a>필터

송장 또는 고객 테이블의 필드에 대한 필터 기준을 설정하여 학습에 사용되는 송장을 필터링할 수 있습니다. 예를 들어 합계가 특정 금액 이상인 송장만 포함하도록 임계값을 설정할 수 있습니다. 또는 특정 고객 그룹의 고객과 연결된 송장을 제외할 수 있습니다.

데이터 필터링에 대한 자세한 내용은 [예측 모델 만들기](/ai-builder/prediction-create-model#filter-your-data)를 참조하세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
