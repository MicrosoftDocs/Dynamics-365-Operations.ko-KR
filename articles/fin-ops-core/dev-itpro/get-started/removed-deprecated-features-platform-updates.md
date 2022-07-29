---
title: 제거되거나 더 이상 사용되지 않는 플랫폼 기능
description: 이 항목에서는 제거되었거나 금융 및 운영 앱의 플랫폼 업데이트에서 제거될 예정인 기능에 대해 설명합니다.
author: sericks007
ms.date: 03/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 27be0e720b7eca5883c5d73dfe312c09fcd22c65
ms.sourcegitcommit: ddcab9726e9dbcf3296cb0988b97a3ae7ccb3dfb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2022
ms.locfileid: "8460788"
---
# <a name="removed-or-deprecated-platform-features"></a>제거되거나 더 이상 사용되지 않는 플랫폼 기능

[!include [banner](../includes/banner.md)]

이 항목에서는 제거되었거나 금융 및 운영 앱의 플랫폼 업데이트에서 제거될 예정인 기능에 대해 설명합니다.

- *제거된* 기능은 더 이상 제품에서 사용할 수 없습니다.
- *더 이상 사용되지 않는* 기능은 현재 개발 중이 아니며 향후 업데이트에서 제거될 수 있습니다.

이 목록은 자체 계획을 위해 이러한 제거 및 사용 중단을 고려하는 데 도움을 주기 위한 것입니다. 

재무 및 운영 앱의 개체에 대한 자세한 정보는 [기술 참조 보고서](/dynamics/s-e/global/axtechrefrep_61)에서 찾을 수 있습니다. 이러한 보고서의 여러 버전을 비교하여 각 버전의 재무 및 작동 앱에서 변경되거나 제거된 개체에 대해 알아볼 수 있습니다.

## <a name="feature-removal-effective-march-14-2022"></a>2022년 3월 14일부터 기능 제거

### <a name="xslt-scripting-in-data-management"></a>데이터 관리의 XSLT 스크립팅

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 데이터 관리에서 XSLT 스크립팅에 대한 지원은 재무 및 운영 앱 내에서 보안 및 데이터 보호를 개선하기 위해 더 이상 사용되지 않습니다.  |
| **다른 기능으로 대체되었습니까?**   | 아니요. 고객과 ISV는 XSLT 스크립팅 대신 X++ 언어를 기반으로 솔루션을 다시 구현하는 것을 고려해야 합니다. |
| **영향을 받는 제품 영역**         | 금융 및 운영 앱. |
| **배포 옵션**              | 모두. |
| **상태**                         | 더 이상 사용되지 않음 - 계획된 제거 날짜는 2022년 3월 14일입니다.<br><br>예외: 현재 XLST 스크립팅을 사용 중인 고객. 버전 10.0.30 이상으로 업데이트할 때까지 계속 사용할 수 있습니다. 이 예외가 있는 고객은 Microsoft 365 관리 센터의 메시지 센터에서 알림을 받았습니다. |

## <a name="feature-removal-effective-october-2021"></a>2021년 10월부터 기능 제거

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Lifecycle Services(LCS)의 Microsoft Azure SQL 보고서

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 모든 활동과 모니터링은 자동화를 통해 플랫폼에서 내부적으로 수행됩니다. 수동 개입이 필요하지 않습니다.|
| **다른 기능으로 대체되었습니까?**   | 예, 이제 이러한 기능을 쓸모없게 만드는 자동화된 시스템이 있습니다. |
| **영향을 받는 제품 영역**         | SQL 보고서: 현재 DTU, 현재 DTU 세부 정보, 잠금 세부 정보 가져오기, 현재 계획 가이드 목록, 쿼리 ID 목록 가져오기, 주어진 계획 ID에 대한 SQL 쿼리 계획 가져오기, 쿼리 계획 및 실행 상태 가져오기, 스로틀 구성 가져오기, 대기 가져오기 통계, 가장 비싼 쿼리 나열 |
| **배포 옵션**              | 클라우드 배포: Microsoft 관리 프로덕션 환경과 Tier 2~Tier 5 샌드박스 환경에 영향을 줍니다. |
| **상태**                         | 삭제됨 |

