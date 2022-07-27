---
title: 정기 데이터 내보내기 앱 만들기
description: 이 항목에서는 정기 일정에 따라 Microsoft Dynamics 365 Human Resources에서 데이터를 내보내는 Microsoft Azure 논리 앱을 만드는 방법을 설명합니다.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 368eee6bb182f363f47467a5c5ad8208a57db7ec
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452584"
---
# <a name="create-a-recurring-data-export-app"></a>정기 데이터 내보내기 앱 만들기


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 정기 일정에 따라 Microsoft Dynamics 365 Human Resources에서 데이터를 내보내는 Microsoft Azure 논리 앱을 만드는 방법을 설명합니다. 이 자습서에서는 Human Resources의 DMF 패키지 REST API(애플리케이션 프로그래밍 인터페이스)를 활용하여 데이터를 내보냅니다. 데이터를 내보낸 후 논리 앱은 내보낸 데이터 패키지를 Microsoft 비즈니스용 OneDrive 폴더에 저장합니다.

## <a name="business-scenario"></a>비즈니스 시나리오

Microsoft Dynamics 365 통합을 위한 한 가지 일반적인 비즈니스 시나리오에서 정기 일정에 따라 데이터를 다운스트림 시스템으로 내보내야 한다고 가정해 보겠습니다. 이 자습서에서는 Microsoft Dynamics 365 Human Resources에서 모든 근로자 레코드를 내보내고 비즈니스용 OneDrive 폴더에 근로자 목록을 저장하는 방법을 보여줍니다.

> [!TIP]
> 이 자습서에서 내보낸 특정 데이터와 내보낸 데이터의 대상은 예시일 뿐입니다. 비즈니스 요구 사항에 맞게 쉽게 변경할 수 있습니다.

## <a name="technologies-used"></a>사용된 기술

이 자습서에서는 다음 기술을 사용합니다.

