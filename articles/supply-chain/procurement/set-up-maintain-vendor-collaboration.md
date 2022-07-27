---
title: 공급업체 협업 설정 및 유지 관리
description: 이 토픽에서는 Dynamics 365 Supply Chain Management에서 공급업체 협업을 설정하는 방법에 대해 설명합니다. 또한 새로운 공급업체 협업 사용자를 프로비저닝하고 해당 사용자의 보안 역할을 관리하는 방법에 대해서도 설명합니다.
author: Henrikan
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirExternalRole, SysUserRequestListPage, VendVendorPortalUsers, WorkflowTableListPageRnr
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 220774
ms.assetid: 69d05e8b-7dc2-48ea-bc24-bea9ac963579
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b635255fffa6fd3c6612cd248dc692df204aa76d
ms.sourcegitcommit: 614d79cba238e466d445767a7d0a012e785a9861
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "8449395"
---
# <a name="set-up-and-maintain-vendor-collaboration"></a>공급업체 협업 설정 및 유지 관리

[!include [banner](../includes/banner.md)]

공급업체 협업 인터페이스는 구매 주문, 송장 및 위탁 재고에 대한 제한된 정보 집합을 외부 공급업체 사용자에게 제공합니다. 이 인터페이스에서 공급업체는 견적 요청(RFQ)에 응답하고 기본 회사 정보를 보고 편집할 수도 있습니다.

이 토픽에서는 Dynamics 365 Supply Chain Management에서 공급업체 협업을 설정하는 방법에 대해 설명합니다. 또한 새로운 공급업체 협업 사용자를 프로비저닝하기 위해 워크플로를 설정하는 방법과 해당 사용자에 대한 보안 역할을 관리하는 방법에 대해서도 설명합니다.

> [!NOTE]
> 공급업체 협업을 위한 보안 역할 설정에 대한 정보는 현재 버전의 재무 및 운영에만 적용됩니다. Microsoft Dynamics AX 7.0(2016년 2월) 및 Microsoft Dynamics AX 애플리케이션 버전 7.0.1(2016년 5월)에서는 **벤더 포털** 모듈을 사용하여 벤더와 협업합니다. Microsoft Dynamics AX의 벤더 포털에 대한 사용자 권한에 대한 정보는 [벤더 포털 사용자 보안](configure-security-vendor-portal-users.md)을 참조하세요.

## <a name="set-up-vendor-collaboration-security-roles"></a>공급업체 협업 보안 역할 설정

조달 전문가 또는 충분한 권한이 있는 공급업체는 담당자 레코드에서 **공급업체 사용자 프로비저닝** 을 활성화하여 담당자를 사용자로 프로비저닝하도록 요청할 수 있습니다. 프로비저닝 프로세스 중에 새 외부 사용자에 대한 사용자 권한이 선택되고 새 공급업체 사용자 요청이 제출됩니다. 공급업체 사용자 요청에서 선택할 수 있는 사용자 권한을 올바르게 설정하는 것이 중요합니다. 그렇지 않으면 공급업체가 Supply Chain Management에서 액세스할 수 없는 정보에 대한 액세스 권한을 부여받을 수 있습니다.

### <a name="set-up-the-security-roles-that-are-available-for-selection-when-a-new-user-request-is-used-for-a-contact-person"></a>담당자에 대해 새 사용자 요청을 사용할 때 선택할 수 있는 보안 역할 설정

1. **시스템 관리** &gt; **보안** &gt; **외부 역할** 을 선택합니다.
2. **새로 만들기** 를 선택한 다음 보안 역할과 **공급업체** 당사자 역할을 선택합니다.

Supply Chain Management에서 제공되는 **공급업체 관리자(외부)** 및 **공급업체(외부)** 역할을 추가할 수 있습니다. 또는 회사에서 생성한 보안 역할을 사용할 수 있습니다.

**공급업체 관리자(외부)** 역할은 공급업체가 새 연락처를 만들고, 새 사용자에 대한 공급업체 협업 사용자 요청과 사용자 정보 변경 사항을 제출하고, 워크플로를 통해 이러한 요청을 처리할 수 있어야 하는 경우에만 사용할 수 있도록 설정해야 합니다.