### <a name="azure-sql-actions-in-lcs"></a>LCS의 Azure SQL 작업

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | LCS에서 일부 SQL 작업을 더 이상 사용하지 않습니다. 모든 활동과 모니터링은 자동화를 통해 플랫폼에서 내부적으로 수행됩니다. 수동 개입이 필요하지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | 예, 이제 이러한 기능을 쓸모없게 만드는 자동화된 시스템이 있습니다. |
| **영향을 받는 제품 영역**         | SQL 작업: 계획 ID를 강제 적용하기 위한 계획 지침 만들기, 테이블 힌트를 추가하기 위한 계획 지침 만들기, 계획 지침 제거, 페이지 잠금 및 잠금 에스컬레이션 비활성화/활성화, 테이블에 대한 통계 업데이트, 인덱스 다시 작성, 인덱스 만들기 |
| **배포 옵션**              | 클라우드 배포: Microsoft 관리 프로덕션 환경과 Tier 2~Tier 5 샌드박스 환경에 영향을 줍니다. |
| **상태**                         | 삭제됨 |


## <a name="feature-deprecation-effective-october-2021"></a>2021년 10월부터 기능 지원 중단

### <a name="show-related-document-attachments-feature"></a>"관련 문서 첨부 파일 표시" 기능

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 기능이 예기치 않은 결과를 반환했습니다. |
| **다른 기능으로 대체되었습니까?**   | 아니요. 이 기능에 대한 추가 계획은 표준 릴리스 웨이브 공개 프로세스를 통해 전달됩니다. |
| **영향을 받는 제품 영역**         | 웹 클라이언트 - 문서 첨부 경험 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음  |

## <a name="platform-updates-for-version-10023-of-finance-and-operations-apps"></a>금융 및 운영 앱 버전 10.0.23의 플랫폼 업데이트

### <a name="ondbsynchronize-event"></a>OnDBSynchronize 이벤트

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 이 이벤트를 실행할 컨트롤이 없습니다. |
| **다른 기능으로 대체되었습니까?**   | 예, **OnDB동기화** 이벤트를 구독하는 기존 메서드를 SysSetup 확장 클래스로 이동합니다. |
| **영향을 받는 제품 영역**         | 데이터베이스 동기화 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음. 계획된 제거 날짜는 2022년 10월입니다. |


### <a name="systemnotificationsmanageraddnotification-api"></a>SystemNotificationsManager.AddNotification API

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | Microsoft는 알림을 추가할 때 추가 매개변수를 요구합니다. |
| **다른 기능으로 대체되었습니까?**   | 예, **SystemNotificationsManager.AddSystemNotification()** API. 이 API를 사용하려면 생성된 알림에 대해 ExpirationDateTime 및 RuleID를 명시적으로 설정해야 합니다. |
| **영향을 받는 제품 영역**         | 웹 클라이언트 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음. 계획된 제거 날짜는 2023년 4월입니다. |

## <a name="platform-updates-for-version-10021-of-finance-and-operations-apps"></a>금융 및 운영 앱 버전 10.0.21의 플랫폼 업데이트

### <a name="skype-for-business-online-support"></a>비즈니스용 Skype Online 지원

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 비즈니스용 Skype Online이 사용 중지되었습니다. 자세한 내용은 [비즈니스용 Skype Online 서비스가 중단되었습니다](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/the-skype-for-business-online-service-has-retired/ba-p/2596601)를 참조하세요. |
| **다른 기능으로 대체되었습니까?**   | 현재는 아니지만 향후 Teams에서 존재감을 추가하는 것을 고려할 수 있습니다.|
| **영향을 받는 제품 영역**         | 웹 클라이언트 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음. **스카이프 활성화** 설정은 릴리스 10.0.21부터 꺼져 있습니다. 이 설정의 제거는 2022년 4월을 목표로 합니다. 그러나 Skype 팀이 서비스를 종료한 후에는 기능이 중지됩니다. |
 
