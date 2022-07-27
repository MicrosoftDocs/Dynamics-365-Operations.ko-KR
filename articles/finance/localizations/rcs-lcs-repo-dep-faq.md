---
title: RCS(Regulatory Configuration Service) - LCS(Lifecycle Services) 스토리지 사용 중지
description: 이 항목에서는 RCS(Regulatory Configuration Service) 전역 리포지토리 롤아웃의 일부로 계획된 LCS(Microsoft Dynamics Lifecycle Services) 스토리지의 지원 중단에 대한 정보를 제공합니다.
author: JaneA07
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, LCS storage, LCS storage deprecation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.19
ms.openlocfilehash: 68f1ed6a6d6bb0d15a81539da7f483ad71a4d696
ms.sourcegitcommit: 477efa4cb138f41d4f68bcd82552af3473bcc3d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2021
ms.locfileid: "8451114"
---
# <a name="regulatory-configuration-service-rcs--lifecycle-services-lcs-storage-deprecation"></a>RCS(Regulatory Configuration Service) - LCS(Lifecycle Services) 스토리지 지원 중단

[!include [banner](../includes/banner.md)]

ER(전자 보고) 구성을 위한 스토리지 리포지토리로 LCS(Microsoft Dynamics Lifecycle Services)를 사용하는 것은 지원이 중단됩니다. 이 지원 중단에는 다음과 같은 변경 사항이 포함됩니다.

- Microsoft Dynamics 365 애플리케이션에서 사용되는 Microsoft에서 제작한 구성은 더 이상 LCS의 공유 자산 라이브러리에 게시되지 않습니다. 대신 RCS 전역 리포지토리를 통해서만 게시됩니다. 그러나 Dynamics AX 2012의 구성은 AX 2012의 지원 수명 주기가 끝날 때까지 LCS의 공유 자산 라이브러리에 계속 게시됩니다.
- 재무 및 운영 앱과 RCS에서 LCS의 프로젝트 자산 라이브러리에 구성을 업로드할 수 있는 기능은 비활성화됩니다. 그러나 LCS의 브라우저를 사용하여 프로젝트 자산 라이브러리에 구성을 업로드할 수 있습니다. 따라서 LCS에 구성을 추가하여 솔루션 패키지에 포함할 수 있습니다.
- LCS에서 구성 가져오기는 재무 및 운영 앱과 RCS에서 한동안 계속 사용할 수 있으며 지원됩니다. 하지만 결국 지원이 중단될 것입니다. (정확한 지원 중단 날짜는 추후 공지될 예정입니다.)

## <a name="deprecation-notice"></a>지원 중단 알림

