---
title: 공급업체 협업 사용자 관리
description: 이 토픽에서는 새 공급업체 협업 사용자의 프로비저닝을 요청하는 방법과 새 공급업체 협업 연락처를 추가하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: smmContactPerson, VendVendorContactPerson, VendVendorPortalUser
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: 220744
ms.assetid: edc19ad0-3565-4d47-98ac-dda6098f63ac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ff0d11bf2c42f7ae63e3db5f31f3ffea2c28f693
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449077"
---
# <a name="manage-vendor-collaboration-users"></a>공급업체 협업 사용자 관리

[!include [banner](../includes/banner.md)]

이 토픽에서는 새 공급업체 협업 사용자의 프로비저닝을 요청하는 방법과 새 공급업체 협업 연락처를 추가하는 방법에 대해 설명합니다. 

Dynamics 365 Supply Chain Management의 공급업체 협업 인터페이스는 구매 주문, 송장 및 위탁 재고에 대한 정보를 외부 공급업체에 노출합니다. **공급업체 관리자(외부)** 보안 역할 또는 유사한 권한이 있는 외부 공급업체로 작업하는 경우 새 공급업체 협업 연락처를 만들고 새 사용자가 프로비저닝되도록 요청할 수 있습니다. 조달 전문가로 일하는 경우에도 이러한 작업을 수행할 수 있습니다. 이 토픽에서 이 역할은 Supply Chain Management 인스턴스를 소유한 회사 내에서 일하는 조달 전문가를 나타냅니다. 외부 공급업체인 경우 공급업체 협업을 사용하는 방법에 대한 자세한 내용은 [고객과 공급업체 협업](vendor-collaboration-work-customers-dynamics-365-operations.md)을 참조하세요.  

조달 전문가인 경우 공급업체 협업을 사용하는 방법에 대한 자세한 내용은 [외부 공급업체와의 공급업체 협업](vendor-collaboration-work-external-vendors.md)을 참조하세요.

## <a name="add-new-vendor-collaboration-contacts"></a>새 공급업체 협업 연락처 추가
누군가가 공급업체 협업에 액세스할 수 있도록 하려면 먼저 공급업체 협업 담당자로 추가해야 합니다. 공급업체 협업을 사용하지 않을 회사 직원의 연락처를 추가할 수도 있습니다. 예를 들어, 다른 종류의 조달 정보에 대한 연락처가 될 수 있습니다. **공급업체 협업** &gt; **연락처** 메뉴에서 액세스할 수 있는 **모든 연락처** 페이지에 새 연락처가 추가됩니다. 새 연락처를 추가하려면:

