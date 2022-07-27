---
title: 지원자 추적 시스템 통합 API 소개
description: 이 항목에서는 Dynamics 365 Human Resources 지원자 추적 시스템(ATS) 통합 API에 관해 설명합니다.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e16c781a6e51c57db8ae76dcfe0d28ec709428eb
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452602"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a>지원자 추적 시스템 통합 API 소개


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources 지원자 추적 시스템(ATS) 통합 API에 관해 설명합니다. API의 목적은 Dynamics 365 Human Resources와 파트너 ATS 간의 간소화된 통합을 가능하게 하는 것입니다.

![ATS 통합 흐름.](media/hr-admin-integration-ats-api-introduction-flow.png)

통합 환경은 채용 관리자가 Human Resources에서 채용 요청을 생성할 때 시작됩니다. 요청이 활성화되면 ATS는 모집 프로젝트를 생성하기 위해 요청에 대한 세부 정보를 가져옵니다. 그런 다음 채용 파이프라인을 따라 해당 직위에 대한 후보자를 선택하고 채용합니다. 마지막으로 ATS는 선택된 후보자의 기록을 Human Resources에 전송하여 왕복 통합을 완료합니다. 후보 레코드는 이어서 직원 레코드를 생성하기 위해 더 많은 온보딩 유효성 검사 및 워크플로를 거칠 수 있습니다.

통합을 활성화하기 위해 Human Resources는 다음 구성 요소를 추가했습니다.

1.  모집 요청을 생성하는 기능.
2.  확장된 후보자 프로필 및 관련 워크플로.
3.  통합 애플리케이션에 대한 새로운 기능을 여는 통합 API.

모집 요청과 후보자 기능 설정 및 사용에 관한 자세한 내용은 [구직 후보자 모집](hr-personnel-recruit.md)을 참조하세요.

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

이 API는 Microsoft Dataverse(이전 Common Data Service)에 기반을 둡니다. 이 API와의 모든 RESTful 상호 작용은 OData를 사용하는 Microsoft Dataverse 웹 API를 통해 수행됩니다. 이 API는 Dataverse 웹 API의 하위 집합입니다. Dataverse 웹 API는 인증, SLA, 일괄 처리, 동시성 제어 및 오류 처리와 같은 특성을 정의합니다.

Microsoft Dataverse 웹 API에 대한 더 일반적인 내용은 다음을 참조하세요.

- [Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)
- [Microsoft Dataverse 웹 API 사용](/powerapps/developer/data-platform/webapi/overview)
- [Microsoft Dataverse 개발자 가이드](/powerapps/developer/data-platform)

위의 설명서에는 [인증 관리](/powerapps/developer/data-platform/webapi/authenticate-web-api), [작업 수행](/powerapps/developer/data-platform/webapi/perform-operations-web-api), [API로 Postman 사용](/powerapps/developer/data-platform/webapi/use-postman-web-api), API로 [변경 추적 또는 델타 토큰 사용](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems)과 같은 Dataverse 웹 API 사용에 대한 세부 정보와 개발자 지침이 포함되어 있습니다.

### <a name="option-sets"></a>옵션 집합

이 문서에서 설명하는 ATS 통합 API용 데이터 모델에는 엔터티 속성과 관련된 열거형 값을 제공하는 옵션 집합이 포함되어 있습니다. Dataverse 웹 API의 옵션 집합 사용에 대한 자세한 내용은 [웹 API를 사용하여 옵션 집합 만들기 및 업데이트](/powerapps/developer/data-platform/webapi/create-update-optionsets)를 참조하세요. 옵션 집합은 각 Dataverse 환경별로 정의됩니다.

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Dataverse의 Human Resources를 위한 가상 테이블

ATS 통합 API의 엔드포인트는 Microsoft Dataverse의 가상 테이블 플랫폼 기능을 사용합니다. 기본적으로 가상 테이블 및 관련 API 엔드포인트는 Human Resources 환경에 배포되지 않으므로 조직에서 환경에 노출될 OData 엔드포인트를 결정할 수 있습니다. API를 사용하려면 Human Resources 엔터티에 대한 가상 테이블이 환경에 생성되어야 합니다. 

API용 가상 테이블 생성에 대한 정보는 [Dataverse 가상 테이블 구성](./hr-admin-integration-common-data-service-virtual-entities.md)을 참조하세요.

## <a name="data-model"></a>데이터 모델

데이터 모델은 두 가지 주요 엔터티를 중심으로 합니다.

