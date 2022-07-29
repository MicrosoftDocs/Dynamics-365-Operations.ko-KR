---
title: "'새 사용자 생성',"
description: 사용자는 조직의 내부 직원이거나 작업을 수행하기 위해 시스템에 액세스해야 하는 외부 고객 및 공급 업체입니다.
author: peakerbl
ms.date: 01/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 480d181e8abb3af5a7406efd13c8bd9961a7490a
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8460989"
---
# <a name="create-new-users"></a>'새 사용자 생성',

[!include [banner](../../includes/banner.md)]

재무 및 운영 앱에 액세스하려면 먼저 **사용자** 페이지(**시스템 관리 \> 사용자 \> 사용자**)에 추가해야 합니다. 사용자에는 조직의 내부 직원이나 외부 고객 및 공급 업체가 포함됩니다. 사용자를 수동으로 가져오거나 추가할 수 있습니다. 모든 사용자는 규정을 준수하여 사용하려면 올바른 라이선스를 받아야 합니다.

Finance 및 Operations 앱의 구매 및 라이선스 방법에 대한 자세한 내용은 [Microsoft Dynamics 365 라이선스 가이드](https://go.microsoft.com/fwlink/?LinkId=866544&amp;clcid=0x409)를 참조하십시오.

## <a name="assign-a-license-to-a-user"></a>사용자에게 라이선스 할당
시스템 관리자는 [Microsoft 365 관리 센터](/office365/admin/admin-overview/about-the-admin-center)의 [사용자에게 라이선스를 할당](/office365/admin/subscriptions-and-billing/assign-licenses-to-users)할 수 있습니다.

## <a name="add-an-external-user-in-azure-ad-and-assign-a-license"></a>Azure AD 외부 사용자 추가 및 라이선스 할당 
외부 사용자는 라이선스를 할당받을 수 있도록 테넌트 디렉터리(Azure Active Directory(Azure AD))에 표시되어야 합니다. 이러한 외부 사용자는 게스트 사용자로 Azure AD 테넌트에 추가한 다음 적절한 라이선스를 할당해야 합니다. 재무 및 운영 앱에 대한 요구 사항은 게스트 사용자의 회사에서 Azure AD을 사용해야 한다는 것입니다. 자세한 내용은[ Azure Portal에서 Azure Active Directory B2B 공동 작업 사용자 추가](/azure/active-directory/b2b/add-users-administrator)를 참조하십시오.

## <a name="import-new-users-from-azure-ad"></a>다음에서 새 사용자 가져오기 Azure AD 
1. **시스템 관리** \> **사용자** \> **사용자** 로 이동합니다.
2. 작업 창에서 **사용자 옵션** 을 선택합니다.
3. 가져올 사용자를 선택합니다. 목록에는 현재 이 환경의 사용자가 아닌 Azure AD 사용자가 포함됩니다.
4. **사용자 가져오기** 를 선택합니다.
5. **닫기** 를 선택합니다.

> [!NOTE]
> **회사** 필드의 값은 관리자의 현재 세션 회사를 기반으로 설정됩니다. 가져온 후에는 해당하는 역할과 조직을 할당해야 합니다. 자세한 내용은 [보안 역할에 사용자 할당](assign-users-security-roles.md)을 참조하십시오. 조건부로 사용자를 사람과 연결하고 언어와 같은 **사용자** 옵션을 업데이트해야 할 수도 있습니다.

## <a name="manually-add-a-new-user"></a>수동으로 새 사용자 추가
1. **시스템 관리** \> **사용자** \> **사용자** 로 이동합니다.
2. 작업 창에서 **새로 만들기** 를 선택합니다.
3. **사용자 ID** 필드에 사용자의 고유 식별자를 입력합니다.   
4. **사용자 이름** 필드에 사용자 이름을 입력합니다.  
5. **공급자** 필드에서:
 - 내부 사용자의 경우 기본값을 사용합니다. 예를 들어 Azure AD 테넌트의 접두사가 https://sts.windows.net/.  
 - Service-2-Service 계정과 같은 비 Azure AD 사용자의 경우 기본 텍스트 값을 입력합니다. 예를 들어, NA. 이 값은 유효한 ID 공급자 값이 사용되는 경우 오류가 발생할 수 있는 잘못된 인증 호출을 방지하는 데 도움이 됩니다.  
 - 외부 또는 게스트 사용자의 경우 Azure AD 테넌트 이름을 https://sts.windows.net/ 뒤에 추가합니다.
6. **이메일** 필드에 사용자의 전체 이메일/사용자 원칙 이름을 입력합니다.  
7. **회사** 필드에서 사용자의 기본 시작 회사를 선택하십시오. 
8. **저장** 을 선택합니다.

ID 공급자 및 원격 분석 ID 값은 사용자 기록이 저장될 때 [Microsoft 그래프](/graph/overview) 호출을 기반으로 업데이트됩니다. 원격 분석 ID는 Azure AD에 있는 사용자의 개체 ID/SID(보안 식별자)를 기반으로 합니다.

> [!NOTE]
> 사용자를 추가한 후 해당하는 역할과 조직을 할당해야 합니다. 자세한 내용은 [보안 역할에 사용자 할당](assign-users-security-roles.md)을 참조하십시오. 조건부로 사용자를 **사람** 과 연결하고 언어와 같은 **사용자 옵션** 을 업데이트해야 할 수도 있습니다.

## <a name="change-a-user-id"></a>사용자 ID 변경
사용자 ID를 변경하려면 데이터베이스에서 키의 이름을 변경해야 합니다. 이 절차를 사용하여 사용자 ID를 변경하면 모든 관련 사용자 설정이 새 사용자 ID를 사용하도록 수정됩니다. 예를 들어, **SysLastValue** 테이블의 사용 정보는 새 사용자 ID를 참조하도록 업데이트됩니다.

> [!NOTE]
> 사용자 ID는 사용자 정보 테이블의 기본 키입니다. 키에 대한 모든 참조도 데이터베이스에서 업데이트되기 때문에 기존 사용자의 경우 기본 키의 이름을 바꾸는 데 시간이 걸릴 수 있습니다. 

1. **시스템 관리 \> 사용자 \> 사용자** 로 이동합니다.
2. 목록에서 사용자를 선택하고 **옵션\> 기록 정보** 를 선택합니다.
3. **이름 바꾸기** 를 선택합니다.
4. 사용자 ID에 대해 새롭고 고유한 값을 입력한 다음 **확인** 을 선택합니다. 
5. **예** 를 선택하여 확인합니다.

## <a name="additional-resources"></a>추가 리소스

B2B 사용자를 구현하는 추가 옵션은 [B2B 사용자를 Azure AD로 내보내기](../implement-b2b.md)를 참조하십시오.

미리 구성된 시스템 계정에 대한 자세한 내용은 [미리 구성된 시스템 계정](../pre-configured-system-accounts.md)을 참조하십시오.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]