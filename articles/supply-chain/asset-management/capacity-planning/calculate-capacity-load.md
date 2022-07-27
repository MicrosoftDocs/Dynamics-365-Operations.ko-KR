---
title: 최대 수용 작업량 계산
description: 이 토픽에서는 자산 관리에서 최대 수용 작업량을 계산하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCapacityLoad, EntAssetWorkOrderCapacityLoadCalculate, EntAssetWorkOrderCapacityLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eed75cd5268b19d819d42e764bdbb5e6f4c79a0a732c5023b3fc40da798e2ca1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447097"
---
# <a name="calculate-capacity-load"></a>최대 수용 작업량 계산

[!include [banner](../../includes/banner.md)]


자산 관리에서 다음에 대한 용량 부하를 계산할 수 있습니다.

- 유지 보수 일정 라인  
- 아직 예약되지 않은 작업 주문  
- 예약된 작업 주문

이는 특정 기간에 대한 예상 용량 부하의 개요를 확인하려는 경우에 유용합니다. 용량 부하 계산은 모든 자산 또는 선택한 자산에 대해 수행할 수 있습니다. 또한 유지 관리 다운타임 활동 또는 작업 주문 풀에 대해 계산할 수 있습니다.

1. **자산 관리** > **문의** > **용량 부하** 또는 **자산 관리** > **공통** > **작업 주문 풀** > **모든 작업 주문 풀** / **활성 작업 주문 풀** > 목록에서 작업 주문 풀 선택 > **용량 부하** 버튼 또는 **자산 관리** > **공통** > **유지 관리 다운타임 활동** > **모든 유지 관리 다운타임 활동** / **활성 유지 보수 다운타임 활동** > 목록에서 유지 관리 활동 선택 > **용량 부하** 단추를 클릭합니다.

2. **용량 부하 계산** 대화 상자에서 **시작 날짜/시간** 및 **종료 날짜/시간** 필드에 계산 기간을 선택합니다.

3. 계산에 유지 관리 일정 라인을 포함하려면 **유지 관리 일정 포함** 토글 버튼에서 "예"를 선택합니다.

4. 계산에 작업 주문 작업을 포함하려면 **작업 주문 포함** 토글 버튼에서 "예"를 선택합니다.

5. **수준** 필드를 사용하여 기능 위치와 관련하여 용량 로드 라인이 얼마나 상세하게 표시되기를 원하는지 나타낼 수 있습니다. 

    예를 들어, 필드에 숫자 "1"을 삽입하고 다중 레벨 기능 위치 구조가 있는 경우 기능 위치에 대한 모든 유지 관리 일정 라인 및 작업 주문이 최상위 레벨에 표시되므로 라인의 시간은 다음과 같이 표시될 수 있으며, 하위 수준에 위치한 기능적 위치에서 추가됩니다. 
    
    **레벨** 필드에 숫자 "0"을 입력하면 관련된 모든 기능적 위치 수준의 모든 유지 관리 일정 라인 및 모든 작업 주문을 보여주는 자세한 결과를 볼 수 있습니다.

6. **확인** 을 클릭하여 비용 계산을 시작합니다.

7. **그룹화 기준...** 그룹에서 관련 버튼을 클릭하여 필요한 계산 세부 수준을 표시합니다. 아래 스크린샷에서 선택한 **그룹화 기준** 버튼이 파란색으로 강조 표시됩니다. 단추를 클릭하여 활성화하거나 비활성화합니다.

    ![그림 1.](media/01-capacity-planning.png)

>[!NOTE]
>예약된 작업 주문과 관련된 용량 계획에만 집중하려면 [예약된 작업 주문에 대한 용량 부하 계산](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md)을 참조하세요.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]