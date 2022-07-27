---
title: Dataverse 가상 테이블 구성
description: 이 항목에서는 기존 가상 테이블을 구성, 생성, 업데이트하고 Dynamics 365 Human Resources를 위해 생성 및 사용 가능한 테이블을 분석하는 방법을 보여줍니다.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f7ffe522f0f17a21280e53728c6efc2823743733
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452527"
---
# <a name="configure-dataverse-virtual-tables"></a>Dataverse 가상 테이블 구성


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Dynamics 365 Human Resources는 Microsoft Dataverse의 가상 데이터 원본입니다. Dataverse 및 Microsoft Power Platform에서 전체 생성, 읽기, 업데이트 및 삭제(CRUD) 작업을 제공합니다. 가상 테이블의 데이터는 Dataverse에 저장되지 않고 애플리케이션 데이터베이스에 저장됩니다.

Dataverse의 Human Resources 엔터티에 대한 CRUD 작업을 활성화하려면 Dataverse에서 엔터티를 가상 테이블로 사용할 수 있도록 해야 합니다. 이를 통해 Human Resources에 있는 데이터에 대해 Dataverse 및 Microsoft Power Platform에서 CRUD 작업을 수행할 수 있습니다. 작업은 또한 엔터티에 데이터를 쓸 때 데이터 무결성을 보장하기 위해 Human Resources의 전체 비즈니스 논리 유효성 검사를 지원합니다.

> [!NOTE]
> Human Resources 엔터티는 Dataverse 테이블에 해당합니다. Dataverse(이전의 Common Data Service) 및 용어 업데이트에 대한 자세한 내용은 [Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)을 참조하세요.

## <a name="available-virtual-tables-for-human-resources"></a>사용 가능한 Human Resources의 가상 테이블

Human Resources의 모든 OData(Open Data Protocol) 엔터티는 Dataverse에서 가상 테이블로 사용할 수 있습니다. Power Platform에서도 사용할 수 있습니다. 이제 데이터를 Dataverse에 복사하거나 동기화하지 않고도 완전한 CRUD 기능으로 Human Resources에서 직접 데이터를 사용하여 앱과 환경을 구축할 수 있습니다. Power Apps 포털을 사용하여 Human Resources의 비즈니스 프로세스의 공동 작업 시나리오를 가능하게 하는 외부 웹 사이트를 구축할 수 있습니다.

