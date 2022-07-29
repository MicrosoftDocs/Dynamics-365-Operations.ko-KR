---
title: 재무 기간 마감 작업 영역
description: 이 문서에서는 재무 기간 마감 작업 영역 및 관련 구성에 대한 개요를 제공합니다.
author: kweekley
ms.date: 11/29/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ab203a18229cd426f8483ed6d0483c98614af9c
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2021
ms.locfileid: "8451141"
---
# <a name="financial-period-close-workspace"></a>재무 기간 마감 작업 영역

[!include [banner](../includes/banner.md)]

이 항목에서는 **재무 기간 마감** 작업 영역 및 관련 구성에 대한 개요를 제공합니다.

재무 기간 마감 작업 영역

**재무 기간 마감** 작업 영역을 사용하면 회사, 영역 및 사람 전반에 걸쳐 재무 마감 프로세스를 추적할 수 있습니다. **재무 기간 마감** 작업 영역의 보기에 따라 정산 일정의 모든 작업 및 상태 또는 할당된 작업만 표시됩니다. 

먼저 작업 영역 상단에서 마감 일정을 선택해야 합니다. 그러면 작업 영역에 표시되는 모든 데이터가 선택한 마감 일정에 따라 필터링됩니다.

### <a name="summary-tiles"></a>요약 타일

**요약** 타일은 프로세스에 대한 개요를 제공하고 표시기는 마감 프로세스를 추적하는 데 도움이 됩니다. 기한이 지난 작업, 오늘 남은 작업, 오늘 마감이지만 종속성으로 인해 차단된 작업, 그리고 프로세스에 대한 남은 모든 작업을 볼 수 있습니다. 이 정보는 선택한 마감 일정에 포함된 모든 회사에 대한 것입니다.

### <a name="tasks-and-status-section"></a>작업 및 상태 섹션

**작업 및 상태** 섹션에서는 전체 마감 일정의 상태를 회사별 상태, 영역별 상태, 담당자별 상태 등 다양한 방식으로 분류합니다. 카드 목록 상단의 필터를 변경하여 마감 일정의 모든 작업, 오늘 마감인 작업만 또는 마감된 작업의 상태를 볼 수 있습니다. 회사 필터를 선택하여 특정 회사의 상태를 볼 수도 있습니다. 각 상태 탭은 완료 비율과 남은 작업 수를 기준으로 분석을 제공합니다. 선택한 카드로 세부 작업 목록을 필터링하려면 카드를 클릭하거나 **세부 정보 보기** 작업을 클릭합니다. 

마지막 탭은 세부 작업 목록입니다. 이 목록은 전체 작업 목록을 표시하며 관심 있는 작업만 표시하도록 필터링할 수 있습니다. 여러 가지 방법으로 작업 목록을 필터링할 수 있습니다. 예를 들어 작업 기한, 관련 회사 및 관련 영역별로 필터링할 수 있습니다. 완료된 작업을 작업 목록에 표시하거나 숨기도록 선택할 수도 있습니다. 

작업에는 두 가지 지표가 사용됩니다.

-   느낌표 아이콘은 작업 기한이 지났음을 나타냅니다. 기한이 지난 작업의 기한도 빨간색으로 강조 표시됩니다.
-   자물쇠 아이콘은 작업이 아직 완료되지 않은 다른 작업에 종속되어 있음을 나타냅니다. 종속성에 의해 차단된 작업은 완료된 것으로 표시할 수 없습니다. **종속성 설정** 작업을 사용하여 작업의 종속성을 설정할 수 있습니다.

작업 이름은 사용자가 작업을 완료하기 위해 이동해야 하는 페이지에 대한 하이퍼링크입니다. 작업을 편집하거나 만들 때 **작업 링크** 필드를 사용하여 이 하이퍼링크를 설정할 수 있습니다. 

