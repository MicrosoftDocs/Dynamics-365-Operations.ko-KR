---
title: Teams의 Human Resources 앱
description: 이 항목에서는 Microsoft Teams의 Microsoft Dynamics 365 Human Resources 앱을 소개합니다.
author: twheeloc
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ffd6967431227b578e227ee570dbe06c356fb8d6
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452302"
---
# <a name="human-resources-app-in-teams"></a>Teams의 Human Resources 앱


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Teams의 Microsoft Dynamics 365 Human Resources 앱을 사용하면 직원이 Microsoft Teams에서 신속하게 휴가를 요청하고 남은 휴가 일수 정보를 볼 수 있습니다. 직원은 봇과 상호 작용하여 정보를 요청할 수 있습니다. **휴가** 탭에는 자세한 정보가 표시됩니다. 또한 Human Resources 앱 외부에서 팀 및 채팅의 예정된 시간에 대한 정보를 사람들에게 보낼 수 있습니다.

![Human Resources Teams 휴가 앱 봇.](./media/hr-teams-leave-app-bot.png)

![Human Resources Teams 휴가 앱 휴가 탭.](./media/hr-teams-leave-app-timeoff-tab.png)

![Human Resources 휴가 요청 카드.](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a>설치 및 설정

Dynamics 365 Human Resources 앱은 Teams 스토어에서 찾을 수 있습니다. Teams 앱 설치에 대한 자세한 내용은 [Teams에서 휴가 요청 관리](hr-teams-leave-app.md)를 참조하세요.

Teams에서 앱 권한 관리에 대한 자세한 내용은 [Microsoft Teams에서 앱 권한 정책 관리](/MicrosoftTeams/teams-app-permission-policies)를 참조하세요.

사용자가 앱에서 휴가 및 휴무 일정을 보도록 하려면 기능 관리에서 **Teams의 휴가 및 휴무 일정** 을 활성화해야 합니다. 기능의 활성화에 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

## <a name="update-app"></a>앱 업데이트
>[!NOTE]
> 2021년 12월 20일부터 Microsoft 테넌트에서 호스팅되는 Human Resources 앱 봇 서비스가 서비스 해제됩니다. 설치할 수 있는 최신 확장(버전 1.1.5)에는 영향이 없습니다. 주요 영향은 오래된 확장(버전 1.1.4)에 있습니다. 이 버전의 채팅 봇은 작동을 멈춥니다. **휴가** 탭은 두 확장 모두에서 계속 작동합니다.

버전 1.1.4의 경우 채팅 봇은 모든 메시지에 응답하지 않습니다. 예를 들어 **로그인**, **남은 일수** 및 **휴가 보기** 가 있습니다. 앱을 수동으로 최신 버전으로 업데이트해야 합니다. 자세한 내용은 [Microsoft Teams에서 앱 업데이트](/MicrosoftTeams/apps-update-experience)를 참조하세요.

버전 1.1.5로 업데이트하려면 다음 단계를 완료합니다.
1. Microsoft Teams에서 **앱** 으로 이동합니다.
2. **Human Resources** 앱을 찾습니다.
3. **업그레이드** 를 선택합니다.

**정보** 탭으로 이동하거나 **개인 앱** 섹션으로 이동하여 Human Resources 앱의 버전을 확인할 수 있습니다. 

![Human Resources **정보** 탭.](./media/HR-teams-about.png)

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a>Teams에서 Human Resources 앱에 대한 알림 활성화

사용자가 Teams 앱에서 휴가 요청 알림을 받을 수 있게 하려면 Dynamics 365 Human Resources에서 알림을 활성화해야 합니다.

>[!NOTE]
>Teams에 로그인하고 Dynamics 365 Human Resources 앱을 사용하는 사용자만 알림을 받습니다.

1. Human Resources에서 **시스템 관리** 를 선택합니다.

2. **연결** 을 선택합니다.

3. **설정** 에서 **시스템 매개 변수** 를 선택합니다.

4. **일반** 탭에서 **Teams 앱에 대한 알림 사용** 을 **예** 로 설정합니다.

   ![시스템 매개 변수에서 Teams 앱 알림을 활성화.](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. 모든 사용자에 대해 Teams 알림을 켜려면 표시되는 메시지에서 **예** 를 선택합니다.

   ![모든 사용자에 대해 Teams 알림 활성화.](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a>개별 사용자에 대해 Teams 알림 켜거나 끄기

Dynamics 365 Human Resources Teams 앱에 대한 알림을 활성화한 후 개별 사용자에 대한 알림을 켜거나 끌 수 있습니다.

1. Human Resources에서 **시스템 관리** 를 선택합니다.

2. **연결** 을 선택합니다.

3. **사용자** 에서 **사용자 옵션** 을 선택합니다.

4. **워크플로** 탭을 선택합니다.

5. **Teams 앱에 대한 알림 활성화** 를 **예** 로 설정하여 사용자에 대한 알림을 활성화하거나 **아니요** 로 설정하여 사용자에 대한 알림을 비활성화합니다.

   ![사용자 옵션의 워크플로 탭에서 Teams 앱 알림 활성화.](./media/hr-admin-teams-leave-app-notifications.png)

6. **저장** 을 선택합니다.

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

## <a name="notes"></a>메모

다음 작업 항목은 향후 릴리스로 예정되어 있습니다.

| 작업 항목 | 상태 |
| --- | --- |
| 미래 날짜로 휴가를 제출할 때 남은 일수가 잘못되었습니다. | 아직 예측할 수 없습니다. 현재 날짜에 대한 남은 일수가 표시됩니다. |
| **검토 중** 요청을 취소할 수 없습니다. | 이 기능은 현재 지원되지 않으며 향후 릴리스에 추가될 예정입니다. |
| 남은 일수 정보는 오늘 기준으로 계산됩니다. | 시스템은 현재 **휴가 및 휴무 매개 변수** 페이지에서 구성된 경우에도 적립 기간을 기준으로 남은 일수를 표시하지 않습니다. |

## <a name="troubleshooting"></a>문제 해결

사용자가 Human Resources Teams 앱에 로그인하거나 사용하는 데 문제가 있는 경우 다음 문제 해결 지침을 따르세요. 문제 해결 후에도 문제가 계속되면 고객 지원팀에 문의하세요. 자세한 내용은 [지원받기](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md)를 참조하세요.

### <a name="ensure-the-teams-human-resources-application-is-up-to-date"></a>Teams Human Resources 애플리케이션이 최신 상태인지 확인합니다.
Teams Human Resources 앱에 문제가 발생하면 최신 버전을 실행하고 있는지 확인해야 합니다. 지원되는 최소 버전은 1.1.5입니다. Teams 애플리케이션을 업데이트하는 방법에 대한 지침은 [Teams 설명서](/MicrosoftTeams/apps-update-experience)를 참조하세요.

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a>Teams에서 Human Resources 앱에 로그인할 수 없음

사용자가 앱에 로그인할 수 없다고 문의하는 경우 Human Resources에 연결된 직원 레코드가 있는지 확인하세요.

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a>Teams의 Human Resources 앱에서 휴가 요청을 승인할 때 오류 발생

사용자가 Teams 앱에서 휴가 요청을 승인하는 동안 오류가 발생하는 경우 다음 문제 해결 단계를 시도하세요.

1. Teams 계정이 Human Resources에 액세스하는 데 사용하는 계정과 같은지 확인합니다.

2. 휴가 승인에 대한 워크플로 설정을 확인하여 요청에 대한 유효한 승인자인지 확인합니다. 휴가 요청 워크플로에 대한 자세한 내용은 [휴가 요청 워크플로 만들기](hr-leave-and-absence-workflow.md)를 참조하세요.

### <a name="leave-approvers-dont-receive-teams-chat-messages-to-approve-leave-requests"></a>휴가 승인자는 휴가 요청을 승인하기 위한 Teams 채팅 메시지를 받지 않습니다.

1. 환경 및 사용자에 대해 알림이 활성화되어 있는지 확인합니다. 자세한 내용은 [Teams에서 Human Resources 앱에 대한 알림 활성화](hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) 및 [개별 사용자에 대해 Teams 알림 켜거나 끄기](hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users)를 참조하세요.

2. 사용자가 휴가 요청 승인에 사용하는 것과 같은 자격 증명으로 **채팅** 탭에 로그인했는지 확인합니다. "로그아웃" 메시지를 사용한 다음 "로그인"을 사용하여 올바른 자격 증명으로 로그인합니다.

3. 문제가 지속되면 시스템 관리자로 **비즈니스 이벤트 시스템** 일괄 작업의 상태를 확인하세요. **대기 중** 또는 **실행 중** 단계인 경우 몇 분 후에 다시 확인하세요. 상태가 변경되지 않으면 지원 티켓을 기록하여 당사의 팀이 문제를 해결하는 데 도움을 제공할 수 있습니다.

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
[Teams에서 휴가 요청 관리](hr-teams-leave-app.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
