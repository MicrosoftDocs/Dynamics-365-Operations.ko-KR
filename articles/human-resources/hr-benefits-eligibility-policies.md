---
title: 혜택 자격 정책
description: 이 항목에서는 특정 혜택을 받을 수 있는 사용자를 정의하는 혜택 자격 정책에 대한 정보를 제공합니다.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: e1f64a0beffe12f6b4e0ad53d3bbaa96822dc7e8
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452191"
---
# <a name="benefit-eligibility-policies"></a>혜택 자격 정책


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 특정 혜택을 받을 수 있는 사용자를 정의하는 혜택 자격 정책에 대한 정보를 제공합니다.

혜택을 생성할 때 어떤 혜택을 어떤 직원이 받을 수 있는지 결정합니다. 다음 표에는 특정 직원이 사용할 수 있는 혜택의 예가 나와 있습니다.

| 혜택          | 혜택을 받을 수 있는 사람 |
|------------------|---------------------------------|
| 건강 보험 | 모든 직원                   |
| 휴대 전화     | 영업 사원, 임원         |
| 주차권   | 임원                      |

자격 정책을 생성하는 데 다음 구성 요소가 사용됩니다.

-   정책 규칙 유형
-   혜택 자격 정책

정책 규칙 유형은 특정 정책 규칙을 개발할 때 사용되는 쿼리 매개 변수를 정의합니다. 정책 규칙 유형을 생성한 후에 혜택 자격 정책을 생성할 수 있습니다. 정책을 사용하여 하나 이상의 법인에 적용되는 규칙 모음을 생성할 수 있습니다. 각 정책 내에서 이전에 생성한 혜택 자격 정책 규칙 유형을 볼 수 있습니다. 

정책 내에서 규칙의 범위를 정의합니다. 예를 들어 **임원** 이라는 이름의 혜택 자격 정책 규칙 유형을 생성하는 경우 해당 정책 내의 규칙을 지정할 수 있습니다. 이 예에서 규칙은 "임원" 단어를 포함하는 모든 작업 제목을 규칙에 포함해야 한다고 명시할 수 있습니다. 정책에 포함된 규칙의 매개 변수를 정의한 후에는 특정 규칙을 혜택에 할당할 수 있습니다.






[!INCLUDE[footer-include](../includes/footer-banner.md)]