**첨부 파일** 작업을 사용하여 작업에 파일, 메모, 이미지 및 URL을 첨부할 수 있습니다. 예를 들어 작업의 일부로 사용되는 분개장 번호를 표시하거나 특정 작업에 대한 설명을 추가하거나 작업을 위해 인쇄된 보고서 파일을 첨부할 수 있습니다. 첨부 파일이 있는 경우 작업의 **첨부 파일** 열에 아이콘이 나타납니다. 

**작업 완료** 옵션은 작업이 완료된 후 수동으로 선택해야 합니다. 작업을 완료된 것으로 표시하면 **완료 날짜** 필드가 현재 날짜 및 시간으로 자동 업데이트됩니다. 종속성 표시기도 적절하게 업데이트됩니다.

## <a name="all-financial-period-close-tasks-list-page"></a>모든 재무 기간 마감 작업 목록 페이지
**모든 재무 기간 마감 작업** 목록 페이지에서 모든 현재 및 이전 기간 마감 작업을 볼 수 있습니다. 이 목록 페이지는 예정된 마감 날짜, 실제 완료 날짜 및 작업을 완료한 사람에 대한 정보를 포함하기 때문에 마감 프로세스의 기록을 분석하는 데 가장 적합합니다. 보고 및 감사를 위해 이 목록 페이지의 정보를 Microsoft Excel로 쉽게 내보낼 수 있습니다.

## <a name="financial-period-close-configuration-page"></a>재무 기간 마감 구성 페이지
**재무 기간 마감** 작업 영역을 사용하려면 먼저 **재무 기간 마감 구성** 페이지를 사용하여 프로세스를 구성해야 합니다. (**총계정원장** &gt; **기간 마감** &gt; **재무 기간 마감 구성** 을 클릭합니다.)

### <a name="resources"></a>리소스

**리소스** 탭에서 마감 프로세스에 관련된 사람을 정의합니다. 마감 작업을 담당할 직원을 먼저 여기에 지정해야 합니다. 직원의 작업 영역 보기도 지정해야 합니다. 다음 옵션을 사용할 수 있습니다.

-   **할당된 작업만** – 사용자는 자신에게 할당된 작업만 볼 수 있습니다.
-   **모든 작업 및 상태** – 사용자는 모든 마감 작업과 전체 프로세스의 상태를 볼 수 있습니다.

할당된 작업만 볼 수 있는 권한이 있는 사용자는 작업 목록에 작업을 추가하거나 작업을 편집하거나 작업 목록에서 작업을 제거할 수 없습니다.

### <a name="task-areas"></a>작업 영역

작업 영역을 사용하면 마감 작업을 조직 내의 논리적 소유권 영역으로 그룹화할 수 있습니다. 예를 들어 지급 계정, 수취 계정 또는 총계정원장을 작업 영역으로 사용할 수 있습니다.

### <a name="calendars"></a>달력

달력 탭을 사용하여 재무 마감 일정을 만들고 편집합니다. 여기에서 마감 프로세스의 근무일을 정의하고 마감 작업을 예약합니다.  새 달력을 만들고 작업 예약에 사용할 근무일을 지정합니다.  달력은 만든 후 수정이 가능하므로 1년, 수년 등 장기간의 달력을 만드는 것이 좋습니다.  달력을 만든 후, 공휴일과 같은 특정 요일의 달력을 업데이트하려면 편집 버튼을 클릭합니다.  마감 작업은 제어 값이 열림으로 설정된 날에 예약됩니다.  마감 작업이 특정 날짜에 예약되지 않아야 하는 경우 해당 날짜의 제어 값이 닫힘으로 설정되어야 합니다.

### <a name="templates"></a>템플릿

