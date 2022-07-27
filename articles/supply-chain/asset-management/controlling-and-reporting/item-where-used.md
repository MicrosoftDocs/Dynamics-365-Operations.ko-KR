---
title: 항목 사용 위치
description: 이 토픽에서는 자산 관리에서 항목이 사용되는 위치에 대한 개요를 얻는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2308fc4fabe541b8affeba5860a3154f81e8903e4853fd36d777f15a503d9dd8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447034"
---
# <a name="item-where-used"></a>항목 사용 위치

[!include [banner](../../includes/banner.md)]

 

자산 관리에서 항목 사용 위치에 대한 개요를 얻기 위해 특정 항목을 계산할 수 있습니다. 결과는 항목이 수명 동안 사용된 컨텍스트를 보여줍니다. **항목 사용 위치** 페이지는 기본 자산 관리 메뉴에서 열 수 있으며 다음 페이지에서도 액세스할 수 있습니다.

- [자산 BOM](../objects/object-BOM.md)

- [자산 유형 기본값의 예비 부품](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [유지 관리 작업 유형 범주 및 유지 관리 작업 유형, 유지 관리 작업 유형 변형, 유지 관리 작업 거래 및 관리 보수 체크리스트](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [유지 관리 예측](../work-orders/maintenance-forecasts.md)

- [조달](../work-orders/procurement.md)

- [작업 주문 구매](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a>항목 사용 위치 계산하기

1. **자산관리** > **문의** > **항목 사용처** 를 클릭하거나 위 페이지 중 하나에서 **항목 사용 위치** 단추를 선택합니다.

2. **항목 사용 위치** 대화 상자의 **품목 번호** 필드에서 계산할 항목을 선택합니다.

3. **수준** 필드를 사용하여 기능 위치와 관련하여 항목 라인이 얼마나 상세하게 표시되기를 원하는지 나타낼 수 있습니다. 

    예를 들어, 필드에 숫자 "1"을 삽입하고 다단계 기능 위치 구조가 있는 경우 기능 위치에 대한 모든 항목 라인은 최상위 레벨에 표시됩니다. 따라서 라인의 관계/수량은 하위 수준에 위치한 기능적 위치에서 합산될 수 있습니다. 
    
    **레벨** 필드에 숫자 "0"을 입력하면 관련된 모든 기능적 위치 수준의 모든 항목 라인을 보여주는 자세한 결과를 볼 수 있습니다.

4. **포함** 섹션에서 계산에 포함할 토글 단추에서 "예"를 선택합니다.

5. **확인** 을 클릭하여 비용 계산을 시작합니다.

6. **항목 사용 위치** 탭에서 **그룹화 기준** 단추를 선택하여 필요한 계산 세부 수준을 표시합니다. 선택한 **그룹화 기준** 단추가 강조 표시됩니다. 단추를 클릭하여 활성화하거나 비활성화합니다.

7. 항목과 관련된 차원을 표시하려면 **차원 표시** 를 클릭하고 표시할 차원을 선택합니다.

## <a name="example"></a>예

아래 스크린샷에서 품목 번호 "1000"에 대한 항목 사용 계산의 예를 볼 수 있습니다.

![항목 사용 위치 계산의 예입니다.](media/12-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]