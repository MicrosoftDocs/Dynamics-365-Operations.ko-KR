---
title: 복리 간격 기능
description: 이 토픽에서는 월별, 분기별, 반기별 및 연간 복리 계산 간격 중에서 선택하는 데 도움이 되는 정보를 제공합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d0f01748d370dfa5351ceb007a630564ca5d3a76c142830f32ce11951db9088
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450163"
---
# <a name="compounding-interval-functionality"></a>복리 간격 기능

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

이 토픽에서는 월별, 분기별, 반기별 및 연간 복리 계산 간격 중에서 선택하는 데 도움이 되는 정보를 제공합니다. 복리 간격 기능은 임대의 지불 일정에서 연간 복리 기간 수를 결정하는 데 사용됩니다. 이 토픽의 네 가지 예는 각각 다른 간격에 대한 임대의 지불 일정이 어떻게 나타나는지 보여줍니다.

임대의 지불 빈도보다 빈도가 적은 복리 간격은 선택할 수 없습니다. 예를 들어 분기별 복리 간격은 월별 지불 빈도와 함께 사용할 수 없으며 연간 복리 간격은 반기 지불 빈도와 함께 사용할 수 없습니다. 임대의 지불 빈도보다 빈도가 적은 복리 간격을 선택하려고 하면 오류 메시지가 나타납니다.

> [!NOTE]
> 이 토픽의 네 가지 예 모두에서 복리 간격은 지불 빈도와 일치합니다.

## <a name="examples"></a>예

### <a name="setup-for-all-four-leases"></a>4가지 임대 모두에 대한 설정

다음 표는 예제에서 사용된 4개의 임대에 대해 **일반** 및 **지불 일정 라인** 탭에 설정된 값을 보여줍니다.

**일반 탭**

| 필드                      | 값                        |
|----------------------------|------------------------------|
| 증분 차입 이자율 | **5%**                       |
| 연금 유형               | **일반 연금**         |
| 복리 간격       | 개별 예를 참조하십시오. |
| 지불 빈도          | **매월**                  |
| 개시일          | **2020년 1월 1일**                 |

**지불 일정 라인 탭**

| 필드             | 값                        |
|-------------------|------------------------------|
| 시작 날짜        | **2020년 1월 1일**                 |
| 기간           | **120**                      |
| 기간 간격   | **개월**                   |
| 종료 날짜          | **2029년 12월 31일**               |
| 지불 빈도 | 개별 예를 참조하십시오. |
| 결제 금액    | **50,000**                   |

### <a name="lease-1-monthly-compounding-interval-and-monthly-payment-frequency"></a>임대 1: 월 복리 간격 및 월 지불 빈도

다음 표는 지불 일정의 처음 12개월을 나열합니다. 다음 세부 정보를 확인하세요.

- "기간" 열의 값은 매월 새로운 복리 간격이기 때문에 매월 1씩 증가합니다.
- "현재 값" 열의 공식에서 연간 복리 기간이 12회이기 때문에 비율을 12로 나눕니다. 지수(즉, 위 첨자 숫자)는 "기간" 열의 값과 같습니다.

| 기간 | 개월 | 날짜       | 결제 금액 | 현재 값                                       |
|--------|-------|------------|----------------|-----------------------------------------------------|
| 1      | 1     | 2020년 1월 31일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>1</sup> = 49,792.53  |
| 2      | 2     | 2020년 2월 29일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>2</sup> = 49,585.92  |
| 3      | 3     | 2020년 3월 31일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>3</sup> = 49,380.17  |
| 4      | 4     | 2020년 4월 30일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>4</sup> = 49,175.28  |
| 5      | 5     | 2020년 5월 31일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>5</sup> = 48,971.23  |
| 6      | 6     | 2020년 6월 30일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>6</sup> = 48,768.03  |
| 7      | 7     | 2020년 7월 31일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>7</sup> = 48,565.67  |
| 8      | 8     | 2020년 8월 31일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>8</sup> = 48,364.15  |
| 9      | 9     | 2020년 9월 30일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>9</sup> = 48,163.47  |
| 10     | 10    | 2020년 10월 31일 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>10</sup> = 47,963.62 |
| 11     | 11    | 2020년 11월 30일 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>11</sup> = 47,764.61 |
| 12     | 12    | 2020년 12월 31일 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 12\])<sup>12</sup> = 47,566.41 |

