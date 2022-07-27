---
title: 위치 예산 문제 해결
description: 이 문서에서는 위치 예산을 구성할 때 발생할 수 있는 질문에 대한 답변을 제공합니다. 예산 비용 요소, 보상 그룹 및 보상 표를 만드는 방법에 대한 자주 묻는 질문을 다룹니다.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: roschlom
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 492a0798d1934b0fe1adf4f0546013f394beab06948f02f92358bae408e7748f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450250"
---
# <a name="position-budgeting-troubleshooting"></a>위치 예산 문제 해결

[!include [banner](../includes/banner.md)]

이 문서에서는 위치 예산을 구성할 때 발생할 수 있는 질문에 대한 답변을 제공합니다. 예산 비용 요소, 보상 그룹 및 보상 표를 만드는 방법에 대한 자주 묻는 질문을 다룹니다. 

## <a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a>Human Resources에서 예측 위치 페이지를 찾을 수 없는 이유는 무엇입니까?

예측 위치가 Budgeting으로 이동되었습니다.

## <a name="why-cant-i-delete-a-budget-cost-element"></a>예산 비용 요소를 삭제할 수 없는 이유는 무엇입니까?
예측 위치에 할당된 예산 비용 요소는 삭제할 수 없습니다. 예산 비용 요소를 삭제하려면 먼저 모든 예측 위치에서 제거해야 합니다. **팁:** 예산 비용 요소가 할당된 모든 위치를 찾으려면 **예산 비용 요소** 페이지에서 비용 요소를 선택한 다음 **위치 업데이트** 를 클릭합니다. 비용 요소를 사용하는 위치가 위쪽 표에 나열됩니다.

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a>각 예측 위치를 열지 않고 여러 예측 위치에서 비용 요소를 제거하려면 어떻게 해야 합니까?
비용 요소는 제거할 수 없습니다. 그러나 예산 계획 주기 날짜를 벗어나도록 시작 날짜와 종료 날짜를 변경하면 비용 요소가 해당 예산 계획 주기의 예측 위치에 더 이상 할당되지 않습니다. 이렇게 변경하려면 예산 비용 요소를 연 다음 **비용 계산** FastTab에서 **날짜 변경** 을 클릭하고 유효 날짜 또는 만료 날짜를 변경하십시오. 그런 다음 **확인** 을 클릭하여 비용 요소가 할당된 모든 예측 위치를 자동으로 업데이트합니다. **팁**: 이 방법을 사용할 경우 시작일과 종료일이 더 이상 적절한 범위에 속하지 않는 **모든** 예측 위치에서 예산 비용 요소를 제거합니다. 이 효과가 의도하지 않은 경우 예산 비용 요소를 제거할 각 예측 위치를 열고 수동으로 변경해야 합니다.

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a>예산 비용 요소의 비용 계산 FastTab에 연간 금액을 입력할 수 없는 이유는 무엇입니까?
**계산 기준** FastTab에 예산 비용 요소가 있으면 연간 금액을 입력할 수 없습니다. 시스템이 값을 계산하기 위해 백분율을 요구하기 때문입니다. 값을 변경하려면 **계산 기준** FastTab에서 모든 예산 비용 요소를 제거하십시오.

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a>예산 비용 유형을 수익에서 다른 예산 비용 유형으로 변경할 수 없는 이유는 무엇입니까?
일부 예산 비용 요소는 수익 비용 요소를 계산 기준으로 사용합니다. **예산 비용 유형** 필드를 변경하려면 모든 예산 비용 요소의 **계산 기준** FastTab에서 수익 비용 요소를 제거하십시오.

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a>예산 비용 요소에 대한 예산 비용 요소 라인의 날짜를 변경할 수 없는 이유는 무엇입니까?
예산 비용 요소가 예측 위치에서 사용되는 경우 예산 비용 요소 라인에서 날짜를 변경할 수 없습니다. 이러한 제한은 예측 위치가 항상 예산 비용 요소의 지침 내에 있도록 하는 데 도움이 됩니다. 날짜를 변경하려면 **비용 계산** FastTab에서 **날짜 변경** 을 클릭하고 새 날짜를 입력합니다. 그런 다음 **확인** 을 클릭하여 비용 요소가 할당된 위치를 업데이트합니다.

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a>보상 그룹 페이지에서 예산 비용 요소의 비용을 변경할 수 없는 이유는 무엇입니까?
예산 비용 요소는 **예산 비용 요소** 페이지에서만 생성 및 변경할 수 있습니다.

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a>예측 위치에서 비용 요소의 날짜를 변경할 때 오류 메시지가 표시되는 이유는 무엇입니까?
예측 위치 비용 요소 라인의 날짜는 다음 범위 내에 있어야 합니다.

-   위치의 활성화 및 만료 날짜.
-   예산 비용 요소의 활성화 및 만료 날짜.
-   예측 위치의 예산 계획 프로세스와 관련된 예산 주기의 시작 및 종료 날짜.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]