---
title: 최적화 조언자에 대한 규칙 만들기
description: 이번에는 Optimization Advisor에 새 규칙을 추가하는 방법에 대해 설명합니다.
author: roxanadiaconu
ms.date: 02/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: sericks
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: a65a71da066d70cafc641aafe21538830a9ebe56b607316570ea2435398cda1c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460777"
---
# <a name="create-rules-for-optimization-advisor"></a>최적화 조언자에 대한 규칙 만들기

[!include [banner](../includes/banner.md)]

이번에는 **Optimization Advisor** 에 대한 새 규칙을 만드는 방법에 대해 설명합니다. 예를 들어 빈 제목이 있는 견적 요청(RFQ) 사례를 식별하는 새 규칙을 생성할 수 있습니다. 케이스에 제목을 사용하면 케이스를 쉽게 식별하고 검색할 수 있습니다. 매우 간단하지만 이 예는 최적화 규칙으로 달성할 수 있는 것을 보여줍니다. 

*규칙* 은 애플리케이션 데이터를 확인하는 것입니다. 규칙이 평가하는 조건이 충족되면 프로세스를 최적화하거나 데이터를 개선할 수 있는 기회가 생성됩니다. 기회에 따라 조치를 취할 수 있으며 선택적으로 조치의 영향을 측정할 수 있습니다. 

**Optimization Advisor** 에 대한 새 규칙을 생성하려면 **SelfHealingRule** 추상 클래스를 확장하고 **IDiagnosticsRule** 인터페이스를 구현하며 **DiagnosticRule** 속성으로 장식되는 새 클래스를 추가하십시오. 클래스에는 **DiagnosticsRuleSubscription** 특성으로 장식된 메서드도 있어야 합니다. 관례에 따라 이는 나중에 논의될 **기회타이틀** 메서드에서 수행됩니다. 이 새 클래스는 **SelfHealingRules** 모델에 대한 종속성을 사용하여 사용자 지정 모델에 추가할 수 있습니다. 다음 예시에서 구현되는 규칙을 **RFQTitleSelfHealingRule** 이라고 합니다.

```xpp
[DiagnosticsRule] 
public final class RFQTitleSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule 
{ 
… 
} 
```

**SelfHealingRule** 추상 클래스에는 상속 클래스에서 구현해야 하는 추상 메서드가 있습니다. 핵심은 규칙에 의해 식별된 기회 목록을 반환하는 **평가** 방법입니다. 기회는 법인별로 제공되거나 전체 시스템에 적용될 수 있습니다.

```xpp
protected List evaluate() 
{ 
    List results = new List(Types::Record); 
    
    DataArea dataArea; 

    while select id from dataArea 
        where !dataArea.isVirtual 
    { 
        changecompany(dataArea.id) 
        { 
            container result = this.findRFQCasesWithEmptyTitle(); 

            if (conLen(result) > 0) 
            { 
                SelfHealingOpportunity opportunity = this.getOpportunityForCompany(dataArea.Id); 
                opportunity.EvaluationState = SelfHealingEvaluationState::Evaluated; 
                opportunity.Data = result; 
                opportunity.OpportunityDate = DateTimeUtil::utcNow(); 
                
                results.addEnd(opportunity); 
            } 
        } 
    } 
    
    return results; 
} 
```

위에 표시된 방법은 회사를 반복하고 **findRFQCasesWithEmptyTitle** 방법에서 제목이 비어 있는 RFQ 사례를 선택합니다. 이러한 사례가 하나 이상 발견되면 **getOpportunityForCompany** 메소드를 사용하여 회사별 기회가 생성됩니다. **SelfHealingOpportunity** 테이블의 **데이터** 필드는 **컨테이너** 유형이므로 이 규칙과 관련된 논리와 관련된 모든 데이터를 포함할 수 있습니다. 현재 타임스탬프로 **OpportunityDate** 를 설정하면 기회에 대한 최신 평가 시간이 등록됩니다.  

기회는 회사 간일 수도 있습니다. 이 경우 회사에 대한 루프가 필요하지 않으며 **getOpportunityAcrossCompanies** 메소드를 사용하여 기회를 생성해야 합니다. 

다음 코드는 빈 제목이 있는 RFQ 사례의 ID를 반환하는 **findRFQCasesWithEmptyTitle** 메서드를 보여줍니다.

