---
title: 공제 구성
description: Microsoft Dynamics 365 Human Resources에서 공제를 사용하여 각 복리후생을 위해 직원의 급여에서 공제할 금액(있는 경우)을 결정합니다.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bf7ddbfb8717c0311fab7388f346f03618a7b43d
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452167"
---
# <a name="configure-deductions"></a>공제 구성


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources에서 공제를 사용하여 각 복리후생을 위해 직원의 급여에서 공제할 금액(있는 경우)을 결정합니다. 공제는 날짜가 적용되므로 공제 정보의 과거 기록을 유지할 수 있습니다. 

1. **복리후생 관리** 작업 영역의 **설정** 에서 **공제** 를 선택합니다.

2. **새로 만들기** 를 선택합니다.

3. 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **공제** | 복리후생 공제를 식별하는 데 사용되는 고유 ID. |
   | **설명** | 복리후생에 대한 설명. |
   | **유효** | 시작 날짜. 기본값은 현재 시스템 날짜입니다. |
   | **만료** | 종료 날짜. 기본값은 2154-12-31이며 종료되지 않음을 의미합니다. |
   | **제목** | 급여에 대해 복리후생을 처리할 때 이 공제가 공제의 직원 부분에 사용할 급여 시스템의 제목 코드. 타사 급여 공급자를 사용할 때 사용됩니다. |
   | **직원 급여 공제 참조** | 급여에 대해 복리후생을 처리할 때 이 공제가 공제의 직원 부분에 사용할 급여 시스템의 공제 코드. |
   | **금액 제목** | 급여에 대해 복리후생을 처리할 때 이 공제 금액이 공제의 직원 부분에 사용할 급여 시스템의 제목 코드. 일반적으로 타사 급여 공급자를 사용할 때 사용됩니다. |
   | **삭제할 수 있음** | Dynamics 365 for Finance and Operations에서 내보낸 값으로 인해 급여 시스템에서 값이 삭제될 수 있는지를 지정합니다. |
   | **연결된 열** | 연결된 인접 열의 제목 및 공제 금액을 급여 시스템으로 내보낼지를 지정합니다. |
   | **적용 날짜 변경** | 급여 공제 변경이 적용되는 날짜. **공제 변경 업데이트** 처리를 실행하는 한 이 날짜에 복리후생 공제 변경 사항 및 이 공제와 관련된 모든 복리후생 계획이 업데이트됩니다. |
   | **공제 변경 완료** | 공제 업데이트 변경 처리를 통해 급여 공제 변경이 완료되면 **공제 변경 완료** 확인란이 자동으로 선택됩니다. |
   
4. 복리후생 요율 설정에 대한 변경 사항을 추적하고 유지하려면 **작업** 을 선택한 다음 **버전 유지** 를 선택합니다.

5. **저장** 을 선택합니다. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
