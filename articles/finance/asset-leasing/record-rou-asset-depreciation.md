---
title: 사용권 자산 감가상각 레코드(미리보기)
description: 이 항목에서는 조직의 대차 대조표에 인식되는 임대에 필요한 상각에 대한 저널 항목을 만드는 방법에 대해 설명합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseAssetSchedule
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a766247e5482677429706a324c09cc9be4386c0b
ms.sourcegitcommit: 304a482dfcc31dcb61849f710ae73432324ddef3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/29/2021
ms.locfileid: "8451324"
---
# <a name="record-right-of-use-asset-depreciation-preview"></a>사용권 자산 감가상각 레코드(미리보기)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


조직의 대차 대조표에 인식된 임대의 경우 ROU(사용권) 자산이 월 단위로 상각됩니다. 이 항목에서는 상각에 대한 저널 항목을 만드는 방법에 대해 설명합니다. 상각은 당신의 게시 프로필과 임대 유형 설정에 따라 경비 원장 계정에서 차감하고 누적 감가상각 원장 계정을 차감합니다. 이러한 항목은 각 임대에 대해 생성하거나 배치 저널 기능을 사용하여 여러 임대에 대해 생성할 수 있습니다.

## <a name="asset-depreciation-schedule"></a>자산 감가상각 일정

1. **임대 요약** 페이지에서 임대를 선택합니다. 그런 다음 **장부 \> 자산 감가상각 일정** 을 선택하여 **자산 감가상각 일정** 페이지를 엽니다.

    ROU 자산 감가상각 경비 저널 항목은 **감가상각 경비** 열의 금액을 기준으로 합니다. 회계 표준 준수를 위한 지침의 예는 이 항목의 뒷부분에 있는 [금융 임대에 대한 ROU 자산 상각비 계산](#calculation-of-rou-asset-amortization-expense-for-finance-leases) 섹션을 참조하십시오.
    
2. 감가상각 기간을 선택한 다음 **저널 만들기** 를 선택합니다. 감가상각을 기록하는 데 사용할 저널이 생성되었다는 메시지가 표시됩니다.
3. **저널 \> 자산 임대 저널** 을 선택하여 생성된 감가상각 저널 항목을 볼 수 있는 **자산 임대 저널** 페이지를 엽니다.

   시스템은 트랜잭션과 일정 간의 차이를 방지하기 위해 특정 재무 필드를 편집하지 못하도록 잠급니다. 잠긴 필드에는 **계정**, **금액,** **재무 차원**, **통화**, **트랜잭션 유형** 입니다. 또한, 일정과 거래 간에 차이가 발생할 수 있으므로 자산 임대 분개에 분개 라인을 추가하거나 삭제할 수 없습니다.

4. 저널 항목을 선택한 후 **게시** 를 선택하여 감가상각 항목을 총계정원장에 기록합니다.

## <a name="calculation-of-rou-asset-amortization-expense-for-operating-leases"></a>운영 임대에 대한 ROU 자산 상각 비용 계산

운용 임대의 감가상각 경비는 미국회계기준(US GAAP)의 기준인 회계기준 코드화 주제 842(ASC 842)에 따라 월별 직선 임대 비용과 월별 임기 부채 이자 비용의 차액으로 계산합니다. 직선 임대 비용은 모든 임대 납입액을 월 단위로 임대 기간으로 나눈 값으로 계산됩니다. (임대료 지급액에는 선불금, 초기 직접 비용, 해체 비용, 임대 장려금 등이 포함됩니다.) 다음 표는 운영 임대에 대한 상각 경비의 예를 보여줍니다.

### <a name="example-of-rou-asset-amortization-expense-for-operating-leases"></a>운영 임대에 대한 ROU 자산 상각 경비의 예

| 필드                                          | 값       |
|------------------------------------------------|-------------|
| 결제 금액                                 | 1,000       |
| 결제 빈도                              | 매월     |
| 임대 기간(개월)                            | 24          |
| 총 임대 결제                           | 24,000      |
| 증분 차입 이자율                     | 5%          |
| 연금 유형                                   | 연금 기한 |
| 복리 간격                           | 매월     |
| 미래 최소 임대료 지급의 현재 값 | 22,888.87   |

앞서 설명했듯이, 직선 임대 비용은 모든 지급액을 임대 기간으로 나눈 값으로 계산됩니다. 부채 상각 일정에 따라 월 이자 비용이 자동으로 계산됩니다. 이자 비용은 유효 이자 비율 방법을 이용하여 계산됩니다. 시스템은 월별 이자 비용을 공제하기 위해 직선 임대 비용을 사용합니다. 이 값은 ROU 자산을 줄이는 데 사용됩니다.

| 개월 | 직선 임대료 | 이자 비용                        | ROU 자산 상각 비용 계산 |
|-------|--------------------------|-----------------------------------------|-----------------------------------------------|
| 1     | (24,000 ÷ 24) = 1,000.00 | (22,888.87 – 1,000) × (5% ÷ 12) = 91.20 | 1,000 – 91.20 = 908.80                        |
| 2     | (24,000 ÷ 24) = 1,000.00 | (21,980.08 – 1,000) × (5% ÷ 12) = 87.42 | 1,000 – 87.42 = 912.58                        |
| 3     | (24,000 ÷ 24) = 1,000.00 | (21,067.49 – 1,000) × (5% ÷ 12) = 83.62 | 1,000 – 83.62 = 916.39                        |

> [!NOTE]
> ASC 842에 따르면 운영 임대에 대한 ROU 자산의 감가상각은 손익계산서에 임대 비용으로 분류됩니다. 가시성을 위해 자산 임대에서는 항목을 ROU 자산의 감가상각으로 설명합니다. 그러나 차변 항목은 운영 임대 비용 계정에 할당되어야 하며, 크레딧 항목은 운영 임대에 대한 ROU 자산에 직접 할당되어야 합니다. 그럼에도 불구하고, 임대 매개 변수에서 운영 ROU 자산에 대한 누적 감가상각 계정에 크레딧 항목을 생성하도록 지정할 수 있습니다.

운용 리스로 분류되는 임대의 경우 손상을 계산한 후 월별 감가상각은 정액 감가상각을 사용하여 계산합니다.

## <a name="calculation-of-rou-asset-amortization-expense-for-finance-leases"></a>금융 임대에 대한 ROU 자산 상각 비용 계산

재무로 분류되는 임대의 경우 시스템은 직선 기준으로 ROU 자산 상각 금액을 계산합니다. 따라서 감가상각은 매월 동일하게 됩니다.

IFRS 16(International Financial Reporting Standard 16)와 ASC 842호에 따라 임대 기간이나 자산의 내용 연수 중 더 짧은 기간을 기준으로 자산을 상각합니다. 또한 임대에 대해 **소유권 이전** 매개 변수가 설정된 경우 임대는 자산의 내용 연수 동안 자동으로 감가상각됩니다.

### <a name="example-of-rou-asset-amortization-expense-for-finance-leases"></a>금융 임대에 대한 ROU 자산 상각 경비의 예

| 필드                                | 값                                   |
|--------------------------------------|-----------------------------------------|
| 사용권 자산 시작 잔액 | 22,889.87                               |
| 임대 기간(개월)                  | 24                                      |
| 자산 내용 연수(개월)           | 36                                      |
| 개월                                | 사용권 자산 상각 경비 |
| 1                                    | 22,889.87 ÷ 24 = 953.74                 |
| 2                                    | 22,889.87 ÷ 24 = 953.74                 |
| 3                                    | 22,889.87 ÷ 24 = 953.74                 |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]