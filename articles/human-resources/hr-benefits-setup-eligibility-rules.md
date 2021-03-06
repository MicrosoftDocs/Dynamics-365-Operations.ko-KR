---
title: 자격 규칙 및 옵션 구성
description: 이 항목에서는 Microsoft Dynamics 365 Human Resources의 복리후생 관리에서 자격 규칙 및 옵션을 설정하는 방법을 설명합니다.
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
ms.openlocfilehash: e87bef8994fe1eac0089764c8d4f9b18289c13ea
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452566"
---
# <a name="configure-eligibility-rules-and-options"></a>자격 규칙 및 옵션 구성 


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

복리후생 관리에 필요한 매개 변수를 구성한 후 복리후생 계획과 연결할 자격 규칙, 번들, 기간 및 프로그램을 만들 수 있습니다.

자격 규칙은 직원이 계획에 대한 자격이 있는지를 결정하는 데 사용됩니다. 직원이 복리후생 자격이 있는 것으로 간주되려면 최소한 하나의 규칙 조건을 충족해야 합니다. 예를 들어 계획에 두 규칙이 있다고 가정해보겠습니다. 첫 번째 규칙(1행)은 직원 유형이 **직원** 이어야 한다고 명시합니다. 두 번째 규칙(2행)은 직원이 정규직으로 고용되어야 한다고 명시합니다. 따라서 규칙 1을 충족하는 직원은 시간제로 고용되어도 자격이 됩니다.

그러나 여러 조건이 있는 단일 규칙을 설정할 수 있습니다. 이 경우 직원은 규칙의 모든 조건을 충족해야 복리후생 자격이 있는 것으로 간주됩니다. 예를 들어 **정규직 직원** 이라는 규칙이 있다고 가정해보겠습니다. 이 규칙은 직원 유형이 **직원** 이고 *또한* 직원이 정규직으로 고용되어야 한다고 명시합니다. 따라서 직원이 자격을 갖추려면 규칙의 두 조건을 모두 충족해야 합니다.

> [!IMPORTANT]
> 적어도 하나의 자격 규칙이 모든 복리후생 계획과 연결되어야 합니다. 하나의 복리후생에 여러 규칙을 연결할 수 있습니다.

## <a name="create-an-eligibility-rule"></a>자격 규칙 만들기

자격 규칙은 각 복리후생 계획에 등록할 수 있는 직원을 정의합니다. 자격 규칙을 정의한 후 복리후생 계획에 할당합니다. 그러면 등록 자격을 처리하여 각 계획에 자격이 있는 직원을 확인할 수 있습니다. 

직원은 공개 등록 중에 복리후생 계획을 선택할 수 있습니다. 이미 등록된 후 자격 규칙에 따라 복리후생 계획에 대한 자격이 없는 경우 자동으로 등록이 취소되지는 않습니다. 일반적으로 계획 자격에 영향을 미치는 생활 이벤트가 발생하면 사원이 적격한 계획을 선택할 수 있도록 등록 기간이 시작됩니다. 

1. **복리후생 관리** 작업 영역의 **설정** 에서 **자격 규칙 및 옵션** 을 선택합니다.

2. **자격 규칙** 탭에서 **새로 만들기** 를 선택하여 자격 규칙을 만듭니다. 자격 규칙과 연결된 계획을 보려면 **연결된 계획** 을 선택합니다.