## <a name="feature-deprecation-effective-august-2021"></a>2021년 8월부터 기능 지원 중단

### <a name="microsoft-azure-sql-reports-in-lifecycle-services-lcs"></a>Lifecycle Services(LCS)의 Microsoft Azure SQL 보고서

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 모든 활동과 모니터링은 자동화를 통해 플랫폼에서 내부적으로 수행됩니다. 수동 개입이 필요하지 않습니다.|
| **다른 기능으로 대체되었습니까?**   | 예, 이제 이러한 기능을 쓸모없게 만드는 자동화된 시스템이 있습니다. |
| **영향을 받는 제품 영역**         | SQL 보고서: 현재 DTU, 현재 DTU 세부 정보, 잠금 세부 정보 가져오기, 현재 계획 가이드 목록, 쿼리 ID 목록 가져오기, 주어진 계획 ID에 대한 SQL 쿼리 계획 가져오기, 쿼리 계획 및 실행 상태 가져오기, 스로틀 구성 가져오기, 대기 가져오기 통계, 가장 비싼 쿼리 나열 |
| **배포 옵션**              | 클라우드 배포: Microsoft 관리 프로덕션 환경과 Tier 2~Tier 5 샌드박스 환경에 영향을 줍니다. |
| **상태**                         | 사용되지 않음: 계획된 제거 날짜는 2021년 10월입니다. |

### <a name="azure-sql-actions-in-lcs"></a>LCS의 Azure SQL 작업

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | LCS에서 일부 SQL 작업을 더 이상 사용하지 않습니다. 모든 활동과 모니터링은 자동화를 통해 플랫폼에서 내부적으로 수행됩니다. 수동 개입이 필요하지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | 예, 이제 이러한 기능을 쓸모없게 만드는 자동화된 시스템이 있습니다. |
| **영향을 받는 제품 영역**         | SQL 작업: 계획 ID를 강제 적용하기 위한 계획 지침 만들기, 테이블 힌트를 추가하기 위한 계획 지침 만들기, 계획 지침 제거, 페이지 잠금 및 잠금 에스컬레이션 비활성화/활성화, 테이블에 대한 통계 업데이트, 인덱스 다시 작성, 인덱스 만들기 |
| **배포 옵션**              | 클라우드 배포: Microsoft 관리 프로덕션 환경과 Tier 2~Tier 5 샌드박스 환경에 영향을 줍니다. |
| **상태**                         | 사용되지 않음: 계획된 제거 날짜는 2021년 10월입니다. |

## <a name="feature-deprecation-effective-may-2021"></a>2021년 5월부터 기능 지원 중단

### <a name="globalization-portal-in-lifecycle-services-lcs"></a>LCS(Lifecycle Services)의 세계화 포털

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 이 기능이 다른 LCS 기반 서비스로 대체되었으므로 LCS에서 세계화 포털을 더 이상 사용하지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | 예, 이 기능은 LCS [문제 검색](../lifecycle-services/issue-search-lcs.md) 및 [Dynamics 규제 경고 제출 서비스](../lcs-solutions/submit-localization-alerts.md)로 대체되었습니다. |
| **영향을 받는 제품 영역**         | LCS의 세계화 포털|
| **배포 옵션**              | 클라우드 배포 |
| **상태**                         | 사용되지 않음: 계획된 제거 날짜는 2022년 5월입니다. |


## <a name="feature-removed-effective-january-28-2021"></a>2021년 1월 28일부터 기능이 제거됨

