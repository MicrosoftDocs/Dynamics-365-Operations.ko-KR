---
title: 혜택 프로그램을 정의 및 관리
description: Human Resources는 조직이 근로자에게 제공하거나 처리하는 급여, 공제 및 근로자 보상 계획을 설정하고 유지하는 데 사용할 수 있는 도구 집합을 제공합니다. 이 항목에서는 혜택을 설정하고 관리하는 방법에 대한 정보를 제공합니다.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, HcmBenefitSelection, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 15681
ms.assetid: 6aee97ac-29f7-4b3c-8aa1-c65810de3090
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 1f2bfa901aa299a091194978ee95ff0e69f2cdbf
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452122"
---
# <a name="define-and-manage-a-benefits-program"></a>혜택 프로그램을 정의 및 관리


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Human Resources는 조직이 근로자에게 제공하거나 처리하는 급여, 공제 및 근로자 보상 계획을 설정하고 유지하는 데 사용할 수 있는 도구 집합을 제공합니다. 이 항목에서는 혜택을 설정하고 관리하는 방법에 대한 정보를 제공합니다.

## <a name="benefit-setup"></a>혜택 설정

근로자를 혜택에 등록하려면 먼저 각 혜택의 요소를 작성해야 합니다. 이러한 요소는 유사한 혜택 계획을 결합하고 공제율 및 회계 세부 정보와 같은 기본 설정을 정의합니다. 이러한 설정의 대부분은 나중에 근로자가 혜택에 등록될 때 조정할 수 있습니다. 각 혜택 플랜에 대해 조직은 여러 가지 등록 옵션을 제공하거나, 근로자는 플랜 등록을 포기할 수 있습니다. 

[![혜택 프로세스 흐름.](./media/benefit-process-flow1.png)](./media/benefit-process-flow1.png)

## <a name="benefit-elements"></a>혜택 요소

혜택을 만들고 해당 혜택에 직원을 등록하기 전에 혜택을 구성하는 요소(유형, 계획 및 옵션)를 정의해야 합니다.

-   **유형** – 의료 또는 주차와 같은 특정 혜택을 위한 계획 모음입니다.
-   **계획** – 제공자와 계약한 특정 혜택입니다.
-   **옵션** – 직원 전용 또는 직원 및 배우자/파트너와 같은 적용 범위 수준입니다.

안과나 치과와 같은 각 유형의 혜택에 대해 조직은 직원들에게 하나 이상의 계획을 제공할 수 있습니다. 각 계획에 대해 조직은 서로 다른 옵션을 제공할 수 있습니다. 예를 들어, 근로자들은 그들의 연봉의 1배, 2배, 또는 3배의 추가 기간 종신보험에 가입할 수 있습니다. 계획과 옵션의 각 조합은 근로자가 등록할 수 있는 혜택이 됩니다. 

[![혜택 그림.](./media/benefit-pic.png)](./media/benefit-pic.png)

## <a name="eligibility"></a>자격
많은 요인들이 고용주가 제공하는 다양한 유형의 혜택에 대한 근로자들의 자격을 결정합니다. Dynamics 365 Human Resources에서 혜택을 생성할 때 해당 혜택에 적용되는 자격 유형을 설정할 수 있습니다. 

모든 근로자에게 혜택을 제공할 수 있습니다. 예를 들어, 어떤 회사는 부수적인 혜택으로 모든 직원에게 주차권을 제공합니다. 이 혜택을 만들 때 자격 요건을 **모든 근로자가 대상** 으로 설정합니다. 

장식이나 세금과 같은 다른 혜택은 자격이 적용되지 않습니다. 이러한 유형의 혜택을 만들 때 자격 부여를 **자격 부여 프로세스를 무시** 하도록 설정합니다. 

마지막으로, 혜택 자격은 규칙 기반일 수 있습니다. 예를 들어, 회사가 직원에게 두 가지 유형의 생명 보험 혜택을 제공합니다. 임원은 하나의 생명보험에 가입할 수 있는 반면, 다른 모든 정규직 직원은 다른 생명보험에 가입할 수 있습니다. Human Resources에서 모든 임원 직원을 찾기 위한 혜택 자격 규칙을 만들고 다른 모든 정규직 직원을 찾기 위한 다른 규칙을 만든 다음 해당 규칙을 적절한 혜택에 적용할 수 있습니다.

## <a name="enrollment"></a>등록
조직에서 제공하는 혜택을 만들고 자격을 결정한 후에는 직원을 혜택에 등록할 수 있습니다. 단일 근로자를 혜택에 등록하거나 단일 프로세스 동안 하나 이상의 혜택에 여러 근로자를 등록할 수 있습니다. 

때때로 조직은 특정 혜택을 제공하는 것을 중단합니다. 이 경우 혜택과 등록된 근로자를 업데이트해야 합니다. 대량 혜택 만료로 혜택 및 해당 혜택에 대한 근로자 등록의 만료 날짜를 동시에 변경할 수 있습니다. 또한 혜택에 등록된 여러 명의 근로자를 선택하고 해당 근로자의 보험 적용 종료 날짜를 변경할 수 있습니다. 

마찬가지로, 대규모 혜택 연장을 사용하면 혜택을 원래 계획보다 더 길게 제공하기로 결정한 경우 혜택과 해당 혜택에 대한 근로자 등록의 만료 날짜를 모두 연장할 수 있습니다.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