- **RecruitingRequest** 는 ATS에 대한 하나 이상 공석의 모집 요청을 나타냅니다. 쿼리의 예는 [채용 요청 예제 쿼리](hr-admin-integration-ats-api-recruiting-request-example-query.md)를 참조하세요.
- **CandidateToHire** 는 채용 제안을 수락한 후보자의 세부 정보를 나타냅니다. **Person** 은 후보자 개인을 나타냅니다. 한 사람은 회사에서 후보자, 근로자, 직원 또는 계약자와 같이 여러 역할을 가질 수 있습니다. 예제 쿼리는 [채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)를 참조하세요.

다음 다이어그램은 API 내의 관계를 보여줍니다. 여러 유형에는 여기에 설명되지 않은 Human Resources의 다른 기존 엔터티에 대한 외래 키가 있습니다. 이 문서는 모집 통합 시나리오와 관련된 엔터티에 대한 정보를 제공합니다. 그러나 Dynamics 365 Human Resources용 Dataverse 웹 API에는 통합과 관련될 수 있는 다른 많은 엔터티가 있습니다. 예를 들어 여기에 정의되지 않은 근로자, 직무, 직위 또는 기타 엔터티에 대한 세부 정보가 필요할 수도 있습니다. 이러한 엔터티 중 다수는 외래 키 관계 또는 탐색 속성에서 참조됩니다.

![ATS 통합 API 데이터 모델.](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a>모집 요청 및 관련 엔터티 및 옵션 집합

예제 쿼리: 

- [모집 요청 예제 쿼리](hr-admin-integration-ats-api-recruiting-request-example-query.md)

엔터티:

- [모집 요청](hr-admin-integration-ats-api-recruiting-request.md)
- [모집 요청 직위](hr-admin-integration-ats-api-recruiting-request-position.md)
- [모집 요청 기술](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [모집 요청 교육](hr-admin-integration-ats-api-recruiting-request-education.md)
- [모집 요청 위치](hr-admin-integration-ats-api-recruiting-request-location.md)

옵션 집합:

- [직무 면제 상태](hr-admin-integration-ats-api-job-exempt-status.md)
- [모집 요청 직위 상태](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [모집 요청 상태](hr-admin-integration-ats-api-recruiting-request-status.md)
- [규제 직종](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a>채용 후보자 및 관련 엔터티 및 옵션 집합

예제 쿼리:

- [채용할 후보자에 대한 예제 쿼리](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

엔터티:

- [채용할 후보자](hr-admin-integration-ats-api-candidate-to-hire.md)
- [개인](hr-admin-integration-ats-api-person.md)
- [개인 교육](hr-admin-integration-ats-api-person-education.md)
- [개인 전문 경험](hr-admin-integration-ats-api-person-professional-experience.md)
- [개인 주소](hr-admin-integration-ats-api-person-address.md)
- [당사자 연락처](hr-admin-integration-ats-api-party-contact.md)
- [개인 기술](hr-admin-integration-ats-api-person-skill.md)
- [등급 수준](hr-admin-integration-ats-api-rating-level.md)
- [개인 자격증](hr-admin-integration-ats-api-person-certificate.md)
- [자격증 유형](hr-admin-integration-ats-api-certificate-type.md)
- [개인 심사](hr-admin-integration-ats-api-person-screening.md)
- [심사 유형](hr-admin-integration-ats-api-screening-types.md)
- [개인 식별 번호](hr-admin-integration-ats-api-person-identification-number.md)

옵션 집합:

- [지원자 통합 결과](hr-admin-integration-ats-api-applicant-integration-result.md)
- [공백 예 아니오](hr-admin-integration-ats-api-blank-yes-no.md)
- [완료 상태](hr-admin-integration-ats-api-completion-status.md)
- [연락처 유형](hr-admin-integration-ats-api-contact-type.md)
- [교육 학점 기준](hr-admin-integration-ats-api-education-credit-basis.md)
- [성별](hr-admin-integration-ats-api-gender.md)
- [결혼 상태](hr-admin-integration-ats-api-marital-status.md)
- [월](hr-admin-integration-ats-api-months-of-year.md)
- [아니요 예](hr-admin-integration-ats-api-no-yes.md)
- [기간 단위](hr-admin-integration-ats-api-period-unit.md)
- [심사 빈도](hr-admin-integration-ats-api-screening-frequency.md)
- [심사 빈도 생성](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [기술 수준 유형](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a>참고 항목

[구직 후보자 모집](hr-personnel-recruit.md)<br>
[Microsoft Dataverse란?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Microsoft Dataverse 웹 API 사용](/powerapps/developer/data-platform/webapi/overview)<br>
[웹 API를 사용하여 옵션 집합 만들기 및 업데이트](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
