---
title: Regression Suite Automation Tool 자습서 설정 및 설치
description: 이 항목은 Regression Suite Automation Tool(RSAT)을 설정하고 설치하는 방법을 보여주는 자습서입니다.
author: tonyafehr
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: 21761, NotInToc
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 5dcdd14f54b9c0ad39794ff98ede29332c246513
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "8461010"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a>Regression Suite Automation Tool 자습서 설정 및 설치

이 항목은 RSAT 및 RSAT 사용과 관련된 도구를 설정하고 시작하는 데 도움이 되는 자습서입니다.

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> 인터넷 브라우저 도구를 사용하여 이 페이지를 PDF 형식으로 다운로드하고 저장하세요.

## <a name="key-concepts"></a>주요 컨셉

- RSAT(Regression Suite Automation Tool)를 지원하는 다양한 응용 프로그램에 필요한 설치 및 필수 구성 요소 설정을 이해합니다.
- Microsoft Dynamics Lifecycle Services(LCS) 및 Microsoft Azure DevOps와 함께 작업 레코더 기능을 사용하여 테스트 사례를 생성, 구성, 실행, 조사 및 보고하는 방법을 이해합니다.
- 기능적 사용자는 작업 레코더를 사용하여 비즈니스 작업을 기록하고 소스 코드를 작성할 필요 없이 작업 레코딩을 자동화된 테스트 제품군으로 변환할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="prerequisites"></a>전제 조건

- 이 자습서에는 Microsoft Dynamics 365 for Finance and Operations 버전 10.0(2019년 4월) 이상을 실행하는 환경이 필요합니다. Microsoft Dynamics 365 for Finance and Operations을 사용 중인 고객의 경우 Enterprise Edition 7.3, 플랫폼 업데이트 20(PU20) 이상도 지원됩니다.
- 사용자는 환경에 대한 관리자 권한이 있어야 합니다.
- 고객 테넌트 LCS 및 Azure DevOps(이전 명칭은 Microsoft Visual Studio 팀 서비스\[VSTS\])에 액세스할 수 있어야 합니다.
- 테스트 스위트를 생성하고 관리하는 사용자는 Azure DevOps 테스트 계획 또는 Test Manager 라이선스가 있어야 합니다. 다음 라이선스를 통해 테스트 계획에 액세스할 수도 있습니다.
    - Visual Studio Enterprise 라이선스
    - Visual Studio 테스트 전문가 라이선스
    - MSDN 플랫폼 구독자 라이선스
- RSAT는 웹 브라우저를 통해 테스트 환경에 액세스할 수 있어야 합니다.
- 테스트 매개변수를 생성하고 편집하려면 Microsoft Excel이 설치되어 있어야 합니다.

## <a name="configure-azure-devops"></a>Azure DevOps 구성

### <a name="user-eligibility"></a>사용자 적격 여부

