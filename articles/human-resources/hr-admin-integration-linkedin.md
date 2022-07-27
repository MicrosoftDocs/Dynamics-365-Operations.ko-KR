---
title: LinkedIn Talent Hub와 통합
description: Microsoft Dynamics 365 Human Resources와 LinkedIn Talent Hub 간의 통합을 설정하는 방법을 설명합니다.
author: jaredha
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fb75c391809f1ce5c7d48728a735f347ef1784ed
ms.sourcegitcommit: 696796ca5635863850ae9ef16fc1fb0fc46ce8f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/28/2021
ms.locfileid: "8451954"
---
# <a name="integrate-with-linkedin-talent-hub"></a>LinkedIn Talent Hub와 통합

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

> [!IMPORTANT]
> 이 항목에서 설명하는 Dynamics 365 Human Resources와 LinkedIn Talent Hub 간의 통합은 2021년 12월 31일에 사용 중지됩니다. 이 날짜 이후에는 더는 통합 서비스를 사용할 수 없습니다. 아직 통합 서비스를 사용하지 않는 조직은 사용 중지 전에 서비스를 구현할 수 없습니다.

[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub)는 지원자 추적 시스템(ATS) 플랫폼입니다. 한곳에서 직원을 소싱, 관리 및 고용할 수 있습니다. Microsoft Dynamics 365 Human Resources를 LinkedIn Talent Hub와 통합하면 Human Resources에서 채용된 지원자의 직원 레코드를 쉽게 만들 수 있습니다.

## <a name="setup"></a>설정

시스템 관리자는 LinkedIn Talent Hub와 통합을 위한 설정 작업을 완료해야 합니다. 먼저 Power Apps 환경에서 Human Resources에 데이터를 기록할 적절한 권한을 LinkedIn Talent Hub에 부여하기 위해 사용자 및 보안 역할을 설정해야 합니다.

### <a name="link-your-environment-to-linkedin-talent-hub"></a>LinkedIn Talent Hub에 환경 연결

1. [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub)를 엽니다.

2. 사용자 드롭다운 메뉴에서 **제품 설정** 을 선택합니다.

3. 왼쪽 탐색 창의 **고급** 섹션에서 **통합** 을 선택합니다.

4. Microsoft Dynamics 365 Human Resources 통합에 대해 **승인** 을 선택합니다.

