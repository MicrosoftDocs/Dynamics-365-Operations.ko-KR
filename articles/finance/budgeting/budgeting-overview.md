---
title: 예산 책정 홈 페이지
description: 이 토픽에서는 Microsoft Dynamics 365 Finance의 예산 책정 기능 구성 요소, 예산 책정 도구 및 보고 기능에 대한 개요를 제공합니다.
author: panolte
ms.date: 04/29/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanningWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "106043"
- intro-internal
ms.assetid: 702f692e-ad1c-4798-8d3e-c3cf8591d3fa
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ad0d055702a3801bf9fe9ac3159eba7c297b6f0
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451414"
---
# <a name="budgeting-home-page"></a>예산 책정 홈 페이지

[!include [banner](../includes/banner.md)]

이 토픽에서는 예산 책정 기능 구성 요소, 예산 책정 도구 및 보고 기능에 대한 개요를 제공합니다. 

## <a name="components-of-budgeting-functionality"></a>예산 책정 기능의 구성 요소

회사의 리소스 계획 주기는 일반적으로 계획, 예산 책정 및 예측 활동으로 구성됩니다.

[![예산 책정 기능 구성 요소.](./media/budgeting-functionality-components.jpg)](./media/budgeting-functionality-components.jpg)

장기 전략 계획 및 연간 예산 계획 프로세스는 예산 계획 문서를 통해 지원됩니다. 예산 계획 문서는 Microsoft Excel과 긴밀하게 통합됩니다. 사용자는 금전적 및 양적 시나리오를 무제한으로 구성할 수 있으며 하향식 및 상향식 예산 책정 방법을 모두 지원하도록 예산 편성 조직 계층 구조를 정의할 수도 있습니다. 예산이 설정되고 애플리케이션에서 승인되면 예산 계획을 예산 등록 항목으로 변환합니다. 예산 등록 항목은 예산을 유지하고 예산 코드를 통해 추적 가능한 금액을 유지하기 위한 도구를 제공합니다. 예산 등록 항목을 사용하면 원래 예산을 수정하고 이전을 수행하고 전년도의 예산 금액을 이월할 수 있습니다. 설정된 예산을 기반으로 회사는 예산 통제를 가능하게 할 수 있습니다. 통제 수준은 조직 문화와 조직의 성숙도에 따라 다릅니다. 성숙도가 낮은 조직은 예산을 "있는 그대로" 유지할 수 있으며 예산이 기대에 미치지 못할 경우 사전 예방적이기보다 사후 대응적일 수 있습니다. 다른 조직에서는 예산 자금을 사용할 수 없는 경우 사용자가 구매하지 못하도록 하는 예산 관리 정책을 활성화할 수 있습니다.

마지막으로, 매우 성숙한 조직은 직원이 조직 목표에 대해 교육받는 조직 문화를 구축하고 "출장 대신 온라인 회의 고려"와 같은 정책을 통해 이러한 목표를 따를 수 있습니다. 이 애플리케이션에는 회사의 경영진이 하드 컨트롤(예산을 초과하는 전기를 방지함) 또는 소프트 컨트롤(사용자가 사용 가능한 예산 기금을 초과할 것이라는 경고를 받지만 진행 방법을 스스로 결정할 수 있음)을 선택할 수 있는 예산 컨트롤 프레임워크가 포함되어 있습니다. 마지막으로 롤링 예측을 사용할 수 있습니다. 롤링 예측은 예산과 실제 금액을 정기적으로 비교하는 것으로 회사가 예산 대비 얼마나 잘 운영되는지 정의하는 데 사용됩니다. 롤링 예측은 추세를 식별하는 데도 사용됩니다. 재무 및 운영에서 초기 계획 활동으로 예산 계획 문서를 통해 롤링 예측이 지원됩니다. 롤링 예측은 다가오는 예산 주기에 대한 계획과 병행하여 수행할 수 있습니다.

-   [예산 책정 개요](basic-budgeting-overview-configuration.md)
-   [예산 통제 개요](budget-control-overview-configuration.md)
-   [예산 계획 개요](budget-planning-overview-configuration.md)
-   [위치 예측](position-forecasting.md)
-   [예산 계획 근거 문서](budget-planning-justification-docs.md)
-   [Excel용 예산 계획 템플릿](budget-planning-excel-templates.md)

## <a name="budgeting-tools"></a>예산 책정 도구
[![예산 책정 도구.](./media/budgeting-tools.jpg)](./media/budgeting-tools.jpg) 

추가 계획 및 예산 책정 기능을 사용할 수 있으며 원장 예산과 통합됩니다.

-   **인력 예산** – 인력 예산 책정에는 직위, 보상 그룹 등에 대한 상세한 예산 비용 구성 요소 계획이 포함됩니다.
-   **고정 자산 예산** – 고정 자산 정보를 기반으로 계획 감가상각을 계산하고 고정 자산과 관련된 기타 계획 거래를 기록할 수 있습니다.
-   **프로젝트 예산** – 프로젝트 모듈에서 상세한 프로젝트 예측을 생성할 수 있습니다. 프로젝트 예측에는 계획된 시간, 비용, 수수료 및 항목에 대한 세부 정보가 포함됩니다.
-   **수요 예측** – 과거 거래 데이터를 기반으로 미래의 재고 수요를 예측하고 수요 예측을 생성할 수 있습니다.

다른 모듈의 계획 데이터를 예산 계획으로 가져오는 방법에 대한 자세한 내용은 [다른 모듈과의 예산 계획 통합](budget-planning-integration-other-modules.md)을 참조하십시오.

## <a name="user-interface-and-reporting-capabilities"></a>사용자 인터페이스 및 보고 기능
사용자는 클라이언트에서 직접(구성 가능한 예산 계획 문서 페이지 사용) 또는 Excel을 통해 예산 계획을 작성할 수 있습니다. Excel은 몇 가지 추가 기능을 제공합니다. 예를 들어 외부 데이터를 예산 계획의 원본으로 사용하고, 사용자 지정 계산을 수행하고, Microsoft 피벗 테이블 및 차트를 사용할 수 있습니다. 예산 계획 프로세스에서 대부분의 변수를 구성할 수 있습니다. 

예를 들어, 누가 예산 책정을 하는지, 무엇을 예산 책정했는지, 프로세스는 어떤 모습인지 정의할 수 있습니다. 예산 계획에 Excel을 사용할 수 있지만 애플리케이션은 단일 정보 소스로 유지되며 예산 관리 문제를 방지하는 데 도움이 됩니다. 정기적인 프로세스를 사용하여 예산 책정을 위한 초기 데이터를 예산 계획에 가져올 수 있습니다. 보고를 위해 애플리케이션은 예산 데이터를 보고 분석할 수 있는 일련의 표준 조회 페이지를 제공합니다. 예산 계획 데이터는 [재무 보고](../general-ledger/financial-reporting-getting-started.md)를 통해 액세스할 수 있으며, 재무 보고서에 별도의 예산 계획 시나리오를 열로 표시할 수 있습니다.








[!INCLUDE[footer-include](../../includes/footer-banner.md)]
