---
title: 급여 통합 매개 변수
description: 이 항목에서는 Dynamics 365 Human Resources 급여 통합 매개 변수에 관해 설명합니다.
author: marcelbf
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-17
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 37d4dc52e7fe5ddd95f43d98267db819a275bd92
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452593"
---
# <a name="payroll-integration-parameters"></a>급여 통합 매개 변수


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources 급여 통합을 사용하기 전에 이 항목에 설명된 매개 변수를 설정해야 합니다.

## <a name="enable-payroll-address"></a>급여 주소 활성화

급여 주소를 사용하려면 급여 통합 탭의 [공유 매개 변수 양식](hr-setup-shared-parameters.md)에서 활성화해야 합니다.

## <a name="define-the-identification-type"></a>식별 유형 정의

[급여 직원 엔터티](hr-admin-integration-payroll-api-payroll-employee.md)에서 식별 유형 ID를 노출하려면 각 회사에 대해 [Human Resources 매개 변수를 구성](hr-setup-shared-parameters.md)해야 합니다.

1. **보상 관리** 작업 영역의 연결에서 **Human Resources 매개 변수** 를 선택합니다. 
2. **급여 통합** 탭에서 다음 필드의 값을 지정합니다.

| 필드 | 설명 |
| --- | --- |
| 급여 처리에 식별 유형 사용 | 이 옵션을 선택하면 선택한 유형 ID가 급여 직원 엔터티에 노출됩니다. |
| 식별 유형 | [급여 직원 엔터티](hr-admin-integration-payroll-api-payroll-employee.md)의 **mshr_payrollemployeeentityid** 필드에 노출될 식별 유형. |

## <a name="see-also"></a>참고 항목

[급여 통합 API 소개](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
