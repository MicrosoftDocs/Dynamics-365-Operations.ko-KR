---
title: 다음을 사용하여 작업 공간에 분석 추가 Power BI Embedded
description: 이번에는 작업 영역의 분석 탭에 Power BI 보고서를 포함하는 방법을 보여줍니다.
author: RichdiMSFT
ms.date: 06/21/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: richdi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: ed562dca621acea24efa3f157f695257cb919cdda577cf9ae6dd0b0c942e1b70
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460975"
---
# <a name="add-analytics-to-workspaces-by-using-power-bi-embedded"></a>다음을 사용하여 작업 공간에 분석 추가 Power BI Embedded

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 이 기능은 Finance and Operations(버전 7.2 이상)에서 지원됩니다.

## <a name="introduction"></a>소개
이번에는 작업 영역의 **분석** 탭에 Microsoft Power BI 보고서를 포함하는 방법을 보여줍니다. 여기에 제공된 예시에서는 Fleet Management 애플리케이션의 **예약 관리** 작업 영역을 확장하여 **분석** 탭에 분석 작업 영역을 포함합니다.

## <a name="prerequisites"></a>전제 조건
+ 플랫폼 업데이트 8 이상을 실행하는 개발자 환경에 대한 액세스.
+ Microsoft Power BI Desktop을 사용하여 생성되고 엔터티 저장소 데이터베이스에서 가져온 데이터 모델이 있는 분석 보고서(.pbix 파일).

## <a name="overview"></a>개요
기존 애플리케이션 작업 공간을 확장하거나 고유한 새 작업 공간을 도입하는 경우 포함된 분석 보기를 사용하여 비즈니스 데이터에 대한 통찰력 있는 대화형 보기를 제공할 수 있습니다. 분석 작업 영역 탭을 추가하는 프로세스에는 4단계가 있습니다.

1. .pbix 파일을 Dynamics 365 리소스로 추가합니다.
2. 분석 작업 영역 탭을 정의합니다.
3. 작업 영역 탭에 .pbix 리소스를 포함합니다.
4. 선택 과목: 보기를 사용자 지정하려면 확장을 추가하십시오.

> [!NOTE]
> 분석 보고서를 만드는 방법에 대한 자세한 내용은 [Power BI Desktop 시작하기](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/)를 참조하십시오. 이 페이지는 뛰어난 분석 보고 솔루션을 만드는 데 도움이 되는 통찰력을 얻을 수 있는 훌륭한 소스입니다.

