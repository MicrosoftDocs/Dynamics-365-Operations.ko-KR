---
title: ATS 통합 API를 위한 서버 간 인증
description: 이 항목에서는 Dynamics 365 Human Resources 지원자 추적 시스템(ATS) 통합 API에 대한 통합을 위해 서버 간 인증을 설정하는 방법을 설명합니다.
author: jaredha
ms.date: 06/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d221e1a47dca85880fd683177ca95dd1b7766fb9
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452077"
---
# <a name="server-to-server-authentication-for-the-ats-integration-api"></a>ATS 통합 API를 위한 서버 간 인증


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources 지원자 추적 시스템(ATS) 통합 API에 대한 애플리케이션 통합을 위해 서버 간 인증을 설정하는 방법을 설명합니다. 서비스 주체가 Microsoft Dataverse 가상 테이블 및 관련 데이터에 액세스할 수 있도록 하려면 몇 가지 보안 계층을 관리해야 합니다. 사용자는 Microsoft Power Platform의 Dataverse 가상 테이블에 대한 액세스 권한과 Dynamics 365 Human Resources의 데이터에 대한 액세스 권한을 부여받아야 합니다.

## <a name="enable-access-to-dataverse-virtual-tables-in-power-platform"></a>Power Platform의 Dataverse 가상 테이블에 대한 액세스 활성화

Power Platform에서 Dataverse 가상 테이블에 대한 액세스를 활성화하는 첫 번째 단계는 Dataverse 가상 테이블 엔드포인트에 대한 인증을 위해 Power Platform에서 애플리케이션을 설정하는 것입니다. 이를 수행하는 단계는 [Microsoft Dataverse 개발자 가이드](/powerapps/developer/data-platform)에 설명되어 있습니다.

  - 단일 테넌트 앱 등록: [단일 테넌트 서버 간 인증 사용](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication)
  - 다중 테넌트 앱 등록: [다중 테넌트 서버 간 인증 사용](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication)

### <a name="creating-a-security-role-for-ats-integrations"></a>ATS 통합을 위한 보안 역할 생성

