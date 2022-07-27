---
title: 서비스 환경
description: 이 항목에서는 전자 송장 발행을 위한 서비스 환경에 대한 정보를 제공하고 설정 방법을 설명합니다.
author: dkalyuzh
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: a8a135098f71e1413cd20ff8ad4003f090ae3407
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451708"
---
# <a name="service-environments"></a>서비스 환경

[!include [banner](../includes/banner.md)]

서비스 환경은 세계화 기능과 전자 송장 발행 서비스에서 처리되는 해당 문서를 지원하기 위해 생성되는 논리 파티션입니다. 보안 비밀과 디지털 인증서, 액세스 사용 권한(거버넌스)은 서비스 환경 수준에서 설정해야 합니다.

사용자는 필요한 만큼 서비스 환경을 만들 수 있습니다. 사용자가 만드는 모든 서비스 환경은 서로 독립적입니다. 모범 사례로 최소한 두 개의 서비스 환경을 만드는 것이 좋습니다.

- 주요 개발 및 검증 목적을 위한 한 환경. 이 환경은 일반적으로 UAT(User Acceptance Test) 환경입니다.
- 프로덕션 목적을 위한 한 환경. 이 환경은 일반적으로 프로덕션 환경입니다.

이러한 유형의 분할은 전자 송장 발행 프로세스가 프로덕션으로 이동하기 전에 샌드박스에서 검증되고 사용자 지정되도록 하는 데 도움이 됩니다.

서비스 환경은 RCS(Regulatory Configuration Service)에서 만들고 유지 관리해야 합니다. 그런 다음 준비가 되면 전자 송장 발행 서비스에 게시해야 합니다. 게시 프로세스는 RCS 인스턴스에서 전자 송장 발행 서비스로 서비스 환경의 매개 변수를 보냅니다.

새 서비스 환경을 생성하거나 기존 서비스 환경을 조정한 후(예: 사용자 또는 Microsoft Azure Key Vault 비밀 추가 또는 제거) 게시 프로세스를 완료하지 않으면 변경 사항이 적용되지 않습니다. Dynamics 365 Finance 또는 Dynamics 365 Supply Chain Management에서는 게시된 환경만 액세스할 수 있습니다.

## <a name="service-environment-statuses"></a>서비스 환경 상태

서비스 환경은 상태를 통해 관리할 수 있습니다. **서비스 환경** 페이지에서 환경의 상태를 볼 수 있습니다. 다음과 같은 상태를 사용할 수 있습니다.

- **게시되지 않음** – 환경이 생성되었지만 아직 게시되지 않았습니다.
- **게시됨** – 환경이 전자 송장 발행 서비스에 게시되었습니다.
- **변경됨** – 게시된 환경의 특성이 변경되었지만 변경 사항이 아직 게시되지 않았습니다.

## <a name="users"></a>사용자

각 서비스 환경은 Finance 또는 Supply Chain Management에서 전자 송장 발행에 연결할 수 있는 사용자를 나열해야 합니다.

## <a name="applications"></a>애플리케이션

일부 시나리오에서 Finance 또는 Supply Chain Management 이외의 애플리케이션은 추가 처리를 위해 전자 문서를 제출하거나 문서 제출 상태와 같은 정보를 검색하기 위해 전자 송장 발행 서비스에 연결해야 할 수 있습니다. 이러한 시나리오에서 애플리케이션은 애플리케이션 목록에 정의되어야 합니다. 이러한 방식으로 전자 송장 발행 서비스에 액세스할 수 있습니다. 또한 애플리케이션은 Azure AD(Azure Active Directory)에 애플리케이션으로 등록해야 하며 개체 ID를 사용하여 식별해야 합니다. 

Microsoft는 전자 송장 발행 서비스에 연결할 수 있는 애플리케이션에 대해 높은 수준의 보안 제어를 요구하므로 <DGXRegulatoryservicesengineering@service.microsoft.com>으로 Microsoft에 문의하고 애플리케이션에 대한 다음 세부 정보를 제공해야 합니다.

- Azure AD 테넌트 ID
- Microsoft Dynamics Lifecycle Services(LCS) 환경 ID
- 애플리케이션 ID(클라이언트 ID)
- 개체 ID
- 애플리케이션의 타당성 및 개략적 설명

Microsoft는 요청을 평가하고 애플리케이션을 보안 등록부에 등록하여 전자 송장 발행과 함께 작동할 수 있는지 확인합니다.