LCS를 스토리지로 사용하는 것이 지원 중단된다는 내용은 [Dynamics 365 Finance의 제거 또는 지원 중단 기능 - LCS 지원 중단 알림](../get-started/removed-deprecated-features-finance.md#features-removed-or-deprecated-in-the-finance-10017-release)에 담겨 있습니다. 계획된 지원 중단 날짜는 2022년 4월 1일입니다.

## <a name="key-features"></a>주요 기능

- RCS를 사용하여 ER 구성 및 전역화 기능을 만들고 편집합니다.
- 구성을 RCS 디자이너에서 직접 Dynamics 365 Finance 환경과 같은 연결된 애플리케이션으로 푸시하여 신속하게 구성을 변경하고 테스트할 수 있습니다.
- 전역 리포지토리의 중앙 집중식 스토리지를 통해 ER 구성 및 전역화 기능에 대한 수명 주기를 중앙에서 저장, 공유 및 관리합니다.

## <a name="guidance-for-one-time-and-ongoing-actions"></a>일회성 조치와 지속적 조치에 대한 지침

이 섹션에서는 한 번 완료해야 하는 일련의 단계에 대해 설명합니다. 또한 이후 지속적으로 완료해야 하는 단계에 대해서도 설명합니다.

### <a name="one-time-action"></a>일회성 작업

필요한 모든 구성을 LCS에서 RCS로 가져온 다음 RCS에서 전역 리포지토리로 게시합니다. 프로젝트별 자산 라이브러리를 사용하여 파생 구성을 LCS에 저장하는 경우 LCS에 액세스할 수 있는 동안 다음 단계를 완료해야 합니다.

1. RCS 인스턴스가 아직 없으면 프로비저닝합니다. 자세한 내용은 [RCS 개요](rcs-overview.md)를 참조하십시오.
2. 프로비저닝된 RCS 인스턴스에서 파생된 ER 구성을 포함하는 자산 라이브러리의 모든 LCS 프로젝트에 대해 적절한 LCS 리포지토리를 등록합니다.
3. LCS 리포지토리에서 RCS로 ER 구성을 가져옵니다. 자세한 내용은 [LCS에서 구성 가져오기](../../dev-itpro/analytics/tasks/er-import-configuration-lifecycle-services.md)를 참조하십시오.
4. 전역 리포지토리가 자동으로 제공되지 않는 경우 RCS에 등록합니다.
5. 현재 RCS 인스턴스에서 파생된 모든 구성을 전역 리포지토리로 업로드합니다. **구성 패키지** 기능이 업로드에 도움이 됩니다. 자세한 내용은 [RCS 전역 리포지토리 업로드](rcs-global-repo-upload.md)를 참조하십시오.

### <a name="going-forward"></a>향후

RCS의 비주얼 디자이너는 다음과 같은 용도로 사용합니다.

- Microsoft에서 제공하는 템플릿을 확장합니다.
- 조직에 필요한 새 구성을 만듭니다.
- 전자 송장 처리 및 세금 계산 서비스를 위한 전역화 기능을 사용자 정의합니다.

전역화 저장소는 다음과 같은 목적으로 사용합니다.

- Microsoft에서 제작한 구성 및 전역화 기능에 액세스합니다.
- 생성하거나 확장한 구성을 저장을 위해 전역 리포지토리에 업로드하고 조직의 Dynamics 365 애플리케이션 환경 또는 외부 조직과 공유합니다. 자세한 내용은 [RCS에서 ER 구성 생성 및 전역 리포지토리에 업로드](rcs-global-repo-upload.md)를 참조하십시오.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

### <a name="does-this-change-mean-that-lcs-cant-be-used-as-central-storage-for-configurations"></a>이러한 변경은 LCS를 구성을 위한 중앙 스토리지로 사용할 수 없다는 것을 의미합니까?

예. 재무 및 운영 앱에서 LCS의 프로젝트 자산 라이브러리에 구성을 업로드할 수 있는 기능은 더 이상 지원되지 않습니다. 그러나 필요에 따라 LCS의 브라우저를 사용하여 프로젝트 자산 라이브러리에 구성을 업로드할 수 있습니다.

### <a name="i-thought-that-rcs-was-a-replacement-repository-for-importing-global-template-files-i-didnt-think-that-its-used-to-store-configurations-which-is-correct"></a>RCS가 전역 템플릿 파일을 가져오기 위한 대체 리포지토리라고 생각했습니다. 구성을 저장하는 데 사용되는 줄은 몰랐습니다. 어떤 것이 맞습니까?

RCS는 ER 구성을 만들고 편집하기 위한 설계 서비스입니다. RCS에는 전역 리포지토리라고 하는 자체 리포지토리가 있습니다. 이 리포지토리가 RCS에서 생성된 구성을 저장하는 데 사용됩니다. LCS를 스토리지로 사용하는 것이 지원 중단되면 전역 리포지토리는 Microsoft 구성을 위한 단일 원본이 됩니다. 필요한 모든 구성을 LCS에서 RCS로 가져온 다음 RCS에서 전역 리포지토리로 게시하려면 일회성 작업을 완료해야 합니다.

### <a name="without-lcs-what-is-the-suggested-way-to-store-configurations-so-that-test-and-production-configurations-can-easily-be-managed-and-transferred"></a>LCS가 없으면 "테스트" 및 "프로덕션" 구성을 쉽게 관리하고 전송할 수 있도록 구성을 저장하는 권장 방법은 무엇입니까?

RCS는 *연결된 애플리케이션* 의 개념을 사용합니다. 연결된 애플리케이션은 RCS와 재무 및 운영 앱 인스턴스 간의 연결을 형성합니다. RCS를 사용하여 구성을 편집할 수 있으므로 연결된 애플리케이션을 사용하여 디자이너에서 재무 및 운영 앱 환경으로 직접 구성을 푸시할 수 있습니다. 따라서 LCS 프로젝트 수준 스토리지를 거치지 않고도 신속하게 구성을 변경하고 테스트할 수 있습니다.

### <a name="are-there-any-examples-that-show-the-setup-and-management"></a>설정과 관리 방법을 보여주는 예가 있습니까?

예는 없지만 이 항목의 앞부분에 있는 단계를 완료하여 구성을 RCS 전역 리포지토리로 마이그레이션할 수 있습니다.

### <a name="is-rcs-a-prerequisite-to-configure-electronic-reporting"></a>RCS는 전자 보고를 구성하기 위한 필수 조건입니까?

예. RCS에는 전자 송장 처리 및 세금 계산 서비스와 같은 전역화 서비스에서 사용하는 전역화 기능의 설정을 지원하는 기능이 포함되어 있습니다. 그러나 이 서비스에는 새 ER 구성을 확장하거나 생성할 수 있는 동일한 비주얼 디자이너 기능이 있습니다. 또한 RCS는 ER 구성과 전역화 기능 모두에 대한 수명 주기 관리 기능을 제공합니다.

### <a name="which-regions-can-rcs-be-deployed-in"></a>RCS를 배포할 수 있는 지역은 어디입니까?

RCS는 다음 Azure 지역에서 사용할 수 있습니다.

- 미국
- 인도
- 프랑스
- 유럽

제품 지원에 대한 자세한 내용은 [Dynamics 전역화 서비스 개요](globalization-services-overview.md)를 참조하십시오. 지리적 지원에 대한 자세한 내용은 [Dynamics 365 및 Power Platform: 가용성, 데이터 위치, 언어 및 현지화](https://aka.ms/rcs/D365Productavailabilityguide)를 참조하십시오.

### <a name="whats-the-cost-of-using-rcs"></a>RCS 사용 비용은 얼마입니까?

RCS와 전역화 리포지토리는 기존 재무 및 운영 앱 라이센스의 일부로 무료로 제공됩니다. RCS 설계 서비스를 사용하거나 전역 리포지토리에 구성을 저장하는 데 드는 별도의 비용은 없습니다. 현재 구성 또는 연결된 애플리케이션 수에 제한이 없습니다.
