---
title: 유지 관리 상태
description: 이 토픽에서는 자산 관리에서 유지 관리 상태를 계산하는 방법에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetStatusCalculate, EntAssetStatus
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 138e2e72fbf761d209d288c2bd778c08519b9c69b0715f4466d4838255a2a31e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447010"
---
# <a name="maintenance-status"></a>유지 관리 상태

[!include [banner](../../includes/banner.md)]

 

자산 관리에서 신규, 활성 및 완료된 유지 관리 요청, 작업 주문 및 유지 관리 중단 시간 활동에 대한 특정 기간에 대한 개요 계산을 수행할 수 있습니다. 같은 기간에 완료된 상태 평가의 수도 볼 수 있습니다. 이 계산을 사용하여 수신 및 완료된 유지 관리 요청 및 작업 주문에 대한 작업 부하의 개요를 확인합니다.

## <a name="make-a-maintenance-status-calculation"></a>유지 관리 상태 계산

1. **자산 관리** > **문의** > **유지 관리 상태** 를 클릭합니다.

2. **상태 계산** 대화 상자의 **시작 날짜** 및 **종료 날짜** 필드에서 계산할 시간 범위를 선택합니다.

3. **수준** 필드를 사용하여 기능 위치와 관련하여 유지 관리 라인이 얼마나 상세하게 표시되기를 원하는지 나타낼 수 있습니다. 

  예를 들어, 필드에 숫자 "1"을 삽입하고 다중 레벨 기능 위치 구조가 있는 경우 기능 위치에 대한 모든 유지 관리 라인이 최상위 레벨에 표시되므로 라인의 상태는 다음과 같이 표시될 수 있으며, 하위 수준에 위치한 기능적 위치에서 추가됩니다. 
  
  **레벨** 필드에 숫자 "0"을 입력하면 관련된 모든 기능적 위치 수준의 모든 유지 관리 라인을 보여주는 자세한 결과를 볼 수 있습니다.

4. **확인** 을 클릭하여 비용 계산을 시작합니다.

5. **그룹화 기준** 단추를 클릭하여 계산에 필요한 세부 정보 수준을 표시합니다. 선택한 **그룹화 기준** 단추가 강조 표시됩니다. 단추를 클릭하여 활성화하거나 비활성화합니다.

6. **그룹화 기준** 단추를 활성화 또는 비활성화하거나 새 기간에 대한 계산을 수행하여 변경할 때마다 **업데이트** 버튼을 클릭하여 계산을 업데이트해야 합니다.

7. 새 유지 관리 상태 계산을 만들려면 **상태** 를 클릭합니다.

>[!NOTE]
>**유지 관리 상태** 에 표시되는 결과에는 실제 시작 날짜 및 시간이 있는 유지 관리 요청 및 작업 주문만 포함됩니다. 종료일 및 시간이 비어 있을 수 있습니다.

## <a name="example-1"></a>예시 1

아래 스크린샷에서 **연도** 및 **월** 단추가 활성화되었습니다. 이러한 **그룹화 기준** 옵션을 선택하면 유지 관리 요청 및 작업 주문과 관련된 워크로드 및 처리량에 대한 월별 일반 개요를 볼 수 있습니다. 

![월별 작업량의 예.](media/13-controlling-and-reporting.png)

## <a name="example-2"></a>예시 2

아래 스크린샷에는 기능 위치에 대한 정보가 추가되었습니다. 이제 지리적 위치, 공장 또는 작업 영역을 나타낼 수 있는 기능 위치 전체에서 작업량과 처리량을 비교할 수 있습니다. 

![기능 위치가 있는 월별 워크로드의 예.](media/14-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]