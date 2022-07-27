---
title: Teams에서 휴가 요청 관리
description: 이 항목에서는 Microsoft Teams의 Dynamics 365 Human Resources 앱에서 휴가를 요청하는 방법을 보여줍니다.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d004e33d01dbd171626d7e23f93df081bc0210a9
ms.sourcegitcommit: 70ac76be31bab7ed5e93f92f4683e65031fbdf85
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2021
ms.locfileid: "8451975"
---
# <a name="manage-leave-requests-in-teams"></a>Teams에서 휴가 요청 관리

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Teams의 Dynamics 365 Human Resources 앱을 사용하면 Microsoft Teams에서 바로 휴가를 신속하게 요청하고 휴가 잔액 정보를 볼 수 있습니다. 봇과 상호 작용하여 정보를 요청하고 휴가 요청을 시작할 수 있습니다. **휴가** 탭에는 자세한 정보가 표시됩니다. Teams에서 예정된 휴가에 대한 정보를 보내고 Human Resources 앱 외부에서 채팅할 수도 있습니다.

## <a name="install-the-app"></a>앱 설치

Dynamics 365 Human Resources 앱은 Teams 스토어에서 찾을 수 있습니다.

1. Microsoft Teams에서 앱 목록으로 이동합니다.
 
2. Dynamics 365 Human Resources를 검색한 다음 **Human Resources** 타일을 선택합니다.