### <a name="batch-job-to-handle-sql-index-defragmentation"></a>SQL 인덱스 조각 모음을 처리하는 일괄 작업

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 고객의 인덱스 관리 운영, 모니터링 및 유지 관리의 오버헤드를 줄이기 위해 이 기능을 제거했습니다. |
| **다른 기능으로 대체되었습니까?**   | 앞으로 인덱스 유지 관리는 Microsoft 서비스에서 수행됩니다. 이는 사용자 워크로드에 영향을 주지 않고 지속적으로 발생합니다. |
| **영향을 받는 제품 영역**         | 금융 및 운영 앱|
| **배포 옵션**              | 클라우드 배포 - Microsoft 관리 프로덕션 환경과 Tier 2~Tier 5 샌드박스 환경에 영향을 줍니다. |
| **상태**                         | 이 기능은 제거되었습니다. |


## <a name="platform-updates-for-version-10017-of-finance-and-operations-apps"></a>금융 및 운영 앱 버전 10.0.17의 플랫폼 업데이트


### <a name="visual-studio-2015"></a>Visual Studio 2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | Visual Studio의 최신 버전을 지원하려면 Visual Studio에 대한 X++ 확장을 일부 변경해야 합니다. 이러한 변경 사항은 Visual Studio 2015와 호환되지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | Visual Studio 2017이 Visual Studio 2015를 배포 및 필수 버전으로 대체합니다. |
| **영향을 받는 제품 영역**         | Visual Studio 개발 도구 |
| **배포 옵션**              | 모두 |
| **상태**                         | 더 이상 사용되지 않음: 업데이트 시 이전 X++ 도구는 Visual Studio 2015에서 제거되고 업데이트된 도구는 Visual Studio 2015에 설치되지 않습니다. 호스팅된 빌드에는 영향이 없습니다. [Azure Pipelines에서 레거시 파이프라인 업데이트](../dev-tools/pipeline-msbuild-update.md)에 설명된 대로 빌드 가상 머신의 경우 빌드 파이프라인(빌드 정의)을 수동으로 업데이트하여 MSBuild 14.0(Visual Studio 2015)에서 MSBuild 15.0(Visual Studio 2017)으로 종속성을 변경합니다. |

### <a name="user-avatar"></a>사용자 아바타 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 탐색 모음의 오른쪽에 표시되는 사용자 아바타는 더 이상 사용되지 않는 Dynamics 365 헤더 컨트롤의 API를 사용하여 검색했습니다. |
| **다른 기능으로 대체되었습니까?**   | 대신 탐색 모음의 원 안에 이니셜이 표시됩니다. 이것은 현재 개발 머신에서 사용되는 것과 동일한 비주얼입니다. |
| **영향을 받는 제품 영역**         | 웹 클라이언트 |
| **배포 옵션**              | 모두 |
| **상태**                         | 버전 10.0.17에서 제거됨 |

### <a name="enterprise-portal-ep-deprecation"></a>Enterprise Portal(EP) 지원 중단  

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | Dynamics AX 2012 Enterprise Portal(EP)과 관련된 메타데이터 아티팩트는 재무 및 운영 앱에서 EP가 지원되지 않았기 때문에 더 이상 사용되지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | 아니요 |
| **영향을 받는 제품 영역**         | 웹 클라이언트 |
| **배포 옵션**              | 모두 |
| **상태**                         | 더 이상 사용되지 않음: 모든 EP 코드는 2021년 10월 릴리스에서 제거될 예정입니다. |

