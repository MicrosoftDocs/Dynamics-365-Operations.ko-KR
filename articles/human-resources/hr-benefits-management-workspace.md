---
title: 혜택 관리 작업 공간
description: 이 항목에서는 Dynamics 365 Human Resources의 혜택 관리 작업 공간에 대해 설명합니다.
author: twheeloc
ms.date: 01/03/2022
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
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 424f4a2098e05b4f7dc6fa84df133dda81cc59f0
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452290"
---
# <a name="benefits-management-workspace"></a>혜택 관리 작업 공간


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

이 항목에서는 Dynamics 365 Human Resources의 **혜택 관리** 작업 공간에 대해 설명합니다.

> [!NOTE]
> **혜택 관리** 작업 공간을 보려면 먼저 기능 관리에서 **(미리 보기) 혜택 관리 작업 공간** 기능을 사용하도록 설정해야 합니다. 미리 보기 기능의 활성화에 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.<br><br>![혜택 관리 작업 공간 사용.](./media/hr-benefits-management-workspace-enable.png)

**혜택 관리** 작업 공간에서 주의가 필요한 혜택 항목을 빠르게 볼 수 있습니다. 이 페이지에서 다음을 볼 수 있습니다.

- 작업 대기 중인 항목의 합계
- 확인되지 않은 선택이 있는 작업자
- 최근에 혜택에 등록한 근로자
- 미래의 이벤트가 있는 근로자
- 등록되지 않은 신입사원
- 현재 이벤트가 있는 근로자
- 어떤 계획도 선택하지 않은 공개 등록이 있는 근로자

