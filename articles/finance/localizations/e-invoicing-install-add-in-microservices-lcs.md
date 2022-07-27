---
title: Lifecycle Services에서 마이크로 서비스용 추가 기능 설치
description: 이 항목에서는 Microsoft Dynamics LCS(Lifecycle Services)에 전자 송장 발행 기능을 설치하는 방법을 설명합니다.
author: dkalyuzh
ms.date: 02/11/2022
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
ms.openlocfilehash: a575f3e26489607dc2143ba05c941240969a0feb
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8451732"
---
# <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Lifecycle Services에서 마이크로 서비스용 추가 기능 설치

[!include [banner](../includes/banner.md)]

전자 송장 발행 서비스에서 인증하려면 Microsoft Dynamics Lifecycle Services(LCS)에서 환경에 대한 추가 기능을 설치하여 서비스 플랫폼에 Microsoft Dynamics 365 Finance 또는 Dynamics 365 Supply Chain Management 환경을 등록해야 합니다.

환경을 등록하려면 다음 단계를 따릅니다.

1. LCS 계정에 로그인합니다.
2. 프로젝트 대시보드에서 LCS 프로젝트를 선택합니다.
2. 프로젝트의 **환경** 대시보드에서 배포된 환경을 선택합니다. 선택한 환경은 실행 중이어야 합니다.
3. **Power Platform 통합** 탭의 **환경 추가 기능** 섹션에서 **새 추가 기능 설치** 를 선택합니다.
4. **전자 송장 발행** 을 선택합니다.
5. **AAD 애플리케이션 ID** 필드에서 **091c98b0-a1c9-4b02-b62c-7753395ccabe** 를 입력합니다. 이 값은 고정 값입니다. GUID(Globally Unique Identifier)만 입력해야 합니다. 공백, 쉼표, 마침표 또는 따옴표와 같은 다른 기호는 포함하지 마십시오.
6. **AAD 테넌트 ID** 필드에 Azure 구독 계정의 테넌트 ID를 입력합니다. 지정하는 Azure Active Directory(Azure AD) 테넌트는 RCS(Regulatory Configuration Service)에 사용되는 것과 동일한 테넌트여야 합니다.
7. 계약조건을 검토한 다음 확인란을 선택합니다.
8. **설치** 를 선택합니다. 몇 분 후 상태가 **설치 중** 에서 **설치됨** 으로 변경됩니다. 이 변경 사항을 보려면 페이지를 새로 고쳐야 할 수 있습니다.

이제 전자 송장 발행을 사용할 준비가 되었습니다.

> [!NOTE]
> 회사에는 일반적으로 여러 Finance 또는 Supply Chain Management 환경이 있습니다. 이러한 환경에는 프로덕션 환경, UAT(User Acceptance Test) 환경 및 개발(샌드박스) 환경이 포함됩니다. 전자 송장에 연결하려는 모든 환경에 대해 앞의 절차를 완료해야 합니다.