재무 마감 템플릿을 사용하여 마감 프로세스의 일부인 모든 작업을 정의할 수 있습니다. 마감 작업은 각 마감 프로세스의 일부로 완료하기 위해 개인에게 할당되는 정기 작업 노력입니다. 템플릿에서 각 마감 작업에 대한 상대적 기한을 정의해야 합니다. 상대적 기한은 각 기간에 작업이 기한이 되는 정의된 기간 종료 날짜 전후의 일수입니다. 또한 각 작업에는 마감 시간이 할당됩니다. 마감 시간은 표준 시간대 컨텍스트를 사용하여 설정되며 각 사용자의 표준 시간대로 변환됩니다. 

템플릿의 작업을 해당 작업이 적용되는 하나 이상의 회사에 할당할 수 있습니다. 각 회사에서 해당 작업을 완료하기 위해 다른 사람이 할당된 경우 동일한 작업 노력을 위해 여러 작업을 만드는 것이 도움이 될 수 있습니다. 각 회사별로 하나의 작업을 만듭니다. 

**작업 링크** 메뉴 항목은 작업 노력과 연결되어 있으며 작업 영역의 작업 링크에서 연결된 페이지로 직접 이동하는 데 사용할 수 있습니다. 예를 들어 지급 계정에 대한 통화 재평가 프로세스를 실행하기 위한 마감 작업을 연관된 **외화 재평가** 페이지에 연결할 수 있습니다. 외부 URL에 연결할 수도 있습니다. 

> [!TIP]
> 특정 Management Reporter 보고서를 재무 기간 마감 작업에 연결하려는 경우 보고서 URL을 사용할 수 있습니다. 보고서 URL에 액세스하려면 Report Designer에서 보고서를 열고 **파일** &gt; **보고서 보기** 를 클릭하여 웹 브라우저에서 보고서를 엽니다. 그런 다음 브라우저의 주소 표시줄에서 URL을 복사하여 **작업 링크** **URL** 필드에 붙여넣습니다. 

템플릿에서 작업 종속성을 정의할 수 있습니다. 작업이 하나 이상의 작업에 종속되도록 설정된 경우 모든 종속성이 완료될 때까지 해당 작업을 완료된 것으로 표시할 수 없습니다. 

여러 재무 마감 템플릿을 만들 수 있습니다. 그런 다음 다양한 템플릿을 사용하여 월말 또는 연말과 같은 다양한 기간 유형의 마감 프로세스를 추적하거나 다른 마감 프로세스를 사용하는 회사를 추적할 수 있습니다. 템플릿 하나를 만든 후 새 템플릿에 복사하고 필요한 사항을 변경할 수 있습니다. 각 마감 일정에는 하나의 템플릿만 할당할 수 있습니다.

### <a name="closing-schedules"></a>마감 일정

마감 일정을 사용하여 마감해야 하는 특정 재무 기간에 재무 마감 템플릿을 할당합니다. 그러면 지정된 동안 템플릿의 작업이 자동으로 생성되고 작업 영역에 새 마감 일정이 추가됩니다. 새 마감 일정을 만들 때 **기간 종료 날짜** 필드는 재무 마감 템플릿에 할당된 상대적 기한에 따라 마감 작업의 실제 기한을 결정하는 데 사용됩니다. 

마감 일정에 적합한 달력을 할당하여 작업 일정에 사용할 근무일을 표시합니다. 특정 달력을 정의하지 않으면 작업 기한은 요일을 모두 사용합니다. 

마감 일정과 연결할 회사도 정의해야 합니다. 템플릿 작업이 여러 회사에 할당된 경우 마감 일정에 있고 템플릿 작업에 할당된 회사별로 별도의 작업이 생성됩니다. 

마감 일정이 완료되면 **닫힘** 옵션을 선택합니다. 작업 기록은 **모든 재무 기간 마감 작업** 목록 페이지에서 계속 사용할 수 있지만 마감 일정은 작업 영역에서 제거됩니다. 마감 일정을 **닫힘** 으로 표시한 후에는 일정에 작업을 추가하거나 작업을 편집하거나 작업을 제거할 수 없습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]