- **[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)** – 내보낼 근로자의 마스터 데이터 원본.
- **[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – 정기 내보내기의 오케스트레이션 및 일정을 제공하는 기술.

    - **[커넥터](/azure/connectors/apis-list)** – 논리 앱을 필요한 엔드포인트에 연결하는 데 사용되는 기술.

        - [HTTP with Azure AD](/connectors/webcontents/) 커넥터
        - [비즈니스용 OneDrive](/azure/connectors/connectors-create-api-onedriveforbusiness) 커넥터

- **[DMF 패키지 REST API](../fin-ops-core/dev-itpro/data-entities/data-management-api.md)** – 내보내기를 시작하고 진행 상황을 모니터링하기 위한 기술.
- **[비즈니스용 OneDrive](https://onedrive.live.com/about/business/)** – 내보낸 근로자의 대상.

## <a name="prerequisites"></a>전제 조건

이 자습서의 연습을 시작하기 전에 다음 항목이 있어야 합니다.

- 환경에 대한 관리자 수준 권한이 있는 Human Resources
- 논리 앱을 호스트하기 위한 [Azure 구독](https://azure.microsoft.com/free/)

## <a name="the-exercise"></a>연습

이 연습을 진행하면 Human Resources 및 비즈니스용 OneDrive 계정에 연결된 논리 앱을 만들 수 있습니다. 논리 앱은 Human Resources에서 데이터 패키지를 내보내고 내보내기가 완료될 때까지 기다렸다가 내보낸 데이터 패키지를 다운로드하고 지정한 비즈니스용 OneDrive 폴더에 데이터 패키지를 저장합니다.

완성된 논리 앱은 다음 그림과 비슷합니다.

![논리 앱 개요.](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a>1단계: Human Resources에서 데이터 내보내기 프로젝트 만들기

Human Resources에서 근로자를 내보내는 데이터 내보내기 프로젝트를 만듭니다. 프로젝트 이름을 **근로자 내보내기** 로 지정하고 **데이터 패키지 생성** 옵션이 **예** 로 설정되어 있는지 확인합니다. 단일 엔터티(**근로자**)를 프로젝트에 추가하고 내보낼 형식을 선택합니다. (이 자습서에서는 Microsoft Excel 형식을 사용합니다.)

![근로자 데이터 내보내기 프로젝트.](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> 데이터 내보내기 프로젝트의 이름을 기억하세요. 다음 단계에서 논리 앱을 만들 때 필요합니다.

### <a name="step-2-create-the-logic-app"></a>2단계: 논리 앱 만들기

연습의 대부분은 논리 앱을 만드는 과정입니다.

1. Azure Portal에서 논리 앱을 만듭니다.

    ![논리 앱 만들기 페이지.](media/integration-logic-app-creation-1.png)

2. Logic Apps Designer에서 빈 논리 앱으로 시작합니다.
3. 논리 앱을 24시간마다(또는 선택한 일정에 따라) 실행하도록 [되풀이 일정 트리거](/azure/connectors/connectors-native-recurrence)를 추가합니다.

    ![되풀이 대화 상자.](media/integration-logic-app-recurrence-step.png)

4. [ExportToPackage](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API를 호출하여 데이터 패키지 내보내기를 예약합니다.

    1. Azure AD 커넥터를 사용하여 HTTP에서 **HTTP 요청 호출** 작업을 사용합니다.

        - **기본 리소스 URL:** Human Resources 환경의 URL(경로/네임스페이스 정보를 포함하지 마세요.)
        - **Azure AD 리소스 URI:** `http://hr.talent.dynamics.com`

        > [!NOTE]
        > Human Resources 서비스는 **ExportToPackage** 와 같이 DMF 패키지 REST API를 구성하는 모든 API를 노출하는 커넥터를 아직 제공하지 않습니다. 대신 Azure AD 커넥터가 있는 HTTP를 통해 원시 HTTPS 요청을 사용하여 API를 호출해야 합니다. 이 커넥터는 Human Resources에 대한 인증과 권한 부여를 위해 Azure AD(Azure Active Directory)를 사용합니다.

        ![HTTP with Azure AD 커넥터.](media/integration-logic-app-http-aad-connector-step.png)

    2. HTTP with Azure AD 커넥터를 통해 Human Resources 환경에 로그인합니다.
    3. **ExportToPackage** DMF REST API를 호출하도록 HTTP **POST** 요청을 설정합니다.

        - **방식:** POST
        - **요청 URL:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage
        - **요청 본문:**

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![HTTP 요청 작업 호출.](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > 각 단계의 이름을 기본 이름인 **HTTP 요청 호출** 보다 더 의미 있는 이름으로 변경할 수 있습니다. 예를 들어 이 단계의 이름을 **패키지로 내보내기** 로 변경할 수 있습니다.

5. [변수 초기화](/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable)로 **패키지로 내보내기** 요청의 실행 상태를 저장합니다.

    ![변수 초기화 작업.](media/integration-logic-app-initialize-variable-step.png)

6. 데이터 내보내기의 실행 상태가 **성공** 이 될 때까지 기다립니다.

    1. **ExecutionStatus** 변수의 값이 **성공** 이 될 때까지 반복되는 [Until 루프](/azure/logic-apps/logic-apps-control-flow-loops#until-loop)를 추가합니다.
    2. 내보내기의 현재 실행 상태를 폴링하기 전에 5초 동안 대기하는 **지연** 작업을 추가합니다.

        ![Until 루프 컨테이너.](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > 제한 횟수를 **15** 로 설정하여 내보내기가 완료될 때까지 최대 75초(15회 반복 × 5초)를 기다리도록 설정합니다. 내보내기에 더 많은 시간이 소요되는 경우 제한 횟수를 적절하게 조정하세요.        

    3. **HTTP 요청 호출** 작업을 추가하여 [GetExecutionSummaryStatus](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API를 호출하고 **ExecutionStatus** 변수를 **GetExecutionSummaryStatus** 응답의 결과로 설정합니다.

        > 이 샘플은 오류 검사를 수행하지 않습니다. **GetExecutionSummaryStatus** API가 성공하지 못한 터미널 상태(즉, **성공** 이외의 상태)를 반환할 수 있습니다. 자세한 내용은 [API 설명서](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus)를 참조하세요.

        - **방식:** POST
        - **요청 URL:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus
        - **요청 본문:** body('Invoke\_an\_HTTP\_request')?['value']

            > [!NOTE]
            > **요청 본문** 값을 코드 보기나 디자이너의 함수 편집기에 입력해야 할 수 있습니다.

        ![HTTP 요청 2 작업 호출.](media/integration-logic-app-get-execution-status-step.png)

        ![변수 설정 작업.](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > 디자이너에 값이 동일하게 표시되지만 **변수 설정** 작업(**body('Invoke\_an\_HTTP\_request\_2')?['value']**)에 대한 값은 **HTTP 요청 2 호출** 본문에 대한 값과는 다릅니다.

7. 내보낸 패키지의 다운로드 URL을 가져옵니다.

    - **HTTP 요청 호출** 작업을 추가하여 [GetExportedPackageUrl](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API를 호출합니다.

        - **방식:** POST
        - **요청 URL:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl
        - **요청 본문:** {"executionId": body('GetExportedPackageURL')?['value']}

        ![GetExportedPackageURL 작업.](media/integration-logic-app-get-exported-package-step.png)

8. 내보낸 패키지를 다운로드합니다.

    - 이전 단계에서 반환된 URL에서 패키지를 다운로드하는 HTTP **GET** 요청(기본 제공 [HTTP 커넥터 작업](/azure/connectors/connectors-native-http))을 추가합니다.

        - **방식:** GET
        - **URI:** body('Invoke\_an\_HTTP\_request\_3').value

            > [!NOTE]
            > **URI** 값을 코드 보기나 디자이너의 함수 편집기에 입력해야 할 수 있습니다.

        ![HTTP GET 작업.](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > **GetExportedPackageUrl** API가 반환하는 URL에는 파일 다운로드에 대한 액세스 권한을 부여하는 공유 액세스 서명 토큰이 포함되어 있으므로 이 요청에는 추가 인증이 필요 없습니다.

9. [비즈니스용 OneDrive](/azure/connectors/connectors-create-api-onedriveforbusiness) 커넥터를 사용하여 다운로드한 패키지를 저장합니다.

    - 비즈니스용 OneDrive [파일 만들기](/connectors/onedriveforbusinessconnector/#create-file) 작업을 추가합니다.
    - 필요에 따라 비즈니스용 OneDrive 계정에 연결합니다.

        - **폴더 경로:** 원하는 폴더
        - **파일 이름:** worker\_package.zip
        - **파일 내용:** 이전 단계의 본문(동적 콘텐츠)

        ![파일 만들기 작업.](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a>3단계: 논리 앱 테스트

논리 앱을 테스트하려면 디자이너의 **실행** 버튼을 선택합니다. 논리 앱의 단계가 실행되기 시작하는 것을 볼 수 있습니다. 30~40초 후에 논리 앱 실행이 완료되면 비즈니스용 OneDrive 폴더에 내보낸 근로자가 포함된 새 패키지 파일이 포함되어 있을 것입니다.

실패가 보고되는 단계가 있으면 디자이너에서 실패한 단계를 선택하고 **입력** 및 **출력** 필드를 검사합니다. 오류를 수정하는 데 필요한 단계를 디버그하고 조정합니다.

다음 그림은 논리 앱의 모든 단계가 정상적으로 실행될 때 Logic Apps Designer를 보여줍니다.

![정상적인 논리 앱 실행.](media/integration-logic-app-successful-run.png)

## <a name="summary"></a>요약

이 자습서에서는 논리 앱을 사용하여 Human Resources에서 데이터를 내보내고 내보낸 데이터를 비즈니스용 OneDrive 폴더에 저장하는 방법을 배웠습니다. 비즈니스 요구 사항에 맞게 필요에 따라 이 자습서의 단계를 수정할 수 있습니다.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