### <a name="lease-2-quarterly-compounding-interval-and-quarterly-payment-frequency"></a>임대 2: 분기 복리 간격 및 분기 지불 빈도

다음 표는 지불 일정의 처음 12개월을 나열합니다. 다음 세부 정보를 확인하세요.

- 각 분기는 새로운 복리 간격이기 때문에 "기간" 열의 값은 3개월마다(즉, 분기마다) 1씩 증가합니다.
- "현재 값" 열의 공식에서 연간 복리 기간이 4회이기 때문에 비율을 4로 나눕니다. 지수는 "기간" 열의 값과 같습니다.

| 기간 | 개월 | 날짜       | 결제 금액 | 현재 값                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 2020년 1월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 2     | 2020년 2월 29일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 3     | 2020년 3월 31일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 49,382.72 |
| 2      | 4     | 2020년 4월 30일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 5     | 2020년 5월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 6     | 2020년 6월 30일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 48,773.05 |
| 3      | 7     | 2020년 7월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 8     | 2020년 8월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 9     | 2020년 9월 30일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 48,170.92 |
| 4      | 10    | 2020년 10월 31일 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 11    | 2020년 11월 30일 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 12    | 2020년 12월 31일 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 47,576.21 |

> [!NOTE]
> 연금 유형을 **기초 연금** 으로 변경하면 분기말이 아닌 분기초에 지급됩니다.

### <a name="lease-3-semiannual-compounding-interval-and-semiannual-payment-frequency"></a>임대 3: 반기 복리 간격 및 반기 지불 빈도

다음 표는 지불 일정의 처음 12개월을 나열합니다. 다음 세부 정보를 확인하세요.

- 각 반기는 새로운 복리 간격이기 때문에 "기간" 열의 값은 6개월마다(즉, 반기마다) 1씩 증가합니다.
- "현재 값" 열의 공식에서 연간 복리 기간이 2회이기 때문에 비율을 2로 나눕니다. 지수는 "기간" 열의 값과 같습니다.

| 기간 | 개월 | 날짜       | 결제 금액 | 현재 값                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 2020년 1월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 2     | 2020년 2월 29일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 3     | 2020년 3월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 4     | 2020년 4월 30일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 5     | 2020년 5월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 6     | 2020년 6월 30일  | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 48,780.49 |
| 2      | 7     | 2020년 7월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 8     | 2020년 8월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 9     | 2020년 9월 30일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 10    | 2020년 10월 31일 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 11    | 2020년 11월 30일 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 12    | 2020년 12월 31일 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 47,590.72 |

> [!NOTE]
> 연금 유형을 **기초 연금** 으로 변경하면 6월과 12월이 아닌 1월과 7월에 지급됩니다.

### <a name="lease-4-annual-compounding-interval-and-annual-payment-frequency"></a>임대 4: 연간 복리 간격 및 연간 지불 빈도

다음 표는 지불 일정의 처음 12개월을 나열합니다. 다음 세부 정보를 확인하세요.

- 각 반기는 새로운 복리 간격이기 때문에 "기간" 열의 값은 12개월마다(즉, 연간) 1씩 증가합니다.
- "현재 값" 열의 공식에서 연간 복리 기간이 1회이기 때문에 비율을 1로 나눕니다. 지수는 "기간" 열의 값과 같습니다.

| 기간 | 개월 | 날짜       | 결제 금액 | 현재 값                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 2020년 1월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 2     | 2020년 2월 29일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 3     | 2020년 3월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 4     | 2020년 4월 30일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 5     | 2020년 5월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 6     | 2020년 6월 30일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 7     | 2020년 7월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 8     | 2020년 8월 31일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 9     | 2020년 9월 30일  | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 10    | 2020년 10월 31일 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 11    | 2020년 11월 30일 | 0.00           | 0.00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 12    | 2020년 12월 31일 | 50,000.00      | 50,000 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 47,619.05 |

> [!NOTE]
> 연금 유형을 **기초 연금** 으로 변경하면 12월이 아닌 1월에 지급됩니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
