---
title: 유지 관리 작업 유형, 범주, 변형, 거래 및 체크리스트
description: 이 토픽에서는 자산 관리의 유지 관리 작업 유형 범주 및 유지 관리 작업 유형, 유지 관리 작업 유형 변형, 유지 관리 작업 거래 및 유지 관리 체크리스트에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetJobTypeDefaultForecast, EntAssetJobTrade, EntAssetJobTypeDefaultCopy, EntAssetChecklistVariableValueLookup, EntAssetChecklistTemplateCreate, EntAssetJobVariant, EntAssetJobTypeDefaultReference, EntAssetJobTypeDefaultChecklist, EntAssetJobTypeDefault, EntAssetJobType, EntAssetJobTypeDefaultChecklistCopy, EntAssetChecklistTemplate, EntAssetJobTypeDefaultDescription, EntAssetJobTypeLookup, EntAssetJobTypeDefaultToolCopy, EntAssetJobTypePreviewPart, EntAssetJobTypeDefaultTool, EntAssetJobTypeDefaultForecastCopy, EntAssetChecklistTemplateLookup, EntAssetJobGroup, EntAssetChecklistVariable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 54bd489a3c9be5be298ef75893b7acad38104a1379d20f853dd700635a3e058e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8446923"
---
# <a name="maintenance-job-types-categories-variants-trades-and-checklists"></a>유지 관리 작업 유형, 범주, 변형, 거래 및 체크리스트

[!include [banner](../../includes/banner.md)]

자산 유형은 모든 자산에 첨부됩니다. 자산 유형은 자산에서 수행할 수 있는 유지 관리 작업 유형(따라서 유지 관리 작업)을 정의합니다. 작업 주문을 생성할 때 유지 관리 작업 유형을 선택해야 합니다. 자산에 사용되는 자산 유형 설정과 관련된 유지 관리 작업 유형만 선택할 수 있습니다.

자산 및 유지 관리 작업 유형에 대한 그래픽 개요와 작업 주문에 대한 연결은 [기능 위치 및 자산](../overview/functional-locations-and-objects.md)을 참조하세요.

유지 관리 작업 유형 변형은 유지 관리 작업 유형에 설정할 수 있습니다. 유지 관리 작업 유형 변형은 크기(소형, 중형 또는 대형), 기간(매주, 격주, 1개월 또는 3개월) 및 구성(낮은 표준, 유연성 또는 고성능)과 같은 작업 유형의 변형을 정의합니다.

유지 관리 작업 거래는 기계, 전기 및 유압 거래와 같은 전문 거래에 대한 정보를 제공합니다. 능력 요구 사항은 유지 관리 작업 거래에 설정할 수 있습니다. 모든 유지 관리 작업 거래는 모든 유지 관리 작업 유형과 관련하여 사용할 수 있습니다. 작업 주문에 대한 유지 관리 작업 유형 변형 및/또는 유지 관리 작업 거래의 선택은 선택 사항입니다.

각 유지 관리 작업 유형에 대해 유지 관리 작업 유형 설정의 변형을 만들 수 있습니다. 예를 들어 이름이 **Service** 인 유지 관리 작업 유형이 있는 경우 해당 유지 관리 작업 유형에 대해 **Trucks 30,000km**, **Cars 30,000km** 및 **Vans 30,000km** 변형을 만들 수 있습니다.

유지 관리 작업 유형 범주는 개요를 위해 유지 관리 작업 유형 그룹을 수집하는 데 사용됩니다. 유지 관리 작업 유형 범주의 예에는 **교정**, **검사**, **정밀 검사** 및 **계측** 이 포함될 수 있습니다.

유지 관리 체크리스트 템플릿과 유지 관리 체크리스트 변수는 유지 관리 체크리스트를 설정하는 데 사용됩니다. 유지 관리 체크리스트는 유지 관리 작업 유형에 설정되고 작업 주문에 사용됩니다.

먼저 필수 유지 관리 작업 유형 범주, 유지 관리 작업 유형 변형 및 유지 관리 작업 거래를 설정합니다. 그런 다음 유지 관리 작업 유형을 만듭니다. 마지막으로 **유지 관리 작업 유형 기본값** 페이지에서 장비에 필요한 유지 관리 작업 유형의 모든 변형을 만듭니다. 해당 페이지에서 유지 관리 작업 유형 조합에 대한 예측, 유지 관리 체크리스트 및 도구를 설정할 수도 있습니다.

