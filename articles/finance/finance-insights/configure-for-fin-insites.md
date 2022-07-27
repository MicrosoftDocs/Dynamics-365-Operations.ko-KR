---
title: Finance Insights 구성
description: 이 토픽에서는 시스템이 Finance Insights에서 사용할 수 있는 기능을 사용할 수 있도록 하는 구성 단계에 대해 설명합니다.
author: ShivamPandey-msft
ms.date: 01/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: b9bad6445e9e77688f66c6c4186422d7a898edd7
ms.sourcegitcommit: 7fc0a9a6440ac087292e9e76c26c67f56154b9e6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2022
ms.locfileid: "8451504"
---
# <a name="configuration-for-finance-insights"></a>Finance Insights 구성

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Finance insights는 Microsoft Dynamics 365 Finance의 기능을 Dataverse, Azure 및 AI Builder와 결합하여 조직에 강력한 예측 도구를 제공합니다. 이 토픽에서는 시스템이 Finance Insights에서 사용할 수 있는 기능을 사용할 수 있도록 하는 구성 단계에 대해 설명합니다. 이 토픽의 절차를 성공적으로 완료하려면 [Power Portal 관리 센터](https://admin.powerplatform.microsoft.com/)에서 시스템 관리자 및 시스템 사용자 지정자 액세스 권한, Dynamics 365 Finance에서 시스템 관리자 액세스 권한, Microsoft Dynamics LCS(Lifecycle Services)에서 환경 생성에 대한 액세스 권한이 있어야 합니다.

> [!NOTE]
> Finance Insights를 설정하기 위한 다음 절차는 Dynamics 365 Finance 버전 10.0.21 이상 버전에 유효합니다.

## <a name="deploy-dynamics-365-finance"></a>Dynamics 365 Finance 배포

환경을 배포하는 순서는 다음과 같습니다.

1. LCS에서 Dynamics 365 Finance 환경을 만들거나 업데이트합니다. 환경에는 앱 버전 10.0.21 이상이 필요합니다.

    > [!NOTE]
    > 환경은 고가용성(HA) 환경이어야 합니다. (이 유형의 환경은 Tier-2 환경이라고도 합니다.) 자세한 내용은 [환경 계획](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)을 참조하십시오.

2. 샌드박스 환경에서 Finance Insights을 구성하는 경우 예측이 작동하기 전에 프로덕션 데이터를 해당 환경에 복사해야 할 수 있습니다. 예측 모델은 예측을 구축하기 위해 다년간의 데이터를 사용합니다. Contoso 데모 데이터에는 예측 모델을 적절하게 훈련시키기에 충분한 기록 데이터가 포함되어 있지 않습니다. 

## <a name="configure-your-azure-ad-tenant"></a>Azure AD 테넌트 구성

Azure Active Directory(Azure AD)는 Dataverse 및 Microsoft Power Platform 애플리케이션과 함께 사용할 수 있도록 구성해야 합니다. 이 구성을 사용하려면 LCS의 **프로젝트 보안 역할** 필드에서 **프로젝트 소유자** 역할 또는 **환경 관리자** 역할이 사용자에게 할당되어야 합니다.

다음 설정이 완료되었는지 확인합니다.

- Power Portal 관리 센터에서 **시스템 관리자** 및 **시스템 사용자 지정자** 액세스 권한이 있습니다.
- Dynamics 365 Finance 또는 이에 상응하는 라이선스는 Finance Insights 추가 기능을 설치하는 사용자에게 적용됩니다.

Azure AD에 등록된 Azure AD 앱은 다음과 같습니다.

|  응용 프로그램                             | 앱 ID                               |
|------------------------------------------|--------------------------------------|
| Microsoft Dynamics ERP 마이크로 서비스 CDS | 703e2651-d3fc-48f5-942c-74274233dba8 |
    
## <a name="configure-dataverse"></a>Dataverse 구성

Finance insights용으로 Dataverse를 구성하려면 다음 단계를 따르십시오.

- LCS에서 환경 페이지를 열고 **Power Platform 통합** 섹션이 이미 설정되어 있는지 확인합니다.

    - Dataverse가 이미 설정되어 있으면 Finance 환경에 연결된 Dataverse 환경 이름이 나열되어야 합니다.
    - Dataverse가 아직 설정되지 않은 경우 **설정** 을 선택합니다. Dataverse 환경 설정에는 최대 1시간이 소요될 수 있습니다. 설정이 성공적으로 완료되면 Finance 환경에 연결된 Dataverse 환경 이름이 나열되어야 합니다.
    - 이 통합이 기존 Microsoft Power Platform 환경과 함께 설정된 경우 관리자에게 문의하여 연결된 환경이 비활성화된 상태가 아닌지 확인하십시오.

        자세한 내용은 [Power Platform 통합 활성화](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md)를 참조하십시오. 

        Microsoft Power Platform 관리 사이트에 액세스하려면 <https://admin.powerplatform.microsoft.com/environments>로 이동하십시오.

## <a name="configure-the-finance-insights-add-in"></a>Finance insights 추가 기능 구성

이전에 인사이트 Finance Insights 추가 기능을 설치한 경우 다음 절차를 완료하기 전에 제거하십시오.

> [!NOTE]
> LCS에 Data Lake 추가 기능을 이미 설치한 경우 Finance insights는 이를 사용하여 예측에 필요한 데이터를 저장합니다. 아직 LCS에 Data Lake 추가 기능을 설치하지 않은 경우 Finance insights 추가 기능이 관리형 Data Lake를 생성합니다.

Finance insights 추가 기능을 설치하려면 다음 단계를 따르십시오.

1. LCS에 로그인한 후, 페이지 우측의 환경 이름에서 **전체 세부 정보** 를 선택합니다.
2. **환경 추가 기능** 섹션에서 **새 추가 기능 설치** 를 선택합니다.
3. **Finance insights** 추가 기능을 선택합니다.
4. 이용약관에 동의한 후 **설치** 를 선택합니다.

추가 기능을 설치하는 데 몇 분 정도 걸릴 수 있습니다.

## <a name="one-last-thing"></a>마지막으로...

추가 기능이 성공적으로 설치된 후 Dynamics 365 Finance의 **기능 관리** 작업 영역에서 Finance insights 기능을 활성화하려면 최대 1시간이 소요될 수 있습니다. 그렇게 오래 기다리지 않으려면 **인사이트 프로비저닝 상태 확인** 프로세스를 수동으로 실행할 수 있습니다. 

1. Dynamics 365 Finance에서, **시스템 관리 \> 설정 \> 프로세스 자동화** 로 이동합니다.
2. **백그라운드 프로세스** 탭에서, **인사이트 프로비저닝 상태 확인** 을 찾고 **편집** 을 선택합니다.
3. **다음 실행** 필드를 현재 시간 30분 전으로 변경합니다.

   이렇게 변경하면 **인사이트 프로비저닝 상태 확인** 프로세스가 즉시 실행됩니다.

   **인사이트 프로비저닝 상태 확인** 프로세스가 성공적으로 실행된 후 **기능 관리** 작업 영역에서 Finance insights 기능을 활성화할 수 있습니다.

> [!NOTE]
> **인사이트 프로비저닝 상태 확인** 프로세스가 실행되지 않으면 **시스템 관리** > **문의** > **일괄 처리 작업** 으로 이동하십시오. **프로세스 자동화 폴링 시스템** 필드에서 값을 **대기 중** 으로 변경하여 프로세스를 시작합니다. 
> 
## <a name="feedback-and-support"></a>피드백 및 지원

피드백 제공에 관심이 있거나 지원이 필요한 경우 [Finance Insights(프리뷰)](mailto:fiap@microsoft.com)로 이메일을 보내주세요.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