3. 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **자격 규칙** | 자격 규칙의 고유 식별자. |
   | **설명** | 자격 규칙에 대한 설명. |
   | **유효 기간 시작 날짜 및 시간** | 자격 규칙의 시작 날짜. | 
   | **유효 기간 종료 날짜 및 시간** | 자격 규칙의 종료 날짜. |
   | **사용자 직원 유형** | 복리후생 자격 규칙에 직원의 직원 유형을 사용할지를 지정합니다. |
   | **작업자 유형** | **직원 유형 사용** 토글이 **예** 로 설정된 경우 작업자 유형. |
   | **직원 상태 사용** | 복리후생 자격 규칙에 직원의 고용 상태를 사용할지를 지정합니다. |
   | **상태** | **직원 상태 사용** 토글이 **예** 로 설정된 경우 직원 유형. **직원 상태 사용** 토글이 **아니요** 로 설정된 경우 필드가 사용되지 않습니다. |
   | **고용 범주 사용** | 복리후생 자격 규칙의 일부로 직원의 **고용 범주** 값을 사용할지를 지정합니다. | 
   | **고용 범주** | **고용 범주 사용** 토글이 **예** 로 설정된 경우 직원의 고용 범주. |
   | **신규 채용 규칙 사용** | 신규 채용의 신규 채용 기간 값을 복리후생 자격 규칙의 일부로 사용할지를 지정합니다. |
   | **등록 기간** | 신규 채용 등록이 허용되는 기간. 매개 변수에서도 이를 설정하면 매개 변수 설정이 이 설정보다 우선합니다. |
   | **이전 고용 상태 사용** | 복리후생 자격 규칙의 일부로 직원의 이전 고용 상태를 사용할지를 지정합니다. 예를 들어, 이전 고용 후 90일 이내에 **해고** 상태에서 **고용** 상태로 전환된 모든 직원에 대해 보장 대기 기간을 면제하는 자격 규칙을 지정할 수 있습니다. |

4. **추가 기준** 에서 다음 옵션을 선택하고 필요에 따라 정보를 추가합니다.

   | 옵션 | 설명 |
   | --- | --- |
   | **적격 나이** | 자격 규칙을 충족하는 나이 범위를 지정합니다. |
   | **적격 부서** | 자격 규칙을 충족하기 위한 직원의 부서를 지정합니다. |
   | **적격 고용 유형** | 직원이 자격 규칙을 충족하기 위해 분류되어야 하는 고용 유형을 지정합니다. 예: 정규직 또는 비정규직. |
   | **적격 직무** | 자격 규칙을 충족하는 직무를 지정합니다. 직무는 직위와 연결되어 있으며 직위가 직원으로 채워집니다. |
   | **적격 직무 기능** | 자격 규칙을 충족하는 직무 기능을 지정합니다. 예: 영업사원 또는 기술자. |
   | **적격 직무 유형** | 자격 규칙을 충족하는 직무 유형을 지정합니다. 예: 사무직 또는 임원. |
   | **적격 법인** | 자격 규칙에 대해 유효한 법인을 지정합니다. 예: Contoso Entertainment System USA. |
   | **적격 보상 지역** | 자격 규칙을 충족하는 직원 위치를 지정합니다. 예: 미국 중부. |
   | **적격 직위** | 자격 규칙을 충족하는 직위를 지정합니다. 예: 인사대리 또는 인사과장. |
   | **적격 직위 유형** | 자격 규칙을 충족하는 직위 유형을 지정합니다. 예: 정규직. |
   | **적격 주/도** | 자격 규칙을 충족하는 주 또는 도를 지정합니다. 예: 미국 노스다코타 또는 캐나다 브리티시 컬럼비아. |
   | **적격 고용 조건** | 자격 규칙을 충족하는 고용 조건을 지정합니다. 예: 자발 고용 또는 그룹 계약. |
   | **적격 조합** | 자격 규칙을 충족하는 노조 구성원 자격을 지정합니다. 예: 미국 지게차 운전사 노조.</br></br>노조 기반 자격 규칙을 사용할 때는 작업자의 노조 레코드에 종료 날짜가 채워져 있어야 합니다. 비워둘 수 없습니다. |
   | **적격 우편 번호** | 자격 규칙을 충족하는 우편 번호를 지정합니다. 예: 58104. |

5. **추가 세부 정보** 에서 다음과 같은 추가 세부 정보를 볼 수 있습니다.

   | 필드 | 설명 |
   | --- | --- |
   | **적격 사용자 필드** | 고객 정의 필드를 기반으로 추가 자격 규칙을 지정합니다. |
   | **적격 유형** | **추가 기준** 에서 선택한 기준 범주를 지정합니다. |
   | **적격 참조** | **추가 기준** 에서 선택한 값을 지정합니다. |
   | **설명** | **추가 기준** 에서 선택한 설명. |