```xpp
private container findRFQCasesWithEmptyTitle() 
{ 
    container result; 

    PurchRFQCaseTable rfqCase; 
    while select RFQCaseId from rfqCase 
        where rfqCase.Name == '' 
    { 
        result += rfqCase.RFQCaseId; 
    } 
    
    return result; 
} 
```

구현해야 하는 두 가지 추가 메서드는 **기회 제목** 및 **기회 세부 정보** 입니다. 전자는 기회에 대한 짧은 제목을 반환하고 후자는 데이터를 포함할 수 있는 기회에 대한 자세한 설명을 반환합니다.

**기회 제목** 이 반환한 제목은 **최적화 조언자** 작업 공간의 **최적화 기회** 열 아래에 나타납니다. 또한 기회에 대한 추가 정보를 표시하는 측면 창의 헤더로 나타납니다. 규칙에 따라 이 메서드는 다음 인수를 사용하는 **DiagnosticRuleSubscription** 특성으로 장식됩니다. 

* **진단 영역** – **DiagnosticArea::SCM** 과 같이 규칙이 속하는 애플리케이션 영역을 설명하는 **DiagnosticArea** 유형의 열거형입니다. 

* **규칙 이름** – 규칙 이름이 있는 스트링입니다. 이것은 **Dianostics 유효성 검사** 규칙 양식(**DiagnosticsValidationRuleMaintain**)의 **규칙 이름** 열 아래에 나타납니다. 

* **실행 빈도** – **DiagnosticRunFrequency::Daily** 와 같이 규칙을 실행해야 하는 빈도를 설명하는 **DiagnosticRunFrequency** 유형의 열거형입니다. 

* **규칙 설명** – 규칙에 대한 보다 자세한 설명이 있는 스트링입니다. 이것은 **Dianostics 유효성 검사 규칙** 양식(**DiagnosticsValidationRuleMaintain**)의 **규칙 설명** 열 아래에 나타납니다. 

> [!NOTE]
> 규칙이 작동하려면 **DiagnosticRuleSubscription** 속성이 필요합니다. 일반적으로 **기회 제목** 에 사용되지만 클래스의 모든 메서드를 꾸밀 수 있습니다.

다음은 구현 예입니다. 단순성을 위해 원시 스트링이 사용되지만 올바른 구현에는 레이블이 필요합니다. 

```xpp
[DiagnosticsRuleSubscription(DiagnosticsArea::SCM, 
                             'Assign titles to Request for Quotation cases', 
                             DiagnosticsRunFrequency::Daily,  
                             'This rule detects Requests for Quotation with empty titles.')] 
public str opportunityTitle() 
{ 
    return 'Assign titles to Request for Quotation cases'; 
} 
```

기회에 대한 추가 정보를 표시하는 **기회 세부 정보** 에서 반환된 설명이 측면 창에 나타납니다. 이것은 기회에 대한 자세한 정보를 제공하는 데 사용할 수 있는 **데이터** 필드인 **SelfHealingOpportunity** 인수를 사용합니다. 이 예시에서 메서드는 제목이 비어 있는 RFQ 사례의 ID를 반환합니다. 

```xpp
public str opportunityDetails(SelfHealingOpportunity _opportunity) 
{ 
    str details = ''; 
    container opportunityData = _opportunity.Data; 
    int affectedRFQCasesCount = conLen(opportunityData); 

    if (affectedRFQCasesCount != 0) 
    { 
        details = 'The following Request for Quotation cases have an empty title:\n'; 
        for (int i = 1; i <= affectedRFQCasesCount ; i++) 
        { 
            PurchRFQCaseId rfqCaseId = conPeek(opportunityData, i); 
            details += rfqCaseId + '\n'; 
        } 
    } 

    return details; 
}
```

구현할 나머지 두 가지 추상 메서드는 **provideHealingAction** 및 **securityMenuItem** 입니다. 

**providerHealingAction** 은 치유 작업이 제공되면 true를 반환하고, 그렇지 않으면 false를 반환합니다. true가 반환되면 **performAction** 메서드를 구현해야 합니다. 그렇지 않으면 오류가 발생합니다. **performAction** 메서드는 데이터를 작업에 사용할 수 있는 **SelfHealingOpportunity** 인수를 사용합니다. 예시에서 조치는 수동 수정을 위해 **PurchRFQCaseTableListPage** 를 엽니다. 