환경에 활성화된 가상 테이블 목록을 확인하고 **Dynamics 365 HR Virtual Tables** 솔루션의 [Power Apps](https://make.powerapps.com)에서 테이블 작업을 시작할 수 있습니다.

![Power Apps의 Dynamics 365 Virtual Tables 가상 테이블.](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a>가상 테이블 대 기본 테이블

Human Resources의 가상 테이블은 Human Resources를 위해 생성된 기본 Dataverse 테이블과는 다릅니다. 

Human Resources의 기본 테이블은 별도로 생성되고 Dataverse의 HCM 공통 솔루션에서 유지 관리됩니다. 기본 테이블을 사용하면 데이터가 Dataverse에 저장되며 Human Resources 애플리케이션 데이터베이스와 동기화해야 합니다.

> [!NOTE]
> Human Resource의 기본 Dataverse 테이블 목록은 [Dataverse 테이블](./hr-developer-entities.md)을 참조하세요.

## <a name="setup"></a>설정

환경에서 가상 테이블을 활성화하려면 다음 설정 단계를 따르세요.

### <a name="enable-virtual-tables-in-human-resources"></a>Human Resources에서 가상 테이블 활성화

먼저 **기능 관리** 작업 영역에서 가상 테이블을 활성화해야 합니다.

1. Human Resources에서 **시스템 관리** 를 선택합니다.

2. **기능 관리** 타일을 선택합니다.

3. **Dataverse에서 HR을 위한 가상 테이블 지원** 을 선택하고 **활성화** 를 선택합니다.

기능의 활성화 및 비활성화에 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

### <a name="register-the-app-in-microsoft-azure"></a>Microsoft Azure에 앱 등록

Microsoft ID 플랫폼이 앱과 사용자에 인증 및 권한 부여 서비스를 제공할 수 있도록 Azure Portal에 Human Resources 인스턴스를 등록해야 합니다. Azure에 앱을 등록하는 방법에 대한 자세한 내용은 [빠른 시작: Microsoft ID 플랫폼에 애플리케이션 등록](/azure/active-directory/develop/quickstart-register-app)을 참조하세요.

1. [Microsoft Azure 포털](https://portal.azure.com)을 엽니다.

2. Azure 서비스 목록에서 **앱 등록** 을 선택합니다.

3. **신규 등록** 을 선택합니다.

4. **이름** 필드에 앱을 설명하는 이름을 입력합니다. 예를 들어 **Dynamics 365 Human Resources 가상 테이블** 을 입력합니다.

5. **리디렉션 URI** 필드에 Human Resources 인스턴스의 네임스페이스 URL을 입력합니다.

6. **등록** 을 선택합니다.

7. 등록이 완료되면 Azure Portal은 **애플리케이션(클라이언트) ID** 가 포함된 앱 등록의 **개요** 창을 표시합니다. 이때 **애플리케이션(클라이언트) ID** 를 기록해 둡니다. 이 정보는 [가상 테이블 데이터 원본을 구성할 때](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source) 입력해야 합니다.

8. 왼쪽 탐색 창에서 **인증서 및 비밀** 을 선택합니다.

9. 페이지의 **클라이언트 비밀** 섹션에서 **새 클라이언트 비밀** 을 선택합니다.

10. 설명을 제공하고 기간을 선택한 다음 **추가** 를 선택합니다.

11. 테이블의 **값** 속성에서 비밀 값을 기록해 둡니다. 이 정보는 [가상 테이블 데이터 원본을 구성할 때](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source) 입력해야 합니다.

    > [!IMPORTANT]
    > 이때 비밀의 값을 기록해 둡니다. 이 페이지를 닫으면 다시는 비밀이 표시되지 않습니다.

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a>Dynamics 365 HR Virtual Table 앱 설치

Dataverse에 가상 테이블 솔루션을 배포하려면 Power Apps 환경에 Dynamics 365 HR Virtual Table 앱을 설치합니다.

1. Human Resources에서 **Microsoft Dataverse 통합** 페이지를 엽니다.

2. **가상 테이블** 탭을 선택합니다.

3. **Virtual Table 앱 설치** 를 선택합니다.

### <a name="configure-the-virtual-table-data-source"></a>가상 테이블 데이터 원본 구성

다음 단계에서는 Power Apps 환경에서 가상 테이블 데이터 원본을 구성해야 합니다.

1. [Power Platform 관리 센터](https://admin.powerplatform.microsoft.com)를 엽니다.

2. **환경** 목록에서 Human Resources 인스턴스와 연결된 Power Apps 환경을 선택합니다.

3. 페이지의 **세부 정보** 섹션에서 **환경 URL** 을 선택합니다.

4. **솔루션 상태 허브** 에서 애플리케이션 페이지 오른쪽 상단의 **고급 찾기** 아이콘을 선택합니다.

5. **고급 찾기** 페이지의 **찾을 대상** 드롭다운 목록에서 **금융 및 운영 가상 데이터 원본 구성** 을 선택합니다.

   > [!NOTE]
   > 이전 설정 단계에서 Virtual Table 앱을 설치하는 데 몇 분이 소요될 수 있습니다. 목록에 **금융 및 운영 가상 데이터 원본 구성** 이 없으면 잠시 기다렸다가 목록을 새로 고칩니다.

6. **결과** 를 선택합니다.

7. **Microsoft HR 데이터 원본** 레코드를 선택합니다.

8. 데이터 원본 구성에 필요한 정보를 입력합니다.

   - **대상 URL**: Human Resources 네임스페이스의 URL. 대상 URL의 형식은 다음과 같습니다.
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     예:
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >URL 끝에 "**/**" 문자를 포함해야 오류가 발생하지 않습니다.

     >[!NOTE]
     >대상 URL은 가상 테이블이 데이터를 위해 가리킬 Human Resources 환경을 결정합니다. 프로덕션 환경의 복사본을 만들어 샌드박스 환경을 만드는 경우 이 값을 새 샌드박스 환경의 네임스페이스 URL로 업데이트합니다. 이렇게 하면 가상 테이블이 프로덕션 환경을 계속 가리키지 않고 샌드박스 환경 데이터를 연결합니다.

   - **테넌트 ID**: Azure Active Directory(Azure AD) 테넌트 ID.

   - **AAD 애플리케이션 ID**: Microsoft Azure Portal에 등록된 애플리케이션을 위해 생성된 애플리케이션(클라이언트) ID. 이 정보는 이전의 [Microsoft Azure에서 앱 등록](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) 단계에서 얻었습니다.

   - **AAD 애플리케이션 비밀**: Microsoft Azure Portal에 등록된 애플리케이션을 위해 생성된 클라이언트 비밀. 이 정보는 이전의 [Microsoft Azure에서 앱 등록](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure) 단계에서 얻었습니다.

   ![Microsoft HR 데이터 원본.](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. **저장 및 닫기** 를 선택합니다.

### <a name="grant-app-permissions-in-human-resources"></a>Human Resources에서 앱 권한 부여

Human Resources의 두 Azure AD 애플리케이션에 대한 권한을 부여합니다.

- Microsoft Azure Portal에서 테넌트를 위해 만든 앱
- Power Apps 환경에 설치된 Dynamics 365 HR Virtual Table 앱 

1. Human Resources에서 **Azure Active Directory 애플리케이션** 페이지를 엽니다.

2. **새로 만들기** 를 선택하여 새 애플리케이션 레코드를 만듭니다.

    - **클라이언트 ID** 필드에 Microsoft Azure 포털에 등록한 앱의 클라이언트 ID를 입력합니다.
    - **이름** 필드에 Microsoft Azure 포털에 등록한 앱의 이름을 입력합니다.
    - **사용자 ID** 필드에서 Human Resources 및 Power Apps 환경의 관리자 권한이 있는 사용자의 사용자 ID를 선택합니다.

3. **새로 만들기** 를 선택하여 두 번째 애플리케이션 레코드를 만듭니다.

    - **클라이언트 ID**: f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **이름**: Dynamics 365 HR Virtual Table
    - **사용자 ID** 필드에서 Human Resources 및 Power Apps 환경의 관리자 권한이 있는 사용자의 사용자 ID를 선택합니다.

## <a name="generate-virtual-tables"></a>가상 테이블 생성

설정이 완료되면 생성하려는 가상 테이블을 선택하고 Dataverse 인스턴스에서 활성화할 수 있습니다.

1. Human Resources에서 **Microsoft Dataverse 통합** 페이지를 엽니다.

2. **가상 테이블** 탭을 선택합니다.

> [!NOTE]
> 필요한 모든 설정을 완료하면 **가상 테이블 활성화** 토글이 자동으로 **예** 로 설정됩니다. 토글이 **아니요** 로 설정된 경우 이 문서에서 이전 섹션에 나온 단계를 검토하여 모든 전제 조건 설정이 완료되었는지 확인합니다.

3. Dataverse에서 생성할 테이블을 선택합니다.

4. **생성/새로 고침** 을 선택합니다.

![Dataverse 통합.](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a>테이블 생성 상태 확인

가상 테이블은 비동기 백그라운드 프로세스를 통해 Dataverse에서 생성됩니다. 프로세스에 대한 업데이트는 작업 센터에 표시됩니다. 오류 로그를 포함한 프로세스에 대한 세부 정보는 **프로세스 자동화** 페이지에 나타납니다.

1. Human Resources에서 **프로세스 자동화** 페이지를 엽니다.

2. **백그라운드 프로세스** 탭을 선택합니다.

3. **가상 테이블 폴링 비동기 작업 백그라운드 프로세스** 를 선택합니다.

4. **가장 최근 결과 보기** 를 선택합니다.

슬라이드아웃 창에 프로세스에 대한 가장 최근 실행 결과가 표시됩니다. Dataverse에서 반환된 오류를 포함하여 프로세스에 대한 로그를 볼 수 있습니다.

## <a name="see-also"></a>참고 항목

[Dataverse란?](/powerapps/maker/common-data-service/data-platform-intro)<br>
[Dataverse의 테이블](/powerapps/maker/common-data-service/entity-overview)<br>
[테이블 관계 개요](/powerapps/maker/common-data-service/relationships-overview)<br>
[외부 데이터 원본의 데이터가 포함된 가상 테이블 만들기 및 편집](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[Power Apps 포털이란?](/powerapps/maker/portals/overview)<br>
[Power Apps에서 앱 만들기 개요](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
