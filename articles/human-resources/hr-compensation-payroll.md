---
title: 지불 준비됨
description: 이 항목은 Dynamics 365 Human Resources에서 직원을 지불 준비됨으로 표시하는 방법을 보여줍니다.
author: marcelbf
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 825aa327cc1530675fad57be6fc1b4313f0cf998
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452509"
---
# <a name="ready-to-pay"></a>지불 준비됨


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

> [!NOTE]
> 직원을 지불 준비됨으로 표시하려면 먼저 기능 관리에서 **(미리 보기) 급여 통합** 기능을 활성화해야 합니다. 미리 보기 기능의 활성화에 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

인사 전문가는 이 기능으로 급여 처리 준비가 된 직원과 타사 급여 공급자가 사용하기 전에 조치가 필요한 직원을 파악할 수 있습니다.

## <a name="mark-employee-as-ready-to-pay"></a>직원을 지불 준비됨으로 표시

직원 정보를 수집하고 검증하는 데는 시간이 오래 걸리고 오류가 발생하기 쉽습니다. Dynamics 365 Human Resources는 인사 전문가가 직원 정보를 검토하고 쉽게 업데이트하는 방법을 제공하여 급여 처리를 준비하는 시간을 줄이도록 도와줍니다.

직원을 지불할 준비가 된 것으로 표시하려면 다음을 수행합니다.

1. **보상 관리** 를 엽니다. 작업 영역에는 두 개의 타일이 있습니다. 
    - **지불할 준비가 된 직원**
    - **지불할 준비가 되지 않은 직원**
    ![보상 관리 작업 영역.](./media/hr-ready-to-pay-1-workspace.png)

2. **지불할 준비가 되지 않은 직원** 타일을 선택합니다.

3. 검증할 직원을 선택합니다. **급여 탭** 의 **지불 준비됨** 그룹에서 **유효성 검사** 를 선택합니다.
    ![직원 유효성 검사.](./media/hr-ready-to-pay-2-validate.png)

4. 결과를 검토하려면 **급여 탭** 의 **지불 준비됨** 그룹에서 **결과** 를 선택합니다.

## <a name="validation"></a>유효성 검사

직원을 지불 준비가 된 것으로 표시하기 전에 직원의 프로필이 완전한지 확인됩니다.

![유효성 검사 결과.](./media/hr-ready-to-pay-3-results.png)

| 유효성 검사 | 세부 정보 |
| --- | --- |
| **주소 목적 매개 변수** | **급여 주소 목적 사용** 매개 변수가 선택되었는지 확인합니다. |
| **급여 주소** | 작업자 프로필에 **급여 거주지 위치** 또는 **급여 근무 위치** 목적의 주소가 하나 이상 있고 목적당 주소가 하나만 있는지 확인합니다. |
| **고용** | 작업자가 적어도 하나의 고용(현재, 이전 또는 미래)을 갖고 있는지 확인합니다. |
| **ID 번호** | **인적 자원 매개 변수** 페이지의 **급여 처리에 식별 유형 사용** 필드가 **예** 이고 매개 변수에 표시된 식별 유형이 작업자 프로필에 채워져 있는지 확인합니다. |
| **이름 및 성** | **이름** 및 **성** 필드가 채워져 있는지 확인합니다.|
| **직위** | 작업자에게 할당된 직위가 있는지 확인합니다. |
| **생년월일** | **생년월일** 필드가 채워져 있는지 확인합니다. |
| **보상** | 작업자가 고정 보상 계획에 등록되어 있는지 확인합니다. |

이러한 유효성 검사 중 하나가 실패하면 직원을 지불할 준비가 된 것으로 표시할 수 없습니다.

**지불 준비됨** 필드가 **아니요** 인 경우 작업자 프로필이 완전한지 확인하기 위해 작업을 수행해야 함을 나타냅니다. 이것은 데이터 엔터티에서 데이터 노출을 중지하지 않습니다. 

## <a name="process-automation"></a>프로세스 자동화

[프로세스 자동화](/dynamics365/fin-ops-core/dev-itpro/sysadmin/process-automation)를 사용하여 모든 직원의 유효성 검사를 자동화할 수 있습니다. **보상 관리** 작업 영역에서 **연결** \> **매개 변수** \> **프로세스 자동화** 로 이동합니다.

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