```xpp
public boolean providesHealingAction() 
{ 
    return true; 
} 

protected void performAction(SelfHealingOpportunity _opportunity) 
{ 
    new MenuFunction(menuItemDisplayStr(PurchRFQCaseTableListPage), MenuItemType::Display).run(); 
} 
```

규칙의 세부 사항에 따라 기회 데이터를 사용하여 자동 작업을 수행할 수 있습니다. 이 예시에서 시스템은 RFQ 사례에 대한 제목을 자동으로 생성할 수 있습니다. 

**securityMenuItem** 은 작업 메뉴 항목에 액세스할 수 있는 사용자에게만 규칙이 표시되도록 작업 메뉴 항목의 이름을 반환합니다. 보안을 위해 승인된 사용자만 특정 규칙과 기회에 액세스할 수 있어야 합니다. 예시에서 **PurchRFQCaseTitleAction** 에 대한 액세스 권한이 있는 사용자만 기회를 볼 수 있습니다. 이 작업 메뉴 항목은 이 예를 위해 생성되었으며 **PurchRFQCaseTableMaintain** 보안 권한에 대한 진입점으로 추가되었습니다. 

> [!NOTE]
> 보안이 제대로 작동하려면 메뉴 항목이 작업 메뉴 항목이어야 합니다. **디스플레이 메뉴 항목** 과 같은 다른 메뉴 항목 유형은 올바르게 작동하지 않습니다.

```xpp
public MenuName securityMenuItem() 
{ 
    return menuItemActionStr(PurchRFQCaseTitleAction); 
}
```

규칙이 컴파일된 후 다음 작업을 실행하여 사용자 인터페이스(UI)에 표시되도록 합니다.

```xpp
class ScanNewRulesJob 
{         
    public static void main(Args _args) 
    {         
        SysExtensionCache::clearAllScopes(); 
        var controller = new DiagnosticsRuleController(); 
        controller.runOperation(); 
    } 
} 
```

규칙은 **시스템 관리** 에서 사용할 수 있는 **진단 유효성 검사 규칙** 양식에 표시됩니다. > **정기적인 작업** > **진단 유효성 검사 규칙 유지**. 평가를 받으려면 **시스템 관리** > **주기적인 작업** > **스케줄 진단 유효성 검사 규칙** 으로 이동하여 규칙의 빈도(예: **매일**)를 선택합니다. **확인** 을 클릭합니다. 새로운 기회를 보려면 **시스템 관리** > **최적화 어드바이저** 로 이동하십시오. 

다음 예시는 모든 필수 메서드와 속성을 포함하는 규칙의 골격이 있는 코드 조각입니다. 새로운 규칙 작성을 시작하는 데 도움이 됩니다. 예시에 사용된 레이블 및 작업 메뉴 항목은 데모용으로만 사용됩니다.

```xpp
[DiagnosticsRuleAttribute]
public final class SkeletonSelfHealingRule extends SelfHealingRule implements IDiagnosticsRule
{
    [DiagnosticsRuleSubscription(DiagnosticsArea::SCM,
                                 "@SkeletonRuleLabels:SkeletonRuleTitle", // Label with the title of the rule
                                 DiagnosticsRunFrequency::Monthly,
                                 "@SkeletonRuleLabels:SkeletonRuleDescription")] // Label with a description of the rule
    public str opportunityTitle()
    {
        // Return a label with the title of the opportunity
        return "@SkeletonRuleLabels:SkeletonOpportunityTitle";
    }

    public str opportunityDetails(SelfHealingOpportunity _opportunity)
    {
        str details = "";

        // Use _opportunity.data to provide details on the opportunity

        return details;
    }

    protected List evaluate()
    {
        List results = new List(Types::Record);

        // Write here the core logic of the rule

        // When creating an opportunity, use:
        //     * this.getOpportunityForCompany() for company specific opportunities
        //     * this.getOpportunityAcrossCompanies() for cross-company opportunities

        return results;
    }

    public boolean providesHealingAction()
    {
        return true;
    }

    protected void performAction(SelfHealingOpportunity _opportunity)
    {
        // Place here the code that performs the healing action

        // To open a form, use the following:
        // new MenuFunction(menuItemDisplayStr(SkeletonRuleDisplayMenuItem), MenuItemType::Display).run();
    }

    public MenuName securityMenuItem()
    {
        return menuItemActionStr(SkeletonRuleActionMenuItem);
    }

}
```

자세한 내용은 짧은 YouTube 비디오를 시청하십시오. [의 최적화 고문 Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]