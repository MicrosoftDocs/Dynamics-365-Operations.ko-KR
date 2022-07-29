---
title: 금융 및 운영 앱의 서비스 설명
description: 이 항목은 금융 및 운영 앱의 서비스 설명을 제공합니다.
author: tomhig
ms.date: 01/05/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: whigginb
ms.search.validFrom: 2021-09-03
ms.openlocfilehash: 85f82a863f0bde4c0414760fa2477651242538f2
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2022
ms.locfileid: "8461032"
---
# <a name="service-description-for-finance-and-operations-apps"></a>금융 및 운영 앱의 서비스 설명

[!include[banner](../includes/banner.md)]

금융 및 운영 앱은 [Microsoft Azure](https://azure.microsoft.com/overview/what-is-azure/)를 기반으로 빌드된 ERP(Enterprise Resource Planning) SaaS(Software as a Service) 제품입니다. 재무 및 운영 서비스는 조직에 고유한 요구 사항을 지원하고 인프라를 관리할 필요 없이 끊임없이 변화하는 비즈니스 환경에 적응하는 데 도움이 되는 ERP 기능을 제공합니다. 재무 및 운영 앱에는 다음 솔루션 영역 중 하나 이상이 포함될 수 있습니다.

- [Dynamics 365 Finance](/dynamics365/finance/)
- [Dynamics 365 Human Resources](/dynamics365/human-resources/)
- [Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/)
- [Dynamics 365 Commerce](/dynamics365/commerce/)
- [Dynamics 365 Project Operations](/dynamics365/project-operations/)

[비즈니스 인텔리전스](/power-bi/fundamentals/power-bi-service-overview), [하부 구조](https://azure.microsoft.com/global-infrastructure/), [계산](/azure/service-fabric/service-fabric-overview) 및 [데이터베이스 서비스](https://devblogs.microsoft.com/azure-sql/running-1m-databases-on-azure-sql-for-a-large-saas-provider-microsoft-dynamics-365-and-power-platform/)와 함께 이러한 앱을 통해 조직은 산업별 및 운영 비즈니스 프로세스를 실행할 수 있습니다. 구현 파트너의 지원을 받아 고객은 고유한 비즈니스 프로세스에 가장 적합한 비즈니스 애플리케이션 로직의 구성을 결정합니다. 기능 및 비즈니스 프로세스는 다음 솔루션 중 하나 또는 조합을 통해 확장하거나 확장할 수 있습니다.

- [개인화 경험](personalize-user-experience.md) 내장
- [Microsoft Power Platform](../../dev-itpro/power-platform/overview.md) 도구
- [Visual Studio](https://visualstudio.microsoft.com) 기반 [재무 및 운영 소프트웨어 개발 키트(SDK)](../../dev-itpro/dev-tools/developer-home-page.md) 및 [Azure DevOps 빌드 자동화](../../dev-itpro/dev-tools/developer-home-page.md#build-automation-using-azure)
- [AppSource](https://appsource.microsoft.com/partners)의 ISV(독립 소프트웨어 공급업체) 솔루션

요구 사항에 따라 고객은 솔루션 접근 방식을 선택합니다. 구현 파트너와 협력하여 [Microsoft Dynamics Lifecycle Services(LCS)](../../dev-itpro/lifecycle-services/lcs.md)에 제공된 도구 및 모범 사례를 사용하여 솔루션을 정의, 개발 및 테스트합니다. 네 가지 일반적인 시나리오가 있습니다.

- 표준 재무 및 운영 앱 "즉시 사용 가능한" 구성(확장 없음)
- 하나 이상의 ISV 솔루션을 포함하는 재무 및 운영 앱 구성
- 하나 이상의 고객별 확장을 포함하는 재무 및 운영 앱 구성
- 고객별 확장 조합 및 하나 이상의 ISV 솔루션을 포함하는 재무 및 운영 앱 구성

조직은 간단하고 투명한 구독 모델을 통해 사용자와 비즈니스 프로세스를 쉽게 추가하여 비즈니스 성장에 맞출 수 있습니다. 자세한 내용은 [Dynamics 365 라이선스 가이드](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365)를 참조하세요.

## <a name="operating-model"></a>작동 모델

재무 및 운영 앱의 운영 모델은 서비스 수명 주기 전반에 걸쳐 고객, 구현 파트너 및 Microsoft에 대한 특정 역할과 책임을 정의합니다. 자세한 내용은 [클라우드 운영 및 서비스](../../dev-itpro/lifecycle-services/cloud-operations-servicing.md)를 참조하세요.

### <a name="customer-activities"></a>고객 활동

고객은 파트너 및 [Microsoft FastTrack](/dynamics365/fasttrack/)과 협력하며 [Dynamics 365 구현 가이드](https://community.dynamics.com/365/dynamics-365-fasttrack/p/dynamics365implementationguide), [Success by Design](/dynamics365/fasttrack/success-by-design-overview) 프레임워크 및 [Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md)에서 제공하는 도구와 모범 사례를 따라 솔루션을 구현합니다. 일반적인 활동은 다음과 같습니다.

- 사용자 ID 및 보안 관리
- 비즈니스 프로세스 정의, 개발 및 운영
- 확장 정의, 개발, 테스트 및 운영
- 비프로덕션 배포 모니터링 및 관리
- 애플리케이션 업데이트 관리 및 확장 확인
- ISV 솔루션 및 타사 통합 관리

### <a name="microsoft-responsibilities"></a>Microsoft 책임

Microsoft는 Microsoft SaaS 구독에서 고객 샌드박스 및 프로덕션 환경을 배포, 적극적으로 모니터링 및 서비스하여 재무 및 운영 서비스를 관리합니다. 이 관리에는 서비스를 실행하고 서비스 상태에 대해 사전에 고객과 통신하는 데 필요한 시스템 인프라를 할당하는 것이 포함됩니다. 책임에는 다음이 포함됩니다.

**인프라 관리**
- 보안 및 격리
- 운영 체제 및 가상화
- 서버, 스토리지 및 네트워킹
- 데이터 센터 전원, 네트워킹, 냉각

**애플리케이션 플랫폼 관리**
- 연중무휴 애플리케이션 모니터링 및 알림
- 진단, 플랫폼 업데이트, 패치, 서비스 업데이트
- 애플리케이션 라우팅, 로드 밸런싱, 사이트 복제
- 환경 프로비저닝 및 관리
- 데이터베이스 관리, 고가용성(HA)/재해 복구(DR), 규모, 운영
- 컴퓨팅 배포, 확장, 축소

## <a name="system-configuration"></a>시스템 구성

금융 및 운영 앱은 거래량과 사용자 부하에 따라 확장됩니다. 각 고객 구현은 다음 요소로 구성된 고유한 솔루션을 생성합니다.

- **데이터 구성** – 행동, 조직의 레이아웃, 마스터 데이터의 구조(예: 재무 및 재고 차원), 트랜잭션 추적의 세분성을 제어하는 고유한 매개변수 집합입니다.
- **확장 및 구성** – 코드 확장, ISV 솔루션 및 워크플로, 통합 및 보고서 구성을 포함하는 고유한 구성을 사용하는 확장 메커니즘.
- **사용 패턴** – 통합 데이터 흐름을 위해 업스트림 및 다운스트림 시스템과 통합하는 기능 및 고객이 비즈니스 프로세스에서 사용하는 정보 보기를 기반으로 차별화하는 기능과 함께 온라인 및 배치 사용의 고유한 조합.

Microsoft는 트랜잭션 볼륨과 사용자 동시성을 처리할 수 있는 크기로 고객 프로덕션 환경을 구성합니다. Microsoft는 다음 작업을 담당합니다.

- 고객의 [LCS 구독 추정기](../../dev-itpro/lifecycle-services/subscription-estimator.md)의 프로파일링 정보를 기반으로 프로덕션 환경의 리소스를 올바르게 할당합니다
- 프로덕션 환경의 서비스 가용성을 지속적으로 모니터링 및 진단
- 재무 및 운영 앱의 시스템 성능 문제 분석 및 해결

구현이 고성능으로 구성되었는지 확인하려면 고객은 다음 작업을 완료해야 합니다.

- [LCS 구독 추정기](../../dev-itpro/lifecycle-services/subscription-estimator.md)에서 재무 및 운영 구현에 대한 정확한 사용 정보 제공.
- 성능 및 확장을 위한 확장을 빌드하고 테스트합니다.
- 성능을 위해 데이터 구성을 적절하게 테스트합니다.
- 게시하기 전에 [성능 테스트](https://community.dynamics.com/365/b/techtalks/posts/performance-testing-approach-april-30-2018)를 수행하여 확장성 보장.

## <a name="onboarding-and-implementation"></a>온보딩 및 구현

다음 표는 일반적인 온보딩 및 구현 이벤트를 보여줍니다.

| 요청 | 예상되는 Microsoft 조치 | 예상 고객/구현 파트너 조치 |
|---|---|---|
| 초기 제안 구매 | 고객이 트리거한 이벤트를 기반으로 오퍼 구매 후 LCS 프로젝트가 생성됩니다. | EA(기업계약) 또는 CSP(클라우드 솔루션 공급자) [커머셜 프로세스](before-you-buy.md)를 통해 이동합니다. 해당하는 경우 파트너가 고객에 대한 테넌트를 만듭니다. |
| 추가 구매 | 구현 중에 선택한 추가 기능에 대한 액세스 권한을 고객에게 부여합니다. | 해당 없음 |
| 구현 계획 및 분석 | LCS에서 관련 도구를 제공합니다. [비즈니스 프로세스 모델러(BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md) 및 [Azure DevOps와의 상호 운용성](../../dev-itpro/lifecycle-services/synchronize-bpm-vsts.md). | 프로젝트 계획, Azure DevOps 설정, 시스템 온보딩을 완료하고 관리자 계정을 설정합니다. |

자세한 내용은 [구현 프로젝트 온보딩](../imp-lifecycle/onboard.md)을 참조하세요.

## <a name="globalization"></a>세계화

재무 및 운영 앱은 전 세계 여러 Azure 지역에서 제공됩니다. 재무 및 운영 앱은 다양한 국가/지역 및 모국어를 지원하는 기능을 제공합니다. 자세한 내용은 [현지화 및 규제 기능](../../dev-itpro/lcs-solutions/country-region.md#localization-and-regulatory-features)을 참조하세요.

### <a name="countryregion-specific-considerations"></a>국가/지역별 고려 사항

- 현지 데이터 상주를 요구하는 프랑스 법인과 비즈니스를 하는 규제 산업 또는 상업 조직의 고객은 [프랑스의 재무 및 운영](../../dev-itpro/deployment/france-local-deployment.md)을 검토해야 합니다.
- 중국에 사업장이 있는 고객은 [Azure 중국 플레이북](/azure/china/) 및 [중국에서 21Vianet이 운영하는 재무 및 운영](../../dev-itpro/deployment/china-local-deployment.md)을 검토해야 합니다.
- 러시아에 사업장이 있는 고객은 [러시아 개인 데이터 현지화 법률](/business-applications-release-notes/october18/dynamics365-finance-operations/russian-regulations-on-prem#when-will-the-cloud-deployment-option-of-dynamics-365-for-finance-and-operations-be-generally-available-for-russia)을 검토해야 합니다.

### <a name="general-data-protection-regulation-gdpr"></a>일반 데이터 보호 규정(GDPR)

재무 및 운영 앱의 경우 Microsoft는 프로세서 역할을 합니다. 데이터 처리자로서 재무 및 운영은 고객이 데이터 컨트롤러로서 GDPR 의무를 준수하는 데 도움이 되는 프로세스와 기능을 제공합니다. 자세한 내용은 [GDPR 개요](../../dev-itpro/gdpr/gdpr-guide.md)를 참조하세요.

## <a name="environment-and-data-management"></a>환경 및 데이터 관리

이 섹션에서는 서비스에서 발생하는 몇 가지 일반적인 환경 및 데이터 관리 이벤트에 대해 설명합니다.

### <a name="environment-and-data-management-events-for-production-instances"></a>프로덕션 인스턴스에 대한 환경 및 데이터 관리 이벤트

LCS는 [셀프 서비스 도구](../../dev-itpro/deployment/infrastructure-stack.md)와 [데이터베이스 이동 작업](../../dev-itpro/database/dbmovement-operations.md)을 제공하며 환경 및 데이터 관리 작업을 수행하는 데 사용됩니다. 여기 예시들이 있습니다 :

**이벤트:** [프로덕션 인스턴스 요청](../imp-lifecycle/prepare-go-live.md#requesting-the-production-environment)

- [라이브 체크리스트](../imp-lifecycle/prepare-go-live.md)를 완료하고 [Microsoft FastTrack](/dynamics365/fasttrack/) 팀에 제출합니다.
- [LCS 구독 추정기](../../dev-itpro/lifecycle-services/subscription-estimator.md)를 완료한 후 프로덕션 인스턴스를 요청합니다.
- [LCS 방법론](../../dev-itpro/lifecycle-services/create-methodology.md)에 지정된 모든 구현 작업을 완료합니다.

**이벤트:** [프로덕션 인스턴스에 샌드박스 데이터베이스 복사](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- 모의 라이브 또는 실제 라이브 컷오버를 위해 수행되었습니다.

**이벤트:** [유지 관리 모드](../../dev-itpro/sysadmin/maintenance-mode.md)

1. LCS에서 유지 관리 모드를 켭니다.
2. 필수 유지 관리를 완료합니다.
3. LCS에서 유지 관리 모드를 끕니다.

### <a name="environment-and-data-management-events-for-non-production-instances"></a>비프로덕션 인스턴스에 대한 환경 및 데이터 관리 이벤트

LCS는 [셀프 서비스 프로비저닝](../../dev-itpro/deployment/infrastructure-stack.md)과 [데이터베이스 이동 작업](../../dev-itpro/database/dbmovement-operations.md)을 제공하며 환경 및 데이터 관리 작업을 수행하는 데 사용됩니다. 여기 예시들이 있습니다 :

**이벤트:** [새 샌드박스 인스턴스 배포](../../dev-itpro/deployment/deployenvironment-newinfrastructure.md)

- 모든 필수 인스턴스가 [계획](../imp-lifecycle/environment-planning.md)되고 해당 추가 기능을 구매했는지 확인합니다.
- LCS에서 배포 프로세스를 실행합니다.
- LCS 체크리스트에 지정된 모든 작업을 완료합니다.
    
>[!NOTE]
>개발 샌드박스 환경은 가상 머신(VM)이며 [고객의 Azure 구독에 배포](../../dev-itpro/dev-tools/access-instances.md)되고 고객이 관리합니다.

**이벤트:** [샌드박스에서 프로덕션으로 골든 구성 데이터베이스 복사](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- 모의 라이브 또는 실제 라이브 컷오버를 위해 수행되었습니다.

**이벤트:** [프로덕션 시점 백업을 비프로덕션 인스턴스로 복원](../../dev-itpro/database/database-pitr-prod-sandbox.md)

- LCS에서 [데이터베이스 새로 고침](../../dev-itpro/database/database-refresh.md) 옵션을 실행합니다.
- 사후 복사: 스크립트를 통해 민감한 데이터를 삭제하거나 난독화하고, 환경별 애플리케이션 구성(예: 통합 엔드포인트)을 조정하고, 사용자를 활성화하거나 추가합니다. 이러한 변경 사항은 [데이터 패키지](../../dev-itpro/data-entities/data-entities-data-packages.md#import-a-data-package)를 적용하여 이루어집니다.

**이벤트:** [비프로덕션 인스턴스 데이터베이스 지정 시간 복원](../../dev-itpro/database/database-point-in-time-restore.md)

- 프로세스를 취소할 수 없음을 수락합니다.
- LCS에서 특정 시점 복원 작업을 실행합니다.

**이벤트:** 문제 해결 및 [디버깅](../../dev-itpro/database/dbmovement-scenario-debugdiag.md)을 위해 Tier 2 샌드박스 데이터베이스를 개발 샌드박스에 복사

- Tier 2 샌드박스 환경의 LCS에서 데이터베이스 내보내기 작업을 실행합니다.
- 개발 환경에서 데이터베이스를 가져오고 업데이트합니다.

## <a name="data-backup-and-retention"></a>데이터 백업 및 보존

SaaS 구독의 재무 및 운영 환경을 위한 데이터베이스는 자동 백업으로 보호됩니다. 프로덕션 환경의 경우 Microsoft에서 롤백하지 않는 한 자동 백업은 28일 동안 유지됩니다. 샌드박스(Tier 2+) 환경의 경우 7일 동안 보관됩니다. 계획된 유지 관리 업데이트 중에 장애가 발생하면 프로덕션 환경의 롤백을 수행할 수 있습니다.

자동 백업에 대한 자세한 내용은 [자동화된 백업 - Azure SQL Database 및 SQL Managed Instance](/azure/azure-sql/database/automated-backups-overview?tabs=single-database)를 참조하세요.

## <a name="service-activity-responsibilities"></a>서비스 활동 책임

다음 표에서는 서비스에 대한 몇 가지 일반적인 시나리오 및 활동에 대해 설명합니다. 또한 Microsoft, 고객 또는 Microsoft와 고객 모두가 활동에 대해 책임이 있는지 여부를 나타냅니다.

| 활동 | Microsoft의 책임 | 고객의 책임 |
|---|---|---|
| **초기 테넌트 프로비저닝** | | |
| 구독 추정 도구를 사용하여 LCS의 예상 로드 크기를 조정하고 특정 환경을 프로비저닝하도록 요청합니다. | | X |
| 모든 프로덕션 인스턴스 및 비프로덕션 인스턴스를 프로비저닝합니다. | X | |
| 배포된 프로덕션 인스턴스 및 비프로덕션 인스턴스를 검증합니다. | | X |
| **서비스 업데이트** | |
| 지정된 비프로덕션 및 프로덕션 인스턴스에 서비스 업데이트를 적용합니다. | X | |
| LCS의 서비스 업데이트를 샌드박스 인스턴스에 수동으로 적용합니다. 업데이트를 정의, 개발, 테스트하고 코드 업데이트 패키지를 다시 LCS에 제공합니다. | | X |
| 요청 및 일정 확장 업데이트는 프로덕션 인스턴스에 적용됩니다. | | X |
| 업데이트를 적용하기 전에 프로덕션 인스턴스에 대한 코드 및 데이터 백업을 만듭니다. | X | |
| 오류가 발생하면 프로덕션 인스턴스를 코드 및 데이터 백업으로 롤백합니다. | X | |
| **데이터 관리(백업, 복원 및 업데이트)** | | |
| 데이터베이스를 백업합니다. | X | |
| 고가용성 및 재해 복구 계획을 결정합니다. | X | |
| 프로덕션 인스턴스 데이터베이스의 성능을 모니터링합니다. | X | |
| 프로덕션 인스턴스 데이터베이스의 성능을 조정합니다. | X | |
| 비프로덕션 인스턴스로 프로덕션 인스턴스 데이터베이스 지정 시간 새로 고침을 수행합니다. | | X |
| **인프라 업데이트** | | |
| 정기적인 인프라 업데이트를 예약합니다. | X | |
| **확장 및 축소(사용자, 스토리지 및 인스턴스)** | | |
| 추가 사용자 및 비프로덕션 추가 기능을 구매합니다. | | X |
| LCS 구독 추정기 도구에서 사용 변경 사항을 업데이트합니다. | | X |
| 서비스 사용에 영향을 미치는 중요한 성능 문제를 보고합니다. | | X |
| 해당 서비스에 필요한 자원을 선제적으로 관리합니다. | X | |
| 사건을 조사하고 문제를 해결합니다. | X | |
| **보안(사용자 액세스)** | | |
| 서비스에 대한 사용자 액세스를 제공합니다. | | X |
| LCS를 통해 배포된 인스턴스의 관리 및 운영을 위한 LCS 프로젝트 액세스를 제공합니다. | | X |
| **프로덕션 인스턴스 모니터링** | | |
| 프로덕션 인스턴스 연중무휴 모니터링. | X | |
| 프로덕션 인스턴스와 관련된 인시던트에 대해 사전에 고객에게 알립니다. | X | |
| **비프로덕션 인스턴스 관리 및 모니터링** | | |
| LCS를 사용하여 비프로덕션 인스턴스를 관리합니다. | | X |
| 비프로덕션 인스턴스 모니터링. | | X |

## <a name="service-update-strategy"></a>서비스 업데이트 전략

[소프트웨어 수명 주기 정책](../../dev-itpro/migration-upgrade/versions-update-policy.md)에 따라 재무 및 운영 앱은 Microsoft [최신 수명 주기 정책](../../dev-itpro/migration-upgrade/versions-update-policy.md#modern-lifecycle-policy)을 따르며, 여기에는 지속적으로 서비스 및 지원되는 제품이 포함됩니다. 

Microsoft는 매년 다음 달에 재무 및 운영 앱에 대한 8개의 서비스 업데이트를 출시합니다.

- 1월
- 2월
- 4월
- 5월
- 7월
- 8월
- 10월
- 11월

>[!NOTE]
>4월과 10월은 주요 기능 릴리스 파도입니다. 고객은 최대 3회의 연속 업데이트 주기 동안 개별 서비스 업데이트를 일시 중지할 수 있습니다.

자세한 내용은 다음 항목을 검토하세요.

- [단일 버전 서비스 업데이트 개요](../../dev-itpro/lifecycle-services/oneversion-overview.md)
- [LCS를 통해 서비스 업데이트 구성](../../dev-itpro/lifecycle-services/configure-service-updates.md)
- [LCS를 통해 서비스 업데이트 일시 중지](../../dev-itpro/lifecycle-services/pause-service-updates.md)
- [LCS를 통해 서비스 업데이트 알림 받기](../../dev-itpro/lifecycle-services/notifications-service-updates.md)
- [서비스 업데이트를 검증하기 위한 회귀 테스트 도구](../../dev-itpro/perf-test/rsat/rsat-overview.md)
- [Dynamics 365 로드맵 및 릴리스 웨이브](https://dynamics.microsoft.com/roadmap/overview/)

## <a name="security-and-administrative-access"></a>보안 및 관리 액세스

재무 및 운영 프로덕션 환경에 대한 관리 액세스는 엄격하게 제어되고 기록됩니다. 고객 데이터는 [Microsoft 온라인 서비스 약관](https://www.microsoft.com/licensing/terms/productoffering)에 따라 처리됩니다. 

### <a name="customer-administrative-access"></a>고객 관리 액세스

고객의 테넌트 관리자는 다음 표에 설명된 대로 프로덕션 인스턴스 또는 비프로덕션 인스턴스에 액세스할 수 있습니다.

| 환경 유형 | 목적 | 고객 액세스 수준 |
|---|---|---|
| **비프로덕션**<br>티어 1 샌드박스 | 고객이 개발, 데모 또는 교육 목적으로 배포하는 비프로덕션 환경입니다. | 계층 1 샌드박스(클라우드 호스팅 환경이라고도 함)는 LCS에서 고객의 Azure 구독에 배포되는 고객 관리 VM입니다. 고객의 Azure 구독에 있는 VM이기 때문에 고객은 원격 데스크톱을 통해 환경에 대한 전체 관리 액세스 권한을 갖습니다. |
| **비프로덕션**<br>계층 2(또는 그 이상) 샌드박스 | 고객이 사용자 승인 테스트, 통합 테스트, 교육, 스테이징 또는 기타 사전 프로덕션 시나리오를 위해 배포하는 비프로덕션 환경입니다. | Tier 2 이상의 샌드박스는 금융 및 운영 SaaS 구독에 배포됩니다. 비프로덕션 환경과 연결된 Azure SQL 데이터베이스에 대한 액세스는 [적시 액세스](../../dev-itpro/database/database-just-in-time-jit-access.md)를 통해 부여됩니다. 원격 데스크톱 액세스를 사용할 수 없습니다. |
| **생산** | 프로젝트가 [초기 라이브 준비](/imp-lifecycle/environment-planning.md#production-system-readiness)완료되면 프로덕션 환경이 배포됩니다. | 프로덕션 환경은 SaaS 구독에 배포됩니다. 모든 액세스는 브라우저, 서비스 끝점 또는 LCS를 통해 이루어집니다. |

### <a name="microsoft-administrative-access"></a>Microsoft 관리 액세스

다음 표는 다양한 Microsoft 관리자에 대한 다양한 액세스 수준을 보여줍니다.

| 관리자 | 고객 데이터 |
|---|---|
| 운영 대응팀<br>(핵심인력에 한함) | 액세스는 지원 티켓을 통해 부여됩니다. 액세스가 감사되고 지원 활동 기간으로 제한됩니다. |
| Microsoft 고객 지원 서비스(CSS) | 직접 액세스 없음. 고객은 화면 공유를 사용하여 지원 직원과 협력하여 문제를 디버깅할 수 있습니다. |
| 공학 | 직접 액세스 없음. 운영 대응 팀은 화면 공유를 사용하여 엔지니어링과 협력하여 문제를 디버깅할 수 있습니다. |
| Microsoft의 기타 | 액세스 없음. |

## <a name="monitoring"></a>모니터링

Microsoft는 고객의 프로덕션 인스턴스를 모니터링하고 진단하기 위해 광범위한 도구 세트에 투자했습니다. Microsoft는 하루 24시간 연중무휴로 고객의 프로덕션 환경을 모니터링합니다. 자세한 내용은 [생산 지원 및 모니터링](../imp-lifecycle/production-support-monitoring.md)을 참조하세요.

| Microsoft 책임 | 고객 책임 |
|---|---|
| <ul><li>서비스의 가용성을 모니터링합니다.</li><li>AOS(Application Object Server), Batch, DIXF(Data Import/Export Framework), Commerce 및 Management Reporter와 같은 중요한 구성 요소에 대한 상태 메트릭 및 워치독을 통해 지속적으로 모니터링하고 경고합니다.</li><li>인프라 서비스(예: Azure Active Directory\[Azure AD\] 및 Azure SQL)에 의한 성능 저하 모니터링.</li><li>Microsoft가 단일 프로세스 또는 배치 작업으로 인해 이상 현상이 발생한다고 판단하는 경우 해당 프로세스 또는 작업은 고객과 통신한 후 종료됩니다.</li></ul> | <ul><li>기능 및 성능 문제를 일으킬 수 있는 응용 프로그램 구성 및 확장에 대한 변경 사항을 모니터링합니다.</li><li>애플리케이션 오류는 모니터링 도구를 사용하여 진단해야 합니다. 이러한 도구를 사용하여 사용자가 보고한 성능 이상을 진단합니다.</li><li>예상 최대 사용량을 초과하여 시스템에 예상 부하가 있는 경우 Microsoft에 알립니다.</li><li>프로덕션 인스턴스에서 해당 서비스를 사용할 수 없는 경우 고객은 LCS를 사용하여 [생산 중단](../../dev-itpro/lifecycle-services/report-production-outage.md)을 보고할 수 있습니다.</li></ul> |

고객은 LCS를 통해 온라인으로 지원 요청을 제출함으로써 Microsoft가 가장 효과적이고 효율적인 방식으로 빠르고 심층적인 기술 전문 지식을 제공할 수 있습니다. 전화 옵션을 사용할 수 있지만 온라인 옵션을 사용할 수 없는 경우에만 사용해야 합니다. 자세한 내용은 [전화 지원 옵션](/power-platform/admin/support-overview.md?toc=/dynamics365/fin-ops-core/dev-itpro/toc.json&bc=/dynamics365/breadcrumb/toc.json#is-there-a-phone-number-i-can-call-to-contact-support)을 참조하세요.

## <a name="incident-management"></a>인시던트 관리

Microsoft는 심각도 수준에 따라 인시던트에 대응하고 수정합니다. Microsoft의 인시던트 심각도 수준은 인시던트의 초기 평가 중에 그리고 영향 및 범위에 대한 추가 정보가 제공되면 변경될 수 있습니다. 인시던트가 완화되면 인시던트 심각도가 변경되지 않은 상태로 유지됩니다.

심각도 수준에 대한 자세한 내용은 [이 심각도 표](/power-platform/admin/support-overview#what-is-initial-response-time-and-how-quickly-can-i-expect-to-hear-back-from-someone-after-submitting-my-support-request)를 참조하세요.

## <a name="business-continuity-through-high-availability-and-disaster-recovery"></a>고가용성 및 재해 복구를 통한 비즈니스 연속성 

Microsoft는 Azure 지역 전체에서 중단이 발생한 경우 재무 및 운영 앱의 프로덕션 인스턴스에 대한 비즈니스 연속성 및 재해 복구를 제공합니다. 자세한 내용은 [비즈니스 연속성 및 재해 복구](../../dev-itpro/sysadmin/business-continuity-disaster-recovery.md)를 참조하세요.

- **고가용성** – HA 기능은 Azure 데이터 센터의 단일 노드 오류로 인한 가동 중지 시간을 방지하는 방법을 제공합니다. 각 서비스의 클라우드 아키텍처는 단일 실패 지점 이벤트를 방지하기 위해 컴퓨팅 계층에 대해 Azure 가용성 집합을 사용합니다. 데이터베이스용 HA는 [Azure SQL HA 기능](/azure/azure-sql/database/high-availability-sla)을 통해 제공됩니다.
- **재해 복구** – [Azure 재해 복구 기능](/azure/best-practices-availability-paired-regions)은 전체 Azure 데이터 센터에 광범위하게 영향을 미치는 중단으로부터 각 서비스를 보호합니다. 다음은 이러한 기능 중 일부입니다.

    - 기본 데이터베이스(비즈니스 데이터베이스)에 대한 Azure SQL 활성 지역 복제.
    - 다른 Azure 지역에 있는 Azure Blob Storage(문서 첨부 파일 포함)의 지역 중복 복사본.
    - Azure SQL 및 Azure Blob Storage 복제를 위한 보조 지역입니다.

복제를 위해 기본 데이터 저장소가 지원됩니다. 따라서 Management Reporter 및 엔터티 저장소와 같은 각 서비스의 구성 요소는 기본 데이터베이스에서 변환된 데이터를 사용합니다. 이 데이터는 복구 사이트가 설정되고 서비스가 시작된 후에 생성되어야 합니다. 고객 코드 아티팩트 및 복구된 데이터 저장소는 사이트를 재배포하는 데 사용됩니다. 재배포를 통해 컴퓨팅 노드의 상태 복제가 네트워킹 및 기타 구성 요소와 함께 복구된 데이터 저장소를 사용하여 보조 사이트를 설정할 수 있습니다. 재해 복구를 사용하여 고객의 프로덕션 인스턴스를 복구하는 경우 Microsoft와 고객은 [사고 관리](service-description.md#incident-management) 책임을 준수합니다.

Microsoft의 재해 복구 계획 및 절차는 SOC(시스템 및 조직 제어) 감사를 통해 정기적으로 검사됩니다. 이러한 규정 준수 감사는 Dynamics 365 Finance 및 운영 앱을 포함한 Microsoft DR의 기술 및 절차 프로세스를 증명합니다. [SOC 준수](/compliance/regulatory/offering-soc-2) 감사 보고서 및 기타 모든 규정 준수 보고서는 [Microsoft 보안 센터 규정 준수 제품](/compliance/regulatory/offering-home)에서 사용할 수 있습니다.

| Microsoft 책임 | 고객 책임 |
|---|---|
| Microsoft는 기본 프로덕션 인스턴스가 배포될 때 Azure 쌍을 이루는 데이터 센터에 보조 환경을 프로비저닝합니다. 자세한 내용은 [비즈니스 연속성 및 재해 복구(BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions)를 참조하세요. | 없음 |
| Microsoft는 기본 프로덕션 인스턴스가 배포될 때 Azure SQL 및 Azure Blob Storage의 지역 중복성을 활성화합니다. | 없음 |
| Microsoft는 Azure SQL 데이터베이스에서 자동 백업을 활성화합니다. | 없음 |
| <p>중단이 발생하면 Microsoft는 고객에 대해 장애 조치를 수행해야 하는지 여부와 데이터 손실 여부를 결정합니다. 고객은 정전의 성격과 시기에 따라 최대 15분의 데이터 손실을 경험할 수 있습니다. | 데이터 손실이 발생한 경우 고객은 장애 조치를 트리거하기 위해 서면 사인오프를 제공해야 할 수 있습니다. |
| 장애 조치가 발생하면 해당 서비스가 제한 모드로 작동합니다. 장애 조치 모드에서는 업데이트 유지 관리를 트리거할 수 없습니다. | 고객은 장애 조치 모드에서 패키지 배포 또는 기타 정기 유지 관리 요청을 요청할 수 없습니다. |
| 데이터 센터가 작동되면 Microsoft는 기본 Azure 지역의 프로덕션 인스턴스로 장애 조치합니다. 정상 운영이 재개됩니다. | 고객은 기본 Azure 지역의 프로덕션 인스턴스로 장애 복구 시 사인오프해야 할 수 있습니다. |

## <a name="finance-and-operations-support-offerings"></a>재무 및 운영 지원 서비스

기술 지원은 재무 및 운영 서비스가 제공되는 시장에서 사용할 수 있습니다. [지원 경험](../../dev-itpro/lifecycle-services/lcs-support.md)은 LCS 또는 재무 및 운영 앱에서 제공됩니다. 여기 예시들이 있습니다 :

- LCS에서 [문제 검색](../../dev-itpro/lifecycle-services/issue-search-lcs.md)
- 금융 및 운영 앱의 [통합된 기술 지원](../../dev-itpro/lifecycle-services/support-experience.md)
- LCS의 [클라우드 기반 지원](../../dev-itpro/lifecycle-services/cloud-powered-support-lcs.md)

Microsoft는 재무 및 운영 고객에게 Premier, Professional Direct 및 구독에 포함된 지원의 세 가지 지원 계획을 제공합니다. 지원 수준은 계획에 따라 다릅니다. 다음 표는 세 가지 계획을 비교한 것입니다.

| 지원 기능 | 프리미어 | 프로페셔널 다이렉트 | 구독 |
|---|---|---|---|
| 무제한 고장/수리 사건 제출 | 예 | 예 | 예 |
| LCS를 통한 연중무휴 액세스 | 예 | 예 | 예 |
| 사고 대응 시간 | 1시간 미만 | 1시간 미만 | 다음 영업일 |
| 자문 시간 | 풀은 계약에 따라 획득됩니다. | 아니요 | 아니요 |
| 전담 지원 계정 관리자 | 예 | 아니요 | 아니요 |
| 전담 지원 엔지니어 | 별도의 계약에 따라 | 아니요 | 아니요 |

자세한 내용은 [지원 개요](/power-platform/admin/support-overview)를 참조하세요.

### <a name="process-to-engage-support"></a>지원 참여 프로세스

재무 및 운영 앱과 관련된 인시던트의 경우 고객은 LCS를 통해 Microsoft에 지원 티켓을 제출합니다. CSS는 고객의 지원 계획과 CSS에서 지정한 사고의 심각도에 따라 사고를 처리합니다.

### <a name="service-level-agreement"></a>서비스 수준 계약

Microsoft는 매월 99.9%의 서비스 가용성을 약속합니다. Microsoft가 SLA(서비스 수준 계약)에 설명된 대로 해당 서비스에 대한 서비스 수준을 달성 및 유지하지 못하는 경우 고객은 해당 서비스에 대한 월별 서비스 요금의 일부에 대한 크레딧을 받을 수 있습니다. 서비스 크레딧을 시작하는 방법에 대한 정보는 [SLA](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services)의 "클레임" 섹션을 참조하세요.

## <a name="important-resources"></a>중요한 리소스

- **[신뢰 센터](https://www.microsoft.com/trust-center)** – 재무 및 운영 데이터가 저장된 위치에 대한 정보와 개인 정보 보호, 규정 준수 및 보안 절차에 대한 추가 정보를 얻으세요.
- **[라이선스 조건 및 문서](https://www.microsoftvolumelicensing.com/)** – Microsoft 볼륨 라이선스 프로그램을 통해 라이선스가 부여된 제품 및 서비스의 사용과 관련된 라이선스 조건, 추가 정보에 빠르게 액세스합니다.
- **[라이선스 조건](https://www.microsoft.com/licensing/product-licensing/)** – 이 페이지의 리소스는 Microsoft 상용 라이선스 프로그램을 통해 구매하는 소프트웨어 및 온라인 서비스 제품에 대한 조건을 정의합니다.
- **[Microsoft 수명 주기 정책](/lifecycle/)** – 이 페이지는 제품 수명 동안 지원 가용성에 대한 일관되고 예측 가능한 지침을 제공합니다.
- **[라이선스 가이드](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365)** – 이 가이드를 사용하여 Dynamics 365 라이선스 방법에 대해 자세히 알아보세요.
- **[고객 지원](https://dynamics.microsoft.com/support/)** – Dynamics 365 앱에 대한 업계 최고의 지원을 받으세요.
- **[Dynamics Lifecycle Services](https://lcs.dynamics.com/)** – 애플리케이션 수명 주기를 관리하고 예측 가능하고 반복 가능하며 고품질 구현으로 이동합니다.
- **[Dynamics 365 구현 가이드](https://aka.ms/D365ImplementationGuideFlip)** - Dynamics 365 구현 가이드는 시간 테스트를 거친 Success by Design을 문서화하고 원칙을 제시하고 Dynamics 365 솔루션을 설계, 구축, 테스트 및 배포하기 위한 규범적 지침을 제공합니다.

## <a name="definitions"></a>정의

### <a name="azure-region"></a>[Azure 지역](/azure/availability-zones/az-overview#regions)

하나 이상의 Azure 데이터 센터가 있는 지리적 지역입니다. 미국과 유럽이 그 예입니다.

### <a name="business-process-modeler-bpm"></a>[비즈니스 프로세스 모델러(BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md)

재무 및 운영 앱에서 지원되는 APQC(American Productivity & Quality Center)의 비즈니스 프로세스 정의를 사용하여 주어진 구현에 대한 적합성 분석을 완료하는 데 도움이 되는 LCS의 도구입니다.

### <a name="cloud-solution-provider"></a>클라우드 솔루션 제공업체

Microsoft Cloud 솔루션 공급자(CSP) 프로그램의 일부이며 고객에게 부가가치 클라우드 서비스, 지원, 하나의 인보이스 및 대규모 고객 관리를 제공하는 파트너입니다.

### <a name="customer"></a>고객

재무 및 운영 앱을 사용하고 Office 365의 테넌트로 대표되는 비즈니스 엔터티.

### <a name="development-environment"></a>개발 환경

확장을 개발하는 데 사용되는 비프로덕션 샌드박스 환경입니다. 고객은 이 환경을 LCS에서 자체 Azure 구독에 배포합니다. 이 환경은 데모, 교육 또는 기타 테스트 작업에도 사용할 수 있습니다. [Tier 1 샌드박스](../imp-lifecycle/environment-planning.md#tier-1-vs-tier-2-and-higher)라고도 합니다.

### <a name="downtime"></a>가동 중지 시간

Microsoft가 자동화된 상태 모니터링 및 시스템 로그에서 판단한 대로 만료되지 않은 플랫폼 또는 서비스 인프라의 오류로 인해 사용자가 로그인하거나 활성 테넌트에 액세스할 수 없는 기간입니다. 가동 중지 시간에는 예약된 가동 중지 시간, 서비스 추가 기능을 사용할 수 없는 경우, 서비스 수정으로 인해 서비스에 액세스할 수 없는 경우 또는 확장 단위 용량이 초과된 기간이 포함되지 않습니다.

### <a name="implementation-partner"></a>구현 파트너

고객이 재무 및 운영 솔루션을 사용자 지정, 구성, 구현 및 관리하기 위해 선택한 파트너입니다.

### <a name="incident"></a>인시던트

고객이 재무 및 운영 서비스를 사용하는 동안 발생하고 LCS를 통해 티켓을 제출하는 문제입니다.

### <a name="microsoft-customer-support-services-css"></a>Microsoft 고객 지원 서비스(CSS)

재무 및 운영 앱에 고품질 서비스를 제공하기 위해 전담하는 Microsoft 글로벌 지원 팀입니다.

### <a name="microsoft-dynamics-lifecycle-services-lcs"></a>Microsoft Dynamics Lifecycle Services(LCS)

평가판에서 구현, 후반 작업 관리 및 지원에 이르기까지 재무 및 운영 앱의 수명 주기 관리를 위한 관리 포털입니다. 자세한 내용은 [Lifecycle Services 리소스](../../dev-itpro/lifecycle-services/lcs.md)를 참조하세요.

### <a name="non-production-instance"></a>비프로덕션 인스턴스

고객이 확장을 확인하고 기타 개발 작업을 수행하는 데 사용하는 다음 서비스 인스턴스:

- **샌드박스 계층 1** – 개발자 인스턴스(고객 호스팅)
- **샌드박스 티어 2** – 표준 승인 테스트 인스턴스
- **샌드박스 계층 3–5** – 애드온 샌드박스

2~5단계에 대한 자세한 내용은 [올바른 Tier-2 이상 환경 선택](../imp-lifecycle/environment-planning.md#selecting-the-correct-tier-2-or-higher-environment)을 참조하세요.

### <a name="production-instance"></a>프로덕션 인스턴스

고객이 "실시간" 일일 트랜잭션 및 비즈니스 프로세스를 관리하는 데 사용하는 재무 및 운영 환경입니다.

### <a name="sandbox-environment"></a>샌드박스 환경

고객이 데모, 교육, 사용자 승인 테스트, 확장 검증 및 기타 테스트 작업에 사용하는 비프로덕션 환경입니다.

### <a name="service"></a>서비스

재무 및 운영 앱에 포함된 모든 핵심 서비스.

### <a name="service-level-agreement-sla-for-microsoft-online-services"></a>Microsoft 온라인 서비스용 Service Level Agreement(SLA)

SLA는 Microsoft 온라인 서비스에 적용됩니다. 자세한 내용은 [Service Level Agreement(서비스 수준 약정)](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services)을 참조하세요.

### <a name="service-update"></a>서비스 업데이트

Microsoft는 서비스 업데이트를 통해 지속적으로 재무 및 운영 환경에 서비스를 제공합니다. 고객은 비즈니스 요구 사항에 따라 자체 서비스 업데이트 일정을 설정합니다. 자세한 내용은 [단일 버전 서비스 업데이트](../../dev-itpro/lifecycle-services/oneversion-overview.md)를 참조하세요.

### <a name="success-by-design"></a>[Success by Design](/dynamics365/fasttrack/success-by-design-overview)

Dynamics 365 솔루션에 대한 최적의 아키텍처, 보안, 성능 및 사용자 경험을 보장하기 위해 중요한 단계에서 일련의 평가를 통해 구현을 체계적으로 안내하는 프레임워크입니다.

### <a name="user"></a>사용자

재무 및 운영 환경을 사용하고 고객의 테넌트와 연결된 한 사람입니다.
