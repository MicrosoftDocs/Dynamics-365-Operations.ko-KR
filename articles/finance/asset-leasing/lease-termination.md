---
title: 임대 종료 제안
description: 이 항목에서는 임대 종료를 제안하는 방법을 설명합니다.
author: moaamer
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseTerminateLeaseListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2021-1-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 657bd2aa32179941e4103fea31f813688ad478ac6e9902212c976a92620b2e67
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450169"
---
# <a name="propose-a-lease-for-termination"></a>임대 종료 제안

[!include [banner](../includes/banner.md)]

리스가 조기 종료되는 경우 자산 임대는 종료 분개장을 기록하여 임대 부채, 사용권(ROU) 자산 및 감가상각 누계액을 상각하고 손익을 기록할 수 있습니다. 조기 종료 프로세스는 임대 및 관련 임대 장부를 종료합니다. 개별 임대 장부를 종료하지 않습니다. 이 항목에서는 임대 종료를 제안하고 임대 종료 분개장 항목을 처리할 수 있는 기능에 관해 설명합니다.

임대가 이연 지연 임대 처리 리스로 분류되지 않고 고정 자산과 연결되지 않은 경우 자산 임대는 다음과 같은 종료 분개장 항목을 생성합니다.

| 거래                           | 출금(Dr.) | 입금(Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. 임대 부채                   | X           |              |
| Dr. 감가상각 누계          | X           |              |
| Dr. 임대 변경 손익 | X           |              |
| Cr. 임대 자산                       |             | X            |
| Cr. 임대 변경 손익 |             | X            |

리스 장부가 지연 임대 장부로 분류되는 경우 여기에 표시된 것처럼 종료 전 지연 임대 잔액을 손익 계정에 기록합니다.

| 거래                           | 출금(Dr.) | 입금(Cr.) | 
|---------------------------------------|-------------|--------------|
| Dr. 지연 임대                     | X           |              |
| Cr. 임대 변경 손익 |             | X            |
| Cr. 지연 임대                     |             | X            |
| Dr. 임대 변경 손익 | X           |              |

임대 장부가 고정 자산에 연결되어 있는 경우 ROU 자산은 고정 자산으로 처리됩니다. 이 회계에는 조기 종료에 대한 회계가 포함됩니다. 자산 임대는 임대 부채를 상쇄하기 위해 다음 분개장 항목을 생성합니다.

| 거래                           | 출금(Dr.) | 입금(Cr.) |
|---------------------------------------|-------------|--------------|
| Dr. 임대 부채                   | X           |              |
| Cr. 임대 변경 손익 |             | X            |

ROU 자산을 폐기하는 올바른 방법에 대한 정보는 [고정 자산 폐기](../fixed-assets/dispose-of-a-fixed-asset-as-scrap.md)를 참조하세요.

## <a name="propose-a-lease-for-termination"></a>임대 종료 제안

1. 종료해야 하는 임대로 이동한 다음 작업 창에서 **종료 제안** 을 선택합니다.

    > [!NOTE]
    > 장부에 대해 게시되지 않은 분개장 항목이 있는 경우 **종료 제안** 버튼을 사용할 수 없습니다. 임대를 종료하기 전에 임대에 대해 생성된 분개장 항목을 게시하거나 삭제해야 합니다.

2. 표시되는 대화 상자에서 종료 분개장 항목에 대한 **유효 날짜** 및 **게시 날짜** 필드를 설정합니다.
3. **종료 제안** 을 선택하여 임대 종료를 제안합니다.
4. 임대 종료 분개장 항목을 자동으로 게시하려면 **임대 종료 후** 를 선택합니다.
5. **임대 종료** 페이지에서 종료를 제안한 임대의 임대 ID를 선택하여 종료 라인을 확인합니다. 종료 라인은 ROU 자산의 장부 가치, 임대 부채, 감가상각 누계액, 지연 임대료(해당되는 경우) 및 임대 종료 시 인식해야 하는 손익을 표시합니다.

이제 임대를 종료할 준비가 되었습니다. 임대 장부의 **종료 상태** 필드 값이 **종료 준비됨** 으로 변경됩니다. 이 시점부터 더는 임대에 대한 분개장 항목을 게시하거나 조정 또는 손상시킬 수 없습니다. 

## <a name="process-leases-that-are-ready-for-termination"></a>종료 준비된 임대 처리

종료 준비된 임대를 처리하고 종료 분개장 항목을 게시하려면 다음 단계를 따르세요.

1. **임대 종료** 페이지에서 처리할 임대를 선택한 다음 **종료** 를 선택합니다.
2. 표시되는 대화 상자에서 **확인** 을 선택합니다

시스템에서 종료 분개장 항목을 게시합니다. 임대 장부의 **임대 상태** 필드는 **종료됨** 으로 설정되고 **종료 제안 상태** 필드는 **완료됨** 으로 설정됩니다.

## <a name="reverse-a-lease-termination"></a>임대 종료 취소

임대 종료 분개장 항목을 취소하고 종료된 임대를 열려면 이 단계를 따르세요.

- **임대 종료** 페이지에서 되돌리려는 종료된 임대를 선택한 다음 **종료 취소** 를 선택합니다.

시스템에서 종료 분개장 항목을 되돌립니다. 임대 장부의 **임대 상태** 가 **열림** 으로 설정됩니다. 더는 임대가 **임대 종료** 페이지에 표시되지 않으며 다시 종료를 제안할 수 있습니다.

## <a name="example-of-a-lease-termination"></a>임대 종료의 예

이 예에서 임대는 비특수 자산과 연결되어 있으며 자산의 소유권을 이전하거나 임차인에게 자산 구매 옵션을 부여하지 않습니다.

### <a name="setup"></a>설정

다음 표는 이 예제에서 사용된 임대의 **일반** 및 **지불 일정 라인** 탭에 설정된 값을 보여줍니다.

**일반 탭**

| 필드                      | 값            |
|----------------------------|------------------|
| 자산의 공정 가치    | 600,000          |
| 통화                   | USD              |
| 초기 직접 비용       | 1,000            |
| 증분 차입 이자율 | 7%               |
| 복리 간격       | 매년         |
| 자산 내용 연수(개월) | 600              |
| 연금 유형               | 일반 연금 |
| 개시일          | 2019-01-01         |

**지불 일정 라인 탭**

| 필드             | 값      |
|-------------------|------------|
| 시작 날짜        | 2019-01-01   |
| 기간 간격   | 매월    |
| 기간           | 120        |
| 종료 날짜          | 2028-12-31 |
| 지불 빈도 | 매년   |
| 결제 금액    | 10,000     |

### <a name="steps-for-terminating-the-lease"></a>임대 종료 단계

1. 이 항목의 앞부분에서 설명한 대로 임대를 만든 후 임대 장부로 이동하여 지불 일정을 확인합니다. 그런 다음 초기 인식 분개장 항목을 게시합니다. 초기 ROU 자산은 $71,235.81이고 임대 부채는 $70,235.81가 됩니다. 이 예의 임대는 회계 표준 목록 항목 842(ASC 842)에 따라 운용 리스로 분류되었습니다.
2. 배치 분개장 프로세스를 세 번 실행하여 임대료, 이자 비용 및 감가상각비에 대해 3년 경과를 시뮬레이션합니다.
3. 세 가지 일괄 작업을 모두 실행한 후 임대 장부로 돌아가서 부채 및 자산 거래 표를 열어 ROU 자산 및 임대 부채의 현재 장부 가치를 확인합니다. 3년 후 부채의 가치는 약 $-53,893.00이 되고 자산의 가치는 약 $54,593.00가 될 것입니다.

    3년이 경과한 후 사업자와 임대인은 상호 임대를 종료하기로 합의합니다. 따라서 이제 임대를 종료해야 합니다.

4. 종료해야 하는 임대로 이동한 다음 작업 창에서 **종료 제안** 을 선택합니다. 
5. 표시되는 대화 상자의 **적용 날짜** 및 **게시 날짜** 필드에 **2021-01-01** 을 입력합니다.
6. **종료 제안** 을 선택하여 임대 종료를 제안합니다.

    **임대 종료** 페이지가 나타나고 종료될 임대가 표시됩니다.

7. 종료 라인을 보려면 종료를 제안한 임대의 임대 ID를 선택합니다. 종료 라인은 임대의 장부 가치를 보여줍니다. 다음 표는 이 예에서 이러한 가치가 어떻게 표시되는지 보여줍니다. 

    | 필드                                                 | 값      |
    |-------------------------------------------------------|------------|
    | 장부 부채 잔액(거래 통화) | $53,892.89 |
    | 사용권 자산(거래 통화)            | $71,235.81 |
    | 감가상각 누계액(거래 통화)      | $16,642.92 |
    | 손익(거래 통화)                   | $-700.00   |

8. 종료 분개장 항목을 게시하려면 **임대 종료** 페이지에서 임대를 선택한 다음 **종료** 를 선택합니다.
9. 표시되는 대화 상자에서 **확인** 을 선택합니다
10. 작성되고 게시된 종료 분개장 항목을 보려면 임대 장부의 자산 임대 분개장으로 이동합니다. 다음 표는 이 예에서 이러한 항목이 어떻게 나오는지 보여줍니다.

    | 거래                           | 출금(Dr.) | 입금(Cr.) |
    |---------------------------------------|-------------|--------------|
    | Dr. 임대 부채                   | 53,892.89   |              |
    | Dr. 감가상각 누계          | 16,642.92   |              |
    | Dr. 임대 변경 손익 | 700.00      |              |
    | Cr. 임대 자산                       |             | 71,235.81    |

11. ROU 자산 및 임대 부채가 0(영)이 되는 종료의 순 효과를 보려면 부채 및 자산 거래 표를 엽니다.

임대 상태는 이제 **종료됨** 이 됩니다. 종료가 되돌리지 않는 한 이 임대에 관한 추가 분개장 항목은 게시되지 않습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
