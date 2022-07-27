---
title: 고정 자산 폐기
description: 이 항목에서는 폐기된 고정 자산에 대한 거래를 제거하는 프로세스를 설명합니다.
author: moaamer
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 90eb791bae2bbe70cf9fe7127a98962305449e1d0b370cfa001afbd3654046ec
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450556"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a>고정 자산 폐기

[!include [banner](../includes/banner.md)]

이 항목에서는 폐기된 고정 자산에 대한 거래를 제거하는 프로세스를 설명합니다. 제거할 수 있는 거래 유형에는 자산의 취득과 감가상각 누계 거래 및 기타 고정 자산 거래가 포함됩니다. 이러한 거래를 제거하면 취득 조정, 감가상각 조정, 재평가, 계정 감가상각과 같은 대차 대조표 계정이 영향을 받습니다.

| 거래                                         | 출금(Dr.) | 입금(Cr.) |
|-----------------------------------------------------|-------------|--------------|
| Dr. 감가상각 누계                        | X           |              |
| Cr. 고정 자산 손익                          |             | X            |
| Dr. 고정 자산 손익                          | X           |              |
| Cr. 고정 자산 취득 계정                 |             | X            |
| Dr. 고정 자산 손익(순 장부가액 \[NBV\]) | X           |              |
| Cr. 고정 자산 손익(NBV)                    |             | X            |

> [!NOTE]
> 회사의 최고 재무 책임자(CFO) 또는 회계 담당자와 긴밀히 협력하여 각 거래 유형에 사용해야 하는 올바른 계정을 구분하고 폐기 프로세스와 생성된 거래로 해당 계정이 올바르게 업데이트되는지 확인하는 것이 좋습니다.

고정 자산을 폐기하기 전에 자산의 취득 가치, 현재 연도의 감가상각, 이전 연도의 감가상각 및 자산의 NBV와 연결된 원장 계정을 생성해야 합니다. 고정 자산 거래 유형은 **고정 자산 게시 프로필** 페이지에 나열됩니다. **고정 자산 \> 설정 \> 고정 자산 게시 프로필** 로 이동한 다음 **처분** 빠른 탭에서 그리드 위쪽의 **폐기** 필드를 선택합니다. 다음 그림은 **고정 자산 게시 프로필** 페이지의 고정 자산 거래 유형 목록을 보여줍니다.


[![자산 폐기, 그림 1.](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)

다음 예에서 고정 자산은 2018년 1월 1일에 취득되었으며 2019년 3월 31일에 폐기됩니다.

- **취득 가격:** 24,000.00달러(USD)
- **서비스 수명:** 2년
- **감가상각 방법:** 직선 서비스 수명
- **감가상각 금액:** 1,000.00 USD/월

고정 자산의 NBV는 다음 공식으로 계산됩니다.

순 장부가액 = 취득 가격 – 감가상각

이 예에서는 고정 자산을 취득하여 2018년 1월부터 2019년 3월까지 15개월 동안 감가상각했습니다. 따라서 자산의 NBV는 9,000.00 USD(24,000.00 USD – 15,000.00 USD)입니다.

[![고정 자산 감가상각 예.](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)


폐기 분개장을 작성하려면 **고정 자산 \> 분개장 항목 \> 고정 자산 분개장** 으로 이동하고 작업 창에서 **라인** 을 선택합니다. **폐기 – 스크랩** 을 선택한 다음 고정 자산 ID를 선택합니다. 자산을 완전히 폐기하려면 **출금** 필드나 **입금** 필드에 값을 입력하지 마십시오.

[![고정 자산 분개장.](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)

고정 자산 폐기 거래는 다음과 같은 방식으로 고정 자산 장부의 필드 값을 변경합니다.

- **잔액** 섹션의 **상태** 필드가 **폐기됨** 으로 업데이트됩니다.
- **이슈** 섹션의 **폐기 날짜** 필드는 자산이 폐기된 날짜로 설정됩니다.

[![고정 자산 분개장 세부 정보.](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)

다음 그림은 고정 자산 잔액을 보여줍니다.

[![고정 자산 잔액.](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)

다음 그림은 게시된 바우처를 보여줍니다.

[![순 장부가액.](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]