공급업체 연락처 및 사용자를 수동으로 설정하려는 경우 **공급업체(외부) 역할** 만 사용할 수 있도록 설정할 수 있습니다. 그러면 이 역할은 공급업체 사용자 요청을 통해 요청할 수 있는 유일한 역할이 됩니다.

> [!NOTE]
> 새 사용자 계정을 수동으로 생성하면 **SystemUser** 역할이 자동으로 부여됩니다. 따라서 해당 역할을 제거하고 **SystemExternalUser** 역할을 할당해야 합니다. 공급업체 사용자가 새 사용자를 프로비저닝하기 위해 시작한 워크플로를 통해 새 사용자 계정이 생성되면 공급업체 협업을 위해 설정한 역할과 **SystemExternalUser** 역할 중 하나 이상이 할당됩니다.

#### <a name="vendor-admin-external-security-role"></a>공급업체 관리자(외부) 보안 역할

**공급업체 관리자(외부)** 역할은 공급업체 연락처 정보를 유지 관리하고 새로운 공급업체 협업 사용자를 프로비저닝하도록 요청하는 외부 공급업체에 사용할 수 있습니다. 이 보안 역할이 있는 외부 사용자는 다음 작업을 수행할 수 있습니다.

- 개인의 직위, 이메일 주소 및 전화번호와 같은 담당자 정보를 보고 수정합니다.
- 연락처인 공급업체 계정에 신규 또는 기존 담당자를 추가합니다.
- 그들이 만든 모든 담당자를 삭제합니다.
- 담당자와 공급업체 계정 간의 연결을 활성화하거나 비활성화합니다. 담당자와 공급업체 계정 간의 연결이 비활성화된 후에는 새 구매 주문 또는 기타 문서에서 담당자를 참조할 수 없습니다.
- 공급업체 계정과 관련된 공급업체 협업 인터페이스의 문서에 대한 담당자의 액세스를 거부하거나 허용합니다. 담당자와 공급업체 계정 간의 연결이 비활성화된 후에는 공급업체 계정과 관련된 문서에 대한 액세스가 항상 거부됩니다.
- **사용자 프로비저닝** 작업을 사용하여 담당자에 대한 새 사용자 계정을 요청합니다.
- 담당자의 사용자 계정을 비활성화하도록 요청합니다.
- 보안 역할을 추가하거나 제거하려면 담당자의 사용자 계정을 수정하도록 요청합니다.
- RFQ를 봅니다.

#### <a name="vendor-external-security-role"></a>공급업체(외부) 보안 역할

**공급업체(외부) 역할** 은 구매 주문으로 작업할 외부 공급업체에 사용할 수 있습니다. 이 보안 역할이 있는 외부 사용자는 다음 작업을 수행할 수 있습니다.

- 구매 주문에 대한 정보를 보고 응답합니다.
- 공급업체 협업 송장을 유지 관리합니다.
- 위탁 인벤토리를 봅니다.
- RFQ를 보고 응답합니다.
- 공급업체 정보를 봅니다.

## <a name="set-up-security-roles-that-are-used-when-prospective-vendors-are-onboarded"></a>예상 공급업체가 온보딩될 때 사용되는 보안 역할 설정