6. **저장** 을 선택합니다.

## <a name="using-custom-fields-in-eligibility-rules"></a>자격 규칙에서 사용자 지정 필드 사용

Human Resources에서 [사용자 지정 필드](hr-developer-custom-fields.md)를 만들어 추가 정보를 추적할 수 있습니다. 이러한 필드는 사용자 인터페이스에 직접 추가할 수 있으며 열은 기본 테이블에 동적으로 추가됩니다.  

사용자 지정 필드는 자격 프로세스에서 사용할 수 있습니다. 자격 규칙은 하나 이상의 사용자 지정 필드 값을 사용하여 직원의 자격을 결정할 수 있습니다.  기존 규칙에 사용자 지정 필드를 추가하거나 새 규칙을 생성하려면 **복리후생 관리 > 링크 > 설정 > 적격 규칙 > 사용자 지정 필드 자격** 으로 이동합니다. 이 페이지 내에서 하나 이상의 사용자 지정 필드를 사용하는 규칙을 만들 수 있으며 각 사용자 지정 필드에 대해 여러 값을 정의하여 자격을 결정할 수 있습니다.

다음 표는 자격 처리에 사용할 수 있는 사용자 지정 필드를 지원합니다.

- 작업자(HcmWorker)  
- 직무(HcmJob)  
- 직위(HcmPosition)  
- 직위 세부 정보(HcmPositionDetail)  
- 직위 작업자 배정  
- 고용(HcmEmployment)  
- 고용 세부 정보(HcmEmploymentDetails)  
- 직무 세부 정보(HcmJobDetails)  

자격 처리에 지원되는 사용자 지정 필드 유형은 다음과 같습니다.

- 텍스트  
- 선택 목록  
- 숫자  
- 십진수  
- 확인란  

다음 표는 사용자 지정 필드 자격 양식 필드 정보를 보여줍니다.

| 필드  | 설명 |
|--------|-------------|
| 이름 | 만드는 기준의 이름. |
| 테이블 이름 | 자격 규칙에 사용 중인 사용자 지정 필드가 포함된 테이블 이름. |
| 필드 이름 | 자격 규칙에 사용될 필드. |
| 연산자 유형 | 사용자 지정 필드 자격 구성에 사용된 연산자를 표시합니다. |
| 값 | 사용자 지정 필드 자격 구성에 사용된 값을 표시합니다. |

## <a name="eligibility-logic"></a>자격 논리

다음 섹션에서는 복리후생 자격이 처리되는 방법을 설명합니다.

### <a name="rules-assigned-to-a-plan"></a>계획에 할당된 규칙 
하나의 복리후생 계획에 여러 자격 규칙이 할당된 경우 직원은 하나 이상의 규칙을 충족해야 복리후생 계획에 등록할 자격이 됩니다.  다음 예에서 직원은 **직무 유형** 규칙 또는 **활성 직원** 규칙의 요구 사항 중 하나를 충족해야 합니다.

![직원은 직무 유형 규칙 또는 활성 직원 규칙의 요구 사항 중 하나를 충족해야 합니다.](media/RulesAssignedToAPlan.png)
 
### <a name="criteria-within-an-eligibility-rule"></a>자격 규칙 내의 기준 
규칙 내에서 규칙을 구성하는 기준을 정의합니다. 위의 예에서 **직무 유형** 규칙의 기준은 직무 유형 = 이사인 경우입니다. 따라서 직원이 자격을 갖추려면 이사여야 합니다. 이것은 규칙 내에 기준이 하나만 있는 규칙입니다.

여러 기준이 있는 규칙을 정의할 수 있습니다. 하나의 자격 규칙 내에서 여러 기준을 정의하면 직원이 규칙의 모든 기준을 충족해야 해당 복리후생 계획의 자격이 있습니다. 