![혜택 관리 작업 공간.](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>작업 항목 보기

타일 또는 탭을 선택하여 작업 항목을 볼 수 있습니다. 탭을 선택하면 작업 영역 페이지에서 근로자를 보고 선택할 수 있습니다.

![작업 항목.](./media/hr-benefits-management-workspace-action-items.png)

타일을 선택하면 해당 영역의 페이지로 이동합니다. 예를 들어, 이러한 타일을 선택하면 다음과 같은 작업을 수행해야 하는 직원을 위해 필터링된 **근로자 혜택 계획** 페이지가 표시됩니다.

- **확인되지 않은 선택 사항**
- **체크아웃된 계획이 없는 등록 열기**
- **혜택에 등록**
- **등록되지 않은 신입 사원**

![근로자 혜택 계획.](./media/hr-benefits-management-workspace-plans.png)

**활성 이벤트** 또는 **미래 이벤트** 를 선택하면 활성 또는 미래 이벤트 목록으로 이동합니다.

![생활 이벤트.](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>처리 중

등록 자격, 생활 이벤트 또는 속도 변경 업데이트를 처리하려면 탐색 모음에서 해당 항목을 선택하십시오.

![처리 중.](./media/hr-benefits-management-workspace-processing.png)

처리 결과를 보려면 페이지에서 **결과 처리** 를 선택합니다.

![처리 결과.](./media/hr-benefits-management-workspace-process-results.png)

혜택 처리에 대한 자세한 내용은 다음을 참조하십시오.

- [등록 자격 처리](hr-benefits-process-enrollment-eligibility.md)
- [생활 이벤트 변경 처리](hr-benefits-process-life-event-changes.md)
- [생활 이벤트 자격 처리](hr-benefits-process-life-event-eligibility.md)
- [생활 이벤트 처리](hr-benefits-process-life-events.md)
- [요율 변경 처리](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>기간 변경

다른 혜택 기간을 보려면 **기간** 드롭다운 목록에서 해당 기간을 선택합니다.

![기간 변경.](./media/hr-benefits-management-workspace-period.png)


## <a name="open-enrollment-tab"></a>등록 탭 열기

타일 또는 탭을 선택하여 작업 항목을 볼 수 있습니다. 탭을 선택하면 작업 영역 페이지에서 근로자를 보고 선택할 수 있습니다.
**등록 열기** 탭은 열린 등록 프로세스에 대한 주요 메트릭을 제공합니다. 

공개 등록에 대한 정보는 **등록 시작일** 30일 전에 표시됩니다. 이는 **혜택 관리**  >  **링크**  >  **기간** 의 **기간** 설정의 **등록 시작 날짜** 필드에 정의됩니다.  이 설정을 변경하려면 **Human Resources 공유 매개변수** > **혜택 관리** > **등록 옵션 열기** 로 이동하고 **수** 필드를 업데이트하십시오.  

**등록 열기** 탭에서 다음 정보를 사용할 수 있습니다.
 - 공개 등록 절차를 시작하지 않은 직원
 - 선발이 진행 중인 직원입니다.
 - 선발 프로세스를 완료한 직원
 - 확인되지 않은 선택 사항

**요약 타일**

- **시작되지 않음** – **시작되지 않음** 타일은 등록 프로세스를 시작하지 않은 직원의 수를 보여줍니다. **시작되지 않음** 타일은 열려 있는 등록 계획 기간에 대해 선택, 보류 또는 체크아웃된 계획이 없는 직원만 표시하는 필터링된 목록입니다. 필수 계획은 기본적으로 직원용으로 선택되므로 무시되고 포함되지 않습니다.  이 타일을 드릴백하여 **근로자 혜택 계획** 페이지에서 공개 등록 프로세스를 시작하지 않은 직원 목록을 볼 수 있습니다.

  > [!NOTE]
  > **계획 유형** 에 대해 열려 있는 등록 진행률을 추적하지 않으려면 **혜택 관리** > **링크** > **직원 셀프 서비스 매개 변수** > **혜택 계획 타일 설정** 으로 이동하여 **열려 있는 등록 진행률 추적** 필드를 업데이트하여 제외할 수 있습니다.  예를 들어, **계획 유형** = **기타** 로 작성된 계획이 있을 수 있습니다. 이러한 계획은 등록 진행률을 추적하지 않으려는 선택적 계획일 수 있습니다. 이 계획 유형을 선택하지 않으면 **등록 열기** 탭에서 등록 진행률 또는 완료를 추적할 때 이러한 유형의 계획이 무시됩니다. 이 설정은 모든 기간 및 법인에 대해 선택된 계획 유형에 적용됩니다.

- **진행 중** – **진행 중** 타일은 진행 중인 선발이 있는 직원 수를 제공합니다. **진행 중** 타일은 취소되거나 선택된 하나 이상의 계획이 있는 직원만 표시하는 필터링된 목록입니다. 필수 계획은 기본적으로 직원용으로 선택되므로 무시되고 포함되지 않습니다. 이 타일에서 드릴백하여 **근로자 혜택 계획 대량 업데이트** 페이지에서 선택한 계획 및 포기된 계획을 볼 수 있습니다.

- **혜택 등록** – **혜택 등록** 타일은 혜택에 완전히 등록된 직원 수를 보여줍니다. **혜택에 등록** 타일은 모든 계획을 선택했거나 포기한 직원을 보여주는 필터링된 목록입니다. 쿼리는 **직원 셀프 서비스 매개 변수** 페이지에서 열린 등록을 위해 추적되지 않는 계획을 제외합니다. 이 타일을 드릴백하여 **근로자 혜택 계획** 페이지에서 직원 목록을 볼 수 있습니다.

- **확인되지 않은 선택 항목** – **확인되지 않은 선택 항목** 타일은 선택되거나 취소된 계획이 있으며 확인해야 하는 직원 수를 표시합니다. 이 타일에서 드릴백하여 **근로자 혜택 계획 대량 업데이트** 페이지를 표시할 수 있습니다.

**활동**

- **시작되지 않음** - **시작되지 않음** 탭에는 등록 프로세스를 시작하지 않은 직원 목록이 표시됩니다. **시작되지 않음** 타일은 열려 있는 등록 계획 기간에 대해 선택, 보류 또는 체크아웃된 계획이 없는 직원을 표시하는 필터링된 목록입니다. 필수 계획은 기본적으로 직원용으로 선택되므로 무시되고 포함되지 않습니다. 근로자를 드릴다운하여 **근로자 혜택 계획 세부 정보** 페이지를 표시할 수 있습니다.

- **선발 진행 중** - **선발 진행 중** 탭에는 선발이 진행 중인 직원 목록이 표시됩니다. **선발 진행 중** 은 취소되거나 선택된 하나 이상의 계획이 있는 직원을 표시하는 필터링된 목록입니다. 필수 계획은 기본적으로 직원용으로 선택되므로 무시되고 포함되지 않습니다. 근로자를 드릴다운하여 **근로자 혜택 계획 세부 정보** 페이지를 표시할 수 있습니다.

## <a name="view-more-options"></a>더 많은 옵션 보기

추가 정보 및/또는 추가 작업을 보려면 **링크** 를 선택합니다.

![링크.](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>참고 항목

[혜택 관리 개요](hr-benefits-management-overview.md)