예상 공급업체 등록 요청을 통해 시작된 공급업체를 온보딩하려면 외부 보안 역할을 설정해야 합니다. 이 역할은 **사용자 요청 워크플로(플랫폼)** 유형의 워크플로에 의해 제어되는 프로비저닝 프로세스 중에 새 사용자에게 할당됩니다. 자세한 내용은 이 토픽 뒷부분의 [공급업체 협업 사용자 요청을 처리하도록 워크플로 설정](#set-up-workflows-to-process-vendor-collaboration-user-requests) 섹션을 참조하세요.

예상 공급업체를 온보딩하는 방법에 대한 자세한 내용은 [공급업체 온보딩](vendor-onboarding.md)을 참조하세요.

### <a name="set-up-a-security-role-that-is-used-when-a-new-prospective-vendor-user-request-is-submitted"></a>새로운 예상 공급업체 사용자 요청이 제출될 때 사용되는 보안 역할 설정

1. **시스템 관리** > **보안** > **외부 역할** 을 선택하세요.
2. **새로 만들기** 를 선택한 다음 보안 역할과 **예상 공급업체** 당사자 역할을 선택합니다.

Supply Chain Management에서 제공되는 **공급업체 잠재 고객(외부)** 역할을 추가해야 합니다.

보안 역할은 새 공급업체 등록 마법사에게만 액세스 권한을 부여합니다.

## <a name="set-up-workflows-to-process-vendor-collaboration-user-requests"></a>공급업체 협업 사용자 요청을 처리하기 위한 워크플로 설정

모든 관련 작업이 완료되고 적절한 승인이 제공되도록 하려면 공급업체 협업 사용자 요청을 처리하도록 워크플로를 설정해야 합니다.

공급업체 협업 사용자 요청은 **공급업체 관리자(외부)** 보안 역할 또는 유사한 권한이 있는 외부 공급업체 또는 회사의 조달 전문가가 제출합니다. 또한 공급업체 온보딩 프로세스 동안 예상 공급업체 등록 요청에서 생성될 수도 있습니다.

세 가지 유형의 요청이 있습니다.

- 새 사용자 프로비저닝 요청
- 기존 사용자 비활성화 요청
- 기존 사용자의 보안 역할 수정 요청

공급업체 협업 사용자 요청에 대한 자세한 내용은 [공급업체 협업 사용자 관리](manage-vendor-collaboration-users.md)를 참조하세요.

세 가지 유형의 공급업체 협업 사용자 요청을 모두 처리하려면 두 개 이상의 워크플로를 만들어야 합니다. 새 워크플로는 **사용자 워크플로** 페이지에서 생성됩니다.

### <a name="example-of-a-workflow-for-provisioning-new-users-and-modifying-security-roles"></a>새 사용자를 프로비저닝하고 보안 역할을 수정하기 위한 워크플로의 예

새 사용자를 만들고 보안 역할을 수정하라는 공급업체 사용자 요청을 처리하기 위해 워크플로 시작 부분에 분기 조건을 넣을 수 있습니다. 이러한 방식으로 요청이 새 사용자를 만드는 것인지 아니면 기존 사용자를 수정하는 것인지에 따라 워크플로의 다른 분기가 사용됩니다.

이 분기를 설정하려면 **사용자 요청 워크플로(플랫폼)** 유형의 새 워크플로를 만듭니다. 이 워크플로의 분기에는 다음 요소가 포함될 수 있습니다.

#### <a name="branch-to-provision-new-users"></a>신규 사용자 프로비저닝을 위한 분기

1. 새 사용자에게 공급업체 협업 정보에 대한 액세스 권한을 부여해야 한다는 승인을 담당하는 사람에게 승인 작업을 할당합니다.
2. Azure Portal에서 새로운 Microsoft Azure Active Directory(Azure AD) 사용자 계정을 요청하는 담당자에게 작업을 할당합니다. 이 단계에 대해 미리 정의된 **Azure B2B 사용자 초대 보내기** 작업을 사용합니다. B2B 사용자는 자동으로 Azure AD로 내보낼 수 있습니다. 미리 정의한 **Azure AD B2B 사용자 프로비저닝** 을 사용합니다. 자세한 내용은 [Azure AD로 B2B 사용자 내보내기](../../fin-ops-core/dev-itpro/sysadmin/implement-b2b.md)를 참조하세요.
3. Azure에 업로드하는 사람에게 승인 작업을 할당합니다. 계정이 성공적으로 생성되지 않으면 이 사람은 작업을 거부하고 워크플로를 종료합니다. B2B API(애플리케이션 인터페이스)를 통해 새 사용자 계정을 Azure로 자동으로 내보내는 단계가 포함된 경우 이 승인 작업을 건너뛸 수 있습니다.
4. 새 사용자를 프로비저닝하는 자동화된 작업을 추가합니다. 이 단계에 대해 사전 정의된 **자동 프로비저닝 사용자** 작업을 사용합니다.
5. 새 사용자에게 알리는 작업을 추가합니다. Supply Chain Management에 대한 URL이 포함된 환영 이메일을 새 사용자에게 보낼 수 있습니다. 이 이메일은 **이메일 메시지** 페이지에서 생성한 템플릿을 사용하고 **사용자 워크플로 매개 변수** 페이지에서 선택할 수 있습니다. 템플릿은 **%portalURL%** 태그를 포함할 수 있습니다. 환영 이메일이 생성되면 이 태그는 Supply Chain Management 테넌트의 URL로 대체됩니다.

    > [!NOTE]
    > 이 워크플로는 사용자 온보딩과 관련된 여러 시나리오에서 사용할 수 있습니다. 예를 들어, 예상 공급업체나 담당자에게 공급업체 협업 계정이 필요한 경우 사용할 수 있습니다. 따라서 이메일을 여러 용도로 사용할 수 있는 일반적인 문구로 표현해야 합니다.

#### <a name="branch-to-modify-security-roles"></a>보안 역할을 수정하는 분기

1. 보안 역할에 대한 변경 승인을 담당하는 사람에게 승인 작업을 할당합니다.
2. 관련 보안 역할을 추가하거나 제거하는 자동화된 작업을 추가합니다. 이 단계에서는 **자동화된 사용자 프로비저닝** 작업을 사용합니다.

### <a name="example-of-a-workflow-for-inactivating-a-user"></a>사용자 비활성화 워크플로의 예

**사용자 요청 비활성화 워크플로 플랫폼** 유형의 워크플로를 만들고 다음 작업을 추가합니다.

1. 사용자 비활성화 요청을 수락할 책임이 있는 사람에게 승인 작업을 할당합니다. 이 승인 단계를 자동화하는 조건을 추가할 수 있습니다.
2. 사용자를 비활성화하는 자동화된 작업을 추가합니다. 이 단계에서는 **자동화된 사용자 비활성화** 작업을 사용합니다.
3. 필요한 정리 작업을 추가합니다. 예를 들어 Azure Portal의 디렉터리에서 계정을 제거하는 작업을 추가할 수 있습니다.

## <a name="enable-vendor-collaboration-for-a-specific-vendor"></a>특정 공급업체에 대한 공급업체 협업 사용 설정

공급업체 협업을 사용할 사용자 계정을 만들기 전에 공급업체 협업을 사용할 수 있도록 공급업체를 설정해야 합니다. **공급업체** 페이지의 **일반** 탭에서 **협업 활성화** 필드를 설정합니다. 다음 옵션을 사용할 수 있습니다.

- **활성(PO가 자동 확인됨)** – 공급업체가 변경을 요청하지 않고 수락하면 구매 주문이 자동으로 확인됩니다.
- **활성(PO가 자동 확인되지 않음)** – 조직은 공급업체가 구매 주문을 수락한 후 수동으로 구매 주문을 확인해야 합니다.

> [!NOTE]
> 회사의 조달 전문가도 이 작업을 완료할 수 있습니다.

## <a name="troubleshoot-the-provisioning-of-new-vendor-collaboration-users"></a>새로운 공급업체 협업 사용자 프로비저닝 문제 해결

새 공급업체 협업 사용자는 **공급업체 사용자 프로비저닝** 유형의 공급업체 협업 사용자 요청을 처리하도록 설정한 워크플로를 통해 프로비저닝됩니다.

신규 공급업체 협업 사용자의 이메일 주소가 Azure에 테넌트로 등록된 도메인에 속하는 경우(즉, 관리되는 도메인 계정인 경우) 이메일 주소는 기존 Azure AD 계정이어야 합니다. 그렇지 않으면 프로비저닝 프로세스를 완료할 수 없습니다.

Azure AD 계정 관리 워크플로에서 **Azure B2B 사용자 초대 보내기** 작업에 사용되는 프로세스에 대한 자세한 내용은 [Azure Active Directory B2B 협업](/azure/active-directory/external-identities/what-is-b2b)을 참조하세요.

## <a name="additional-resources"></a>추가 리소스

[외부 공급업체와 공급업체 협업](vendor-collaboration-work-external-vendors.md)

공급업체 온보딩 프로세스에 대한 짧은 비디오 보기: [새 공급업체 온보딩](https://www.youtube.com/watch?v=0KUc3AGaTKk&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