예를 들어 위의 **활성 직원** 규칙은 다음 기준으로 구성됩니다. 직원이 **활성 직원** 규칙에 따라 자격을 갖추려면 직원이 법인 USMF에 고용되어 있어야 *하고* 직위 유형이 정규직이어야 합니다.  

![자격 규칙 내의 기준.](media/CriteriaWithinAnEligibilityRule.png) 
 
### <a name="multiple-conditions-within-criteria"></a>기준 내의 여러 조건

단일 기준 내에서 여러 조건을 사용하도록 추가로 규칙을 확장할 수 있습니다. 직원이 자격을 갖추려면 최소한 하나의 조건을 충족해야 합니다. 위의 예를 기반으로 **활성 직원** 규칙을 추가로 확장하여 비정규직 직원도 포함하도록 할 수 있습니다. 결과적으로 이제 직원은 USMF의 직원이어야 *하며* 정규직 또는 비정규직 직원이어야 합니다.  

![기준 내의 여러 조건.](media/MultipleConditionsWithinCriteria.png) 
 
### <a name="eligibility-conditions-within-a-custom-field-criterion"></a>사용자 지정 필드 기준 내의 자격 조건 
위와 비슷하게 자격 규칙을 만들 때 사용자 지정 필드를 사용할 수 있으며 동일한 방식으로 작동합니다. 예를 들어 파고와 코펜하겐 지역에서 재택근무를 하는 직원에게 인터넷 상환을 제공할 수 있습니다. 해당 지역의 인터넷 비용이 더 많이 들기 때문입니다. 이렇게 하려면 **사무실 위치**(선택 목록) 및 **재택근무**(확인란)의 두 사용자 지정 필드를 만듭니다. 그런 다음 **WFH 직원** 이라는 규칙을 만듭니다. 이 규칙의 기준은 **사무실 위치 = 파고** 또는 **코펜하겐** *그리고* **재택근무 = 예** 입니다.

사용자 지정 자격 규칙은 다음 이미지에 표시된 대로 설정해야 합니다. 

![사용자 지정 필드 기준 내의 자격 조건.](media/EligibilityConditionsWithinACustomFieldCriterion.png) 
 
## <a name="configure-bundles"></a>번들 구성

번들은 연관된 복리후생 계획의 집합입니다. 복리후생 번들을 사용하여 사원이 다른 복리후생 계획 등록에 종속될 수 있는 특정 복리후생 계획에 등록하기 위해 선택해야 하는 복리후생 계획을 그룹화할 수 있습니다. 번들을 사용할 수 있는 예는 다음과 같습니다.

- 건강 예금 계좌(HSA)와 연결된 높은 공제 건강 보험이 포함된 건강 계획 번들.

- 의무적인 직원 생명 보험이 피부양자 생명 보험과 함께 제공되는 생명 보험 상품. 이렇게 하면 직원이 직원 보장에 가입하지 않으면 피부양자 생명 보험 보장을 선택할 수 없습니다.

1. **복리후생 관리** 작업 영역의 **설정** 에서 **자격 규칙 및 옵션** 을 선택합니다.

2. **번들** 탭에서 **새로 만들기** 를 선택하여 번들을 만듭니다. 번들과 연결된 계획을 보려면 **연결된 계획** 을 선택합니다.

3. 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **번들** | 번들의 고유 식별자. |
   | **설명** | 번들에 대한 설명. |
   | **마스터** | 번들의 계획 중 하나를 마스터 계획으로 표시해야 하는지를 나타냅니다. 복리후생 관리자가 직원 복리후생 선택을 확정하려면 먼저 마스터 계획을 번들의 일부로 공개 등록 중에 선택해야 합니다. |
   | **유효 기간 시작 날짜 및 시간** | 번들이 활성화되는 날짜 및 시간. |
   | **유효 기간 종료** | 번들이 만료되는 날짜. 기본값은 2154-12-31이며 종료되지 않음을 의미합니다. |

4. **저장** 을 선택합니다.

## <a name="configure-periods"></a>기간 구성