애플리케이션 사용자를 생성한 후의 단계 중 하나는 사용자를 엔드포인트에 대한 애플리케이션의 액세스 권한을 정의하는 보안 역할에 할당하는 것입니다. 이 과정은 단일 테넌트 앱 등록의 경우 [애플리케이션 사용자 만들기](/powerapps/developer/data-platform/use-single-tenant-server-server-authentication#application-user-creation), 다중 테넌트 등록의 경우 [애플리케이션 사용자의 보안 역할 만들기](/powerapps/developer/data-platform/use-multi-tenant-server-server-authentication#create-a-security-role-for-the-application-user)의 7단계입니다. 

애플리케이션 사용자를 할당하는 역할에는 ATS 통합에 사용되는 데이터 엔터티에 대한 액세스 권한이 있어야 합니다. 이는 기본적으로 존재하지 않으므로 새 보안 역할을 만들어야 합니다. 새 역할은 [보안 역할 만들기](/power-platform/admin/create-edit-security-role#create-a-security-role)에 설명된 단계에 따라 만들 수 있습니다.

새 역할에 대해서는 최소한 새 역할의 **사용자 지정 엔터티** 탭에서 다음 엔터티에 적절한 액세스 권한을 할당해야 합니다. 통합에 더 광범위한 애플리케이션 데이터가 사용되는 경우 추가 엔터티가 필요할 수 있습니다. 새 역할이 생성된 후 애플리케이션 사용자에게 할당할 수 있습니다.

  - 기본 근로자(mshr)
  - 채용할 후보자(mshr)
  - 인증서 역량(mshr)
  - 인증서 유형(mshr)
  - 회사
  - 보상 직무 기능(mshr)
  - 보상 직무 유형(mshr)
  - 국가/지역(mshr)
  - 부서(mshr)
  - 교육 역량(mshr)
  - 교육 학위(mshr)
  - 교육 학과(mshr)
  - 학력 요구 사항(mshr)
  - 식별(mshr)
  - 식별 유형(mshr)
  - 기관(mshr)
  - 발급 기관(mshr)
  - 직무 보상(mshr)
  - 직무(mshr)
  - 교육 수준(mshr)
  - 당사자 연락처(mshr)
  - 개인(mshr)
  - 개인 주소(mshr)
  - 개인 심사(mshr)
  - 직위 유형(mshr)
  - 직위 V2(mshr)
  - 전문 경험 역량(mshr)
  - 등급 수준(mshr)
  - 등급 모델(mshr)
  - 이유 코드(mshr)
  - 모집 요청(mshr)
  - 모집 요청 위치(mshr)
  - 모집 요청 직위(mshr)
  - 모집 요청 기술(mshr)
  - 심사 유형(mshr)
  - 기술 역량(mshr)
  - 기술(mshr)
  - 직함(mshr)
  - 재향 군인 신분(mshr)
  - 근로자(mshr)

## <a name="granting-application-permissions-to-human-resources-data"></a>Human Resources 데이터에 애플리케이션 권한 부여

두 번째 단계는 Human Resources 애플리케이션의 사용자를 연결하여 애플리케이션에 Human Resources의 데이터에 대한 적절한 사용 권한이 부여되도록 하는 것입니다. 애플리케이션 사용자의 경우 Dataverse 가상 테이블을 통한 서버 간 호출은 작업을 호출하는 Dataverse의 사용자(앱) ID 컨텍스트에서 수행됩니다. 그러면 가상 테이블 어댑터 서비스가 Human Resources에서 연결된 사용자를 조회하고 해당 사용자의 컨텍스트에서 쿼리를 실행합니다. 이는 통합 애플리케이션에 필요한 데이터에 대한 액세스를 제공하려면 Human Resources에서 올바른 역할이 할당된 사용자를 만들어야 한다는 의미입니다.

Human Resources 사용자에게는 Human Resources의 데이터에 대한 올바른 사용 권한도 할당해야 합니다. **모집 지원**(HcmRecruitingIntegrator) 역할은 모집 데이터를 통합하는 데 필요한 기본 엔터티에 대한 권한으로 사용할 수 있습니다. 데이터에 대한 적절한 액세스 권한을 부여하기 위해 **사용자** 페이지에서 이 역할을 애플리케이션 사용자에게 할당할 수 있습니다. Human Resources 보안 역할에 관한 자세한 내용은 [역할 기반 보안](/fin-ops-core/dev-itpro/sysadmin/role-based-security)을 참조하세요.

### <a name="set-up-the-new-user-with-appropriate-permissions"></a>적절한 사용 권한을 가진 새 사용자 설정

다음 단계에 따라 적절한 사용 권한을 가진 새 사용자를 설정합니다.

  1. Human Resources에서 **사용자** 페이지를 열고 **새로 만들기** 를 선택합니다.
  2. 새 애플리케이션 사용자의 **사용자 ID** 및 **사용자 이름** 을 입력합니다. 예를 들어 "RecruitingIntegration"을 입력할 수 있습니다.

      > [!NOTE]
      > 앱에 Microsoft Azure Active Directory(Azure AD) 사용자 계정 또는 이메일 주소가 없는 경우 사용자의 이메일 주소 및 공급자 필드에 "RecruitingApp"과 같은 항목을 입력할 수 있습니다.

  3. **사용자의 역할** 빠른 탭에서 **역할 할당** 작업을 선택합니다.
  4. **사용자에게 역할 할당** 페이지에서 **모집 지원** 을 선택하고 **확인** 을 선택합니다.
  5. 새 사용자 레코드를 저장합니다.

### <a name="link-the-new-human-resources-user-to-the-application"></a>새 Human Resources 사용자를 애플리케이션에 연결

사용자가 생성된 후 **Azure Active Directory 애플리케이션** 양식에서 애플리케이션에 대한 레코드를 생성하여 앱을 Human Resources 사용자에게 연결해야 합니다.

  1. **Azure Active Directory 애플리케이션** 양식을 열고 **새로 만들기** 를 선택합니다.
  2. **클라이언트 ID** 필드에 애플리케이션에 대해 생성된 애플리케이션 사용자의 클라이언트 ID를 입력합니다.
  3. **이름** 필드에 통합 애플리케이션의 이름을 입력합니다.
  4. **사용자 ID** 필드에서 모집 통합을 위해 만든 새 Human Resources 사용자를 선택합니다.
  5. 새 레코드를 저장합니다.

그러면 애플리케이션은 모집 지원 통합에 필요한 데이터로 제한되는 Human Resources 데이터에 액세스할 수 있습니다.

## <a name="see-also"></a>참고 항목

[구직 후보자 모집](hr-personnel-recruit.md)<br>
[Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Microsoft Dataverse 웹 API 사용](/powerapps/developer/data-platform/webapi/overview)<br>
[웹 API를 사용하여 옵션 집합 만들기 및 업데이트](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
