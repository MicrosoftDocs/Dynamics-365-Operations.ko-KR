---
title: Regulatory Configuration Service
description: 이 항목에서는 RCS(Regulatory Configuration Service)의 기능을 간략히 소개하고 서비스에 액세스하는 방법을 설명합니다.
author: JaneA07
ms.date: 06/04/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 816b1bf9da9acdd5999320f39fb68fb6deda197c
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451387"
---
# <a name="regulatory-configuration-service"></a>Regulatory Configuration Service

[!include [banner](../includes/banner.md)]

RCS(Regulatory Configuration Service)는 무코드/저코드 전역화 기능을 위한 독립형 설계자 및 수명 주기 관리 서비스입니다. RCS를 통해 전역화 이해 당사자는 개발자를 참여시키지 않고도 세금, 전자 송장, 규제 보고, 은행 및 비즈니스 문서의 주요 전역화 영역을 확장하고 사용자 정의할 수 있습니다. 이 무코드/저코드 전역화 접근 방식은 전역화를 더 쉽고, 더 빠르고, 더 경제적으로 만들거나 확장할 수 있도록 합니다.

RCS는 다음과 같은 기능을 제공합니다.

- ER(전자 보고)에서 제공하는 모든 기능을 지원합니다.
- 새 전역화 마이크로 서비스를 구성하기 위한 필수 구성 요소입니다.
- 전자 송장을 지원합니다. 자세한 내용은 [전자 송장 발행](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga)을 참조하십시오.
- 세금 계산을 지원합니다. 자세한 내용은 [세금 서비스](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview)를 참조하십시오.
- 다중 구성 요소 기능의 수명 주기 관리를 단순화하고 작업을 구성하고 기능 매개 변수를 설정하는 추가 기능을 제공하는 새로운 전역화 기능을 지원합니다. 자세한 내용은 [Regulatory Configuration Service – 전역화 서비스를 위한 단순화된 전역화 기능 관리](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)를 참조하십시오.
- 전역 리포지토리에서 중앙 집중식 게시, 스토리지 및 사용자 지정 구성 공유를 지원하여 LCS(Microsoft Dynamics Lifecycle Services)를 사용하지 않고도 구성 관리를 단순화할 수 있습니다.

## <a name="access-rcs"></a>RCS 액세스

[Regulatory Configuration Service 페이지](https://marketing.configure.global.dynamics.com/)에서 RCS에 가입하거나 로그인할 수 있습니다.

![RCS 가입/로그인.](media/202103_RCS%20Marketing%20page_updated_1.jpg)

**Regulatory Configuration Service** 페이지에서 서비스 사용에 대한 보충 약관을 검토하고 동의한 후 다음 버튼 중 하나를 선택합니다.

- 서비스를 처음 사용하고 비즈니스 이메일 주소를 사용하여 조직의 서비스 환경을 프로비저닝하는 경우 **가입** 합니다.
- 이전에 서비스에 가입했고 지금 조직 환경에 액세스하려면 **로그인** 합니다.

> [!NOTE] 
> 등록한 후 RCS 환경에 SysAdmin 사용자를 추가하는 것이 좋습니다. 이 사용자는 환경의 공동 관리자로 프로비저닝됩니다. SysAdmin 역할은 해당 환경의 사용자를 관리하는 것이므로 RCS 환경에 대한 액세스를 위한 안정성을 제공하는 데 도움이 됩니다. **RCS 작업 영역 > 시스템 관리** 를 사용하여 사용자를 추가할 수 있습니다.

## <a name="regional-availability"></a>지역별 가용성

RCS는 일반적으로 다음 지역에서 사용할 수 있습니다.

- 미국
- 인도
- 프랑스
- 유럽

전체 지역 목록은 [Dynamics 365 및 Power Platform: 가용성, 데이터 위치, 언어 및 현지화](https://aka.ms/dynamics_365_international_availability_deck)를 참조하십시오.

## <a name="rcs-default-company"></a>RCS 기본 회사

RCS에서 사용되는 디자인 타임 기능은 모든 회사에서 공유됩니다. 회사별 기능은 없습니다. 따라서 RCS 환경에서 **DAT** 라는 한 회사를 사용하는 것이 좋습니다.

그러나 일부 시나리오에서는 ER 형식이 특정 법인과 관련된 매개 변수를 사용하도록 할 수 있습니다. 이러한 시나리오에서만 기본 회사 전환기를 사용해야 합니다. 예를 들어 [법인별로 지정된 매개 변수를 사용하도록 ER 형식 구성](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md)을 참조하십시오.

## <a name="related-rcs-documentation"></a>관련 RCS 설명서

관련 구성 요소에 대한 자세한 내용은 다음 항목을 참조하십시오.

- **RCS:**

    - [RCS에서 ER 구성 생성 및 전역 리포지토리에 업로드](rcs-global-repo-upload.md)

- **글로벌 리포지토리:**

    - [ER 구성 생성 후 Global 리포지토리에 업로드](rcs-global-repo-upload.md)
    - [글로벌 리포지토리에서 구성 공유](rcs-global-repo-share-configuration.md)
    - [글로벌 리포지토리의 향상된 필터링](enhanced-filtering-global-repo.md)
    - [글로벌 리포지토리에서 ER 구성 다운로드](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [글로벌 리포지토리의 구성 지원 중단](discontinuing-configurations-rcs-global-repo.md)
    - [RCS(Regulatory Configuration Service) - LCS(Lifecycle Services) 스토리지 지원 중단](rcs-lcs-repo-dep-faq.md)

- **전역화 기능:**

    - [RCS(Regulatory Configuration Service) - 전역화 기능](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)


## <a name="troubleshooting-rcs-sign-up"></a>RCS 가입 문제 해결

서비스 페이지에서 RCS에 가입할 때 Azure AD(Azure Active Directory)에 관련된 문제가 발생할 수 있습니다. 오류 메시지는 RCS 가입 기능이 현재 꺼져 있으며 가입 프로세스를 완료하려면 켜야 함을 나타냅니다.

![RCS 가입 오류 메시지.](media/01_RCSSignUpError.jpg)

임시 구독에 가입할 수 없도록 차단되어 있고 테넌트에서 `AllowAdHocSubscriptions` 속성을 활성화해야 하기 때문에 발생하는 문제입니다. 

- IT 부서에서 조직의 Azure 테넌트를 관리하는 경우 해당 부서에 문제를 보고하십시오.
- Azure 테넌트를 직접 관리한다면 [Azure Active Directory 셀프 서비스 가입이란?](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings)의 단계를 따라 문제를 해결할 수 있습니다.
