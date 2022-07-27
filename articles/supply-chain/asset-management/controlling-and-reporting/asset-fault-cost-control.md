---
title: 자산 결함 비용 관리
description: 이 항목에서는 자산 관리의 자산 결함 비용 관리에 대해 설명합니다.
author: johanhoffmann
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCostControlFault
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3c36fc791fac6cce0433935adb88eb8cdc23003368204a87efc12cf5a419ec9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447013"
---
# <a name="asset-fault-cost-control"></a>자산 결함 비용 관리

[!include [banner](../../includes/banner.md)]

 

자산 관리에서 자산 결함 등록 비용을 계산하여 예산 비용과 비교한 실제 비용의 개요를 얻을 수 있습니다. 실제 비용은 게시된 거래를 기반으로 합니다. 날짜는 증상이 기록된 결함 날짜입니다.

1. **자산 관리** > **문의** > **자산 결함** > **자산 결함 비용 관리** 를 클릭합니다.

2. **자산 결함 비용 관리** 대화 상자에서 필요한 경우 계산에 포함할 재무 차원 집합을 선택합니다.

4. 비용이 0인 결과를 표시하지 않으려면 **0 건너뛰기** 토글 버튼에서 "예"를 선택합니다.

5. **수준** 필드를 사용하여 기능 위치와 관련하여 비용 관리 라인이 얼마나 상세하게 표시되기를 원하는지 나타낼 수 있습니다. 

    예를 들어, 필드에 숫자 "1"을 삽입하고 다중 레벨 기능 위치 구조가 있는 경우 기능 위치에 대한 모든 자산 결함 비용 관리 라인이 최상위 레벨에 표시되므로 라인의 시간은 다음과 같이 표시될 수 있으며, 하위 수준에 위치한 기능적 위치에서 추가됩니다. 
    
    **레벨** 필드에 숫자 "0"을 입력하면 관련된 모든 기능적 위치 수준의 모든 자산 결함 비용 관리 라인을 보여주는 자세한 결과를 볼 수 있습니다.

6. 검색을 제한하려면 **포함할 레코드** 빠른 탭에서 특정 자산, 오류 날짜, 오류 원인을 선택할 수 있습니다.

7. **확인** 을 클릭하여 비용 계산을 시작합니다.

8. **그룹화 기준** 단추를 클릭하여 계산에 필요한 세부 정보 수준을 표시합니다. 선택한 **그룹화 기준** 단추가 강조 표시됩니다. 단추를 클릭하여 활성화하거나 비활성화합니다.

## <a name="example"></a>예

이 예는 자산 결함 비용 통제 계산을 보여줍니다.

- **원래 예산** 필드는 작업 주문 예측의 예산 비용을 보여줍니다. 
- **실제 비용** 필드는 작업 주문에 게시된 비용을 보여줍니다. 
- **확정된 비용** 필드는 작업 주문과 관련하여 회사에서 투입하는 총 비용을 보여줍니다.

    ![그림 1.](media/05-controlling-and-reporting.png)

결함을 설정하는 방법에 대한 정보는 [장애 관리](../setup-for-work-orders/fault-management.md) 주제를 참조하세요.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]