> [!NOTE]
> 2021년 12월 20일부터 Microsoft 테넌트에서 호스팅되는 Human Resources 앱 봇 서비스(버전 1.1.4)가 서비스 해제됩니다. 최신 확장(버전 1.1.5)을 설치할 수 있습니다. 자세한 내용은 [Teams에서 휴가 요청 관리 ](hr-admin-teams-leave-app.md#update-app)를 참조하세요.

3. **추가** 버튼을 설치해 앱을 설치합니다.

앱에서 자동으로 로그인하지 않으면 **설정** 탭을 선택하여 로그인합니다.

> [!NOTE]
> 로그인 대화 상자가 표시되지 않으면 팝업을 허용하도록 브라우저 설정을 업데이트하세요. 

둘 이상의 Human Resources 인스턴스에 액세스할 수 있는 경우 **설정** 탭에서 연결할 환경을 선택할 수 있습니다.

> [!NOTE]
> 이제 앱에서 시스템 관리자 보안 역할을 지원합니다.
 
## <a name="use-the-bot"></a>봇 사용

앱이 설치된 후 봇이 사용자를 대신하여 수행할 수 있는 작업 유형을 알려주는 환영 메시지가 나타납니다.

> [!NOTE]
> 봇과 처음 상호 작용할 때 로그인해야 할 수 있습니다. 로그인 대화 상자가 표시되지 않으면 팝업을 허용하도록 브라우저 설정을 업데이트하세요.

봇에게 다음을 요청할 수 있습니다.

- 현재 휴가 잔액을 봅니다. 예를 들어 "휴가 잔액 보기"라는 메시지를 보냅니다.

- 사용자를 위해 휴가 요청을 시작합니다. 예를 들어 "휴가 신청"이라는 메시지를 보내거나 더 구체적인 휴가 유형으로 휴가를 요청하려면 "다음 주 목요일과 금요일에 휴가를 내고 싶습니다"라는 메시지를 보냅니다. 

  ![Teams 채팅에서 휴가 요청을 시작합니다.](./media/hr-teams-leave-app-initiate.png)

- 채팅 봇이 휴가 요청을 입력해줍니다. **휴가 요청** 을 선택하고 요청에 대한 세부 정보를 편집합니다.

   같은 날짜에 여러 휴가 유형으로 휴가 요청을 제출하려면 **추가 옵션** 메뉴에서 **날짜 분할** 옵션을 선택합니다. 

   휴가 신청 단위가 일 단위일 때 반일 휴가를 선택하면 **추가 옵션** 에서 **반일 지정** 옵션을 선택하여 전반기 반일 또는 후반기 반일을 요청할지 지정할 수 있습니다.
   
   ![반일 지정.](./media/HalfDayDefinitions.png)

- 휴가 요청 세부 정보 편집이 완료되면 승인을 위해 **제출** 을 선택하여 제출합니다.

  ![휴가 요청 제출.](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a>Teams에서 휴가 관리

**휴가** 탭에서 다음 사항을 볼 수 있습니다. 

- 등록한 각 휴가 유형에 대한 잔액 정보

- 예정된 휴가 요청

- 휴가 요청

- 휴가 요청 초안 작성
 
### <a name="create-a-new-request"></a>새 요청 만들기

1. 새 휴가 요청을 만들려면 **새 요청** 을 선택합니다.

2. 휴가를 받을 날짜를 입력하고 **추가** 를 선택합니다.

   ![Human Resources Teams 휴가 앱에서 휴가 추가.](./media/TimeOffHours.png)

3. 해당하는 경우 사유 코드를 입력합니다. 또한 설명이 있으면 입력하고 첨부 파일을 추가합니다.

4. 같은 날짜에 여러 휴가 유형으로 휴가 요청을 제출하려면 **추가 옵션** 메뉴에서 **날짜 분할** 옵션을 선택합니다.

5. **반일 지정** 옵션을 선택하여 전반기 휴가를 요청할지 후반기 휴가를 요청할 것인지 지정합니다. 이 옵션은 휴가 요청 단위가 일이고 요청 금액이 0.5일인 경우에 사용할 수 있습니다.

6. 정보 입력이 완료되면 승인을 위해 **제출** 을 입력하여 제출합니다. **초안으로 저장** 을 입력하여 나중에 다시 볼 수도 있습니다.

### <a name="manage-draft-requests"></a>초안 요청 관리

1. **초안** 탭을 선택합니다.

2. 요청을 편집하려면 연필을 선택하고 요청을 삭제하려면 휴지통을 선택합니다.

3. 필요한 사항을 변경합니다. 정보 입력이 완료되면 승인을 위해 **제출** 을 입력하여 제출합니다. **초안으로 저장** 을 선택하여 나중에 다시 볼 수도 있습니다.
   
### <a name="respond-to-teams-notifications"></a>Teams 알림에 응답

사용자 또는 사용자가 승인자인 작업자가 휴가 요청을 제출하면 Teams의 Human Resources 앱에서 알림을 받습니다. 알림을 선택하여 휴가 요청을 볼 수 있습니다. **채팅** 영역에도 알림이 나타납니다.

승인자는 알림에서 **승인** 또는 **거부** 를 선택할 수 있습니다. 선택적인 메시지를 제공할 수도 있습니다.

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a>동료에게 예정된 휴가 정보 보내기

Teams용 Human Resources 앱을 설치한 후 Teams 또는 채팅에서 동료에게 예정된 휴가에 대한 정보를 쉽게 보낼 수 있습니다.

1. Teams 또는 Teams의 채팅에서 채팅 창 아래에 있는 Human Resources 버튼을 선택합니다.

   ![채팅 창 아래 Human Resources 버튼.](./media/hr-teams-leave-app-chat-button.png)

2. 공유할 휴가 요청을 선택합니다. 초안 휴가 요청을 공유하려면 먼저 **초안** 을 선택합니다.

휴가 요청이 채팅에 표시됩니다.

초안 요청을 공유한 경우 초안으로 표시됩니다.

## <a name="view-your-teams-leave-calendar"></a>팀의 휴가 일정 보기

부하 직원이 있는 관리자인 경우 팀의 승인된 휴가와 보류 중인 휴가를 볼 수 있습니다.

1. Teams의 Human Resources 앱에서 **휴가** 를 선택합니다.

2. **팀 달력** 을 선택합니다. 달력에는 부하 직원의 승인된 휴가와 보류 중인 휴가가 표시됩니다.

   > [!NOTE]
   > 팀 일정이 표시되지 않으면 관리자에게 활성화하도록 요청하세요. 자세한 내용은 [설치 및 설정](hr-admin-teams-leave-app.md#install-and-setup)을 참조하세요.

## <a name="supported-languages"></a>지원되는 언어

Teams의 Dynamics 365 Human Resources 앱은 다음 언어를 지원합니다.

| 로케일 ID | 언어 |
| --- | --- |
| de-DE | 독일어(독일) |
| es-ES | 스페인어(스페인) |
| es-MX | 스페인어(멕시코) |
| fr-CA | 프랑스어(캐나다) |
| fr-FR | 프랑스어(프랑스) |
| it-IT | 이탈리아어(이탈리아) |
| nl-NL | 네덜란드어(네덜란드) |
| pt-BR | 포르투갈어(브라질) |
| tr-TR | 터키어(터키) |
| zh-CN | 중국어 간체 |

## <a name="troubleshooting"></a>문제 해결

Dynamics 365 Human Resources Teams 앱에 로그인하거나 사용하는 데 문제가 있는 경우 다음 문제 해결 지침을 따르세요. 문제 해결 후에도 문제가 계속되면 고객 지원팀에 문의하세요. 자세한 내용은 [지원받기](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md)를 참조하세요.

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Teams에서 Human Resources 앱에 로그인할 수 없음

앱에 로그인할 수 없는 경우 Microsoft Teams에 로그인하는 데 사용하는 계정이 Dynamics 365 Human Resources의 직원 기록과 연결되어 있지 않을 수 있습니다. 직원 기록이 올바르게 연결되었는지 확인하려면 시스템 관리자에게 문의하세요.

### <a name="cant-find-the-dynamics-365-human-resources-environment-in-settings"></a>설정에서 Dynamics 365 Human Resources 환경을 찾을 수 없음

올바른 Dynamics 365 환경을 선택할 수 없는 경우 사용자 레코드가 올바르게 동기화되지 않았을 수 있습니다. 시스템 관리자에게 사용자 레코드를 다시 만들고 사용자 자격 증명과 연결하도록 요청하세요. 그런 다음 몇 분 후에 Microsoft Teams용 Human Resources 앱에 로그인을 시도하세요.

### <a name="translations-dont-display-correctly"></a>번역이 올바르게 표시되지 않음

번역이 적절하게 표시되지 않으면 Teams에서 선택한 언어가 Human Resources **사용자 옵션** 에서 선택한 언어와 일치하는지 확인하세요.

Teams에서 **설정** 의 **앱 언어** 를 살펴보세요.

![Teams 설정.](./media/hr-teams-leave-app-settings.png)

Human Resources에서 **설정** 을 선택한 다음 **사용자 옵션** 을 선택합니다. **언어** 필드가 Teams의 **앱 언어** 필드와 일치하는지 확인합니다.

![Human Resources 사용자 옵션.](./media/hr-teams-leave-app-user-options.png)

여전히 번역 문제가 발생하면 저희에게 알려주세요. 자세한 내용은 [금융 및 운영 앱 또는 Lifecycle Services(LCS)에 대한 지원 받기](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json)를 참조하세요.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Teams의 Human Resources 앱에서 휴가 요청을 승인할 때 오류 발생

Teams 앱에서 휴가 요청을 승인하는 동안 오류가 발생하는 경우 다음 문제 해결 단계를 시도하세요.

1. Microsoft Teams에 로그인하는 데 사용하는 계정이 Dynamics 365 Human Resources에 액세스하는 데 사용하는 계정과 같은지 확인합니다.

2. 휴가 승인에 대한 워크플로 설정을 확인하여 요청에 대한 유효한 승인자인지 확인합니다. 휴가 요청 워크플로에 대한 자세한 내용은 [휴가 요청 워크플로 만들기](hr-leave-and-absence-workflow.md)를 참조하세요.

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>휴가 승인자는 휴가 요청을 승인하기 위한 Teams 채팅 메시지를 받지 않습니다.

1. 환경 및 사용자에 대해 알림이 활성화되어 있는지 확인합니다. 자세한 내용은 [Teams에서 Human Resources 앱에 대한 알림 활성화](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) 및 [개별 사용자에 대해 Teams 알림 켜거나 끄기](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users)를 참조하세요.

2. 사용자가 휴가 요청 승인에 사용하는 것과 같은 자격 증명으로 **채팅** 탭에 로그인했는지 확인합니다. "로그아웃" 메시지를 사용한 다음 "로그인"을 사용하여 올바른 자격 증명으로 로그인합니다.

3. 문제가 지속되면 시스템 관리자로 **비즈니스 이벤트 시스템** 일괄 작업의 상태를 확인하세요. **대기 중** 또는 **실행 중** 단계인 경우 몇 분 후에 다시 확인하세요. 상태가 변경되지 않으면 지원 티켓을 기록하여 당사의 팀이 문제를 해결하는 데 도움을 제공할 수 있습니다.

## <a name="known-accessibility-issues"></a>알려진 접근성 문제

Teams의 Human Resources 앱에는 향후 릴리스에서 해결하기 위해 노력하고 있는 다음과 같은 접근성 문제가 있습니다.

| 문제 | 해결 방법 또는 설명 |
| --- | --- |
| 바탕 화면에서 400%로 확대하면 일부 작업 버튼이 보기에서 숨겨집니다. | 이 확대/축소 수준을 지원할 수 있을 때까지 대신 돋보기를 사용하는 것이 좋습니다. |
| **휴가** 탭에서 VoiceOver가 휴가 그리드에 대한 헤더를 읽는 동안 버튼 동작을 알립니다. | 그리드의 헤더와 요소는 연도별로 그룹화되며 축소할 수 있습니다. VoiceOver는 이 표시를 실행 가능한 항목으로 해석하지만 그렇지 않습니다. |
| **휴가** 탭에는 새 요청에서 **사유 코드** 로 이동할 때 추가 살짝 밀기 제스처가 있습니다. | 살짝 밀기 탐색으로 이동하려는 숨겨진 컨트롤이 없습니다. |
| **휴가** 탭에서 일정이 열려 있는 동안 살짝 밀면 새 요청의 맨 위 또는 요청을 편집하는 것이 아닌 컨트롤 외부에 있게 됩니다. | **오늘로 이동** 에 도달하면 컨트롤의 끝이라고 생각하고 맨 위로 돌아가려면 반대 방향으로 살짝 미세요. |
| **채팅** 탭에서 보조 도구 또는 키보드 탐색을 사용하는 동안 날짜를 입력하면 포커스가 맨 위로 이동합니다. | 입력 영역에 다시 도달할 때까지 탭합니다. |

## <a name="privacy-notice"></a>개인정보보호 통지

### <a name="microsoft-language-understanding-intelligent-service-luis"></a>Microsoft LUIS(Language Understanding Intelligent Service)

Microsoft Teams의 Dynamics 365 Human Resources 봇을 사용하면 기본 문의/의도를 이해하기 위해 사용자의 텍스트 입력이 분석됩니다. "Contoso 검색 계정"과 같은 사용자 입력은 LUIS(Language Understanding Intelligent Service)라는 Microsoft의 Cognitive Service 중 하나로 라우팅됩니다. LUIS에 대한 자세한 내용은 [여기](https://www.luis.ai/)에서 읽어보세요. LUIS 서비스는 사용자 입력의 의도(이 경우 의도는 정보를 찾는 것)와 대상 엔터티(이 경우 의도된 엔터티는 Contoso라는 계정임)를 명확하게 하거나 이해합니다. 그런 다음 이 정보는 Microsoft의 [Azure Bot Framework](https://azure.microsoft.com/services/bot-service/)로 전달되고 Dynamics 365 Human Resources의 데이터와 상호 작용하여 사용자가 문의한 원하는 정보를 검색합니다. 

봇을 설치하고 사용할 수 있도록 허용하면 사용자가 LUIS 서비스 및 Azure Bot Framework가 입력 내용의 의도를 처리하도록 허용하여 대화형 사용자 환경을 개선하는 데 동의하는 것입니다. LUIS 서비스 및 Azure Bot Framework는 Dynamics 365 Human Resources와 비교하여 다양한 수준의 규정 준수를 가질 수 있습니다. LUIS 서비스는 사용자 문의에만 액세스할 수 있고 사용자의 Dynamics 365 Human Resources 데이터 또는 계정에 연결하도록 설계되지 않았지만 Dynamics 365 Human Resources 봇의 사용자는 고객 데이터, 개인 데이터 또는 기타 데이터가 포함된 문의를 자발적으로 입력할 수 있으며 이러한 문의 콘텐츠는 LUIS 서비스 및 Azure Bot Framework로 전송될 수 있습니다. 

사용자의 문의 및 메시지 내용은 LUIS 시스템에 최대 30일 동안 보관되며, 보관 중 암호화되며, 학습이나 서비스 개선을 위해 사용되지 않습니다. Cognitive Services에 대한 자세한 내용은 [여기](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/)에서 읽어보세요. 

Microsoft Teams에서 앱의 관리자 설정을 관리하려면 [Microsoft Teams 관리 센터](https://admin.teams.microsoft.com/)로 이동하세요.

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a>Microsoft Teams, Azure Event Grid 및 Azure Cosmos DB

Microsoft Teams에서 Dynamics 365 Human Resources 앱을 사용할 때 특정 고객 데이터가 테넌트의 Human Resources 서비스가 배포된 지리적 지역 외부로 전송될 수 있습니다.

Dynamics 365 Human Resources는 직원의 휴가 요청 및 워크플로 작업 세부 정보를 Microsoft Azure Event Grid 및 Microsoft Teams로 전송합니다. 이 데이터는 최대 24시간 동안 Microsoft Azure Event Grid에 저장될 수 있고 미국에서 처리되며 전송 및 저장 시 암호화되고 Microsoft 또는 그 하위 처리자가 학습 또는 서비스 개선을 위해 사용하지 않습니다. 데이터가 Teams에 저장되는 위치를 이해하려면 [Microsoft Teams의 데이터 위치Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide)를 참조하세요.

Human Resources 앱에서 채팅 봇과 대화하는 동안 대화 내용이 Azure Cosmos DB에 저장되고 Microsoft Teams로 전송될 수 있습니다. 이 데이터는 최대 24시간 동안 Azure Cosmos DB에 저장될 수 있고 테넌트의 Human Resources 서비스가 배포된 지리적 지역 외부에서 처리될 수 있으며 전송 및 보관 중 암호화되며 Microsoft 또는 해당 하위 처리자가 학습 및 서비스 개선을 위해 사용하지 않습니다. 데이터가 Teams에 저장되는 위치를 이해하려면 [Microsoft Teams의 데이터 위치Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide)를 참조하세요.
 
Microsoft Teams의 Human Resources 앱에 대한 조직 또는 조직 내의 사용자의 액세스를 제한하려면 [Microsoft Teams에서 앱 권한 정책 관리](/MicrosoftTeams/teams-app-permission-policies)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Microsoft Teams 다운로드 및 설치](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[Microsoft Teams 도움말 센터](https://support.office.com/teams)</br>
[Teams의 Human Resources 앱](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
