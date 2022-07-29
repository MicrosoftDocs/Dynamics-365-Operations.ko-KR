---
title: 양륙 비용 보고서
description: 이 토픽에서는 양륙 비용 모듈에 사용할 수 있는 다양한 유형의 보고서를 찾고 사용하는 방법에 대해 설명합니다.
author: sherry-zheng
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: cb0ea44c0924fc5d2c295a9285701d1f678c3473
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448450"
---
# <a name="landed-cost-reports"></a>양륙 비용 보고서

[!include [banner](../../includes/banner.md)]

## <a name="outstanding-invoices"></a>미지불 송장

미지불 송장 보고서에는 모든 항해와 관련된 다양한 비용 수준의 미지불 송장 목록이 포함되어 있습니다. 정기적으로 원장 거래 목록과 함께 항해 및 항해 비용을 조정하는 데 사용됩니다. 간접비는 청구된 후 보고서에서 제거됩니다.

미지불 송장 보고서를 생성하려면 다음 단계를 따르세요.

1. **양륙 비용 \> 보고서 \> 추적 \> 미지불 송장** 으로 이동합니다.
1. **미지불 송장** 대화 상자의 **날짜 기준** 필드에서 날짜를 지정합니다. 해당 날짜 또는 그 이전에 미지불된 모든 송장이 출력에 포함됩니다.
1. **표시** 에서 다음 옵션 중 하나를 선택합니다.

    - **청구되지 않은 비용** – 예상 비용 가치는 있지만 실제 비용은 없는 송장 발송물에 대한 비용을 포함합니다.
    - **재고가 청구되지 않음** – 송장이 발행되었지만 아직 구매 주문이 접수되지 않은 비용을 포함합니다.
    - **모두 청구되지 않음** - **청구되지 않은 비용** 옵션과 **청구되지 않은 재고** 옵션의 결과를 모두 포함합니다.

1. **새 비용 포함** 옵션을 *예* 로 설정하여 아직 실제 비용이 없고 해당 재고가 입고되지 않은 비용을 포함합니다. *아니요* 로 설정하면 보고서에 청구된 비용만 포함됩니다.
1. **보기** 섹션에서 보고서에 포함할 각 세부 정보 유형을 활성화합니다.
1. Microsoft Dynamics 365 Supply Chain Management의 다른 유형의 보고서와 마찬가지로 **대상** 빠른 탭을 사용하여 보고서의 출력 형식을 선택합니다.
1. Supply Chain Management의 다른 유형의 보고서에 대해 수행하는 것처럼 **포함할 레코드** 빠른 탭을 사용하여 보고서에 포함될 레코드를 추가로 제한합니다.
1. **확인** 을 선택하여 보고서를 생성합니다.

## <a name="activityprovider-analysis-reports"></a>활동/제공자 분석 보고서

활동/제공자 분석 보고서를 통해 각 제공자에 대한 예상 시간의 정확성을 검토할 수 있습니다.

활동/제공자 분석 보고서를 생성하려면 다음 단계를 따르세요.

1. 생성하려는 보고서 유형에 따라 다음 단계 중 하나를 수행합니다.

    - **양륙 비용 \> 보고서 \> 활동별 활동/제공자 분석** 으로 이동합니다. 이 경우 예상 시간은 활동별로 그룹화됩니다.
    - **양륙 비용 \> 보고서 \> 제공자별 활동/제공자 분석** 으로 이동합니다. 이 경우 예상 시간은 제공자별로 그룹화됩니다.

    **활동별 활동/제공자 분석** 대화 상자 또는 **제공자별 활동/제공자 분석** 대화 상자가 표시됩니다. 두 대화 상자 모두 동일한 옵션을 제공합니다.

1. Supply Chain Management의 다른 유형의 보고서와 마찬가지로 **대상** 빠른 탭을 사용하여 보고서의 출력 형식을 선택합니다.
1. Supply Chain Management의 다른 유형의 보고서에 대해 수행하는 것처럼 **포함할 레코드** 빠른 탭을 사용하여 보고서에 포함될 레코드를 추가로 제한합니다.
1. **확인** 을 선택하여 보고서를 생성합니다.

## <a name="voyage-costing-reports"></a>항해 비용 계산 보고서

항해 비용 계산 보고서는 보고서를 생성할 때 선택한 옵션에 따라 항목 비용과 Folio, 운송 컨테이너 또는 항해당 수입 비용을 표시합니다. 각 항해 비용 계산 보고서를 통해 실제 비용 대비 예상 항해 비용을 볼 수 있으며 여러 식별 요소로 분류할 수 있습니다.

항해 비용 계산 보고서를 생성하려면 다음 단계를 따르세요.