기간은 복리후생이 적용되는 시기와 직원이 등록할 수 있는 시기를 정의합니다. 복리후생 개설 등록 및 복리후생 적용 기간을 유지하기 위해 원하는 만큼 기간을 생성할 수 있습니다. 복리후생 계획 연도는 달력 연도를 따르거나 따르지 않을 수 있습니다. 

1. **복리후생 관리** 작업 영역의 **설정** 에서 **자격 규칙 및 옵션** 을 선택합니다.

2. **기간** 탭에서 **새로 만들기** 를 선택하여 기간을 만듭니다. 유효한 모든 활성 복리후생 계획을 복리후생 기간에 연결하는 프로세스를 실행하려면 **계획 연결** 을 선택합니다. 번들과 연결된 계획을 보려면 **연결된 계획** 을 선택합니다. 

3. 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **기간** | 기간의 고유 식별자. |
   | **유효 기간 시작 날짜 및 시간** | 복리후생 기간이 활성화된 시작 날짜 및 시간. |
   | **유효 기간 종료 날짜 및 시간** | 복리후생 기간이 비활성화된 날짜 및 시간. |
   | **등록 시작** | 공개 등록의 시작 날짜. 공개 등록은 직원이 셀프 서비스 복리후생에서 복리후생을 선택할 수 있는 시기입니다. |
   | **등록 종료** | 공개 등록의 종료 날짜. |
   | **열기** | 시스템 날짜와 유효한 시작 및 종료 날짜 및 시간을 기준으로 기간이 개설되었는지를 나타냅니다. | 
   | **이전 기간** | 선택한 복리후생 기간보다 앞선 복리후생 기간을 지정합니다. 이 정보는 복리후생 자격 등록 중에 계획, 보장 옵션 및 이전 연도의 피지명인을 지정하는 데 사용됩니다. |
 
4. **저장** 을 선택합니다.

## <a name="use-a-flex-credit-program"></a>플렉스 크레딧 프로그램 사용

플렉스 크레딧 프로그램을 사용하여 미리 결정된 플렉스 크레딧 수에 따라 복리후생에 직원을 등록할 수 있습니다. 직원은 플렉스 크레딧을 할당하는 방법을 선택할 수 있습니다. 예를 들어 직원이 배우자의 건강 보험에 가입된 경우 다른 혜택을 받기 위해 건강 보험에 사용했을 크레딧을 사용할 수 있습니다.

1. **복리후생 관리** 작업 영역의 **설정** 에서 **자격 규칙 및 옵션** 을 선택합니다.

2. **기간** 탭에서 **플렉스 크레딧 프로그램** 을 선택합니다.