> [!NOTE]
> 유지 관리 작업 유형은 하나의 유지 관리 작업 유형 범주에만 관련될 수 있습니다.

## <a name="create-a-maintenance-job-type-category"></a>유지 관리 작업 유형 범주 만들기

1. **자산 관리** \> **설정** \> **작업** \> **유지 관리 작업 유형 범주** 를 선택합니다.
2. **새로 만들기** 를 선택합니다.
3. **유지 관리 작업** 유형 카테고리 필드에 유지 관리 작업 유형 카테고리의 ID를 입력합니다.
4. **이름** 필드에 이름을 입력합니다.

    유지 관리 작업 유형 범주를 유지 관리 작업 유형에 연결하면 작업 유형 필드에 이 유지 관리 **작업 유형** 범주와 관련된 유지 관리 작업 유형의 수가 표시됩니다.

![유지 관리 작업 유형 범주 페이지.](media/01-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type-variant"></a>유지 관리 작업 유형 변형 만들기

1. **자산 관리** \> **설정** \> **작업** \> **유지 관리 작업 유형 변형** 을 선택합니다.
2. **새로 만들기** 를 선택합니다.
3. **유지 관리 작업 유형 변형** 필드에 유지 관리 작업 유형 변형의 ID를 입력합니다.
4. **설명** 필드에 설명을 입력합니다.
5. **유지 관리 작업 유형** 빠른 탭에서 **추가** 를 선택하여 유지 관리 작업 유형을 추가합니다.
6. **유지 관리 작업 유형** 필드에서 유지 관리 작업 유형을 선택합니다.
7. 유지 관리 작업 유형 변형에 유지 관리 작업 유형을 더 추가하려면 5~6단계를 반복합니다.

    **세부 정보** 빠른 탭의 **작업 유형** 필드는 이 유지 관리 작업 유형 변형에 추가된 유지 관리 작업 유형의 수를 표시합니다.

![유지 관리 작업 유형 범주 페이지입니다.](media/02-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-trade"></a>유지 관리 작업 거래 만들기

1. **자산 관리** \> **설정** \> **작업** \> **유지 관리 작업 거래** 를 선택합니다.
2. **새로 만들기** 를 선택합니다.
3. **거래** 필드에 유지 관리 작업 거래의 ID를 입력합니다.
4. **설명** 필드에 설명을 입력합니다.
5. **기술** 빠른 탭에서 **추가** 를 선택하여 유지 관리 작업 거래와 관련된 새 기술을 추가합니다.
6. **기술** 필드에서 기술을 선택합니다.
7. **수준** 필드에서 기술을 선택합니다.
8. 유지 관리 작업 거래에 더 많은 기술을 추가하려면 5~7단계를 반복합니다.

    **세부 정보** 빠른 탭의 **기술** 필드는 이 유지 관리 작업 유형 변형에 추가된 유지 관리 작업 유형의 수를 표시합니다.

9. **인증서** 빠른 탭에서 **추가** 를 선택하여 유지 관리 작업 거래에 인증서를 추가합니다.
10. **인증서 유형** 필드에서 인증서를 선택합니다.
11. 유지 관리 작업 거래에 더 많은 인증서를 추가하려면 9~10단계를 반복합니다.

    **세부 정보** 빠른 탭의 **인증서** 필드는 이 유지 관리 작업 유형 변형에 추가된 유지 관리 작업 유형의 수를 표시합니다.

![유지 관리 작업 거래 페이지.](media/03-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-variable"></a>유지 관리 체크리스트 변수 만들기

유지 관리 작업 유형 기본값에서 유지 관리 체크리스트 라인을 생성할 때 유지 관리 체크리스트 유형을 선택해야 합니다. **변수** 는 유지 관리 체크리스트 유형 중 하나입니다. 작업 주문 라인과 관련된 유지 관리 체크리스트 라인의 범위에서 가능한 결과를 정의하는 데 사용됩니다. 변수를 사용하면 정확한 측정을 수행하지 않고도 미리 정의된 결과 집합을 만들 수 있습니다.

**예시 1**: **너무 높은 수준**, **너무 낮은 수준** 및 **범위 내 수준** 의 세 가지 값을 정의하여 오일 수준을 측정할 수 있습니다. 각 값에 대해 값 결과가 **통과**, **실패** 또는 **없음** 인지 정의합니다.

**예시 2:** 마모를 평가하기 위해 장비를 육안으로 검사합니다.

1. **자산 관리** \> **설정** \> **유지 관리 체크리스트** \> **유지 관리 체크리스트 변수** 를 선택합니다.
2. **새로 만들기** 를 선택합니다.
3. **변수** 필드에 유지 관리 체크리스트 변수의 ID를 입력합니다.
4. **이름** 필드에 이름을 입력합니다.
5. **일반** 빠른 탭에서 **추가** 를 선택하여 변수에 대한 라인을 추가합니다.

    순차적인 라인 번호가 **라인 번호** 필드에 자동으로 입력됩니다. 모든 라인을 추가한 후 필요에 따라 라인 번호를 변경할 수 있습니다. 라인을 선택하고 **아래쪽 화살표** 키를 누르면 순서의 다음 번호가 자동으로 다음 라인에 입력됩니다.

6. **값** 필드에 관련 설명을 입력합니다.
7. **결과** 필드에서 라인에 대한 결과를 선택합니다.

![유지 관리 체크리스트 변수 페이지.](media/04-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-template"></a>유지 관리 체크리스트 템플릿 만들기

유지 관리 체크리스트 템플릿은 작업자가 작업 주문을 올바르게 완료하기 위해 수행해야 하는 일반적인 작업 집합으로 사용할 수 있습니다. 템플릿은 유지 관리 작업 유형 기본값의 유지 관리 체크리스트 라인에서 참조됩니다. 템플릿은 여러 유지 관리 작업 유형 기본 라인에서 참조할 수 있습니다. 따라서 일반적인 유지 관리 체크리스트 작업 세트를 쉽게 재사용할 수 있습니다. 유지 관리 체크리스트 템플릿의 예로는 일반 안전 지침, 특정 펌프 또는 컨베이어 벨트의 유사한 모델에서 확인해야 하는 항목 및 조건 목록이 있습니다.

1. **자산 관리** \> **설정** \> **유지 관리 체크리스트** \> **유지 관리 체크리스트 템플릿** 을 선택합니다.
2. **새로 만들기** 를 선택합니다.

    템플릿 ID는 **유지 관리 체크리스트 템플릿** 필드에 자동으로 입력됩니다.

3. **이름** 필드에 유지 관리 체크리스트 템플릿의 이름을 입력합니다.
4. **유지 관리 체크리스트 라인** 빠른 탭에서 **추가** 를 선택하여 템플릿 라인을 추가합니다.

    순차적인 라인 번호가 **라인 번호** 필드에 자동으로 입력됩니다. 모든 라인을 추가한 후 필요에 따라 라인 번호를 변경할 수 있습니다. 라인을 선택하고 **아래쪽 화살표** 키를 누르면 순서의 다음 번호가 자동으로 다음 라인에 입력됩니다.

5. **유형** 필드에서 유지 관리 체크리스트 라인의 유형을 선택합니다. 각 유지 관리 체크리스트 유형에 대해 **라인 세부 정보** 빠른 탭에 관련 필드가 표시됩니다. 다음 값을 사용할 수 있습니다.

    - **텍스트** – 행에는 수행할 작업을 설명하는 텍스트가 있습니다. 작업자가 무언가를 확인하거나 검사하기를 원하지만 특정(측정 가능한) 결과를 기대하지 않는 경우 이 유지 관리 체크리스트 유형을 사용하세요. 이 유형을 선택한 후 **이름** 필드에 이름이나 제목을 입력합니다. **지침** 필드에 수행해야 하는 작업에 대한 설명을 입력합니다. 단계가 유지 관리 체크리스트에 필수인 경우 **필수** 옵션을 **예** 로 설정합니다.
    - **헤더** – 라인은 그 아래에 표시되는 유지 관리 체크리스트 라인을 그룹화하는 제목으로 사용됩니다. 이 유형은 특정 영역으로 나눌 수 있는 여러 유지 관리 체크리스트 행이 있는 경우에 유용합니다. 헤더는 유지 관리 체크리스트 라인이 많은 유지 관리 체크리스트를 완료할 작업자에 대한 개요를 제공합니다. 이 유형을 선택한 후 이름 필드에 설명이 포함된 **이름** 을 입력합니다.
    - **템플릿** – 이 라인은 기존 템플릿을 참조하는 데 사용됩니다. 이 유형을 선택한 후 **이름** 필드에 템플릿 이름을 입력합니다. **템플릿** 필드에서 템플릿을 선택합니다.
    - **변수** – 라인은 범위에서 가능한 결과를 정의하는 데 사용됩니다. 유지 관리 체크리스트 변수를 설정하는 방법에 대한 정보는 [유지 관리 체크리스트 변수 생성](#create-a-maintenance-checklist-variable) 섹션을 참조합니다. 이 유형을 선택한 후 **이름** 필드에 변수를 설명하는 이름을 입력합니다. **변수** 필드에서 변수를 선택합니다. **지침** 필드에 수행해야 하는 작업에 대한 설명을 입력합니다. 단계가 유지 관리 체크리스트에 필수인 경우 **필수** 옵션을 **예** 로 설정합니다.
    - **측정** – 라인은 특정 측정을 기록하는 데 사용됩니다. 미리 정의된 카운터와 관련되어야 하는 측정을 설정할 수 있습니다. 이 유형을 선택한 후 **이름** 필드에 템플릿 이름을 입력합니다. 이 단계가 유지 관리 체크리스트에 필수인 경우 **필수** 옵션을 **예** 로 설정합니다. 측정 라인을 카운터 등록으로 사용하려면 **카운터** 필드에서 카운터를 선택합니다. 그런 다음 관련 **단위** 필드가 자동으로 업데이트됩니다. 카운터를 선택한 경우 **값** 필드에서 업데이트 방법을 선택합니다. **최소 값** 및 **최대 값** 필드에 허용된 값 범위를 입력합니다. **지침** 필드에 수행해야 하는 작업에 대한 설명을 입력합니다.

        > [!NOTE]
        > 카운터 설정이 없는 **측정** 유형의 모든 라인은 자산 관리에서 자동 후속 조치가 없는 독립적인 측정 등록으로 처리됩니다. 마찬가지로 선택한 카운터 유형이 작업 주문과 관련된 자산에 없는 경우 유지 관리 체크리스트 작업은 독립적인 측정으로 처리됩니다. 카운터 값은 여러 번 변경할 수 있습니다. [작업 주문 수명 주기 상태](work-order-lifecycle-states.md)가 **프로세스 유지 관리 체크리스트** 옵션이 **예** 로 설정된 상태로 변경될 때까지 게시되지 않습니다.

    **세부 정보** 빠른 탭의 **검사** 필드에는 템플릿의 총 검사 목록 라인 수가 표시됩니다. 이 숫자에는 템플릿에서 참조한 기존 템플릿의 중첩 행이 포함됩니다.

![유지 관리 체크리스트 템플릿 페이지.](media/05-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type"></a>유지 관리 작업 유형 만들기

1. **자산 관리** \> **설정** \> **작업** \> **유지 관리 작업 유형** 을 선택합니다.
2. **새로 만들기** 를 선택합니다.
3. **유지 관리 작업 유형** 필드에 유지 관리 작업 유형의 ID를 입력합니다.
4. **이름** 필드에 이름을 입력합니다.

    **세부 정보** 빠른 탭에는 이 유지 관리 작업 유형에 대해 생성된 유지 관리 작업 유형 변형, 기술, 인증서, 후속 작업 및 자산 유형의 수에 대한 개요가 표시됩니다. **설정 라인** 필드는 이 유지 관리 작업 유형에 설정된 유지 관리 작업 유형 기본 라인의 수를 표시합니다. **자산** 필드에는 현재 이 유지 관리 작업 유형을 사용하는 활성 자산의 수가 표시됩니다.

5. **일반** 빠른 탭의 **유지 관리 작업 유형 범주** 필드에서 유지 관리 작업 유형 범주를 선택합니다.
6. 유지 관리 작업 유형에서 작업을 수행하기 전에 장비의 유지 관리를 중지해야 하는 경우 **유지 관리 가동 중지 시간** 옵션을 **예** 로 설정합니다.
7. **설명** 빠른 탭에서 유지 관리 작업 유형에 대한 설명을 입력합니다.
8. **유지 관리 작업 유형 변형** 빠른 탭에서 유지 관리 작업 유형에 변형을 추가할 수 있습니다.
9. **필수 기술** 및 **필수 인증서** 빠른 탭에서 유지 관리 작업 유형에 기술 및 인증서 요구 사항을 추가할 수 있습니다.
10. 특정 유지 관리 작업 유형을 다음에 수행해야 하는 경우 **후속 작업** 빠른 탭에 추가합니다. 또한 유지 관리 작업 유형과 관련된 유지 관리 작업 유형 변형 및 거래를 설정할 수 있습니다. 후속 작업이 이 유지 관리 작업 유형을 사용하는 작업이 시작되기 전 또는 후에 특정 일 수만큼 시작되어야 하는 경우 **지연 날짜** 필드에 일 수를 입력합니다. 양수는 관련 작업이 시작된 후의 일을 나타내고 음수는 관련 작업의 예정된 시작 전 일을 나타냅니다. 예를 들어 **5** 를 입력하면 유지 관리 작업 유형과 관련된 작업 시작 5일 후에 후속 작업이 시작됩니다. **-3** 을 입력하면 유지 관리 작업 유형과 관련된 작업의 예약된 시작 3일 전에 후속 작업이 시작됩니다.

    > [!NOTE]
    > 둘 이상의 유지 관리 작업 유형 라인을 추가하는 경우 라인의 순서는 해당 라인이 수행되어야 하는 순서를 나타냅니다. 순서는 목록의 맨 위에서 시작됩니다.

11. **자산 유형** 빠른 탭에서 자산 유형을 유지 관리 작업 유형에 추가할 수 있습니다.

![유지 관리 작업 유형 페이지.](media/06-setup-for-work-orders.png)

## <a name="create-maintenance-job-type-default-lines-and-related-forecasts-maintenance-checklists-tools-description-and-attachments"></a>유지 관리 작업 유형 기본 라인 및 관련 예측, 유지 관리 체크리스트, 도구, 설명 및 첨부를 생성합니다.

1. **자산 관리** \> **설정** \> **작업** \> **유지 관리 작업 유형 기본값** 을 선택합니다.

    –또는–

    **자산 관리** \> **설정** \> **작업** \> **유지 관리 작업 유형** 을 선택하고 유지 관리 작업 유형을 선택한 다음 **유지 관리 작업 유형 기본값** 을 선택합니다.

2. **새로 만들기** 를 선택합니다.
3. **기능 위치**, **자산 유형**, **제조사**, **모델** 및 **자산** 필드에서 유지 관리 작업 유형 기본값이 얼마나 구체적이어야 하는지에 따라 적절한 값을 선택합니다.
4. **유지 관리 작업 유형** 필드에서 자동으로 선택되지 않은 경우 유지 관리 작업 유형을 선택합니다.
5. **유지 관리 작업 유형 변형** 및 **거래** 필드에서 필요에 따라 유지 관리 작업 유형 변형 및 유지 관리 작업 거래를 선택합니다
6. **예측** 을 선택합니다.
7. **유지 관리 작업 유형 기본 예측** 페이지에서 시간, 항목 및 비용에 대한 예측을 수행할 수 있습니다. 관련 탭에서 **추가** 를 선택하고 유지 관리 작업 유형에 필요한 예측을 생성하도록 선택합니다.
8. **항목 예측** 탭에서 항목 라인에 표시되어야 하는 재고 차원을 선택할 수 있습니다. **재고** \> **차원** 을 선택하고 표시할 차원을 선택하고 **설정 저장** 옵션을 **예** 로 설정한 다음 **확인** 을 선택합니다.
9. **항목 예측** 탭에서 선택한 라인의 항목이 자산, 유지 관리 작업 유형 기본값, 예비 부품 및 작업 주문과 관련하여 자산 관리에서 사용되는 위치에 대한 개요를 보려면 **항목 사용 위치** 를 선택합니다. 

    **유지 관리 예측 합계** 빠른 탭에는 예측 합계의 개요가 표시됩니다. 이 개요에는 생성된 총 시간 및 예측 라인이 포함됩니다.

    > [!NOTE]
    > 다른 유지 관리 작업 유형에서 예측 설정을 복사하려면 **예측 복사** 를 선택한 다음 설정을 복사할 유지 관리 작업 유형을 선택합니다.

11. **저장** 을 선택하여 변경 내용을 저장합니다.
12. **유지 관리 작업 유형 기본 예측** 페이지를 닫고 **유지 관리 작업 유형 기본값** 페이지로 돌아갑니다.
13. **유지 관리 체크리스트** 를 선택합니다.
14. **유지 관리 작업 유형 기본 체크리스트** 페이지에서 선택한 유지 관리 작업 유형 기본값에 유지 관리 체크리스트 라인을 추가할 수 있습니다. **유지 관리 검사 라인** 빠른 탭에서 **새로 만들기** 를 선택하여 유지 관리 체크리스트 라인을 추가합니다.

    라인 번호는 유지 관리 체크리스트 라인의 순서를 나타내기 위해 **라인 번호** 필드에 자동으로 입력됩니다. 필요에 따라 라인 번호를 편집할 수 있습니다. 첫 번째 유지 관리 체크리스트 줄을 만든 후 해당 줄을 선택한 다음 **아래쪽 화살표** 키를 눌러 그 아래에 줄을 추가합니다. 또는 유지 관리 체크리스트 라인을 선택한 다음 **새로 만들기** 를 선택할 수 있습니다. 이 경우 선택한 유지 관리 체크리스트 행 위에 새 행이 추가됩니다.

15. **유형** 필드에서 라인 유형을 선택한 다음 유지 관리 체크리스트 유형과 관련된 정보를 추가합니다. 사용 가능한 유형 및 관련 필드에 대한 설명은 [유지 관리 체크리스트 템플릿 만들기](#create-a-maintenance-checklist-template) 섹션을 참조하세요.

    > [!NOTE]
    > 다른 유지 관리 작업 유형에서 유지 관리 검사 목록 설정을 복사하려면 **유지 관리 체크리스 복사** 를 선택한 다음 설정을 복사할 유지 관리 작업 유형을 선택합니다.
    >
    > 기존 유지 관리 체크리스트에서 템플릿을 쉽게 만들 수 있습니다. 그런 다음 여러 유지 관리 체크리스트에서 템플릿을 재사용할 수 있습니다. 새 템플릿은 활성 유지 관리 체크리스트의 정확한 복사본이 됩니다. **템플릿 만들기** 를 선택한 다음 템플릿 이름을 입력합니다. 기존 유지 관리 체크리스트를 새 템플릿을 참조하는 한 줄로 바꾸려면 **바꾸기** 옵션을 **예** 로 설정합니다. **유지 관리 체크리스트 템플릿** 세부 정보 페이지에서 템플릿의 내용을 볼 수 있습니다.

16. **저장** 을 선택하여 변경 내용을 저장합니다.
17. **유지 관리 작업 유형 기본값** 페이지로 돌아갑니다.
18. **도구** 를 선택합니다.
19. **유지 관리 작업 유형 기본 도구** 페이지에서 유지 관리 작업 유형에 사용해야 하는 도구(리소스)를 추가할 수 있습니다. **새로 만들기** 를 선택한 다음 **리소스** 필드에서 도구를 선택합니다.

    > [!NOTE]
    > 다른 유지 관리 작업 유형에서 도구 설정을 복사하려면 **도구 복사** 를 선택한 다음 설정을 복사할 유지 관리 작업 유형을 선택합니다.

20. **저장** 을 선택하여 변경 내용을 저장합니다.
21. **유지 관리 작업 유형 기본값** 페이지로 돌아갑니다.
22. **작업 설명** 을 선택합니다.
23. **작업 설명** 페이지에서 **편집** 을 선택한 다음 필요에 따라 선택한 유지 관리 작업 유형 기본값과 관련된 설명을 추가합니다.
24. **저장** 을 선택하여 설명을 저장합니다.

    여기에 작업 설명을 추가하면 유지 관리 작업 유형 페이지에서 **유지 관리 작업 유형** 에 대해 설정된 모든 설명이 무시됩니다. 여기에 작업 설명을 추가하지 않으면 유지 관리 작업 유형에 대해 설정된 설명이 사용됩니다. 설명은 유지 관리 작업 유형 또는 유지 관리 작업 유형 기본값을 사용하는 작업 주문으로 자동 전송됩니다.

25. **유지 관리 작업 유형 기본값** 페이지로 돌아갑니다.
26. 선택한 유지 관리 작업 유형 기본 라인에 첨부를 설정하려면 **문서 첨부** 를 선택합니다. 유지 관리 작업 유형 기본 라인에 설정된 첨부는 해당 유지 관리 작업 유형 기본 라인을 사용하는 작업 지시 라인에 자동으로 포함됩니다.
27. **새로 만들기** 를 선택한 다음 문서 유형을 선택합니다.
28. 문서 또는 파일을 업로드합니다.
29. **첨부** 페이지에서 필드를 설정합니다. 첨부 설정은 표준 문서 설정 기능을 사용합니다.
30. **저장** 을 선택하여 첨부 문서를 저장합니다.

    > [!NOTE]
    > **자산 관리 매개 변수** 페이지(**자산 관리** \> **설정** \> **자산 관리 매개 변수**)의 **문서 유형** 탭에서 첨부 문서 유형을 선택한 경우에만 유지 관리 작업 유형 기본 라인의 첨부가 작업 지시 보고서와 함께 인쇄됩니다. 첨부 파일의 예에는 특정 작업을 완료하는 방법이나 미리 정의된 유지 관리 체크리스트(유지 관리 작업 유형 기본 라인에 대해 유지 관리 체크리스트 기능을 사용하지 않는 경우)를 완료하는 방법을 설명하는 지침이 포함됩니다.

    **유지 관리 작업 유형 기본값** 페이지에서 각 행은 예상 시간 수와 항목, 비용, 유지 관리 체크리스트 및 도구에 대해 생성된 행 수를 표시합니다. **자산** 필드는 유지 관리 작업 유형 기본 라인과 관련된 활성 자산의 수를 표시합니다.

31. 유지 관리 작업 유형 기본값을 다른 유지 관리 작업 유형 기본값으로 복사하려면 다른 설정을 복사할 유지 관리 작업 유형 기본 행을 선택하고 **설정 복사** 를 선택한 다음 복사할 유지 관리 작업 유형 기본값을 선택합니다.
32. 현재 유지 관리 작업 유형 기본 라인을 사용하는 자산, 유지 관리 계획 또는 유지 관리 라운드 목록을 보려면 해당 라인을 선택한 다음 **사용자** 를 선택합니다.

![유지 관리 작업 유형 기본값 페이지.](media/07-setup-for-work-orders.png)

시스템이 작업 지시 라인에 사용해야 하는 사용 가능한 유지 관리 작업 유형 기본값을 선택하면 자산 및 관련 자산 유형 설정을 기반으로 선택됩니다. 자산 관리는 가능한 일치를 확인하기 위해 자산 유형과 관련된 유지 관리 작업 유형과 관련된 모든 유지 관리 작업 유형 기본 레코드를 살펴봅니다. 항상 가장 구체적인 조합을 먼저 확인합니다. 즉, 가장 구체적인 조합을 찾기 위해 자산 관리는 먼저 **거래** 필드에 가능한 일치 항목을 확인합니다. 일치하는 항목이 없으면 **유지 관리 작업 유형 변형** 필드의 일치 항목이 있는지 확인합니다. 일치하는 항목이 없으면 **유지 관리 작업 유형** 필드와 같은 방식으로 일치하는지 확인합니다(**무역**, **유지 관리 작업 유형 변형**, **유지 관리 작업 유형**, **자산**, **모델**, **제조업체**, **자산 유형**). 일치하는 항목이 없으면 유지 관리 작업 유형만 선택된 기본 레코드가 사용됩니다.

프로젝트 활동 ID는 생성한 각 유지 관리 작업 유형 기본 라인과 자동으로 연결됩니다. 프로젝트 활동은 **자산 관리 매개 변수** 페이지의 **자산** 탭에 있는 **유지 관리 예측 프로젝트** 필드에서 선택한 예측 프로젝트에서 생성됩니다. 프로젝트 활동의 목적은 작업 지시와 관련된 시간, 항목 및 비용에 대한 예측을 관리하는 것입니다. 유지 관리 작업 유형 예측은 자동으로 작업 지시 라인으로 전송되고 예측 프로젝트에서 작업 지시 라인에 대해 생성된 작업 지시 프로젝트로 복사됩니다. 프로젝트 활동의 목적은 작업 주문과 관련된 예측을 관리하는 것입니다.

유지 관리 작업 유형 기본 참조를 정기적으로 업데이트하도록 배치 작업을 설정하거나 작업을 수동으로 실행할 수 있습니다. 일괄 작업을 생성하거나 수동 업데이트를 실행하려면 **자산 관리** \> **정기** \> **예방 유지 관리** \> **유지 관리 작업 유형 기본 참조** 업데이트를 선택합니다.

## <a name="overview-of-maintenance-job-types-that-are-related-to-assets"></a>자산과 관련된 유지 관리 작업 유형 개요

필수 유지 관리 작업 유형 기본 조합을 생성한 후 **모든 자산** 페이지를 사용하여 특정 자산과 관련된 현재 유지 관리 작업 유형 기본값의 개요를 얻을 수 있습니다. 개요는 자산에 대해 선택된 자산 유형에 사용할 수 있는 모든 유지 관리 작업 유형 기본 조합을 보여줍니다. 이러한 조합에는 유지 관리 작업 유형 변형 및 유지 관리 작업 거래의 변형이 있는 조합이 포함됩니다.

1. **자산 관리** \> **공통** \> **자산** \> **모든 자산** 또는 **활성 자산** 을 선택합니다.
2. 목록에서 자산을 선택하여 유지 관리 작업 유형 조합의 개요를 확인합니다.
3. 작업 창에 있는 **일반** 탭의 **관련 정보** 그룹에서 **유지 관리 직업 유형** 을 선택합니다.

    왼쪽 창 **자산 유지 관리 작업 유형** 페이지에는 선택한 자산과 관련된 모든 유지 관리 작업 유형 조합의 목록이 표시됩니다.

4. 유지 관리 작업 유형 조합을 선택하여 유지 관리 체크리스트, 예측 및 도구에 대한 관련 설정을 확인합니다. **유지 관리 작업 유형 기본값** 빠른 탭의 **세부 정보** 섹션은 선택한 유지 관리 작업 유형 조합과 관련된 관련 유지 관리 체크리스트, 예상 시간, 항목 등의 수를 표시합니다.
5. 선택한 **유지 관리 작업 유형** 에 대한 세부 정보를 보려면 유지 관리 작업 유형을 선택합니다.

![자산 관리 작업 유형 페이지.](media/08-setup-for-work-orders.png)

## <a name="automatic-update-of-maintenance-job-type-forecasts"></a>유지 관리 작업 유형 예측의 자동 업데이트

자산 관리에서 다른 모듈에서 업데이트된 시간 비용, 품목 비용 및 비용에 대한 유지 관리 작업 유형 예측의 변경 사항을 자동으로 업데이트할 수 있습니다. 이러한 방식으로 유지 관리 작업 유형 예측이 항상 최신 비용 가격을 사용하도록 보장할 수 있습니다.

1. **자산 관리** \> **주기적** \> **예측** \> **유지 관리 작업 유형 예측 업데이트** 를 선택합니다.
2. **유지 관리 작업 유형 예측 업데이트** 대화 상자의 빠른 **포함할 레코드** 탭에서 필요에 따라 특정 유지 관리 작업 유형에 대한 선택 항목을 추가할 수 있습니다. **필터** 를 선택한 다음 **선택** 을 선택하여 선택합니다.
3. **백그라운드 실행** 빠른 탭에서 필요에 따라 자동 업데이트를 일괄 작업으로 설정할 수 있습니다.
4. **확인** 을 선택하여 예측 업데이트를 시작합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]