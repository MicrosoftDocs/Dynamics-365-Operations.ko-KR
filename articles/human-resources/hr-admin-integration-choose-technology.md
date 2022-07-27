---
title: 데이터 통합 기술 선택
description: 이 항목에서는 Human Resources가 관리하는 데이터와의 통합에 관한 정보를 제공합니다.
author: twheeloc
ms.date: 08/19/2021
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 24ddd242185d736287f61ec250c631ab65e08c95
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452092"
---
# <a name="choose-a-data-integration-technology"></a>데이터 통합 기술 선택


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources가 관리하는 데이터와의 통합에 관한 정보를 제공합니다. 요구 사항에 가장 적합한 기술을 결정하는 데 도움이 되는 다양한 통합 기술에 관해 설명합니다.

## <a name="data-integration-background"></a>데이터 통합 배경

비즈니스 데이터는 회사를 고유하게 만드는 핵심 자산입니다. 귀사의 비즈니스 데이터는 매우 중요합니다. 비즈니스 전반에 걸쳐 수집된 데이터 간의 관계를 사용하여 조직 전체의 비즈니스 프로세스와 비즈니스 인텔리전스를 개선할 수 있습니다. Microsoft는 시스템의 출처와 관계없이 비즈니스 데이터에 대해 쉽고 안전하며 안정적인 액세스를 제공하기 위해 노력하고 있습니다.

여러 시스템 간의 데이터 통합은 역사적으로 어려웠습니다. Microsoft는 데이터 통합을 더 쉽게 만들기 위해 노력하고 있으며 [Dataverse](/powerapps/maker/common-data-service/data-platform-intro)를 통해 그 목표를 향한 큰 진전을 이뤘습니다.

Human Resources는 Dataverse를 Human Resources 데이터에 대한 기본 공용 인터페이스로 만들고 있습니다. 시간이 지남에 따라 Human Resources가 관리하는 중요한 모든 데이터가 Dataverse에 노출될 것으로 예상됩니다. 대부분의 통합 애플리케이션에 대한 선택 기술로 Dataverse를 권장합니다.

Dataverse에는 애플리케이션에 필요한 모든 데이터가 아직 포함되어 있지 않을 수 있습니다. 또한 프로젝트 일정을 위해 대체 기술이 필요할 수 있음을 알고 있습니다. Dataverse로 통합 요구 사항을 충족할 수 없을 때는 저희에게 문의해 주세요.

## <a name="integration-technologies"></a>통합 기술

다음 섹션에서는 Human Resources와 함께 사용할 수 있는 다양한 데이터 통합 기술에 관해 설명합니다.

### <a name="dataverse-tables"></a>Dataverse 테이블