1. 생성하려는 보고서 유형에 따라 다음 단계 중 하나를 수행합니다.

    - **양륙 비용 \> 보고서 \> 비용 계산 \> 개별 비용별 항해 비용 계산** 으로 이동합니다. 이 경우 개별 비용 옵션은 비용 유형 코드당 비용 영역당 수입 비용을 표시합니다.
    - **양륙 비용 \> 보고서 \> 비용 계산 \> 보고 범주별 항해 비용 계산** 으로 이동합니다. 이 경우 수입 비용은 다양한 보고 범주로 분류됩니다. 비용 유형은 보고 범주별로 그룹화됩니다.

    **개별 비용별 항해 비용 계산** 대화 상자 또는 **보고 범주별 항해 비용 계산** 대화 상자가 나타납니다. 이러한 대화 상자는 비슷합니다. 이 절차의 나머지 부분에서 차이점이 기록됩니다.

1. **보고 범주별 항해 비용 계산** 대화 상자를 연 경우 **비용** 필드에서 다음 값 중 하나를 선택합니다.

    - **비용 가치** – 값은 자동 비용을 사용하여 계산되거나 비용 영역에서 수동으로 생성됩니다.
    - **예상** – 상품 수령 후 예상 비용이 설정됩니다.
    - **실제** – 주문이 청구된 후 실제 비용은 청구서의 비용으로 설정됩니다.
    - **최상** – 시스템은 앞의 세 가지 옵션 중 가장 정확한 옵션을 사용합니다. (이 옵션을 선택하는 것이 좋습니다.)

1. **항목별** 옵션을 *예* 로 설정하여 각 항목의 비용을 표시합니다. 항해당 비용을 표시하려면 *아니요* 로 설정합니다.
1. **보기** 섹션에서 비용을 분류할 범주를 선택합니다.
1. **차원** 섹션에서 보고서에 포함할 차원을 선택합니다.
1. Supply Chain Management의 다른 유형의 보고서와 마찬가지로 **대상** 빠른 탭을 사용하여 보고서의 출력 형식을 선택합니다.
1. Supply Chain Management의 다른 유형의 보고서에 대해 수행하는 것처럼 **포함할 레코드** 빠른 탭을 사용하여 보고서에 포함될 레코드를 추가로 제한합니다.
1. **확인** 을 선택하여 보고서를 생성합니다.

## <a name="shipping-container-receipts-list"></a>선적 컨테이너 입고 목록

선적 컨테이너 입고 목록에는 예상 날짜 또는 그 이전에 마감된 모든 미수량이 포함됩니다. 창고 직원은 이 보고서를 사용하여 선적 컨테이너의 예상 상품을 식별할 수 있습니다. 또한 상품이 선적 컨테이너에 도착할 때 상품을 수동으로 검증하는 데 사용할 수도 있습니다.

선적 컨테이너 입고 목록을 생성하려면 다음 단계를 따르세요.

1. **양륙 비용 \> 보고서 \> 추적 \> 선적 컨테이너 입고 목록** 으로 이동합니다.
1. **선적 컨테이너 입고 목록** 대화 상자의 **예상 날짜** 필드에 날짜를 지정합니다. 해당 날짜 또는 그 이전에 미입고된 수량은 출력에 포함됩니다
1. **차원** 섹션에서 보고서에 포함할 차원을 선택합니다.
1. Supply Chain Management의 다른 유형의 보고서와 마찬가지로 **대상** 빠른 탭을 사용하여 보고서의 출력 형식을 선택합니다.
1. Supply Chain Management의 다른 유형의 보고서에 대해 수행하는 것처럼 **포함할 레코드** 빠른 탭을 사용하여 보고서에 포함될 레코드를 추가로 제한합니다.
1. **확인** 을 선택하여 보고서를 생성합니다.

## <a name="expected-delivery-report"></a>예상 배송 보고서

예상 배송 보고서에는 항해, 배송 컨테이너, 폴리오, 품목 및 예상 배송 날짜에 대한 기본 정보가 포함됩니다.

예상 배송 보고서를 생성하려면 다음 단계를 따르세요.

1. **양륙 비용 \> 보고서 \> 추적 \> 예상 배송** 으로 이동합니다.
1. **예상 배송** 대화 상자의 **예상 날짜** 필드에서 최종 목적지 창고로의 상품 배송이 예상되는 날짜를 선택합니다. 예상 날짜가 해당 날짜 또는 그 이전이고 아직 수신되지 않은 모든 항해 노선은 출력에 포함됩니다.
1. 선택 사항: **공급업체 계정** 필드에서 특정 공급업체의 배송만 포함하도록 공급업체 계정을 선택합니다.
1. **차원** 섹션에서 보고서에 포함할 차원을 선택합니다.
1. Supply Chain Management의 다른 유형의 보고서와 마찬가지로 **대상** 빠른 탭을 사용하여 보고서의 출력 형식을 선택합니다.
1. Supply Chain Management의 다른 유형의 보고서에 대해 수행하는 것처럼 **포함할 레코드** 빠른 탭을 사용하여 보고서에 포함될 레코드를 추가로 제한합니다.
1. **확인** 을 선택하여 보고서를 생성합니다.