## <a name="deprecation-effective-december-2020"></a>2020년 12월부터 지원 중단

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Dynamics 365에 대한 Internet Explorer 11 지원은 더 이상 사용되지 않습니다

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 2020년 12월부터 모든 Dynamics 365 제품 및 Dynamics Lifecycle Services(LCS)에 대한 Microsoft Internet Explorer 11 지원은 더 이상 사용되지 않으며 Internet Explorer 11은 2021년 8월 이후에 지원되지 않습니다.<br><br>이는 Internet Explorer 11 인터페이스를 통해 사용하도록 설계된 Dynamics 365 제품 및 LCS를 사용하는 고객에게 영향을 미칩니다. 2021년 8월 이후에는 이러한 Dynamics 365 제품 및 LCS에 대해 Internet Explorer 11이 지원되지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | 고객은 Microsoft Edge로 전환하는 것이 좋습니다.|
| **영향을 받는 제품 영역**         | 모든 Dynamics 365 제품 및 LCS |
| **배포 옵션**              | 모두|
| **상태**                         | 사용되지 않음: Internet Explorer 11은 2021년 8월 이후에 지원되지 않습니다.|

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>금융 및 운영 앱 버전 10.0.15의 플랫폼 업데이트

### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>메타데이터 핫픽스를 적용하는 Visual Studio 추가 기능

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 메타데이터 핫픽스는 2018년 7월 버전 8.1과 함께 도입된 [하나의 버전](../../fin-ops/get-started/one-version.md) 서비스에 더 이상 지원되지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | 지원되는 버전에는 개별 메타데이터 핫픽스를 사용할 수 없습니다. 누적 품질 업데이트가 대신 적용됩니다. |
| **영향을 받는 제품 영역**         | Visual Studio 추가 기능 |
| **배포 옵션**              | 개발 가상 머신 |
| **상태**                         | 버전 10.0.15에서는 추가 기능이 더 이상 Visual Studio 도구에 포함되지 않습니다. |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>금융 및 운영 앱 버전 10.0.14의 플랫폼 업데이트

### <a name="online-users-page"></a>온라인 사용자 페이지 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 이것은 이전 클라이언트/서버 아키텍처를 위해 구축된 레거시 페이지입니다. 이 페이지의 정보가 항상 정확한 것은 아니므로 혼동과 오해의 소지가 있습니다. |
| **다른 기능으로 대체되었습니까?**   | 향후 업데이트에서 새로운 페이지를 제공하겠습니다.|
| **영향을 받는 제품 영역**         | 시스템 관리 |
| **배포 옵션**              | 모두 |
| **상태**                         | 2021년 10월까지 이 양식은 제거됩니다.   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>금융 및 운영 앱 버전 10.0.13의 플랫폼 업데이트