1.  **새로 만들기** 를 클릭합니다.
2.  담당자 세부정보를 입력합니다.
3.  그들이 회사에서 어떤 법인을 대표하고, 그들이 협력할 회사에서 함께 일할 법인을 선택합니다. **내 회사의 법인**/**고객 회사 쌍의 법인** 을 선택하면 됩니다.
4.  **만들기** 를 클릭합니다.

연락처를 삭제하려는 경우 생성한 연락처만 삭제할 수 있습니다.

## <a name="vendor-collaboration-user-requests"></a>공급업체 협업 사용자 요청
공급업체 협업 사용자 요청은 조달 전문가나 외부 공급업체 관리자가 제기할 수 있습니다.

-   외부 공급업체인 경우 **공급업체 협업** 모듈 내의 **모든 연락처** 페이지에서 요청을 제출합니다.
-   조달 전문가인 경우 **연락처 보기** 페이지에서 요청을 제출합니다. 이렇게 하려면 공급업체 레코드의 작업 창에 있는 **설정** 섹션에서 **연락처** &gt; **연락처 보기** 를 선택합니다.

사용자 프로비저닝, 사용자 비활성화 또는 보안 역할 수정을 요청할 수 있습니다. 외부 공급업체 관리자인 경우 사용자 요청을 하려는 공급업체 계정의 담당자로 등록해야 하고 해당 공급업체 계정에 대한 공급업체 협업 인터페이스에 액세스할 수 있어야 합니다.  

요청이 제출되면 **공급업체 협업** 모듈의 **공급업체 협업 사용자 요청** 목록과 조달 및 소싱 모듈의 **공급업체 협업 사용자 요청** 목록에 추가됩니다(**조달 및 소싱** 모듈은 외부 사용자가 액세스할 수 없음).

### <a name="provision-a-user"></a>사용자 프로비전

새 사용자가 프로비저닝되도록 요청하려면 먼저 해당 사용자를 하나 이상의 공급업체 계정에 대한 연락처로 설정해야 합니다. 새 공급업체 협업 사용자에 대한 요청을 생성하려면:

1. **모든 연락처** 페이지에서 **공급업체 사용자 프로비저닝** 을 클릭합니다.
2. 사용자의 이메일 주소를 입력합니다. 이 주소는 사용자가 Supply Chain Management에 로그인하는 데 사용됩니다. 이메일 주소가 Microsoft Azure에 테넌트로 등록된 도메인에 속하는 경우 프로비저닝 프로세스가 성공적으로 완료되려면 이메일 주소가 기존 AAD(Azure Active Directory) 계정이어야 합니다. 이메일 주소가 Microsoft Azure에 등록된 도메인에 속하지 않는 경우 프로비저닝 프로세스의 일부로 AAD 계정이 생성되고 새 사용자는 초대 메일을 받게 됩니다. @hotmail.com, @gmail.com 또는 @comcast.net과 같은 도메인의 소비자 이메일 주소는 사용자를 등록하는 데 사용할 수 없습니다.
3. 사용자가 액세스해야 하는 모든 법인에 대해 **공급업체 협업 액세스 허용** 옵션을 **예** 로 설정합니다.
4. **사용자 역할 할당** 섹션에서 새 사용자가 가져야 하는 보안 역할에 대한 **할당** 확인란을 선택합니다.
5. **제출** 을 클릭합니다.

공급업체 사용자 요청이 제출되면 선택한 공급업체 계정에 대해 **공급업체 협업 액세스 허용** 필드가 **예** 로 설정되고 사용자 요청 워크플로가 시작됩니다. 워크플로의 일부로 새 사용자가 생성되고 보안 역할이 할당됩니다. 또한 Azure Portal과의 상호 작용을 시작하고 신규 또는 기존 AAD 계정을 Supply Chain Management 사용자 계정과 연결하는 Azure B2B 서비스가 활성화됩니다. 자세한 내용은 [Azure AD B2B 공동 작업이란?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b)을 참조하세요.

### <a name="inactivate-a-user"></a>사용자 비활성화

사용자의 공급업체 협업에 대한 액세스 권한을 제거하는 방법에는 두 가지가 있습니다.

-   공급업체의 **연락처** 페이지에서 연락처에 대해 **공급업체 협업 액세스 허용** 옵션을 **아니요** 로 설정합니다. 이는 해당 개인이 연락하는 법인별로 개별적으로 수행할 수 있습니다. 이 옵션은 조달 전문가만 사용할 수 있습니다.
-   **공급업체 사용자 비활성화** 요청을 제출하여 전체 사용자 계정을 비활성화합니다.

사용자 비활성화를 요청하려면:

1.  **모든 연락처** 페이지에서 **공급업체 사용자** **비활성화** 를 클릭합니다.
2.  **비즈니스 타당성** 필드에 의견을 작성합니다.
3.  **제출** 을 클릭합니다.

### <a name="modify-security-roles"></a>보안 역할 수정

**공급업체 사용자 역할 유지 관리** 페이지는 보안 역할 목록을 편집할 수 있다는 점을 제외하고 **공급업체 사용자 프로비전** 페이지와 동일합니다.  

사용자에 대한 보안 역할 수정을 요청하려면:

1.  **모든 연락처** 페이지에서 **공급업체 사용자 역할** **유지 관리** 를 클릭합니다.
2.  **비즈니스 타당성** 필드에 의견을 작성합니다.
3.  **사용자 역할 유지 관리** 섹션에서 할당할 보안 역할을 선택하거나 제거할 보안 역할을 지웁니다.
4.  **제출** 을 클릭합니다.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]