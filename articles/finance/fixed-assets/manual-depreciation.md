---
title: 수동 감가상각
description: 이 문서에서는 수동 감가상각 방법에 대한 개요를 제공합니다.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5b62bbdd5d745bc9d0745cc6fa6d6e8034a61e3
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "8451078"
---
# <a name="manual-depreciation"></a>수동 감가상각

[!include [banner](../includes/banner.md)]

이 문서에서는 수동 감가상각 방법에 대한 개요를 제공합니다.

고정 자산 감가상각 프로필을 설정하고 **감가상각 프로필** 페이지의 **방법** 필드에서 **수동** 을 선택하면 달력 연도의 각 간격에 대해 입력하는 백분율로 감가상각 프로필에 할당된 고정 자산의 감가상각이 결정됩니다. 백분율을 설정한 간격은 **감가상각 프로필** 페이지의 **일반** 빠른 탭에 있는 **기간 빈도** 필드에서 선택한 값에 따라 게시됩니다. 선택할 수 있는 값은 다음과 같습니다.

- 매년
- 매월
- 분기별
- 반년
- 매일

기간 빈도를 선택한 후 **수동 일정** 을 클릭하고 각 게시 간격에 대한 백분율을 설정합니다. 수동 일정과 게시 간격은 이 문서 뒷부분의 예에서 볼 수 있듯이 감가상각 금액을 정의합니다. 수동 감가상각은 항상 취득 가격의 백분율로 계산됩니다. 수동 감가상각의 경우 감가상각 간격에 입력하는 백분율의 합이 100%가 될 필요는 없습니다. 수동 감가상각은 특별한 목적(예: 세금)을 위한 비정기 감가상각과 같이 **장부** 페이지에서 비정기 감가상각 프로필을 정의하는 데 자주 사용되는 유연한 감가상각 방법입니다.

## <a name="examples"></a>예
취득 가격: 11,000.00 예상 폐기 가치: 1,000.00 다음 표는 **고정 자산 감가상각 프로필 일정** 페이지에서 설정한 간격 및 백분율을 보여줍니다.

| 간격 번호 | 백분율 |
|-----------------|------------|
| 1               | 10.00      |
| 2               | 50.00      |
| 3               | 8.00       |

다음 표는 각 구간에 대한 감가상각을 계산하는 방법을 보여줍니다.

|  간격 번호 | 연간 감가상각 금액 계산 | 간격 종료 시 순 장부가액 |
|------------------|-----------------------------------------------|-------------------------------------------|
| 1                | (11,000 – 1,000) × 10% = 1,000                | 10,000 (11,000 – 1,000)                   |
| 2                | (11,000 – 1,000) × 50% = 5,000                | 5,000 (10,000 – 5,000)                    |
| 3                | (11,000 – 1,000) × 8% = 800                   | 4,200 (5,000 – 800)                       |

**기간 빈도** 필드에서 **매월** 을 선택하면 12개의 수동 일정 간격을 설정합니다. 다음 표는 처음 두 간격의 감가상각 금액을 보여줍니다.

| 간격 | 감가상각액            |
|----------|--------------------------------|
| 1월  | (11,000 – 1,000) × 10% = 1,000 |
| 2월 | (11,000 – 1,000) × 50% = 5,000 |

*<strong><em>기간 빈도</em>* 필드</strong>에서 <strong>반년</strong>을 선택하면 두 개의 수동 일정 간격을 설정합니다. 다음 표는 이러한 두 간격의 감가상각 금액을 보여줍니다.

| 간격    | 감가상각액            |
|-------------|--------------------------------|
| 6월 30일     | (11,000 – 1,000) × 10% = 1,000 |
| 12월 31일 | (11,000 – 1,000) × 50% = 5,000 |

모든 간격의 백분율 합계가 100일 필요는 없습니다. 그러나 **고정 자산 감가상각 프로필 일정** 페이지의 **누적 백분율** 필드 값이 **100** 이 아닌 경우 메시지를 받게 됩니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