### <a name="custom-code-defined-in-ssrs-report-properties"></a>SSRS 보고서 속성에 정의된 사용자 지정 코드 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 일반적으로 사용자 지정 코드는 제한된 이점을 제공하는 동시에 지원하려면 상당한 리소스와 컴퓨팅이 필요합니다. 사용자 지정 코드는 보고서 작성자가 사용자 지정 코드 어셈블리에서 공용 메서드를 호출하는 데 주로 사용됩니다. 그러나 클라우드 호스팅 서비스는 SSRS 보고서에 대한 사용자 지정 어셈블리에 대한 참조를 지원하지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | 보고서 작성자는 모든 텍스트 상자 식에서 수학, 변환 및 형식 작업에 대한 공용 .NET API를 계속 참조하도록 선택할 수 있습니다. 자세한 내용은 [보고서에 코드 추가(SSRS)](/sql/reporting-services/report-design/add-code-to-a-report-ssrs)를 참조하세요.  |
| **영향을 받는 제품 영역**         | 사용자 지정 코드를 포함하는 RDL에 정의된 애플리케이션 보고서 디자인의 하위 집합입니다. |
| **배포 옵션**              | 모두 |
| **상태**                         | 버전 10.0.13에서 컴파일러는 SSRS 보고서 정의에서 사용자 지정 코드가 감지되는 인스턴스에 대해 경고를 발행하기 시작합니다. 문제를 해결하려면 보고서 디자인 정의를 열고 모든 사용자 지정 코드 아티팩트를 제거합니다. 이 경고는 향후 업데이트에서 컴파일러 오류로 대체됩니다.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>세 가지 jQuery 구성 요소 라이브러리의 업그레이드 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 보안 수정 및 최신 버전 유지를 위해 3개의 jQuery 구성 요소 라이브러리가 업데이트되고 있습니다.   
| **다른 기능으로 대체되었습니까?**   | 영향을 받는 라이브러리: jQuery(버전 2.1.4에서 버전 3.5.0으로), jQuery UI(버전 1.11.4에서 버전 1.12.1로), jQuery qTip(2.2.1에서 버전 3.0.3으로). 마이그레이션 지침은 jQuery에서 온라인으로 제공되었습니다.  |
| **영향을 받는 제품 영역**         | 확장 가능한 컨트롤, 특히 더 이상 사용되지 않거나 제거된 API를 활용하는 사용자 지정 JavaScript 코드 |
| **배포 옵션**              | 모두 |
| **상태**                         | 버전 10.0.13/플랫폼 업데이트 37을 통해 고객은 "3개의 jQuery 구성 요소 라이브러리 업그레이드" 기능을 활성화하여 선택적으로 최신 라이브러리로 이동할 수 있습니다. 영향을 받는 API의 마이그레이션을 위한 시간을 허용하기 위해 2021년 4월 릴리스에서는 새 라이브러리로의 이동이 필수입니다.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>기존 그리드 제어/forceLegacyGrid() API

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 기존 그리드 컨트롤이 새 그리드 컨트롤로 대체됩니다. |
| **다른 기능으로 대체되었습니까?**   | [새로운 그리드 컨트롤](../..//fin-ops/get-started/grid-capabilities.md) |
| **영향을 받는 제품 영역**         | 웹 클라이언트 |
| **배포 옵션**              | 모두 |
| **상태**                         | 버전 10.0.13에서 새 그리드 컨트롤이 일반적으로 사용 가능하며 고객은 선택적으로 이 기능을 켤 수 있습니다. 새로운 그리드 제어는 2021년 10월 릴리스와 함께 기본적으로 설정되며 현재 2022년 4월에 필수로 설정될 예정입니다. 새로운 그리드 컨트롤이 필수가 되면 **forceLegacyGrid()** API는 더 이상 인정되지 않습니다. |

### <a name="personalization-without-saved-views"></a>저장된 보기가 없는 개인화 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 개인화 하위 시스템은 저장된 보기 기능으로 정밀 검사되어 더 나은 성능과 추가 기능을 제공합니다. |
| **다른 기능으로 대체되었습니까?**   | 저장된 보기 |
| **영향을 받는 제품 영역**         | 웹 클라이언트 |
| **배포 옵션**              | 모두 |
| **상태**                         | 10.0.13/플랫폼 업데이트 37 버전에서는 저장된 보기 기능이 일반 공급되며 고객은 선택적으로 이 기능을 켤 수 있습니다. 저장된 보기 기능은 2021년 10월 릴리스에서 필수가 됩니다. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>금융 및 운영 앱 버전 10.0.12의 플랫폼 업데이트

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>잘못된 필드 참조가 포함된 그리드 또는 그룹 제어 양식 확장

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 그리드 또는 그룹 컨트롤의 데이터 그룹 속성은 필드 그룹의 모든 필드를 자동으로 표시하는 데 사용됩니다. 확장에 의해 추가된 그리드 또는 그룹 컨트롤에는 더 이상 필드 그룹에 정의되지 않은 필드가 포함되거나 필드 그룹에 정의된 누락된 필드가 있을 수 있습니다. 이로 인해 런타임에 일관되지 않은 동작이 발생할 수 있습니다. 재무 및 운영 앱 버전 10.0.12에 대한 플랫폼 업데이트는 이제 이 문제를 컴파일러 *경고* 로 분류합니다. 이 문제를 해결하려면 양식 확장을 열고 저장하세요.
| **다른 기능으로 대체되었습니까?**   | 이 컴파일러 경고는 향후 업데이트에서 컴파일러 오류로 대체됩니다. |
| **영향을 받는 제품 영역**         | Visual Studio 개발 도구 |
| **배포 옵션**              | 모두 |
| **상태**                         | 컴파일러 경고는 금융 및 운영 앱 버전 10.0.12에 대한 플랫폼 업데이트에 포함됩니다. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>금융 및 운영 앱 버전 10.0.11의 플랫폼 업데이트

### <a name="explicit-safe-lists-for-self-service-environments"></a>셀프 서비스 환경에 대한 명시적 허용 목록

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | IP를 수신 허용 목록으로 이동하는 프로세스가 변경되었습니다. 셀프 서비스는 더 이상 IP 수신 허용 목록을 지원하지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | 자세한 내용은 [Azure Active Directory 조건부 액세스 구성](/appcenter/general/configuring-aad-conditional-access)을 참조하세요.|
| **영향을 받는 제품 영역**         | 보안 |
| **배포 옵션**              | 클라우드 |
| **상태**                         | 더 이상 사용되지 않음: 이 기능은 셀프 서비스 배포에 대해 완전히 사용되지 않습니다. |

### <a name="visual-studio-2015"></a>Visual Studio 2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | Visual Studio의 최신 버전을 지원하려면 Visual Studio에 대한 X++ 확장을 일부 변경해야 합니다. 이러한 변경 사항은 Visual Studio 2015와 호환되지 않습니다. |
| **다른 기능으로 대체되었습니까?**   | Visual Studio 2017이 Visual Studio 2015를 배포 및 필수 버전으로 대체합니다. |
| **영향을 받는 제품 영역**         | Visual Studio 개발 도구 |
| **배포 옵션**              | 모두 |
| **상태**                         | 버전 10.0.13(플랫폼 업데이트 37) 이상에 배포된 가상 머신에는 Visual Studio 2017이 포함됩니다. 버전 10.0.16(플랫폼 업데이트 40)은 Visual Studio 2015를 지원하는 최종 릴리스입니다. Visual Studio 2015만 있는 가상 머신은 버전 10.0.17(플랫폼 업데이트 41)로 업데이트할 수 없습니다. |

### <a name="field-groups-containing-invalid-field-references"></a>잘못된 필드 참조가 포함된 필드 그룹

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 테이블 메타데이터 정의의 필드 그룹에는 유효하지 않은 필드 참조가 포함될 수 있습니다. 이러한 필드 그룹이 배포되면 Financial Reporting 및 Microsoft SQL Server 보고 서비스(SSRS)에서 런타임 오류가 발생할 수 있습니다. 플랫폼 업데이트 23에는 컴파일러 *경고* 가 도입되어, 이 메타데이터 문제를 해결할 수 있었습니다. 재무 및 운영 앱 버전 10.0.11에 대한 플랫폼 업데이트는 이제 이 문제를 컴파일러 *오류* 로 분류합니다.<p>이 문제를 해결하려면 다음 단계를 따르세요.</p><ol><li>테이블 필드 그룹 정의에서 잘못된 필드 참조를 제거하세요.</li><li>재컴파일.</li><li>오류가 해결되었는지 확인하세요.</li></ol> |
| **다른 기능으로 대체되었습니까?**   | 이 컴파일러 오류는 컴파일러 경고를 영구적으로 대체합니다.  |
| **영향을 받는 제품 영역**         | Visual Studio 개발 도구 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: 컴파일러 경고는 금융 및 운영 앱 버전 10.0.11에 대한 플랫폼 업데이트의 컴파일러 오류입니다. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>SHA1 해싱 알고리즘을 사용하여 생성된 ISV 라이선스

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | ISV(독립 소프트웨어 공급업체) 라이선스를 만드는 프로세스가 변경되었습니다. 자세한 내용은 [ISV(독립 소프트웨어 공급업체) 라이선스](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes)를 참조하세요. |
| **다른 기능으로 대체되었습니까?**   | 예. Windows PowerShell을 사용하여 라이선스를 만듭니다. |
| **영향을 받는 제품 영역**         | Visual Studio 개발 도구 |
| **배포 옵션**              | 모두 |
| **상태**                         | 사용되지 않음: SHA1 해싱 알고리즘을 사용하여 생성된 ISV 라이선스. 이 알고리즘은 MakeCert 유틸리티를 사용하여 만든 인증서에 의존하며 이 유틸리티는 더 이상 사용되지 않습니다.<br><br>더 이상 사용되지 않음: 보안 또는 해싱 목적으로 SHA1을 사용합니다. SHA1은 2021년 초에 기능이 중단됩니다. 따라서 더 이상 사용해서는 안됩니다.<br><br>제거됨: TLS(전송 계층 보안) 1.0 및 TLS 1.1 수신 또는 발신 요청에 대한 지원. |

## <a name="platform-update-32"></a>플랫폼 업데이트 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>워크플로 요청 변경 대화 상자에 더 이상 사용자 선택 드롭다운 목록이 포함되지 않습니다.

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 이는 변경 요청이 의도하지 않은 사용자에게 전송될 수 있기 때문에 보안 문제였습니다. 이는 사용자가 워크플로 작성자를 확인하고 수동으로 선택해야 했기 때문에 사용성 문제이기도 했습니다.  |
| **다른 기능으로 대체되었습니까?**   | 아니요 |
| **영향을 받는 제품 영역**         | 워크플로 |
| **배포 옵션**              | 모두 |
| **상태**                         | 플랫폼 업데이트 32의 변경 요청 대화 상자에서 사용자 선택 드롭다운 목록이 제거되었습니다. 요청 변경 요청은 의도한 대로 발신자에게 자동으로 전송됩니다. 이 기능에 대한 자세한 내용은 [워크플로 승인 프로세스의 작업](../../fin-ops/organization-administration/workflow-actions.md?toc=%2fdynamics365%2fcommerce%2ftoc.json#request-change)을 참조하세요. |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>포함된 드릴스루 링크는 클라우드 호스팅 서비스에서 렌더링된 페이지를 매긴 문서에서 더 이상 지원되지 않습니다. 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **지원 중단/제거 이유** | 서비스에서 렌더링된 문서에 포함된 탐색 URL에는 민감한 비즈니스 데이터가 포함될 수 있습니다. 고객 데이터를 더욱 보호하기 위한 보안 예방책으로 문서에 포함된 드릴스루 링크에 대한 지원을 제거하고 있습니다. 또한 사용자는 이러한 변경의 결과로 문서를 대화식으로 생성하면서 향상된 성능의 이점을 누릴 수 있습니다.  |
| **다른 기능으로 대체되었습니까?**   | 아니요 |
| **영향을 받는 제품 영역**         | 보고 |
| **배포 옵션**              | 모두 |
| **상태**                         | 이 기능은 서비스에서 적극적으로 제거되고 있습니다.<br><br>최신 클라이언트는 애플리케이션 탐색을 지원하기 위해 자동 생성된 링크를 포함하는 보기를 생성하기 위한 다양한 옵션을 제공합니다. 서비스에서 렌더링된 페이지를 매긴 문서는 수신자를 위해 전자 메일로 전송, 보관 및 인쇄되는 외부 커뮤니케이션에 권장됩니다. 로컬 프린터에 직접 액세스할 수 있는 브라우저에서 직접 문서를 미리 볼 수 있는 환경을 개선했습니다. 자세한 내용은 [내장된 뷰어로 PDF 문서 미리보기](../analytics/preview-pdf-documents.md)를 참조하세요. |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>제거되거나 더 이상 사용되지 않는 기능에 대한 이전 공지
이전 릴리스에서 제거되거나 더 이상 사용되지 않는 기능에 대한 자세한 내용은 [이전 릴리스에서 제거되거나 사용되지 않는 기능](../migration-upgrade/deprecated-features.md)을 참조하세요.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