## <a name="add-a-pbix-file-as-a-resource"></a>.pbix 파일을 리소스로 추가
시작하기 전에 작업 영역에 포함할 Power BI 보고서를 만들거나 가져와야 합니다. 분석 보고서를 만드는 방법에 대한 자세한 내용은 [Power BI Desktop 시작하기](https://powerbi.microsoft.com/documentation/powerbi-desktop-getting-started/)를 참조하십시오.

.pbix 파일을 Visual Studio 프로젝트 아티팩트로 추가하려면 다음 단계를 따르십시오.

1. 적절한 모델에서 새 프로젝트를 만듭니다.
2. 솔루션 탐색기에서 프로젝트를 선택하고 마우스 오른쪽 버튼을 클릭한 다음 **새 항목** \> **추가** 를 선택합니다.
3. **새 항목 추가** 대화 상자의 **작업 아티팩트** 에서 **리소스** 템플릿을 선택합니다.
4. X++ 메타데이터에서 보고서를 참조하는 데 사용할 이름을 입력한 다음 **추가** 를 클릭합니다.

    ![새 항목 추가 대화 상자.](media/analytical-workspace-add.png)

5. 분석 보고서의 정의가 포함된 .pbix 파일을 찾은 다음 **열기** 를 클릭합니다.

    ![리소스 파일 선택 대화 상자.](media/analytical-workspace-select-resource.png)

.pbix 파일을 Dynamics 365 리소스로 추가했으므로 작업 영역에 보고서를 포함하고 메뉴 항목을 사용하여 직접 링크를 추가할 수 있습니다.

## <a name="add-a-tab-control-to-an-application-workspace"></a>애플리케이션 작업 공간에 탭 컨트롤 추가
이 예시에서는 **FMClerkWorkspace** 양식의 정의에 **Analytics** 탭을 추가하여 Fleet Management 모델의 **예약 관리** 작업 공간을 확장합니다.

다음 그림은 **FMClerkWorkspace** 양식이 Microsoft Visual Studio의 디자이너에서 어떻게 보이는지 보여줍니다.

![변경 전 FMClerkWorkspace 양식입니다.](media/analytical-workspace-definition-before.png)

**예약 관리** 작업 공간에 대한 양식 정의를 확장하려면 다음 단계를 따르십시오.

1. 양식 디자이너를 열어 디자인 정의를 확장합니다.
2. 디자인 정의에서 디자인 | 레이블이 지정된 맨 위 요소를 선택합니다. 무늬: **작업 공간 작동**.
3. 마우스 오른쪽 버튼을 클릭한 다음 **새** \> **탭** 을 선택하여 **FormTabControl1** 이라는 새 컨트롤을 추가합니다.
4. 양식 디자이너에서 **FormTabControl1** 을 선택합니다.
5. 마우스 오른쪽 버튼을 클릭한 다음 **새 탭 페이지** 를 선택하여 새 탭 페이지를 추가합니다.
6. 탭 페이지의 이름을 **Workspace** 와 같은 의미 있는 이름으로 바꿉니다.
7. 양식 디자이너에서 **FormTabControl1** 을 선택합니다.
8. 마우스 오른쪽 버튼을 클릭한 다음 **새 탭 페이지** 를 선택합니다.
9. 탭 페이지의 이름을 **Analytics** 와 같이 의미 있는 이름으로 바꿉니다.
10. 양식 디자이너에서 **분석(탭 페이지)** 을 선택합니다.
11. **Caption** 속성을 **Analytics** 로 설정하고 **자동 선언** 속성을 **Yes** 로 설정합니다.
12. 컨트롤을 마우스 오른쪽 버튼으로 클릭한 다음 **새** \> **그룹** 을 선택하여 새 양식 그룹 컨트롤을 추가합니다.
13. 양식 그룹의 이름을 **powerBIReportGroup** 과 같이 의미 있는 이름으로 바꿉니다.
14. 양식 디자이너에서 **PanoramaBody(Tab)** 를 선택한 다음 컨트롤을 **작업 영역** 탭으로 끕니다.
15. 디자인 정의에서 디자인 | 레이블이 지정된 맨 위 요소를 선택합니다. 무늬: **작업 공간 작동**.
16. 마우스 오른쪽 버튼을 클릭한 다음 **패턴 제거** 를 선택합니다.
17. 다시 마우스 오른쪽 버튼을 클릭한 다음 **패턴** \> **작업 공간 탭 추가** 를 선택합니다.
18. 빌드를 수행하여 변경 사항을 확인하십시오.

다음 그림은 이러한 변경 사항을 적용한 후의 디자인을 보여줍니다.

![변경 후 FMClerkWorkspace.](media/analytical-workspace-definition-after.png)

작업 영역 보고서를 포함하는 데 사용할 양식 컨트롤을 추가했으므로 레이아웃을 수용할 수 있도록 부모 컨트롤의 크기를 정의해야 합니다. 기본적으로 **필터 창** 페이지와 **탭** 페이지가 보고서에 표시됩니다. 그러나 보고서의 대상 소비자에 맞게 이러한 컨트롤의 가시성을 변경할 수 있습니다.

> [!NOTE]
> 포함된 작업 영역의 경우 일관성을 위해 확장을 사용하여 **필터 창** 과 **탭** 페이지를 모두 숨길 것을 권장합니다.

이제 신청서 정의 확장 작업을 완료했습니다. 확장을 사용하여 사용자 지정하는 방법에 대한 자세한 내용은 [확장 및 중첩을 통한 사용자 지정](../extensibility/customization-overlayering-extensions.md)을 참조하십시오.

## <a name="add-x-business-logic-to-embed-a-viewer-control"></a>뷰어 컨트롤을 포함하는 X++ 비즈니스 로직 추가
**예약 관리** 작업 영역에 포함된 Report Viewer 컨트롤을 초기화하는 비즈니스 논리를 추가하려면 다음 단계를 따르십시오.

1. **FMClerkWorkspace** 양식 디자이너를 열어 디자인 정의를 확장합니다.
2. F7 키를 눌러 코드 정의 뒤에 있는 코드에 액세스합니다.
3. 다음 X++ 코드를 추가합니다.

    ```xpp
    [Form] 
    public class FMClerkWorkspace extends FormRun
    {
        private boolean initReportControl = true;
        protected void initAnalyticalReport()
        {
            if (!initReportControl)
            {
                return;
            }
            // Note: secure entry point into the Workspace's Analytics report
            if (Global::hasMenuItemAccess(menuItemDisplayStr(FMClerkWorkspace), MenuItemType::Display))
            {
                // initialize the PBI report control using shared helper
                PBIReportHelper::initializeReportControl('FMPBIWorkspaces', powerBIReportGroup);
            }
            initReportControl = false;
        }
        /// <summary>
        /// Initializes the form.
        /// </summary>
        public void init()
        {
            super();
            this.initAnalyticalReport();
        }
    }
    ```

4. 빌드를 수행하여 변경 사항을 확인하십시오.

이제 포함된 Report Viewer 컨트롤을 초기화하기 위해 비즈니스 논리를 추가하는 작업을 완료했습니다. 다음 그림은 이러한 변경 사항을 적용한 후의 작업 공간을 보여줍니다.

![작업 공간에 포함된 보고서입니다.](media/analytical-workspace-final.png)

> [!NOTE]
> 페이지 제목 아래의 작업 영역 탭을 사용하여 기존 작업 보기에 액세스할 수 있습니다.

## <a name="reference"></a>참조

### <a name="pbireporthelperinitializereportcontrol-method"></a>PBIReportHelper.initializeReportControl 메서드
이 섹션에서는 양식 그룹 컨트롤에 Power BI 보고서(.pbix 리소스)를 포함하는 데 사용되는 도우미 클래스에 대한 정보를 제공합니다.

#### <a name="syntax"></a>구문
```xpp
public static void initializeReportControl(
    str                 _resourceName,
    FormGroupControl    _formGroupControl,
    str                 _defaultPageName = '',
    boolean             _showFilterPane = false,
    boolean             _showNavPane = false,
    List                _defaultFilters = new List(Types::Class))
```

#### <a name="parameters"></a>매개 변수

| 이름             | 설명                                                                                                  |
|------------------|--------------------------------------------------------------------------------------------------------------|
| 리소스 이름     | .pbix 리소스의 이름입니다.                                                                              |
| 폼그룹컨트롤 | Power BI 보고서 컨트롤을 적용할 양식 그룹 컨트롤입니다.                                              |
| 기본 페이지 이름  | 기본 페이지 이름입니다.                                                                                       |
| 필터 창 표시   | 필터 창을 표시해야 하는지(**true**) 아니면 숨겨야 하는지(**false**) 나타내는 부울 값입니다.     |
| showNavPane      | 탐색 창이 표시되어야 하는지(**true**) 아니면 숨겨져야 하는지(**false**)를 나타내는 부울 값입니다. |
| 기본 필터   | Power BI 보고서의 기본 필터입니다.                                                                 |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]