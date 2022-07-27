---
title: 혜택 자격 규칙 및 정책 정의
description: 이 항목에서는 혜택 자격 규칙 및 정책을 만든 다음 혜택을 규칙을 할당하는 방법에 대해 설명합니다.
author: twheeloc
ms.date: 08/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysPolicyListPage, SysPolicy, HcmBenefitEligibilityPolicy, HcmBenefit, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Version 7.0.0, Human Resources
ms.openlocfilehash: c2595e40f6f9d1f75a94a3339735cc06bdabd14a
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452380"
---
# <a name="define-benefit-eligibility-rules-and-policies"></a>혜택 자격 규칙 및 정책 정의


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 혜택 자격 규칙 및 정책을 만든 다음 혜택을 규칙을 할당하는 방법에 대해 설명합니다.  

## <a name="create-benefit-eligibility-policy-rule-type"></a>혜택 자격 정책 규칙 유형 만들기

1. **인사 > 혜택 > 자격 > 혜택 자격 정책 규칙 유형** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **규칙 이름** 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다.
5. **쿼리 이름** 필드에서 드롭다운 버튼을 선택하여 조회를 엽니다.
6. 목록에서 선택한 행의 링크를 선택합니다.
7. **저장** 을 선택합니다.
8. 페이지를 닫습니다.

## <a name="benefit-eligibility-policy"></a>혜택 자격 정책

1. **인사 > 혜택 > 자격 > 혜택 자격 정책** 으로 이동합니다.
2. 기존 혜택 정책을 선택합니다.
3. 목록에서 선택한 행의 링크를 선택합니다.
4. **정책 조직** 섹션의 확장을 토글합니다. 정책에 포함할 조직을 추가하거나 제거할 수 있습니다.
5. **정책 규칙** 섹션을 확장하거나 축소합니다.
6. 목록에서 이전에 만든 정책 규칙을 찾습니다.
7. **정책 규칙 만들기** 를 선택합니다.
8. **유효 날짜** 필드에 정책을 적용할 날짜를 입력합니다.
    * 유효 종료 날짜를 설정하면 정책 규칙을 나중에 변경할 수 있으므로 변경 내용을 적용하려는 경우 정책으로 돌아갈 필요가 없습니다.  
9. 필요한 경우 **조건 추가** 필드에 조건 절을 추가합니다.
    * 예를 들어, 규칙이 영업 관리자에만 적용되도록 하려면 조건 절을 만들어 조건: 직급은 영업 관리자와 같이 할 수 있습니다. 규칙에 여러 개의 조건 문을 함께 추가할 수 있습니다.  
10. **확인** 을 선택합니다.
11. 페이지를 닫습니다.

## <a name="assign-rule-to-benefit"></a>혜택에 규칙 할당

1. **인사 > 혜택 > 혜택** 으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 목록에서 선택한 행의 링크를 선택합니다.
4. **자격 규칙** 섹션을 확장하거나 축소합니다.
5. **편집** 을 선택합니다.
6. **자격** 필드에서 규칙을 선택합니다.
7. **규칙 유형** 필드에서 이전에 만든 규칙을 선택합니다.
9. 목록에서 선택한 행의 링크를 선택합니다.
10. **저장** 을 선택합니다.
11. 양식을 닫습니다.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