사용자가 Azure DevOps에 생성되어 있으며 Azure 테스트 계획에 대한 액세스를 제공하는 구독 수준이 있어야 합니다. Azure DevOps 테스트 계획 라이선스는 사용자가 테스트 사례를 만들고 관리하는 경우에만 필요합니다(즉, 모든 RSAT 사용자에게 이 라이선스가 필요한 것은 아님). 라이선스 요구 사항에 대한 자세한 내용은 [라이선스 요구 사항](/azure/devops/test/manual-test-permissions#license-requirements)을 참조하세요.

### <a name="create-a-new-azure-devops-project"></a>새 Azure DevOps 프로젝트 만들기

RSAT는 테스트 사례 및 테스트 제품군 관리, 보고 및 테스트 실행 결과 조사에 Azure Devops를 사용합니다.

> [!NOTE]
> 기존 Azure DevOps 프로젝트를 사용할 수 있습니다. 그러나 기존 Azure DevOps 프로젝트가 사용자 지정 템플릿을 갖도록 설정되어 있는 경우 BPM(비즈니스 프로세스 모델러)에서 Azure DevOps로 테스트 사례를 동기화할 때 "VSTS 동기화 실패" 오류가 수신됩니다([BPM에서 Azure DevOps로의 동기화 테스트](#test-the-synchronization-from-bpm-to-azure-devops) 섹션 참조). 사용자 지정 템플릿에 대해 다음 모범 사례를 따랐다면 테스트 사례를 Azure DevOps에 동기화할 수 있습니다. (이러한 모범 사례는 오류 메시지에 나열되어 있습니다.)

- 작업 항목 유형 또는 기본 제공 필드를 삭제하지 마세요.
- 작업 항목 유형의 상태를 삭제하지 마세요.
- 작업 항목 유형에 필수 필드를 추가하지 마세요.

![모범 사례 목록이 포함된 오류 메시지입니다.](./media/setup_rsa_tool_02.png)

그렇지 않으면 이 자습서에서는 새 Azure DevOps 프로젝트를 만드는 것이 좋습니다. 자세한 내용은 [사용자 지정 Azure DevOps(VSTS) 프로세스 템플릿을 사용하여 BPM에 동기화할 때 문제](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/)를 참조하세요.

1. Azure DevOps URL(`https://dev.azure.com/<Azure DevOps Name>`)을 엽니다.
2. Azure DevOps 페이지의 오른쪽 상단 모서리에 있는 **프로젝트 만들기** 를 선택합니다.

    ![프로젝트 만들기 버튼.](./media/setup_rsa_tool_03.png)

3. 다음 필드를 채우고 **만들기** 를 선택합니다.

    - **프로젝트 이름**
    - **버전 관리** - **Team Foundation 버전 관리** 를 선택합니다. 기본 옵션 **Git** 는 지원되지 않습니다.
    - **작업 항목 프로세스**

    ![새 프로젝트 만들기 대화 상자.](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a>개인용 액세스 토큰 만들기

이 튜토리얼에서는 LCS BPM(Business Process Modeler)을 사용하여 테스트 케이스 라이브러리를 생성하고 테스트 케이스를 Azure DevOps와 동기화합니다. BPM을 Azure DevOps와 동기화하려면 개인 액세스 토큰이 필요합니다.

1. Azure DevOps 프로젝트의 페이지 오른쪽 상단 모서리에 있는 프로필 아이콘을 선택한 다음 **보안** 을 선택합니다.

    ![보안 명령.](./media/setup_rsa_tool_05.png)

2. 왼쪽 창의 **보안** 에서 **개인용 액세스 토큰** 을 선택합니다. 그런 다음 **새 토큰** 을 선택합니다.

    ![사용자 설정의 개인 액세스 토큰 탭에 있는 새 토큰 버튼.](./media/setup_rsa_tool_06.png)

3. 다음 필드를 채우고 **만들기** 를 선택합니다.

    - **이름**
    - **만료(UTC)** - **사용자 정의** 를 선택한 다음 날짜 선택기를 사용하여 사용 가능한 마지막 날짜를 선택합니다.
    - **범위** – **전체 권한** 옵션을 선택합니다.

    ![새 개인 액세스 토큰 대화 상자를 만듭니다.](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > 생성된 개인 액세스 토큰을 기록해 둡니다. 나중에 RSAT 구성을 설정할 때 필요합니다.

    ![개인용 액세스 토큰.](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a>LCS 프로젝트 구성

마스터 테스트 라이브러리에 대한 LCS(Lifecycle Services) 프로젝트가 필요합니다. LCS BPM(Business Process Modeler)은 테스트 케이스의 마스터 라이브러리로 사용됩니다. BPM은 LCS 프로젝트에서 테스트 라이브러리를 관리하고 배포하는 데 사용됩니다. 예를 들어, Microsoft 파트너 또는 ISV(독립 소프트웨어 공급업체) 구축 테스트 라이브러리는 BPM 라이브러리 형태로 테스트 사례를 릴리스합니다. BPM에서 테스트 케이스는 비즈니스 프로세스별로 구성됩니다. BPM은 테스트 통과의 실행 순서나 빈도를 정의하지 않습니다. 이러한 세부 정보는 Azure DevOps에서 관리되며, 이 항목의 뒷부분에서 설명합니다.  

LCS 프로젝트의 경우 기존 고객 구현 또는 파트너 프로젝트를 사용할 수 있습니다.

### <a name="update-the-lcs-language"></a>LCS 언어 업데이트

> [!NOTE]
> 사용자 인터페이스(UI)가 비즈니스 프로세스를 올바르게 표시하려면 LCS 기본 언어를 **영어(미국)** 로 설정해야 합니다.

1. LCS 구현 프로젝트로 이동합니다.
2. 오른쪽 상단 모서리에 있는 **설정** 버튼(기어 기호)을 선택한 다음 **언어 기본 설정** 을 선택합니다.

    ![언어 기본 설정을 업데이트합니다.](./media/setup_rsa_tool_09.png)

3. **선호하는 언어** 필드에서 **영어(미국)** 을 선택한 다음 **저장** 을 선택합니다.

    ![사용자 설정의 언어 기본 설정 탭.](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a>Azure DevOps 프로젝트에 연결하도록 LCS를 구성

이전에 Azure DevOps 프로젝트를 만들었다면 LCS 프로젝트를 구성하여 연결합니다. 그렇지 않고 LCS 프로젝트가 이미 Azure DevOps 프로젝트에 연결되어 있으면 다음 섹션으로 계속 진행할 수 있습니다.

1. LCS 구현 프로젝트로 이동합니다.
2. **메뉴** 버튼을 누른 다음 **프로젝트 설정** 을 선택합니다.

    ![프로젝트 설정 명령.](./media/setup_rsa_tool_11.png)

3. 왼쪽 창에서 **Visual Studio 팀 서비스** 를 선택한 다음 **Visual Studio 팀 서비스 설정** 을 선택합니다.

    ![프로젝트 설정의 Visual Studio 팀 서비스 탭.](./media/setup_rsa_tool_12.png)

4. **Azure DevOps 사이트 URL** 필드에 Azure DevOps 사이트의 URL을 입력합니다. **개인 액세스 토큰** 필드에 이전에 생성한 개인 액세스 토큰을 입력합니다.

    > [!NOTE]
    > VSTS는 현재 Azure DevOps로 알려져 있지만, LCS를 Azure DevOps 프로젝트에 연결하려면 이전 URL을 사용합니다. 예를 들어, 이 튜토리얼에서 사용되는 Azure DevOps URL은 `https://dev.azure.com/D365FOFastTrack/`입니다. 그러나 다음 그림에서는 `https://D365FOFastTrack.visualstudio.com/`으로 입력합니다.

    ![Visual Studio 팀 서비스 설정의 1단계.](./media/setup_rsa_tool_13.png)

5. **계속** 을 선택합니다.
6. **Visual Studio 팀 서비스 프로젝트** 필드에서 LCS 프로젝트와 연결할 선택한 사이트의 VSTS 프로젝트를 선택합니다. **프로세스 템플릿** 필드는 기본적으로 **신속** 으로 설정됩니다. 사용자 지정 템플릿의 경우 [새 Azure DevOps 프로젝트 만들기](#create-a-new-azure-devops-project) 섹션의 모범 사례 지침을 검토하세요. 그런 다음 **계속** 을 선택합니다.

    ![Visual Studio 팀 서비스 설정의 2단계.](./media/setup_rsa_tool_14.png)

7. 설정을 검토한 다음 **저장** 을 선택합니다.

    ![Visual Studio 팀 서비스 설정의 3단계.](./media/setup_rsa_tool_15.png)

8. **승인** 을 선택하여 사용자 대신 구성된 Azure DevOps 사이트에 대한 액세스 권한을 LCS에 부여하고 VSTS와 통합되는 기능을 켭니다.

    ![승인 버튼.](./media/setup_rsa_tool_16.png)

9. 다음과 같은 메시지가 표시됩니다. "LCS가 사용자 대신 Visual Studio 팀 서비스에 연결할 수 있는 권한을 부여하기 위해 영구 사이트로 리디렉션됩니다. 계속할까요?" **예** 를 선택합니다.

    ![메시지 상자입니다.](./media/setup_rsa_tool_17.png)

10. **수락** 을 선택합니다.

    ![액세스 권한 부여.](./media/setup_rsa_tool_18.png)

11. 사용자로 승인된 경우 UI는 LCS 프로젝트 설정 페이지로 돌아가야 합니다.

    ![권한 있는 사용자.](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a>새 BPM 라이브러리 만들기

1. LCS 구현 프로젝트로 이동합니다.
2. **메뉴** 버튼을 누른 다음 **비즈니스 프로세스 모델러** 를 선택합니다.

    ![비즈니스 프로세스 모델러 명령.](./media/setup_rsa_tool_20.png)

3. **새 라이브러리** 를 선택합니다.

    ![새 라이브러리 버튼입니다.](./media/setup_rsa_tool_21.png)

4. **라이브러리 이름** 필드에 이름을 입력한 다음 **만들기** 를 선택합니다. 이 자습서에서는 BPM 라이브러리의 이름을 **RSAT** 로 지정합니다.

    ![새 라이브러리 만들기 대화 상자.](./media/setup_rsa_tool_22.png)

5. 새 **RSAT** BPM 라이브러리를 엽니다.
6. **샘플 핵심 비즈니스 프로세스** 프로세스를 선택한 다음 오른쪽에서 **편집 모드** 를 선택합니다.

    ![편집 모드 버튼.](./media/setup_rsa_tool_23.png)

7. **이름** 필드와 **설명** 필드의 값을 모두 **제품 만들기** 로 변경합니다. 그런 다음 **저장** 을 선택합니다.

    ![이름 및 설명 필드.](./media/setup_rsa_tool_24.png)

## <a name="environment"></a>환경

### <a name="version-requirement"></a>버전 요구 사항

버전 10을 실행하는 테스트 또는 샌드박스 환경이 필요합니다. 버전 7.3을 사용 중인 고객의 경우 플랫폼 업데이트 20 이상도 지원됩니다.

> [!NOTE]
> RSAT는 웹 브라우저를 통해 테스트 환경에 액세스할 수 있어야 합니다.

### <a name="user-criteria"></a>사용자 기준

사용자는 이 환경에 대한 관리자 권한이 있어야 합니다.

### <a name="set-up-help-settings-to-connect-with-lcs"></a>LCS와 연결하기 위한 도움말 설정

이 단계는 클라이언트를 통해 LCS의 해당 BPM 라이브러리에 작업 기록을 저장할 수 있도록 LCS와 연결하기 위해 필요합니다.

1. 클라이언트를 엽니다.
2. **시스템 관리 \> 설정 \> 시스템 매개 변수** 로 이동합니다.
3. **도움말** 탭의 **Lifecycle Services 도움말 구성** 필드에서 관련 LCS 프로젝트를 선택합니다(이 자습서에서는 **RSAT**).

    ![도움말 탭의 Lifecycle Services 도움말 구성 필드](./media/setup_rsa_tool_25.png)

    BPM 라이브러리는 해당 LCS 프로젝트에서 채워집니다.

4. **저장** 을 선택합니다.
5. 업데이트된 도움말 콘텐츠를 보려면 브라우저를 새로 고쳐야 할 수 있습니다.

    ![브라우저 새로 고침에 대한 알림입니다.](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a>작업 기록

> [!NOTE]
> 모든 작업 기록이 기본 대시보드에서 시작되는지 확인합니다. 개별 녹음을 짧게 유지하고 판매 주문 생성과 같은 하나의 비즈니스 작업에 집중합니다.

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a>작업 기록을 만들고 BPM 라이브러리에 저장

새 BPM 라이브러리에서 생성된 단순 비즈니스 프로세스에 첨부할 수 있는 해당 작업 기록을 생성합니다.

1. 클라이언트를 엽니다.
2. 기본 대시보드에서 **설정** 버튼(기어 기호)을 선택한 다음 **작업 레코더** 를 선택합니다.

    ![설정 메뉴에서 작업 레코더를 선택합니다.](./media/setup_rsa_tool_27.png)

3. **녹음 만들기** 를 선택합니다.

    ![녹음 만들기 버튼.](./media/setup_rsa_tool_28.png)

4. **녹음 이름** 및 **녹음 설명** 필드를 작성한 다음 **시작** 을 선택합니다.

    ![녹음 이름 및 녹음 설명 필드.](./media/setup_rsa_tool_29.png)

5. 제품을 만드는 단계를 기록합니다. 완료되면 선택 **중지** 를 선택해 녹음을 중지합니다.

    ![제품을 만드는 단계.](./media/setup_rsa_tool_30.png)

6. **Lifecycle Services에 저장** 을 선택합니다.

    ![Lifecycle Services에 작업 기록을 저장합니다.](./media/setup_rsa_tool_31.png)

    라이브러리 정보는 LCS에서 로드됩니다.

    ![라이브러리 정보를 로드하는 중입니다.](./media/setup_rsa_tool_32.png)

7. 작업 녹화를 연결할 BPM 라이브러리를 선택합니다. 이 자습서에서는 앞서 생성한 **RSAT** BPM 라이브러리와 그 아래의 **제품 만들기** 비즈니스 프로세스를 선택합니다. 그런 다음 **확인** 을 선택합니다.

    ![작업 기록을 BPM 라이브러리 및 비즈니스 프로세스와 연결합니다.](./media/setup_rsa_tool_33.png)

    "Lifecycle Services에 저장했습니다." 메시지가 나타납니다.

    ![LCS에 성공적으로 저장했다는 메시지입니다.](./media/setup_rsa_tool_34.png)

8. 작업 기록을 로컬에 저장한 다음 LCS를 통해 BPM에 업로드하려면 다음 단계를 따르세요.

    1. 녹음 완료 후 **이 PC에 저장** 을 선택합니다.

        ![이 PC에 저장합니다.](./media/setup_rsa_tool_35.png)

    2. 브라우저의 알림 표시줄에서 **저장** 또는 **다른 이름으로 저장** 을 선택하여 로컬 컴퓨터에 파일을 저장합니다.

        ![알림 표시줄.](./media/setup_rsa_tool_36.png)

    3. **RSAT** BPM 라이브러리로 이동하고 작업 기록을 저장할 비즈니스 프로세스를 선택합니다.
    4. **개요** 탭에서 **업로드** 를 선택합니다.

        ![업로드 버튼.](./media/setup_rsa_tool_37.png)

    5. **검색** 을 선택하고 이전에 저장한 .axtr 파일을 선택합니다. 그런 다음 **업로드** 를 선택합니다.

        ![업로드할 .axtr 파일을 선택합니다.](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a>BPM에서 Azure DevOps로의 동기화 테스트

이제 작업 기록이 비즈니스 프로세스에 첨부되었으므로 LCS의 VSTS 동기화 기능을 사용하여 기능 및 테스트 케이스(각각)로 비즈니스 프로세스 및 연결된 작업 기록이 Azure DevOps에 동기화될 수 있는지 확인해야 합니다.

> [!NOTE]
> Azure DevOps에서 생성되는 해당 작업 항목 유형은 Azure DevOps로 LCS 프로젝트를 구성할 때 선택한 프로세스 템플릿에 따라 달라지며 [새 Azure DevOps 프로젝트 만들기](#create-a-new-azure-devops-project) 섹션에 설명되어 있습니다.

1. BPM 라이브러리로 이동하여 이전에 만든 **RSAT** 라이브러리를 엽니다.
2. 줄임표 버튼(**...**)를 선택하고 **VSTS 동기화** 를 선택합니다.

    ![줄임표 메뉴의 VSTS 동기화 명령.](./media/setup_rsa_tool_39.png)

    VSTS 동기화가 완료된 후 **요구 사항** 탭이 왼쪽에 나타나고 해당하는 Azure DevOps 작업 항목이 포함됩니다.

    > [!NOTE]
    > Azure DevOps에서 생성되는 작업 항목은 제목 접두사로 BPM 라이브러리 이름을 갖습니다.

    ![요구 사항 탭.](./media/setup_rsa_tool_40.png)

3. 페이지를 새로 고칩니다.
4. 줄임표 버튼(**...**)을 선택합니다. 추가 옵션 **테스트 케이스 동기화** 가 표시됩니다. 이 옵션을 선택합니다.

    ![줄임표 메뉴의 테스트 케이스 동기화 명령.](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > **테스트 케이스 동기화** 옵션을 페이지를 새로고침한 후에 사용할 수 없으면 BPM의 기본 페이지로 이동하여 **테스트 케이스 동기화** 를 전체 라이브러리 자체에 선택합니다. 이러한 방식으로 전체 라이브러리에 대한 동기화를 효과적으로 강제 실행할 수 있습니다.
    >
    > ![전체 라이브러리에 대한 동기화 테스트 케이스 선택.](./media/setup_rsa_tool_42.png)

    동기화 테스트 케이스가 완료된 후 **요구 사항** 탭에 새 테스트 케이스가 생성됩니다.

    ![요구 사항 탭의 새 테스트 사례.](./media/setup_rsa_tool_43.png)

5. Azure DevOps 프로젝트로 이동하고 **Boards \> 작업 항목** 을 선택합니다.

    ![Boards 아래의 작업 항목 명령.](./media/setup_rsa_tool_44.png)

6. BPM 동기화를 통해 생성한 작업 항목 및 테스트 케이스가 존재하는지 검증합니다.

    ![작업 항목 및 테스트 케이스.](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a>RSAT 설치 및 구성

RSAT는 Windows 10을 실행하고 웹 브라우저를 통해 환경에 연결할 수 있는 모든 컴퓨터에 설치할 수 있습니다(Internet Explorer 또는 Google Chrome).

> [!NOTE]
> 새 버전의 도구를 설치하기 전에 이전 버전을 제거하는 것이 좋습니다.

### <a name="install-an-authentication-certificate"></a>인증 인증서 설치

인증을 사용하려면 RSAT가 실행되는 동일한 컴퓨터에서 인증서를 생성하고 설치해야 합니다.

#### <a name="generate-a-certificate"></a>인증서 생성

1. 인증서 파일을 생성하려면 Microsoft Windows PowerShell 창을 관리자로 실행하고 다음 명령을 실행합니다.

    ```powershell
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. **실행** 대화 상자에 **certlm.msc** 를 입력하여 인증서 관리자를 열고 **D365 자동 테스트 인증서** 인증서가 **개인 \> 인증서** 에 생성되어 있는지 확인합니다.

    > [!NOTE]
    > 인증서가 로컬 컴퓨터에 저장되므로 **certmgr.msc** 가 아닌 **certlm.msc** 를 입력해야 합니다.

    ![D365 자동 테스트 인증서 인증서.](./media/setup_rsa_tool_46.png)

3. 인증서를 마우스 오른쪽 버튼으로 클릭한 다음 **복사** 를 선택합니다.
4. **신뢰할 수 있는 루트 인증 기관 \> 인증서** 로 이동합니다.

    ![신뢰할 수 있는 루트 인증 기관 폴더 아래의 인증서 폴더.](./media/setup_rsa_tool_47.png)

5. **동작** 메뉴에서 **붙여넣기** 를 선택하여 인증서를 **신뢰할 수 있는 인증 기관** 위치에 복사합니다.

    ![작업 메뉴의 붙여넣기 명령입니다.](./media/setup_rsa_tool_48.png)

6. 공백이나 특수 문자 없이 설치된 인증서의 지문을 가져오려면 Windows PowerShell 창을 관리자로 열고 다음 명령을 실행합니다.

    ```powershell
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > 지문은 나중에 AOS(Application Object Server)용 .wif 파일을 업데이트하고 RSAT 구성을 설정할 때 필요하므로 저장합니다.

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a>연결을 신뢰하도록 AOS 컴퓨터 구성

> [!NOTE]
> 환경이 Tier 2+ 환경인 경우 인증서 지문을 환경의 **모든** AOS 컴퓨터에 대해 wif.config 파일에서 업데이트해야 합니다.

1. AOS 컴퓨터에 대한 RDP(원격 데스크톱 프로토콜) 연결을 설정합니다. 로그인 세부 정보는 LCS의 환경 세부 정보 페이지에서 확인할 수 있습니다.
2. Microsoft 인터넷 정보 서비스(IIS)를 열고 사이트 목록에서 **AOSService** 를 찾습니다.

    ![사이트 목록의 AOSService.](./media/setup_rsa_tool_49.png)

3. 마우스 오른쪽 버튼으로 **탐색** 을 클릭하여 **\<Drive\>: \\AosService\\WebRoot** 폴더를 엽니다. **wif.config** 파일을 찾습니다.

    ![WebRoot 폴더의 Wif.config 파일.](./media/setup_rsa_tool_50.png)

4. 다음 예와 같이 인증서 및 기관 이름에 대한 새 기관 항목을 추가하여 **wif.config** 파일을 업데이트합니다.

    ```Xml
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > 여러 사용자가 동일한 응용 프로그램을 사용하는 경우 각 사용자는 별도의 지문을 생성해야 하며 이러한 각 지문은 **\<keys\>** 섹션에 추가되어야 합니다.

5. AOS 컴퓨터가 두 대 이상인 경우 추가 컴퓨터마다 3~4단계를 반복합니다.

    > [!NOTE]
    > 이전 Tier 2 환경과 달리 새로운 Tier 2 환경은 2개의 AOS 인스턴스와 함께 배포됩니다.

6. 모든 AOS 컴퓨터에서 **iisreset** 를 실행합니다.

    > [!NOTE]
    > Tier 1 컴퓨터에서 **iisreset** 를 실행할 관리자 권한이 없는 경우 LCS 환경 세부 정보 페이지에서 유지 관리 > 서비스 다시 시작을 선택합니다.

#### <a name="tier-2-environment"></a>Tier 2+ 환경

Tier 2+(Standard Acceptance Test 샌드박스 이상) 환경을 사용하는 경우 RSAT가 설치된 컴퓨터에서 다음 레지스트리 설정을 확인하거나 설정합니다. 이 단계는 인증 또는 RSAT 연결 오류를 방지하는 데 도움이 되기 때문에 필요합니다.

```PowerShell
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a>RSAT 설치

1. <https://www.microsoft.com/download/details.aspx?id=57357>로 이동하고 **다운로드** 를 선택합니다.
2. 모두 선택 파일을 선택하고 **다음** 을 선택합니다.

    ![모든 파일을 선택합니다.](./media/setup_rsa_tool_51.png)

3. .msi 패키지를 두 번 클릭하여 설치 프로그램을 실행합니다. 그런 다음 설치가 완료되면 **마침** 을 선택합니다.

    ![RSAT 설치 프로그램 파일.](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a>Selenium 및 브라우저 드라이버 설치

이전 버전의 RSAT에서는 Selenium 및 브라우저 드라이버를 설치해야 했습니다. 이러한 드라이버는 자동으로 설치되기 때문에 더 이상 설치할 필요가 없습니다.

1. RSAT를 처음 열면 자동으로 Selenium을 다운로드하고 설치하라는 메시지가 표시됩니다. 자세한 내용은 [RSAT 구성](#configure-rsat) 섹션을 참조하세요.
2. 테스트 사례를 실행하기 전에 RSAT 구성에서 선택한 기본 브라우저에 해당하는 브라우저 드라이버를 자동으로 다운로드하여 설치하라는 메시지가 표시됩니다. 자세한 내용은 [테스트 케이스 로드 및 실행](#load-and-run-test-cases) 섹션을 참조하세요.

## <a name="get-started-with-rsat"></a>RSAT 시작하기

### <a name="create-a-test-plan-and-test-suites"></a>테스트 계획 및 테스트 스위트 생성

1. Azure DevOps 프로젝트로 이동하고 **테스트 계획** 을 선택합니다.

    ![테스트 계획 명령.](./media/setup_rsa_tool_53.png)

2. **새로운 테스트 계획** 을 선택합니다.

    ![새 테스트 계획 버튼.](./media/setup_rsa_tool_54.png)

3. **이름** 필드를 채우고 **만들기** 를 선택합니다. 이 자습서의 경우 테스트 계획의 이름을 **RSAT 시험 계획** 으로 지정합니다.

    ![새 테스트 계획 대화 상자.](./media/setup_rsa_tool_55.png)

4. 더하기 기호(**+**)를 선택한 다음 **정적 제품군** 을 선택하여 새 테스트 계획에 따라 정적 제품군을 생성합니다. 새 테스트 모음 이름을 **T01 – 재고로 만들기** 로 지정합니다.

    > [!NOTE]
    > BPM의 새 테스트 사례를 자동으로 RSAT 테스트 도구 모음으로 가져오려는 경우 쿼리 기반 도구 모음을 만들 수도 있습니다.

    ![정적 제품군 만들기.](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a>테스트 스위트에 테스트 케이스 첨부

1. 오른쪽에서 **기존 추가** 를 선택하여 기존 테스트 케이스를 테스트 스위트에 추가합니다.

    ![기존 버튼을 추가합니다.](./media/setup_rsa_tool_57.png)

2. **제품군에 테스트 케이스 추가** 페이지에서 **쿼리 실행** 을 선택한 다음 테스트 스위트에 추가할 테스트 케이스를 선택합니다. 이 자습서에서는 **새 제품 만들기** 테스트 케이스를 선택합니다. 그런 다음 페이지 오른쪽 하단에서 **테스트 케이스 추가** 를 선택합니다(이 버튼은 다음 그림에 표시되지 않음).

    ![쿼리 버튼을 실행합니다.](./media/setup_rsa_tool_58.png)

    테스트 케이스가 **T01-재고로 만들기** 테스트 스위트에 추가됩니다.

    ![테스트 스위트에 테스트 케이스가 추가되었습니다.](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a>RSAT 구성

1. RSAT를 엽니다.

    ![RSAT 아이콘.](./media/setup_rsa_tool_60.png)

2. 다음 경고 메시지가 나타납니다. "Regression Suite Automation Tool에는 Selenium이 필요합니다. 지금 자동으로 다운로드하여 설치하시겠습니까?" **예** 를 선택합니다.

    ![Regression Suite Automation Tool에 Selenium이 필요하다는 경고 메시지.](./media/setup_rsa_tool_61.png)

3. 오른쪽 상단에서 **설정** 버튼(기어 기호)을 클릭한 다음 나타나는 대화 상자에서 다음 필드를 입력합니다.

    - **Azure DevOps URL** – Azure DevOps 프로젝트의 URL을 입력합니다. 예: `https://yourAzureDevOpsUrlHere.visualStudio.com`.
    - **액세스 토큰** – 도구에서 Azure DevOps에 연결할 수 있는 액세스 토큰을 입력합니다. 이 자습서의 앞부분에서 만든 개인 액세스 토큰을 사용합니다. 자세한 내용은 [개인 액세스 토큰으로 액세스 인증](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate)을 참조하세요.
    - **프로젝트 이름** – Azure DevOps 프로젝트의 이름을 선택합니다.
    - **테스트 계획** – 테스트 케이스가 포함된 Azure DevOps 테스트 계획을 선택합니다. 자세한 내용은 [테스트 계획 및 테스트 스위트 생성](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan)을 참조하세요. 테스트 계획을 선택한 후 **연결 테스트** 을 선택하여 Azure DevOps 연결을 테스트합니다.
    - **호스트 이름** – 다음과 같은 테스트 환경의 호스트 이름을 입력합니다. **\<myaos\>.cloudax.dynamics.com**. **https://** 또는 **http://** 접두사를 포함하지 마세요.
    - **SOAP 호스트 이름** – 테스트 환경의 SOAP 호스트 이름을 입력합니다. 일반적으로 SOAP 호스트 이름은 호스트 이름과 동일하지만 **SOAP** 접미사가 있습니다. 다음은 예입니다. **\<myaos\>soap.cloudax.dynamics.com**. **https://** 또는 **http://** 접두사를 포함하지 마세요.

        > [!NOTE]
        > 호스트 이름과 SOAP 호스트 이름을 찾으려면 IIS 관리자를 열고 마우스 오른쪽 버튼으로 **사이트 \> AOSService** 를 선택한 다음 **바인딩 수정** 을 선택합니다. **호스트 이름** 열의 값은 호스트 이름과 SOAP 호스트 이름을 제공합니다(SOAP 호스트 이름에는 URL에 **SOAP** 접미사가 있음).

        ![호스트 이름 열의 호스트 이름 및 SOAP 호스트 이름.](./media/setup_rsa_tool_63.png)

    - **관리자 사용자 이름** – 테스트 환경의 관리자 이메일 주소를 입력합니다.
    - **지문** – 이 자습서의 앞부분에서 설명한 대로 인증 인증서의 지문을 입력합니다.
    - **작업 디렉토리** – Excel 테스트 데이터 파일과 같은 테스트 자동화 파일을 저장할 폴더 위치를 지정합니다. 예를 들어 **C:\\Temp\\RegressionTool** 을 입력하거나 선택합니다.

        > [!NOTE]
        > 폴더 이름에 공백이 있으면 폴더를 찾을 수 없기 때문에 실행에 실패합니다. 이 문제는 알려진 문제이며 최신 버전의 도구에서 수정되어야 합니다.

    - **기본 브라우저** – **Internet Explorer** 또는 **Google Chrome** 을 선택합니다. 적절한 브라우저 드라이버가 설치되었는지 확인합니다.
    - **테스트 실행 시간 초과** – 테스트 실행에 대한 시간 초과 기간을 분 단위로 지정합니다. 제한 시간이 경과하면 모든 활성 창이 닫히고 보류 중인 테스트 케이스가 실패합니다.
    - **테스트 작업 시간 초과** – 이 필드는 재무 및 운영 환경 서버 요청에 대한 제한 시간(분)을 제어합니다. 일반적으로 기본값(2분)이면 충분합니다. 그러나 속도가 느린 환경의 경우 시간 초과와 관련된 오류가 발생하면 값을 늘릴 수 있습니다.
    - **회사 이름** – Excel 매개 변수 파일 생성 시 기본 회사로 사용할 회사명을 입력합니다. 추후 Excel 매개 변수 파일을 수정하여 회사를 변경할 수 있습니다.

    ![설정 대화 상자.](./media/setup_rsa_tool_62.png)

4. **적용** 을 선택하여 설정을 적용하고 저장합니다.

    현재 설정을 컴퓨터의 구성 파일에 저장하려면 **다른 이름으로 저장** 을 선택합니다. 컴퓨터의 구성 파일에서 설정을 복원하려면 **열기** 를 선택합니다.

5. **닫기** 를 선택하여 대화 상자를 닫습니다.

### <a name="load-and-run-test-cases"></a>테스트 케이스 로드 및 실행

1. **로드** 를 선택하여 Azure DevOps 프로젝트에서 **RSAT 시험 계획** 테스트 계획을 로드합니다.

    ![로드 버튼.](./media/setup_rsa_tool_64.png)

2. 테스트 스위트에서 **새 제품 만들기** 테스트 케이스를 선택한 다음 **새로 만들기 \> 테스트 실행 및 매개변수 파일 생성** 을 선택합니다.

    ![새로 만들기 메뉴에서 테스트 실행 및 매개변수 파일 생성 명령.](./media/setup_rsa_tool_65.png)

    Excel 매개변수 파일은 RSAT 구성에서 지정한 로컬 폴더(예: **C:\\Temp\\RegressionTool**).

    ![Excel 매개변수 파일이 생성되었습니다.](./media/setup_rsa_tool_66.png)

3. 매개변수 파일을 저장하려면 **업로드** 를 선택합니다. 선택한 모든 테스트 케이스의 테스트 자동화 파일이 나중에 사용할 수 있도록 Azure DevOps에 업로드됩니다. (이 파일에는 Excel 테스트 매개변수 파일이 포함되어 있습니다.)

    이러한 방식으로 **로드** 를 선택하여 Azure DevOps의 테스트 케이스에서 매개변수 파일(및 자동화 파일)을 직접 로드할 수 있습니다. 매개변수 파일을 다시 생성할 필요가 없습니다. 이 접근 방식은 나중에 매개변수 파일의 수정 사항을 유지하고 덮어쓰지 않으려는 경우 중요해집니다.

4. 자동화 파일 및 매개변수 파일이 Azure DevOps에 저장되었는지 확인하려면, Azure DevOps 프로젝트로 이동하고 **Boards \> 작업 항목** 을 선택하고 **새 제품 만들기** 테스트 케이스를 선택합니다. **첨부 파일** 탭에 다음 네 개의 파일이 표시되어야 합니다.

    - **.cs** – C\# 자동화 파일
    - **.dll** – 어셈블리로 컴파일된 자동화 파일
    - **.xlsx** – Excel 매개 변수 파일
    - **.xml** – 레코딩 파일

    ![첨부 파일 탭의 파일.](./media/setup_rsa_tool_67.png)

5. 실행할 테스트 케이스를 선택한 다음 **실행** 을 선택합니다.

    > [!NOTE]
    > 테스트 케이스를 실행하기 전에 브라우저로 Internet Explorer를 사용하는 경우 **Windows 디스플레이 설정 \> 배율 및 레이아웃** 에서 데스크톱 해상도가 **100%** 로 설정되어 있는지 확인합니다. 가상 머신(VM)에서 이 설정을 변경할 수 없는 경우 VM에 액세스하려는 클라이언트(노트북)에서 변경하세요. 그러면 해상도 설정이 VM 디스플레이 설정에 상속됩니다.

    ![데스크탑 해상도가 100%로 설정되었습니다.](./media/setup_rsa_tool_68.png)

6. 브라우저 드라이버가 시스템에 설치되어 있지 않으면 다음 경고 메시지를 받습니다. "이 작업에는 \<browser name\> 드라이버가 필요합니다. 지금 자동으로 다운로드하여 설치하시겠습니까?" **예** 를 선택합니다.

    ![Internet Explorer에 대한 경고 메시지.](./media/setup_rsa_tool_69.png)

    ![Chrome에 대한 경고 메시지.](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > Chrome을 브라우저로 사용 중이고 Chrome 버전이 올바르지 않아 세션이 생성되지 않았다는 오류 메시지가 표시되면 <http://chromedriver.chromium.org/downloads>에서 최신 Chrome 드라이버를 다운로드하여 **C:\\Program Files (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium** 폴더에 설치하세요.

    ![Chrome에 대한 오류 메시지.](./media/setup_rsa_tool_71.png)

    테스트 케이스가 실행되고, **결과** 필드가 업데이트됩니다.

    ![업데이트된 결과 필드.](./media/setup_rsa_tool_72.png)

    이 튜토리얼을 작성된 대로 따랐다면 제품 생성을 위한 작업 기록이 제품 이름을 하드 코딩된 값으로 저장했기 때문에 **새 제품 만들기** 테스트 케이스는 실패합니다. 동일한 테스트 케이스를 다시 실행하면 제품이 이미 존재하기 때문에 오류 메시지가 표시되어야 합니다.

    ![결과 필드가 실패로 설정되었습니다.](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a>테스트 결과 보기

1. 실패한 테스트 케이스를 두 번 클릭합니다.

    오류 메시지를 받습니다.

    ![오류 메시지.](./media/setup_rsa_tool_73.png)

2. **세부 정보** 를 선택하여 전체 오류 메시지를 봅니다.

    ![전체 오류 메시지.](./media/setup_rsa_tool_74.png)

3. Azure DevOps에서 오류 메시지의 자세한 버전을 보려면 **Azure DevOps에서 열기** 를 선택합니다. Azure DevOps에서 테스트 케이스의 상태와 자세한 오류 메시지를 볼 수 있습니다.

    ![Azure DevOps의 자세한 오류 메시지.](./media/setup_rsa_tool_75.png)

4. Azure DevOps 프로젝트에서 테스트 결과를 직접 보려면 **테스트 계획 \> 테스트 계획 \> 실행** 으로 이동합니다. 자세한 내용을 보려는 테스트 실행을 두 번 클릭합니다.

    ![Azure DevOps의 테스트 실행 목록.](./media/setup_rsa_tool_76.png)

5. **실행 요약** 탭은 테스트 케이스가 실패했음을 나타내지만 실제 오류 메시지는 제공하지 않습니다. 자세한 오류 메시지를 보려면 **시험 결과** 탭을 선택합니다.

    ![실행 요약 탭.](./media/setup_rsa_tool_77.png)

    **시험 결과** 탭은 결과 및 오류 메시지와 함께 테스트 사례 정보를 제공합니다.

    ![테스트 결과 탭.](./media/setup_rsa_tool_78.png)

6. 자세한 오류 메시지를 보려면 해당 레코드를 두 번 클릭합니다.

    ![자세한 오류 메시지.](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > 모든 오류 메시지는 **C:\\Users\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt** 에서 로컬로 사용할 수도 있습니다.

7. **내보내기** 를 선택하여 테스트 계획 수준에서 테스트 실행 결과를 내보낼 수도 있습니다.

    ![테스트 계획 내보내기.](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a>Excel 매개 변수 파일 수정

1. RSAT를 엽니다.
2. 테스트 케이스를 선택한 다음 **편집** 을 선택하여 Excel 매개변수 파일을 엽니다.

    **EcoResProductCreate** 시트에서 **제품 번호** 필드의 값이 하드 코딩되어 있습니다. 테스트 케이스를 다시 실행하기 전에 이 필드를 새 제품 번호로 업데이트해야 합니다.

3. Excel 매개변수 파일을 다시 열고 매번 수동으로 제품 번호를 업데이트할 필요 없이 각 실행에 대해 고유한 제품 번호를 생성하려면 다음 Excel 수식을 사용하세요.

    ```vba
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > **일반** 탭 외에도 Excel 매개변수 파일에는 테스트 케이스가 방문하는 모든 양식 페이지에 대한 데이터 탭이 포함되어 있습니다.

    ![제품 번호 필드.](./media/setup_rsa_tool_81.png)

4. **저장** 을 선택한 다음 Excel 통합 문서를 닫습니다.
5. **업로드** 를 선택하여 Azure DevOps에 Excel 매개 변수 파일을 저장합니다.

    ![업로드 성공 메시지.](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > 특정 사용자 컨텍스트에서 테스트 사례를 실행하려면 Excel 매개 변수 파일의 **일반** 탭에서 **테스트 사용자** 필드에 사용자 ID를 입력합니다. 최신 버전의 RSAT에서는 Excel 매개 변수 파일의 필드 레이아웃이 업데이트되었지만 개념은 동일하게 유지됩니다.
    >
    > ![테스트 사용자 필드.](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a>결과 유효성 검사

- **실행** 을 선택하여 테스트 케이스를 다시 실행하고 테스트 케이스가 통과했는지 확인합니다. [테스트 결과 보기](#view-the-test-results) 섹션에 에 설명된 대로 테스트 결과를 볼 수 있습니다.

    ![결과 필드가 성공으로 설정되었습니다.](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a>테스트 케이스 연결

RSAT의 주요 기능 중 하나는 테스트 사례의 연결(즉, 다른 테스트에 값을 전달하는 테스트의 기능)입니다. 테스트 케이스는 Azure DevOps 테스트 계획에 정의된 순서에 따라 실행됩니다. (이 순서는 테스트 도구 자체에서 업데이트할 수도 있습니다.) 따라서 한 테스트 케이스에서 다른 테스트 케이스로 변수를 전달하려는 경우 테스트가 올바른 순서로 되어 있는 것이 매우 중요합니다.

이 섹션에서는 첫 번째 테스트 케이스에 저장된 변수를 만들고, 두 번째 테스트 케이스를 만들고, 첫 번째 테스트 케이스에서 두 번째 테스트 케이스로 저장된 변수를 전달합니다. 그런 다음 테스트 사례를 RSAT에서 연결된 테스트 사례로 실행합니다.

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a>기존 작업 기록을 수정하여 저장된 변수 생성

1. 클라이언트를 엽니다.
2. **설정** 버튼(기어 기호)을 선택한 다음 **작업 레코더** 를 선택합니다.
3. **녹음 편집** 을 선택합니다.

    ![레코딩 편집 단추.](./media/setup_rsa_tool_85.png)

4. **Lifecycle Services에서 열기** 를 선택합니다.

    ![Lifecycle Services에서 열기 버튼.](./media/setup_rsa_tool_86.png)

5. **Lifecycle Services 라이브러리 선택** 을 선택합니다.

    ![Lifecycle Services 라이브러리 선택 버튼.](./media/setup_rsa_tool_87.png)

    BPM 라이브러리는 LCS에서 로드됩니다.

    ![BPM 라이브러리를 로드 중입니다.](./media/setup_rsa_tool_88.png)

6. BPM 라이브러리가 LCS에서 로드된 후 작업 기록이 연결된 **RSAT** BPM 라이브러리와 **새 제품 만들기** 비즈니스 프로세스를 선택합니다. 그런 다음 **확인** 을 선택합니다.

    ![BPM 라이브러리 및 비즈니스 프로세스 선택.](./media/setup_rsa_tool_89.png)

7. 적절한 작업 녹화의 이름이 **녹화 이름** 필드에 입력됩니다. **시작** 을 선택합니다.

    ![녹음 이름 필드의 작업 녹음 이름입니다.](./media/setup_rsa_tool_90.png)

8. **상품 정보 관리 \> 제품** 으로 이동하고 **새로 만들기** 를 선택하면 원래 작업 기록 **제품 만들기** 가 기록된 페이지가 열립니다.
9. **단계 삽입** 을 선택합니다.

    > [!NOTE]
    > 청에서 선택한 단계 **뒤에** 새 단계가 삽입됩니다.

    ![단계 삽입 버튼.](./media/setup_rsa_tool_91.png)

10. 마우스 오른쪽 버튼으로 **제품 번호** 필드를 선택한 다음 **작업 레코더 \> 복사** 를 선택합니다.

    ![복사 명령.](./media/setup_rsa_tool_92.png)

11. 창에 새 단계가 추가됩니다. 나중에 필요하므로 **제품 번호** 필드의 값을 기록해 둡니다.

    ![새로운 단계가 추가되었습니다.](./media/setup_rsa_tool_93.png)

12. **편집 완료** 를 선택합니다.
13. **Lifecycle Services에 저장** 을 선택하고 새 작업 기록을 원래 작업 기록과 연결된 동일한 BPM 라이브러리 및 비즈니스 프로세스와 연결합니다. 자세한 내용은 [작업 기록을 만들고 BPM 라이브러리에 저장](#create-a-task-recording-and-save-it-to-the-bpm-library) 섹션을 참조하세요.
14. BPM 라이브러리로 이동하여 **테스트 케이스 동기화** 를 선택하여 Azure DevOps의 테스트 케이스에 첨부된 작업 기록을 덮어쓰세요. [BPM에서 Azure DevOps로의 동기화 테스트](#test-the-synchronization-from-bpm-to-azure-devops) 섹션에 설명되어 있습니다.
15. RSAT를 열고 **로드** 를 선택하여 테스트 스위트의 모든 테스트 케이스를 다시 로드합니다. [테스트 케이스 로드 및 실행](#load-and-run-test-cases) 섹션에 설명된 대로 테스트 케이스를 선택한 다음 **새로 만들기 \> 테스트 실행 및 매개 변수 파일 생성** 을 선택하여 적절한 테스트 케이스에 대한 자동화 및 매개변수 파일을 재생성해야 합니다.

    > [!NOTE]
    > Excel 매개변수 파일이 열려 있으면 재생성이 실패합니다. 따라서 새 Excel 매개변수 파일을 생성하기 전에 테스트 케이스에 대한 Excel 매개변수 파일이 닫혀 있는지 확인합니다.

16. **편집** 을 선택하여 새 Excel 매개변수 파일을 엽니다. 라인 9에 새로 **저장된 변수** 가 있습니다. 이 변수 **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** 는 작업 기록의 XML 파일에 저장되며 후속 테스트에서 사용할 수 있습니다.

    ![저장된 변수 항목입니다.](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a>새 테스트 케이스 생성

1. **RSAT** BPM 라이브러리로 이동합니다.
2. **샘플 지원 비즈니스 프로세스** 프로세스를 선택한 다음 오른쪽에서 **편집 모드** 를 선택합니다.
3. **이름** 필드와 **설명** 필드의 값을 모두 **제품 릴리스** 로 변경합니다. 그런 다음 **저장** 을 선택합니다.

    ![이름과 설명이 제품 출시로 변경되었습니다.](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a>유효성 검사 기능이 있는 새 작업 기록 만들기

- USRT 법인에 이전에 생성된 제품을 출시하기 위한 작업 기록을 생성합니다. 자세한 내용은 [작업 기록을 만들고 BPM 라이브러리에 저장](#create-a-task-recording-and-save-it-to-the-bpm-library) 섹션을 참조하세요.

    > [!NOTE]
    > 연결된 테스트 사례의 경우 항상 *필드 값을 수동으로 입력* 을 통해 필요한 레코드를 찾거나 필터링하는 것이 좋습니다. 이러한 방식으로 도구는 후속 테스트 케이스에서 조치를 취해야 하는 레코드를 결정할 수 있습니다.

    ![유효성 검사 기능이 있는 새 작업 기록.](./media/setup_rsa_tool_96.png)

    앞의 그림과 같이 퀵필터를 이용하여 상품을 찾은 후 **출시 제품** 을 선택하기 전에 **제품 번호** 필드를 입력하여 제품 ID가 이전에 생성된 제품 ID인지 확인하세요. 값을 확인하려면 **제품 번호** 필드를 마우스 오른쪽 버튼으로 클릭한 다음 **작업 레코더 \> 확인 \> 현재 가치** 를 선택합니다.

    ![현재 값 확인.](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a>작업 기록을 BPM에 저장

1. 작업 녹음 완료 후 **Lifecycle Services에 저장** 을 선택합니다.

    ![Lifecycle Services에 완료된 작업 기록을 저장합니다.](./media/setup_rsa_tool_98.png)

2. 라이브러리 정보는 LCS에서 로드됩니다.

    ![LCS에서 라이브러리 정보를 로드하는 중입니다.](./media/setup_rsa_tool_99.png)

3. 작업 녹화를 연결할 BPM 라이브러리를 선택합니다. 이 자습서에서는 앞서 생성한 **RSAT** BPM 라이브러리와 그 아래의 **제품 릴리스** 비즈니스 프로세스를 선택합니다. 그런 다음 **확인** 을 선택합니다.

#### <a name="sync-bpm-to-azure-devops"></a>BPM을 Azure DevOps에 동기화

1. BPM 라이브러리로 이동하여 **RSAT** 라이브러리를 엽니다.
2. **VSTS 동기화** 를 선택한 다음 **테스트 케이스 동기화** 를 선택합니다. 자세한 내용은 [BPM에서 Azure DevOps로의 동기화 테스트](#test-the-synchronization-from-bpm-to-azure-devops) 섹션을 참조하세요.

    동기화가 완료된 후 **제품 릴리스** 비즈니스 프로세스의 새 작업 항목과 해당 테스트 케이스가 Azure DevOps의 **Boards \> 작업 항목** 에 표시됩니다.

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a>기존 테스트 스위트에 새 테스트 케이스 추가

1. **테스트 계획 \> 테스트 계획** 을 선택하고 **RSAT 시험 계획** 계획을 선택합니다.
2. **기존 추가** 를 선택합니다.
3. **제품군에 테스트 케이스 추가** 페이지에서 **쿼리 실행** 을 선택합니다.
4. **제품 릴리스** 에 대해 생성된 새 테스트 케이스를 선택한 다음 페이지 오른쪽 하단의 **테스트 케이스 추가**(이 버튼은 다음 그림에 표시되지 않음)를 선택합니다.

    ![제품군 페이지에 테스트 케이스를 추가합니다.](./media/setup_rsa_tool_100.png)

    테스트 스위트에는 이제 두 개의 테스트 케이스가 있습니다.

    ![테스트 스위트에 두 개의 테스트 케이스.](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a>테스트 케이스를 RSAT에 로드

1. RSAT를 열고 **로드** 를 선택합니다.
2. 테스트 사례가 로드되고 "이 작업은 Excel 테스트 데이터 파일을 덮어쓰므로 로컬 변경 사항이 손실됩니다. 계속 진행하시겠습니까?" **네** 를 선택하여 로컬 시스템의 Excel 매개변수 파일을 업데이트하지만 Azure DevOps에 업로드된 Excel 매개변수 파일은 업데이트하지 않습니다.

    ![이 작업은 Excel 테스트 데이터 파일을 덮어씁니다.](./media/setup_rsa_tool_102.png)

    두 테스트 케이스 모두 첫 번째 테스트 케이스에 대한 Excel 매개변수 파일과 함께 로드됩니다. 마지막 실행에서 **업로드** 를 선택했으므로 매개 변수 파일은 Azure DevOps에서 가져옵니다.

    ![테스트 케이스가 로드되었습니다.](./media/setup_rsa_tool_103.png)

3. 두 번째 테스트 케이스만 선택한 다음 **새로 만들기 \> 테스트 실행 및 매개변수 파일 생성** 을 선택합니다.

#### <a name="edit-the-excel-parameter-file"></a>Excel 매개 변수 파일 편집

1. 두 번째 테스트 케이스만 선택한 다음 **편집** 을 선택하여 해당 Excel 매개변수 파일을 엽니다.
2. **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** 저장된 변수([기존 작업 기록을 수정하여 저장된 변수 생성](#modify-an-existing-task-recording-to-create-a-saved-variable) 섹션 참조)를 첫 번째 테스트 케이스에서 제품 번호가 사용되는 모든 필드로 복사합니다. 이 경우 **EcoResProductListPage** 시트의 **제품 번호** 및 **제품 번호 확인** 필드로 변수를 복사합니다.

    ![제품 번호 및 유효성 검사 제품 번호 필드.](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > 변수는 동일한 테스트 실행 중에만 테스트 간에 전달할 수 있습니다. 변수 이름은 정확히 일치해야 합니다.

3. **저장** 을 선택한 다음 Excel 통합 문서를 닫습니다.
4. **업로드** 를 선택하여 Excel 매개변수 파일에 대한 변경 사항을 저장합니다.

#### <a name="run-the-chained-test-cases"></a>연결된 테스트 케이스 실행

1. 두 테스트 케이스를 선택한 다음 **실행** 을 선택합니다.
2. 두 테스트 케이스가 모두 통과했는지 확인합니다.

    ![두 테스트 케이스 모두에 대해 결과 필드가 통과로 설정되었습니다.](./media/setup_rsa_tool_105.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]