5. **Dynamics 365 Human Resources** 페이지에서 LinkedIn Talent Hub를 연결할 환경을 선택한 후 **연결** 을 선택합니다.

    ![LinkedIn Talent Hub 온보딩.](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > 사용자 계정에 Human Resources 환경 및 연결된 Power Apps 환경 모두의 관리자 액세스 권한이 있는 환경에만 연결할 수 있습니다. Human Resources 연결 페이지에 환경이 나열되지 않으면 테넌트에 Human Resources 환경의 라이선스를 부여했는지, 연결 페이지에 로그인한 사용자에게 Human Resources 환경과 Power Apps 환경에 대한 관리자 권한이 있는지 확인합니다.

### <a name="create-a-power-apps-security-role"></a>Power Apps 보안 역할 만들기

1. [Power Platform 관리 센터](https://admin.powerplatform.microsoft.com)를 엽니다.

2. **환경** 목록에서 LinkedIn Talent Hub 인스턴스를 연결하려는 Human Resources 환경과 연결된 환경을 선택합니다.

3. **설정** 을 선택합니다.

4. **사용자 + 사용 권한** 노드를 확장하고 **보안 역할** 을 선택합니다.

5. **보안 역할** 페이지의 도구 모음에서 **새 역할** 을 선택합니다.

6. **세부 정보** 탭에서 **LinkedIn Talent Hub HRIS 통합** 과 같은 역할의 이름을 입력합니다.

7. **사용자 지정** 탭에서 다음 엔터티에 대해 조직 수준 **읽기** 권한을 선택합니다.

    - 엔터티
    - 필드
    - 관계

8. 보안 역할을 저장하고 닫습니다.

### <a name="create-a-power-apps-application-user"></a>Power Apps 애플리케이션 사용자 만들기

Power Apps 환경에 후보 레코드를 기록하기 위한 권한을 어댑터에 부여하려면 LinkedIn Talent Hub 어댑터에 대한 애플리케이션 사용자를 만들어야 합니다.

1. [Power Platform 관리 센터](https://admin.powerplatform.microsoft.com)를 엽니다.

2. **환경** 목록에서 LinkedIn Talent Hub 인스턴스를 연결하려는 Human Resources 환경과 연결된 환경을 선택합니다.

3. **설정** 을 선택합니다.

4. **사용자 + 사용 권한** 노드를 확장하고 **사용자** 를 선택합니다.

5. **Dynamics 365에서 사용자 관리** 를 선택합니다.

6. 목록 위의 드롭다운 메뉴를 사용하여 기본 **활성화된 사용자** 보기에서 **애플리케이션 사용자** 로 보기를 변경합니다.

    ![애플리케이션 사용자 보기.](./media/hr-admin-integration-power-apps-application-users.jpg)

7. 도구 모음에서 **새로 만들기** 를 선택합니다.

8. **새 사용자** 페이지에서 다음 단계를 따릅니다.

    1. **사용자 유형** 필드의 값을 **애플리케이션 사용자** 로 변경합니다.
    2. **사용자 이름** 필드를 **Dynamics365 HR LinkedIn HRIS 통합** 으로 설정합니다.
    3. **애플리케이션 ID** 필드를 **3a225c96-d62a-44ce-b3ec-bd4e8e9befef** 로 설정합니다.
    4. **이름**, **성** 및 **기본 이메일** 필드에 값을 입력합니다.
    5. 도구 모음에서 **저장 \& 종료** 를 선택합니다.

### <a name="assign-a-security-role-to-the-new-user"></a>새 사용자에게 보안 역할 할당

이전 섹션에서 새 애플리케이션 사용자를 저장하고 닫으면 **사용자 목록** 페이지로 돌아갑니다.

1. **사용자 목록** 페이지에서 보기를 **애플리케이션 사용자** 로 변경합니다.

2. 이전 섹션에서 만든 애플리케이션 사용자를 선택합니다.

3. 도구 모음에서 **역할 관리** 를 선택합니다.

4. 이전에 통합을 위해 만든 보안 역할을 선택합니다.

5. **확인** 을 선택합니다.

### <a name="add-an-azure-active-directory-app-in-human-resources"></a>Human Resources에 Azure Active Directory 앱 추가

1. Dynamics 365 Human Resources에서 **Azure Active Directory 애플리케이션** 페이지를 엽니다.
2. 목록에 새 레코드를 추가하고 다음 필드를 설정합니다.

    - **클라이언트 ID**: **3a225c96-d62a-44ce-b3ec-bd4e8e9befef** 를 입력합니다.
    - **이름**: 이전에 만든 **LinkedIn Talent Hub HRIS 통합** 과 같은 Power Apps 보안 역할의 이름을 입력합니다.
    - **사용자 ID**: 인사 관리에 데이터 쓰기 권한이 있는 사용자를 선택합니다.

### <a name="create-the-table-in-dataverse"></a>Dataverse에 테이블 만들기

> [!IMPORTANT]
> LinkedIn Talent Hub와의 통합은 Human Resources용 Dataverse의 가상 테이블에 따라 다릅니다. 설정에서 이 단계의 전제 조건으로 가상 테이블을 구성해야 합니다. 가상 테이블을 구성하는 방법에 대한 자세한 내용은 [Dataverse 가상 테이블 구성](./hr-admin-integration-common-data-service-virtual-entities.md)을 참조하세요.

1. Human Resources에서 **Dataverse 통합** 페이지를 엽니다.

2. **가상 테이블** 탭을 선택합니다.

3. 엔터티 레이블로 엔터티 목록을 필터링하여 **LinkedIn 내보낸 후보** 를 찾습니다.

4. 엔터티를 선택한 다음 **생성/새로 고침** 을 선택합니다.

## <a name="exporting-candidate-records"></a>후보 레코드 내보내기

설정이 완료되면 모집 담당자와 인사(HR) 전문가는 LinkedIn Talent Hub의 **HRIS로 내보내기** 기능을 사용하여 채용된 후보자 레코드를 LinkedIn Talent Hub에서 Human Resources로 내보낼 수 있습니다.

### <a name="export-records-from-linkedin-talent-hub"></a>LinkedIn Talent Hub에서 레코드 내보내기

후보자가 채용 프로세스를 거쳐 채용된 후 LinkedIn Talent Hub에서 Human Resources로 후보자 레코드를 내보낼 수 있습니다.

1. LinkedIn Talent Hub에서 신입 사원을 고용한 프로젝트를 엽니다.

2. 후보자 레코드를 선택합니다.

3. **상태 변경** 을 선택한 다음 **채용됨** 을 선택합니다.

4. 후보자에 대한 줄임표 메뉴(**...**)에서 **HRIS** 로 내보내기를 선택합니다.

5. **HRIS로 내보내기** 창에서 내보내야 하는 정보를 입력합니다.

    - **HRIS 공급자** 필드에서 **Microsoft Dynamics 365 Human Resources** 를 선택합니다.
    - **시작 날짜** 필드에서 신입 사원에 대한 값을 선택합니다.
    - **직책** 필드에서 신입 사원의 직책을 입력합니다.
    - **위치** 필드에 직원이 근무할 위치를 입력합니다.
    - 직원의 이메일 주소를 입력하거나 확인합니다.

![LinkedIn Talent Hub의 HRIS 창으로 내보내기.](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a>Human Resources에서 온보딩 완료

LinkedIn Talent Hub에서 인사부로 내보낸 후보자 레코드는 **인사 관리** 페이지의 **채용할 후보자** 섹션에 나타납니다.

1. In Human Resources에서 **인사 관리** 페이지를 엽니다.

2. **채용할 후보자** 섹션에서 선택된 후보자에 대해 **채용** 을 선택합니다.

3. **새 근로자 채용** 대화 상자에서 레코드를 검토하고 필요한 정보를 추가합니다. 후보자가 채용된 직위 번호를 선택할 수도 있습니다.

필수 정보를 입력한 후 직원 기록 생성 및 직원 온보딩을 위한 표준 프로세스를 계속할 수 있습니다.

다음 세부 정보를 가져오고 새 직원 레코드에 포함합니다.

- 이름
- 성
- 고용 시작 날짜
- 이메일 주소
- 전화번호

## <a name="see-also"></a>참고 항목

[Dataverse 가상 테이블 구성](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Microsoft Dataverse란?](/powerapps/maker/common-data-service/data-platform-intro)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