3. 적용할 플렉스 크레딧 프로그램을 선택합니다. 필드에는 다음 정보가 포함됩니다.

   | 필드 | 설명 |
   | --- | --- |
   | **복리후생 크레딧 ID** | 플렉스 크레딧 프로그램의 고유 식별자. |
   | **설명** | 플렉스 크레딧 프로그램에 대한 설명. | 
   | **시작 날짜** | 플렉스 크레딧 프로그램이 활성화된 날짜. |
   | **종료 날짜** | 플렉스 크레딧 프로그램의 종료 날짜. 플렉스 크레딧 프로그램에 예정된 만료 날짜가 없음을 나타내기 위해 기본값(2154-12-31)을 그대로 둘 수 있습니다. |
   | **총 크레딧 값** | 각 직원이 복리후생을 위해 사용해야 하는 크레딧 수. |
   | **비례 배분 규칙** | 플렉스 크레딧 기간 중간에 직원이 채용된 경우 플렉스 크레딧을 비례 배분하는 데 사용할 규칙. </br></br><ul><li>**없음** – 직원이 플렉스 크레딧 프로그램 기간이 시작된 후에 채용된 경우 플렉스 크레딧을 받지 않습니다.</li><li>**전체 크레딧** – 직원은 고용된 시기에 관계없이 전체 플렉스 크레딧을 받습니다.</li><li>**비례 배분** – 직원은 시작 날짜를 기준으로 비례 배분된 플렉스 크레딧을 받습니다.</li></ul> |
   | **플렉스 크레딧 비례 배분 공식** | 플렉스 크레딧 프로그램의 복리후생 기간 중간에 채용된 직원에게 플렉스 크레딧을 비례 배분하는 데 사용할 규칙. 비례 배분은 고용 시작 날짜를 기준으로 합니다. 이 필드는 **비례 배분 규칙** 필드에서 **비례 배분** 을 선택한 경우에만 사용됩니다. </br></br><ul><li>**일별** – 직원이 받는 플렉스 크레딧 수를 일별로 비례 배분합니다. 총 플렉스 크레딧 수는 해당 기간의 일수로 나뉩니다. 예를 들어 복리후생 기간이 400일인 경우 시스템은 총 플렉스 크레딧 수를 400으로 나누어 직원이 하루에 받는 플렉스 크레딧 수를 계산합니다.</li><li>**이번 달** – 직원이 받는 플렉스 크레딧 수를 월 수준으로 비례 배분하여 이번 달로 반올림합니다. 총 플렉스 크레딧 수는 해당 기간의 개월 수로 나뉩니다. 예를 들어 복리후생 기간이 15개월인 경우 시스템은 총 플렉스 크레딧 수를 15로 나누어 직원이 매월 받는 플렉스 크레딧 수를 계산합니다.</li><li>**다음 달** – 직원이 받는 플렉스 크레딧 수를 월 수준으로 비례 배분하여 다음 달로 반올림합니다. 총 플렉스 크레딧 수는 해당 기간의 개월 수로 나뉩니다. 예를 들어 복리후생 기간이 15개월인 경우 시스템은 총 플렉스 크레딧 수를 15로 나누어 직원이 매월 받는 플렉스 크레딧 수를 계산합니다.</li></ul> |
   
   각 복리후생 계획은 복리후생 기간당 하나의 플렉스 크레딧 프로그램에만 등록되어야 합니다. 그렇지 않으면 시스템은 플렉스 크레딧을 부여하는 데 어떤 플렉스 크레딧 프로그램을 사용할지 알지 못해 문제가 발생합니다. 

## <a name="configure-programs"></a>프로그램 구성

프로그램은 공통의 자격 규칙 집합을 공유하는 복리후생 계획 집합입니다. 개별 계획 대신 전체 프로그램에 대한 자격 규칙을 정의할 수 있습니다. 예: Contoso Canada FTE 프로그램 또는 Contoso Europe 임원 수준 프로그램. 

1. **복리후생 관리** 작업 영역의 **설정** 에서 **자격 규칙 및 옵션** 을 선택합니다.

2. **프로그램** 탭에서 **새로 만들기** 를 선택하여 프로그램을 만듭니다. 자격 규칙 요구 사항을 충족하지 않는 직원에 대한 예외를 설정하려면 **자격 규칙 재정의** 를 선택합니다. 프로그램과 연결된 계획을 보려면 **연결된 계획** 을 선택합니다.

3. 다음 필드에 값을 지정합니다.

   | 필드 | 설명 |
   | --- | --- |
   | **프로그램** | 프로그램의 고유 식별자. |
   | **설명** | 프로그램에 대한 설명. | 
   | **유효 기간 시작 날짜 및 시간** | 프로그램이 활성화되는 날짜 및 시간. |
   | **유효 기간 종료 날짜 및 시간** | 프로그램이 만료되는 날짜 및 시간 기본값은 2154-12-31이며 종료되지 않음을 의미합니다. |
   | **보장 대기 기간** | 복리후생 프로그램에 대한 보장이 시작되기 전에 직원이 기다려야 하는 기간. |
   | **공제 대기 기간** | 복리후생 프로그램에 대한 공제가 시작되기 전에 직원이 기다리는 기간. |
   | **자격 규칙** | 복리후생 프로그램에 적용할 자격 규칙을 선택합니다. 이 페이지의 **자격 규칙** 탭에서 자격 규칙을 정의합니다. |
   
4. **저장** 을 선택합니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