## <a name="number-sequences"></a>번호 시퀀스

시나리오에 번호 시퀀스(예: 파일 이름)가 필요한 경우 특정 환경에 대해 정의된 숫자 시퀀스를 사용할 수 있지만 이는 전체 세계화 기능이나 특정 세계화 기능에 사용할 수 있습니다. 번호 시퀀스를 정의한 후 변수 및 처리 파이프라인에 사용할 수 있습니다. 사용을 추적하려면 **번호 시퀀스** 페이지에서 **사용 중** 매개 변수에 대한 **현재** 값을 찾습니다.

### <a name="working-with-number-sequences"></a>번호 시퀀스 작업
**번호 시퀀스** 페이지에서 다음을 수행합니다. 

- **새로 만들기** 를 선택하여 번호 시퀀스를 만듭니다. 그런 다음 이름 및 설명을 입력합니다. 
- 더는 사용되지 않는 번호 시퀀스를 삭제하려면 **삭제** 를 선택합니다.
- 변경 사항을 번호 시퀀스에 게시하기 위해 작업 창에서 **게시** 를 선택할 필요가 없습니다. 업데이트는 자동으로 수행됩니다.

## <a name="create-a-key-vault-reference"></a>Key Vault 참조 만들기

1. RCS 계정에 로그인합니다.
2. **세계화 기능** 작업 영역의 **환경** 섹션에서 **전자 송장 발행** 타일을 선택합니다.
3. **환경 설정** 페이지의 작업 창에서 **서비스 환경** 을 선택합니다.
4. **서비스 환경** 페이지의 작업 창에서 **Key Vault 매개 변수** 를 선택합니다.
5. **Key Vault 매개 변수** 페이지에서 **새로 만들기** 를 선택하여 Key Vault 참조를 만듭니다.
6. **이름** 필드에 Key Vault 참조의 이름을 입력합니다.
7. **설명** 필드에 설명을 입력합니다.
8. **Key Vault URI** 필드에 Key Vault(`https://<your key vault>.vault.azure.net/`)의 Key Vault URI를 붙여넣습니다. 자세한 내용은 [Azure Portal에서 Azure Key Vault 만들기](e-invoicing-create-azure-key-vault-azure-portal.md)를 참조하십시오.
9. **저장** 을 선택합니다.
    
## <a name="create-a-secret-for-the-storage-account-secret-token"></a>스토리지 계정 비밀 토큰에 대한 비밀 만들기

1. **Key Vault 매개 변수** 페이지에서 이전 절차에서 만든 Key Vault 참조를 선택한 다음 **인증서** 섹션에서 **추가** 를 선택합니다.
2. **이름** 필드에 스토리지 비밀의 이름을 입력합니다. 이 이름은 스토리지 공유 액세스 서명(SAS) 토큰을 보유하는 Key Vault 비밀의 이름과 일치해야 합니다. 자세한 내용은 [Azure Portal에서 Azure 스토리지 계정 만들기](e-invoicing-create-azure-storage-account-azure-portal.md)를 참조하십시오. 
3. **설명** 필드에 설명을 입력합니다.
4. **유형** 필드에서 **비밀** 을 선택합니다.
5. **저장** 을 선택합니다.
    
## <a name="create-a-service-environment"></a>서비스 환경 만들기

1. 서비스 환경을 만들려면 **서비스 환경** 페이지에서 **새로 만들기** 를 선택합니다.
2. **이름** 필드에 전자 송장 발행 환경의 이름을 입력합니다.
3. **설명** 필드에 설명을 입력합니다.
4. **Storage SAS 토큰 암호** 필드에서 스토리지 계정에 대한 액세스를 인증하는 데 사용해야 하는 스토리지 계정 비밀의 이름을 선택합니다.
5. **사용자** 섹션에서 **추가** 를 선택하여 환경을 통해 전자 송장을 제출하고 스토리지 계정에 연결할 수 있는 사용자를 추가합니다.
6. **사용자 ID** 필드에 사용자의 별칭을 입력합니다. 
7. **이메일** 필드에 사용자의 이메일 주소를 입력합니다.
8. **저장** 을 선택합니다.
9. 서비스 환경 페이지의 작업 창에서 **게시** 를 선택하여 환경을 전자 송장 발행 서비스에 게시합니다. **상태** 필드의 값이 **게시** 로 변경되었는지 확인합니다.
