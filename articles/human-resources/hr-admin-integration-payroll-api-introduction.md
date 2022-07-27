---
title: 급여 통합 API 소개
description: 이 항목에서는 Dynamics 365 Human Resources 급여 통합 API에 관해 설명합니다.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4c71d31d7045c73097b81671793181a29dcac3b5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452080"
---
# <a name="payroll-integration-api-introduction"></a>급여 통합 API 소개


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 문서에서는 Dynamics 365 Human Resources 급여 통합 API에 관해 설명합니다. API는 Human Resources와 파트너 급여 시스템 간의 능률적인 엔드투엔드 통합을 가능하게 합니다. 통합 환경은 직원 프로필, 급여 및 공제, 기여 정보와 함께 Human Resources에서 시작됩니다. 직원을 고용하고 필요한 프로필과 급여 정보를 Human Resources에 입력하면 급여 시스템이 급여를 처리할 때 이 정보를 가져와서 사용합니다. 직원 또는 급여 정보에 대한 모든 업데이트도 나중에 급여 실행에 사용하기 위해 가져옵니다.

[![급여 통합 흐름.](media/hr-admin-integration-payroll-api-introduction-flow.png)](media/hr-admin-integration-payroll-api-introduction-flow-2.png#lightbox)

통합을 활성화하기 위해 Human Resources는 다음 구성 요소를 포함합니다.

- [직원을 지급 준비로 표시하는 기능.](hr-compensation-payroll.md)
- 통합 애플리케이션에 대한 새로운 기능을 여는 통합 API.

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

이 API는 Microsoft Dataverse(이전 Common Data Service)에 기반을 둡니다. 이 API와의 모든 RESTful 상호 작용은 OData를 사용하는 Microsoft Dataverse 웹 API를 통해 수행됩니다. 이 API는 Dataverse 웹 API의 하위 집합입니다. Dataverse 웹 API는 인증, SLA, 일괄 처리, 동시성 제어 및 오류 처리와 같은 특성을 정의합니다.

Microsoft Dataverse 웹 API에 대한 더 일반적인 내용은 다음을 참조하세요.

- [Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)
- [Microsoft Dataverse 웹 API 사용](/powerapps/developer/data-platform/webapi/overview)
- [Microsoft Dataverse 개발자 가이드](/powerapps/developer/data-platform)

이 설명서에는 다음 항목을 포함하여 Dataverse 웹 API 사용에 대한 세부 정보 및 개발자 지침이 포함되어 있습니다.

- [웹 API로 Microsoft Dataverse 인증](/powerapps/developer/data-platform/webapi/authenticate-web-api)
- [웹 API를 사용하여 작업 수행](/powerapps/developer/data-platform/webapi/perform-operations-web-api)
- [웹 API로 Postman 사용](/powerapps/developer/data-platform/webapi/use-postman-web-api)
- [변경 추적을 사용하여 데이터를 외부 시스템과 동기화](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Dataverse의 Human Resources를 위한 가상 테이블

급여 통합 API의 엔드포인트는 Microsoft Dataverse의 가상 테이블 플랫폼 기능을 사용합니다. 기본적으로 가상 테이블 및 관련 API 엔드포인트는 Human Resources 환경에 배포되지 않으므로 조직에서 환경에 노출될 OData 엔드포인트를 결정할 수 있습니다. API를 사용하려면 Human Resources 엔터티에 대한 가상 테이블이 환경에 생성되어야 합니다.

API용 가상 테이블 생성에 대한 정보는 [Dataverse 가상 테이블 구성](./hr-admin-integration-common-data-service-virtual-entities.md)을 참조하세요.

## <a name="data-model"></a>데이터 모델

다음 다이어그램은 API 내의 관계를 보여줍니다. 여러 유형에는 여기에 설명되지 않은 Human Resources의 다른 기존 엔터티에 대한 외래 키가 있습니다. 이 문서는 급여 통합 시나리오와 관련된 엔터티에 대한 정보를 제공합니다. 그러나 Human Resources용 Dataverse 웹 API에는 통합과 관련될 수 있는 다른 많은 엔터티가 있습니다. 이러한 엔터티 중 일부는 외래 키 관계 또는 탐색 속성에서 참조됩니다.

[![급여 통합 API 데이터 모델.](media/hr-admin-payroll-api-data-model.png)](media/hr-admin-payroll-api-data-model.png#lightbox)

## <a name="payroll-employee-and-related-entities"></a>급여 직원 및 관련 엔터티

엔터티:

- [급여 직원](hr-admin-integration-payroll-api-payroll-employee.md)
- [급여 근로자 주소](hr-admin-integration-payroll-api-payroll-worker-address.md)
- [급여 고정 보상 계획](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md)
- [급여 변동 보상 계획](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md)
- [급여 직위 직무](hr-admin-integration-payroll-api-payroll-position-job.md)
- [급여 직위](hr-admin-integration-payroll-api-payroll-position.md)

## <a name="see-also"></a>참고 항목

[급여 엔터티 생성 및 검토](hr-admin-integration-payroll-api-generate-review-entities.md)<br>
[Human Resources 매개 변수 구성](hr-setup-parameters.md)<br>
[Human Resources 공유 매개 변수 구성](hr-setup-shared-parameters.md)<br>
[Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Microsoft Dataverse 웹 API 사용](/powerapps/developer/data-platform/webapi/overview)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
