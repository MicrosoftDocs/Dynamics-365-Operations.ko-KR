---
title: 직선 서비스 수명 감가상각
description: 이 항목에서는 직선 서비스 수명 감가상각 방법에 대한 개요를 제공합니다.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 3341
ms.assetid: ae5ceaeb-aeb7-45cd-b835-23cf9c5cf95a
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b34cdf9485d38cdbf1362bd605841201a4295f26
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451099"
---
# <a name="straight-line-service-life-depreciation"></a>직선 서비스 수명 감가상각

[!include [banner](../includes/banner.md)]

이 항목에서는 직선 서비스 수명 감가상각 방법에 대한 개요를 제공합니다.

고정 자산 감가상각 프로파일을 설정하고 감가상각 프로파일 페이지의 방법 필드에서 직선 서비스 수명을 선택하면 이 감가상각 프로파일이 할당된 자산은 자산의 총 서비스 수명을 기준으로 감가상각됩니다. 이는 일반적으로 각 감가상각 기간에 동일한 감가상각 금액입니다. 

남은 직선 서비스 수명과 직선 서비스 수명 간에 산정되는 감가상각 금액의 차이는 자산에 조정 사항이 게시된 경우에 발생합니다. 

직선 서비스 수명 감가상각을 설정하려면 감가상각 프로파일 페이지의 감가상각 연도, 기간 빈도 필드에서도 옵션을 선택해야 합니다.

## <a name="select-a-depreciation-year"></a>감가상각 연도 선택
감가상각 프로필 페이지의 감가상각 연도 필드에서 달력 또는 회계를 선택할 수 있습니다. 선택에 의해 기간 빈도 필드에서 사용할 수 있는 옵션이 정의됩니다. 기본 옵션은 달력입니다.

### <a name="calendar"></a>달력

달력을 선택하면 회계 달력을 다르게 정의하더라도 1월 1일부터 12월 31일까지의 연도를 가정합니다. 

달력 옵션은 일반적으로 순 장부가액 값에서 잔존 값을 빼 감가상각 기준을 매년 1월 1일에 업데이트합니다. 이 토픽의 뒷부분에 나오는 예제에서 감가상각 기준은 계산 열의 첫 번째 식에 있는 분자입니다. 

달력을 선택하면 기간 빈도 필드에서 다음 옵션을 사용할 수 있으며, 이 필드에서는 감가상각 발생 게시 날짜와 달력 연도의 금액을 정의합니다.
- 연간은 12월 31일에 금액을 게시합니다.
- 월간 게시 날짜는 각 달의 말일입니다.
- 분기별 게시 날짜는 각 달력 분기의 끝(3월 31일, 6월 30일, 9월 30일, 12월 31일)입니다.
- 반기별 게시 날짜는 각 달력 반년의 끝 날짜(6월 30일 및 12월 31일)입니다.
- 일일 감가상각은 하루를 하나의 트랜잭션으로 보고 매일 감가상각을 게시합니다.

예를 들어, 매년을 선택하면 연간 감가상각은 매년 12월 31일에 한 번만 게시됩니다. 매월을 선택하면 매월 감가상각액이 연간 감가상각 금액의 1/12로 게시됩니다.

### <a name="fiscal"></a>회계

감가상각 연도 필드에서 회계를 선택하면 직선 서비스 수명 감가상각이 사용됩니다. 회계 연도를 기준으로 계산되며 회계 연도는 장부에 지정된 회계 달력 또는 원장 페이지에서 선택한 회계 달력에 의해 정의됩니다. 회계 달력은 회계 달력 페이지에서 설정됩니다.

예를 들어 회계 연도 7월 1일부터 6월 30일까지의 경우 감가상각 계산은 7월 1일에 시작됩니다. 회계 연도는 12개월보다 길거나 짧을 수 있습니다. 감가상각은 각 회계 기간에 대해 자동으로 조정됩니다. 다음 회계 연도의 길이는 회계 달력 양식에서 새 회계 연도를 생성할 때 설정한 회계 기간을 기준으로 합니다. 

회계를 선택하면 기간 빈도 필드에서 다음 옵션을 사용할 수 있습니다.
- 연간은 회계연도의 마지막 날에 회계연도에 대해 계산된 감가상각 총액을 하나의 금액으로 전기합니다.
- 회계 기간은 회계 연도의 감가상각 총액을 계산하며, 이는 회계 달력의 회계 달력 양식에 정의된 기간에 누적됩니다.

## <a name="example-straight-line-depreciation-of-an-unchanged-fixed-asset"></a>예: 변경되지 않은 고정 자산의 정액 감가상각
고정자산이 다음과 같은 특성을 가지고 있다고 가정합니다.

| 특성      | 값  |
|:---------------------|--------:|
| 취득 비용    | 11,000 |
| 잔존 가치       | 1,000  |
| 감가상각 기준   | 10,000 |
| 서비스 수명 기간(년)  | 5      |
| 연 감가상각 | 2,000  |

매년 동일한 감가상각 금액을 받게 됩니다. (취득 비용 - 잔존 가치) / 서비스 수명 연도

| 기간 | 연간 감가상각 금액 계산 | 연도 종료 시 순 장부가액 |
|:--------:|:-------------------------------------------|---------------------------------------:|
| 1년 차 | (11,000 - 1,000) / 5 = 2,000              | 9,000                                 |
| 2년 차 | (11,000 - 1,000) / 5 = 2,000              | 7,000                                 |
| 3년 차 | (11,000 - 1,000) / 5 = 2,000              | 5,000                                 |
| 4년 차 | (11,000 - 1,000) / 5 = 2,000              | 3,000                                 |
| 5년 차 | (11,000 - 1,000) / 5 = 2,000              | 1,000                                 |

## <a name="example-straight-line-depreciation-of-a-modified-fixed-asset"></a>예: 수정된 고정 자산의 직선 감가상각

2년 차에 4,000개의 취득 조정을 동일한 고정 자산에 추가한다고 가정합니다. 

취득 조정의 서비스 수명은 고정 자산의 수명과 동일하며 취득 시점부터 시작됩니다. 순 장부가액은 취득 조정의 순 장부가액에 해당하는 5년 차 말에 유지됩니다. 기간별 감가상각비는 다음 표와 같이 계산됩니다.

| 기간 | 연간 감가상각 금액 계산 | 연도 종료 시 순 장부가액 |
|:--------:|:-------------------------------------------|---------------------------------------:|
| 1년 차 | 10,000 / 5 = 2,000                        | 11,000 - 2,000 = 9,000                |
| 2년 차 | 4,000(취득 조정)            | 9,000 + 4,000 =13,000                 |
| 2년 차 | 14,000 / 5 = 2,800                        | 13,000 - 2,800 = 10,200               |
| 3년 차 | 14,000 / 5 = 2,800                        | 10,200 - 2,800 = 7,400                |
| 4년 차 | 14,000 / 5 = 2,800                        | 7,400 - 2,800 = 4,600                 |
| 5년 차 | 14,000 / 5 = 2,800                        | 4,600 - 2,800 = 1,800                 |
| 6년 차 | 남은 800\*                           | 1,800 – 800 = 1,000                   |

\*잔여 금액이 감가상각 금액보다 적기 때문에 잔존 금액에서 잔존 가치를 뺀 금액만 가져갑니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
