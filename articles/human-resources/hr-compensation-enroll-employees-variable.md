---
title: 변동 보상 계획에 직원 등록
description: 보상 및 복리후생 관리자는 직원을 변동 보상 계획에 등록하여 직원의 현금 및 비현금 보상을 계산할 수 있습니다.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49a64407778fba5669ad13f239363bffd4b0c7d6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452422"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>변동 보상 계획에 직원 등록


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

보상 및 복리후생 관리자는 직원을 변동 보상 계획에 등록하여 직원의 현금 및 비현금 보상을 계산할 수 있습니다. 이 절차에서는 **등록 활성화** 필드가 **예** 로 설정된 변동 보상 계획을 만들었고 해당 변동 보상 계획에 대한 자격 규칙을 만들었다고 가정합니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차를 시작하려면 **Human Resources** > **작업자** > **직원** > **보상** > **변동 계획 등록** 으로 이동합니다.

1. **새로 만들기** 를 클릭합니다.
2. **계획** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
    * 계획 조회는 자격 규칙에 따라 직원에게 자격이 있는 변동 보상 계획만 표시하도록 필터링됩니다.  
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. **일반** 섹션의 확장을 토글합니다.
5. **적용 날짜** 필드에 날짜를 입력합니다.
6. **저장** 을 클릭합니다.
7. **재정의** 섹션의 확장을 토글합니다.
    * 선택적으로 선택한 변동 계획에 대해 지정된 채용 규칙이 백분율이면 채용 규칙 날짜이 직원의 채용 날짜보다 우선하도록 설정할 수 있습니다.  
    * 변동 계획이 기준 계획의 백분율이면 직원에 대한 포상 백분율이 재정의될 수 있습니다. 변동 보상 계획이 단위 수 계획이면 직원에 대해 단위 수가 재정의될 수 있습니다.  
    * 직원에게 포상으로 고정 금액을 제공해야 하는 경우 여기에서 금액을 설정할 수 있습니다.  
8. **조직 재정의** 섹션의 확장을 토글합니다.
    * 직원의 성과를 고려해야 하는 경우, 다른 부서의 성과 또는 직원의 직위에 할당된 부서 이외의 부서, 부서는 재정의할 수 있습니다. **백분율** 열의 합계는 100이어야 합니다.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