Dataverse는 Human Resources에서 선호되는 공개 데이터 인터페이스입니다. [Dynamics 365 Customer Engagement](/dynamics365/?panel=customer-engagement#pivot=business-apps) 솔루션에서 사용되는 Dynamics 365 XRM 플랫폼에서 파생되었습니다.

Dataverse는 데이터 테이블을 위한 플랫폼과 API를 제공합니다. Human Resources를 배포하면 Dataverse 인스턴스에 연결됩니다. Human Resources 데이터의 엔터티는 해당 Dataverse 인스턴스에 배포됩니다. 테이블과 해당 데이터는 Dataverse 인스턴스에 연결할 수 있는 모든 애플리케이션에서 사용할 수 있습니다. Human Resources는 Dataverse 테이블과 데이터를 주고받으며 동기화합니다.

> [!NOTE]
> Human Resources 엔터티는 Dataverse 테이블에 해당합니다. Dataverse(이전의 Common Data Service) 및 용어 업데이트에 대한 자세한 내용은 [Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)을 참조하세요.

앱 통합에 필요한 데이터 테이블이 Dataverse에 있으면 [Dataverse 및 이를 지원하는 API](/powerapps/?panel=developer#pivot=home)를 최대한 사용할 수 있습니다. 지원되는 API 중에는 Dataverse 데이터에 액세스하기 위한 OData 구현을 제공하는 [Dynamics 365 웹 API](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)가 있습니다.

Dataverse 테이블 및 관련 API는 웹 애플리케이션, 웹 서비스/API 및 OData 피드에 연결하는 기타 애플리케이션에서 Human Resources 데이터에 액세스하기 위한 최상의 옵션입니다.

> [!NOTE]
> Dataverse를 Human Resources를 위한 선호하는 데이터 인터페이스로 결정한 것이 비교적 최근이기 때문에 통합에 필요한 Human Resources 데이터 엔터티를 아직 Dataverse에서 사용하지 못할 수 있습니다.
> </br>
> Dataverse에서 사용할 수 있는 Human Resources 엔터티의 목록은 [Human Resources 및 Dataverse](/dynamics365/unified-operations/talent/corehrentities)를 참조하세요.
> </br>
> 통합에 필요한 Human Resources 엔터티를 아직 사용할 수 없는 경우 데이터 엔터티가 사용 가능해질 때까지 기다리거나 아래에 설명된 다른 통합 기술 중 하나를 사용해야 합니다.
> </br>
> 제공된 데모 데이터를 포함하지 않는 새로운 환경에는 기본적으로 Dataverse 통합이 꺼져 있습니다. 데모 데이터를 포함하는 새로운 환경에서 켜지고 환경이 프로비저닝될 때 데이터 동기화를 시작합니다. 환경이 데이터를 동기화할 준비가 되면 통합을 켤 수 있습니다.

### <a name="dmfdixf-entities"></a>DMF/DIXF 엔터티

주로 금융 및 운영 애플리케이션과 같은 플랫폼에 구축된 Human Resources는 [DMF(Data Management Framework)](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json)를 제공합니다. DMF는 DIXF(Data Import Export Framework)라고도 합니다. Human Resources는 Human Resources 데이터를 가져오고 내보내는 데 사용할 수 있는 데이터 엔터티 집합을 제공합니다. Dataverse 테이블은 Human Resources를 위한 선호되는 데이터 통합 인터페이스이지만 DMF 엔터티도 다음과 같은 일부 상황에서 여전히 유용합니다.

- Dataverse 테이블이 아직 없습니다.

- 통합에 고성능 대량 데이터 가져오기/내보내기 기능이 필요합니다.

> [!NOTE]
> Human Resources 엔터티는 Dataverse 테이블에 해당합니다. Dataverse(이전의 Common Data Service) 및 용어 업데이트에 대한 자세한 내용은 [Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)을 참조하세요.

DMF 엔터티는 현재 Human Resources 데이터에 대한 가장 완벽한 데이터 적용 범위를 제공합니다.

DMF는 사용자 인터페이스에서 즉각적인 사용자 피드백이 필요한 경우와 같은 실시간 통합에는 적합하지 않습니다. 패키지 작업은 예약된 일괄 작업이며 일괄 처리 서비스가 실행을 위해 작업을 선택하고 가져오기/내보내기 작업을 완료하는 데 필요한 시간에 더해 최소 1~2분의 대기 시간이 걸리는 경우가 많습니다.

DMF는 높은 처리량이 필요한 경우(예: 야간 예약으로 수천 개의 레코드 가져오기/내보내기) 최상의 옵션이 될 수 있습니다.

> [!NOTE]
> DMF는 Attract 및 Onboard에 사용할 수 없습니다.

### <a name="dmf-package-rest-api"></a>DMF 패키지 REST API

DMF는 데이터 패키지를 조작하기 위한 [REST API](/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api)를 제공합니다. 이 API를 사용하여 프로그래밍 방식으로 DMF와 상호 작용하여 다음과 같은 작업을 수행할 수 있습니다.

- 데이터 패키지 가져오기.

- 데이터 패키지 내보내기.

- 가져오기/내보내기 작업의 상태 확인.

DMF 패키지 REST API는 Human Resources에서 완전히 지원됩니다.

### <a name="azure-sql-db-byod"></a>Azure SQL DB(BYOD)

DMF는 Human Resources가 자체 Microsoft Azure SQL 데이터베이스로 데이터를 내보낼 수 있는 강력한 기능인 [BYOD(Bring Your Own Database)](/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database)를 추가로 제공합니다. 이 기능은 엄청난 유연성을 제공합니다. 데이터가 자체 SQL 데이터베이스에 있는 경우 SQL 데이터 저장소에 연결할 수 있는 모든 애플리케이션이나 미들웨어를 사용할 수 있습니다.

BYOD는 주로 읽기 전용 솔루션입니다. Azure SQL 데이터베이스에서 원하는 모든 데이터(예: 데이터 매시업을 위해)를 조작하고 저장할 수 있지만 Azure SQL 데이터베이스에 저장된 데이터는 Human Resources과 동기화되지 않습니다.

BYOD는 [Azure Data Factory](/azure/data-factory/) 파이프라인의 데이터 소스로 보고 솔루션, 데이터 통합, 데이터 매시업에 적합합니다.

> [!NOTE]
> BYOD는 Attract 및 Onboard에 사용할 수 없습니다.

### <a name="odata-enabled-entities"></a>OData 지원 엔터티

대부분의 DMF 엔터티는 Human Resources 데이터 서비스(OData)를 통해 액세스할 수도 있습니다. [금융 및 운영 OData 서비스](/dynamics365/unified-operations/dev-itpro/data-entities/odata)에 대해 제공된 문서는 OData에 노출된 고유한 엔터티 생성을 제외하고 Human Resources에 적용됩니다.

Human Resources 데이터 서비스보다 Dataverse 및 Dataverse가 [Dynamics 365 웹 API](/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8))를 통해 제공하는 OData 구현이 더 선호되지만 Human Resources 데이터 서비스는 Human Resources 데이터에 대한 더 완전한 엔터티 적용 범위를 가지고 있습니다.

### <a name="excel-add-in"></a>Excel 추가 기능

[Excel 추가 기능](/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=%2fdynamics365%2funified-operations%2ftalent%2ftoc.json)은 내부적으로 OData 지원 엔터티를 사용합니다. 최종 사용자가 친숙한 Excel UI로 Human Resources 데이터를 검색하고 수정할 수 있는 편리한 방법을 제공합니다.

Excel 추가 기능은 비즈니스 도메인 전문가의 임시 데이터 가져오기/내보내기 작업에 적합합니다. 프로그래밍 방식의 자동화가 필요한 정기 데이터 통합의 경우 다른 통합 기술이 더 적절할 것입니다.

### <a name="data-integrator"></a>데이터 통합자

[데이터 통합자 서비스](/powerapps/administrator/data-integrator)를 사용하여 Dataverse의 데이터를 통합할 수 있습니다. 데이터 통합자를 사용하면 애플리케이션 개발자가 특정 통합에 맞게 조정한 미리 정의된 템플릿을 기반으로 하는 통합 프로젝트를 정의할 수 있습니다. 정기 일정에 따라 자동으로 실행되도록 통합 프로젝트를 예약하거나 수동으로 실행할 수 있습니다.

데이터 통합자 프로젝트는 Dataverse 일괄 처리 통합에 적합합니다. Dynamics 365 애플리케이션 제품군 간의 통합에 탁월한 선택입니다. 예를 들어 Microsoft는 Human Resources의 데이터를 Dynamics 365 Finance로 통합하기 위한 데이터 통합자 템플릿을 제공합니다. 템플릿에 대한 자세한 내용은 [Dynamics 365 Human Resources에서 Dynamics 365 Finance로 통합](hr-admin-integration-finance.md)을 참조하세요.

### <a name="power-query"></a>Power Query

데이터 통합자는 자체 [고급 쿼리 기능](/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering)을 통해 [Power Query](/power-query/power-query-what-is-power-query)를 지원합니다. Power Query는 풍부한 M 공식 언어를 포함하여 강력하고 유연한 데이터 필터링과 변환을 제공합니다. Power BI 보고서를 개발했다면 Power Query가 익숙할 것입니다.

## <a name="deciding-on-an-integration-technology"></a>통합 기술 결정

사용할 수 있는 통합 기술이 너무 많으므로 때로는 사용할 통합 접근 방식을 결정하기가 부담스러울 수 있습니다. Dataverse의 데이터 적용 범위가 확장됨에 따라 결정이 더 쉬워질 것이며 대부분은 Dataverse가 선호되는 데이터 인터페이스입니다. 그러나 그때까지는 Dataverse가 요구를 충족하지 못할 수 있습니다. 다음 표에는 통합 기술 옵션의 몇 가지 주요 특성이 요약되어 있습니다.

| 기술/도구/API    | 정기 통합                   | 동기/비동기                    | API를 통한 프로그래밍 방식 액세스        | 적절한 데이터 볼륨                                   | 데이터 적용 범위                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Dataverse 테이블           | 예, 데이터 통합자 또는 미들웨어 사용 | 동기/비동기, 일괄 처리(데이터 통합자 사용) | 예, Dynamics 365 웹 API(OData)를 통해 | 사용 사례에 따라 다름(대화형 사용을 위한 페이징 지원) | 개선 중<sup>2</sup>                       |
| DMF 엔터티           | 예, 미들웨어를 통해 예약됨        | 비동기, 일괄 처리                                | 예, DMF 패키지 REST API를 통해         | 높음(수십만 개의 레코드)                    | 높음                                |
| DMF 패키지 REST API   | 예, 미들웨어를 통해 예약됨        | 비동기, 일괄 처리                                | 예                                       | 높음(수십만 개의 레코드)                    | API가 모든 DMF 엔터티 지원       |
| BYOD                   | 예, Human Resources에서 관리자가 예약        | 비동기, 일괄 처리                                | 아니요<sup>3</sup>                                    | 높음(수십만 개의 레코드)                    | 모든 DMF 엔터티 지원           |
| OData 지원 엔터티 | 예, 미들웨어 사용                    | 동기화                                        | 예, Human Resources 데이터 서비스(OData)를 통해  | 사용 사례에 따라 다름(대화형 사용을 위한 페이징 지원) | 높음                                |
| Excel 추가 기능           | 아니요                                       | 동기화                                        | 아니요                                        | 중간(수만 개의 레코드)                      | 모든 OData 지원 엔터티 지원 |
| 데이터 통합자        | 예, 데이터 통합자에서 예약됨        | 비동기, 일괄 처리                                | 아니요                                        | 사용 사례에 따라 다름                                       | 모든 Dataverse 테이블 지원           |

<sup>2</sup>Microsoft는 Dataverse 테이블의 데이터 적용 범위를 늘리기 위해 크게 투자하고 있습니다. 적용 범위가 가능한 경우 Dataverse를 사용하는 것이 좋습니다. 현재 Dataverse 데이터 적용 범위는 DMF 및 OData 지원 엔터티보다 작습니다.

<sup>3</sup>SQL 데이터베이스는 프로그래밍 방식으로 액세스할 수 있습니다.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
