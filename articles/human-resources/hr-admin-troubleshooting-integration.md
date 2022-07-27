---
title: 재무와의 통합 FAQ
description: 이 항목에서는 Human Resources 및 Finance 통합에서 동기화되는 데이터에 대해 설명합니다.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 308e2a538666522edf4a76be13b93c82c3f3a774
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452671"
---
# <a name="integration-with-finance-faq"></a>재무와의 통합 FAQ


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 항목에서는 Dynamics 365 Human Resources가 Dynamics 365 Finance와 통합될 때 동기화되는 데이터에 대한 일반적인 질문에 답변합니다.

## <a name="can-i-edit-the-dynamics-365-talent-application-user-in-power-apps"></a>Power Apps에서 Dynamics 365 Talent 애플리케이션 사용자를 편집할 수 있습니까?

아니요. Human Resources 애플리케이션 사용자를 편집하는 경우 Human Resources와 Dataverse 간의 통합이 실패할 수 있습니다. 다음 표는 Talent 애플리케이션 사용자에 대한 기본 설정을 보여줍니다.

| 전체 이름 | 애플리케이션 ID | Azure AD 개체 ID | 애플리케이션 ID URI |
| --- | --- | --- | --- |
| Dynamics365 for Talent | f9be0c49-aa22-4ec6-911a-c5da515226ff | 27fd8129-4b3c-43f7-b1bf-47495d3a049b | f9be0c49-aa22-4ec6-911a-c5da515226ff |

![Talent 애플리케이션 사용자의 기본 설정.](media/DynamicsApplicationUser.png)

## <a name="is-all-data-synchronized-or-just-some-data-entities"></a>모든 데이터가 동기화됩니까? 아니면 일부 데이터 엔터티만 동기화됩니까?

데이터의 하위 집합이 동기화됩니다. 모든 엔터티의 목록은 [Dynamics 365 Finance와의 통합](hr-admin-integration-finance.md)을 참조하십시오.

## <a name="why-dont-i-see-any-data-synced-to-dataverse"></a>Dataverse와 동기화된 데이터가 표시되지 않는 이유는 무엇입니까?

제공된 데모 데이터가 포함되지 않은 새로운 환경에서는 기본적으로 Dataverse 통합이 해제되어 있습니다. 기본적으로 데모 데이터가 포함된 새 환경에서는 이 기능이 켜져 있으며, 환경이 준비되면 데이터 동기화가 시작됩니다. 환경에서 데이터를 동기화할 준비가 되면 통합을 켤 수 있습니다. 자세한 내용은 [Dataverse 통합 구성](hr-admin-integration-common-data-service.md)을 참조하십시오.

## <a name="can-i-create-a-new-mapping-without-using-the-templates"></a>템플릿을 사용하지 않고 새 매핑을 만들 수 있습니까?

템플릿이 시작점입니다. 템플릿을 직접 생성할 수 있지만 통합 프로젝트를 생성할 때는 템플릿이 항상 필요합니다. 데이터 통합기(DI), 템플릿 및 프로젝트에 대한 자세한 내용은 [Microsoft Dataverse에 데이터 통합](/powerapps/administrator/data-integrator)을 참조하십시오.

## <a name="can-i-map-financial-dimensions-to-transfer-between-human-resources-and-finance"></a>Human Resources와 Finance 사이의 전송을 위해 재무 차원을 매핑할 수 있습니까?

재무 차원은 현재 Dataverse에 없으므로 기본 템플릿의 일부가 아닙니다. 이 엔터티는 계획되어 있지만 현재 릴리스 일정이 없습니다.

Finance에 있지만 Human Resources에 없는 데이터의 경우 Human Resources의 **링크 구성** 을 사용하여 두 시스템을 연결하십시오.

![재무 차원 매핑.](media/MapFinancialDimensions.png)

## <a name="sometimes-when-i-import-employees-they-go-into-inactive-workers-in-finance-why"></a>직원들을 가져오면 Finance에서 비활성 직원으로 들어갑니다. 이유가 무엇입니까?

Human Resources에 직원의 활성 고용 내역 기록이 없는 경우 이 오류가 발생할 수 있습니다. 이를 해결하려면 **개인 관리 \> 직원 \> 고용 내역 \> 날짜 관리자** 로 이동하여 활성 고용 내역 기록이 있는지 확인하십시오.

## <a name="if-i-select-to-map-only-a-subset-of-fields-will-changes-made-to-non-mapped-fields-trigger-a-sync"></a>필드의 하위 집합만 매핑하도록 선택하면 매핑되지 않은 필드를 변경하면 동기화가 트리거됩니까?

데이터 동기화는 실행 일정을 따릅니다. 통합 매핑의 일부인지 여부에 관계없이 레코드의 필드가 변경되면 통합이 레코드를 선택합니다.

## <a name="how-can-i-send-only-active-worker-changes-and-not-the-terminated-records"></a>종료된 레코드가 아닌 활성 직원 변경 사항만 보내려면 어떻게 해야 합니까?

"고급 쿼리"를 사용하여 원본 데이터를 대상으로 전달하기 전에 필터링하고 모양을 변경할 수 있습니다.

![활성 직원 고급 쿼리.](media/MapOnlyActiveWorkersAdvancedQuery.png)

## <a name="can-i-specify-which-fields-to-send-to-finance-for-a-specific-entity"></a>특정 엔티티에 대해 Finance로 보낼 필드를 지정할 수 있습니까?

필드를 통합 작업에서 추가하거나 제거할 수 있습니다. Dataverse 테이블에 있는 모든 데이터 필드가 Human Resources에 채워지는 것은 아닙니다.
추가 데이터는 Power Apps를 통해 채울 수 있습니다.

![통합 작업에 필드를 추가하거나 통합 작업에서 필드를 제거하십시오.](media/SpecifyFieldsIncludedInIntegration.png)

## <a name="i-set-up-integration-as-a-batch-job-but-human-resources-lost-connection-to-the-destination-system-how-can-i-send-the-same-set-of-changes-to-the-destination-system"></a>통합을 일괄 작업으로 설정했지만 Human Resources에서 대상 시스템에 대한 연결이 끊어졌습니다. 동일한 변경 사항을 대상 시스템에 보내려면 어떻게 해야 합니까?

예외 처리를 위해 특별한 설정이 필요하지는 않습니다. 데이터 통합자는 원본 및 대상에서 발생하는 오류를 자동으로 포착하고 보고하며 수동 재시도도 허용합니다. 그러나 수동으로 데이터를 수정할 수는 없습니다. 데이터 업데이트가 필요한 경우 원본 또는 대상에서 업데이트를 해야 합니다.

## <a name="can-i-set-up-bi-directional-integration"></a>양방향 통합을 설정할 수 있습니까?

아니요. 통합은 현재 한 방향(Human Resources에서 Finance 및 Operations로)만 가능합니다. 그러나 Human Resources에서 Finance로 데이터를 전송하는 데 사용할 수 있는 기본 템플릿이 있습니다.

## <a name="can-i-allow-record-deletion-as-part-of-my-integration"></a>통합의 일부로 레코드 삭제를 허용할 수 있습니까?

아니요, 데이터 통합자는 데이터 전송을 위해 삭제된 레코드를 캡처하지 않습니다. 현재 데이터 생성 및 업데이트(UPSERT)만 포함되어 있습니다.

## <a name="can-i-rerun-the-errored-execution-if-so-will-it-send-a-full-file-or-only-the-changes"></a>오류가 발생한 작업을 다시 실행할 수 있습니까? 가능하다면 전체 파일을 보냅니까, 아니면 변경 사항만 보냅니까?

데이터 통합자의 첫 번째 실행은 항상 전체 실행입니다. 이후 실행은 변경 추적을 기반으로 합니다. 오류가 실행되면 실행 범위 내의 레코드를 추출하고 Dataverse에서 가장 최근에 변경된 내용을 전송합니다.

## <a name="when-i-save-the-project-i-get-the-error-project-has-mapping-errors-what-do-i-do"></a>프로젝트를 저장할 때 "프로젝트에 매핑 오류가 있습니다."라는 오류가 표시됩니다. 어떻게 해야 합니까?

통합 키 설정을 확인하고 필요한 설정을 변경한 다음 프로젝트의 엔터티를 새로 고치십시오.

기본 템플릿을 사용하면 통합 키를 자동으로 가져옵니다. 이 문제는 새 작업이 기존 템플릿에 추가될 때 발생할 수 있습니다.

## <a name="if-i-have-n-number-of-legal-entities-where-workers-have-employments-do-i-need-to-create-a-mapping-for-each-of-them"></a>직원이 고용되어 있는 법인이 N개일 경우 각 법인에 대한 매핑을 생성해야 합니까?

예, Finance의 각 법인에 대해 데이터 통합을 위한 별도의 통합 프로젝트가 필요합니다.

## <a name="i-need-to-transfer-data-that-is-not-part-of-the-default-template-provided-by-microsoft-can-i-do-this"></a>Microsoft에서 제공하는 기본 템플릿의 일부가 아닌 데이터를 전송해야 합니다. 가능합니까?

예, 필드를 기존 템플리트에 추가하거나 기존 템플리트에서 제거할 수 있습니다. 템플릿은 다른 Dataverse 테이블의 추가 데이터를 포함하도록 수정할 수 있습니다. 엔터티가 템플릿에 포함되려면 엔터티가 Dataverse에 있어야 합니다. 

## <a name="i-just-created-new-finance-and-human-resources-environments-and-im-getting-the-error-the-data-value-violates-integrity-constraints-why"></a>방금 새로운 Finance 및 Human Resources 환경을 생성했는데 "데이터 값이 무결성 제약 조건을 위반합니다."라는 오류가 발생합니다. 이유가 무엇입니까?

이 오류의 원인은 다음과 같습니다.

- 데이터 전송으로 원본(Dataverse)에서 중복 레코드가 추출되었습니다.

- 데이터 전송에 Finance 및 Operations의 필수 필드에 null 값이 있습니다. Dataverse에 있으며 Finance 및 Operations의 요구 사항에 맞는지 데이터를 확인하십시오.

## <a name="if-there-are-execution-errors-and-the-employee-id-didnt-sync-how-do-i-find-the-history-job-which-has-the-failed-employee-record"></a>실행 오류가 있고 직원 ID가 동기화되지 않은 경우 실패한 직원 기록이 있는 이력 작업을 찾으려면 어떻게 해야 합니까?

데이터 통합자는 Finance에서 여러 프로젝트를 생성합니다. 데이터 통합자 작업과 Finance 프로젝트 간의 관계는 일대일입니다.

데이터 통합자 실행 기록에서 시간을 추적하고 Finance에서 인덱스 -1 프로젝트를 찾으십시오. 데이터 통합자에서 작업 번호가 9이면 Finance의 인덱스는 8입니다.

1. 데이터 통합자에서 작업 인덱스를 캡처합니다(이 예에서는 "9").

    ![데이터 통합자에서 작업 인덱스를 캡처합니다.](media/CaptureTaskIndex.png)

2. 프로젝트의 실행 시간을 추적합니다.

    ![프로젝트의 실행 시간을 추적합니다.](media/CaptureTimeOfExecution.png)

3. Finance에서 인덱스 - 1을 찾습니다. 이 예에서는 접미사가 "8"인 프로젝트와 인덱스 "0" 프로젝트의 실행 시간이 2단계에서 실행 시간과 일치합니다.

    ![인덱스 식별.](media/IdentifyIndex.png)

## <a name="after-integrating-human-resources-and-finance-i-dont-see-my-human-resources-data-in-finance-what-do-i-do"></a>Human Resources와 Finance를 통합한 후 Finance에 Human Resources 데이터가 표시되지 않습니다. 어떻게 해야 합니까?

Finance와의 통합은 2단계 프로세스입니다. 먼저 Human Resources 데이터가 업데이트되어 Dataverse에서 사용할 수 있는지 확인하십시오. 이는 거의 실시간 동기화이며 데이터 테이블 내의 데이터를 확인하여 Power Apps에서 확인할 수 있습니다.

![Dataverse의 데이터.](media/DataInCDS.png)

Dataverse에 데이터가 예상대로 나타나지 않으면 통합에서 엔터티가 지원되는지 확인하십시오. Dataverse에 추가 데이터를 포함하려면 Microsoft 측에서 변경해야 합니다.

엔터티가 지원되고 Dataverse에서 데이터를 사용할 수 있는 경우 데이터 통합자에서 매핑이 올바른지 확인하십시오. 통합자 매핑이 정상인 경우 데이터 관리 작업이 성공적으로 실행되었는지 확인하십시오. 일괄 작업을 실행하는 동안 오류가 발생할 수 있습니다. 데이터 관리에 대한 자세한 내용은 [데이터 관리](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json)를 참조하십시오.

## <a name="the-addresses-for-my-employees-are-incorrect-after-i-import-them-into-finance-what-should-i-do"></a>직원을 Finance로 가져온 후 직원의 주소가 올바르지 않습니다. 어떻게 해야 합니까?

**위치 ID** 의 번호 순서는 Human Resources와 Finance에서 모두 동일한 패턴을 사용합니다. Dataverse에서 Finance 및 Operations로 데이터를 통합할 때 주소 충돌이 없도록 번호 시퀀스가 양쪽에서 고유해야 합니다.

Human Resources를 구현하는 동안 Human Resources와 Finance에서 숫자 시퀀스가 동일하지 않은지 확인하십시오. 데이터가 관리되는 두 시스템에서 모든 숫자 시퀀스가 동일하지 않은지 확인하십시오.

## <a name="when-creating-my-connection-set-i-am-unable-to-see-the-connection-in-the-connection-drop-down-list-what-do-i-do"></a>연결 세트를 생성할 때 연결 드롭다운 목록에서 연결을 볼 수 없습니다. 어떻게 해야 합니까?

연결을 만들 때 Dynamics 365 Finance 및 Dataverse를 선택해야 합니다.

## <a name="when-syncing-employments-i-get-the-errors-companyinfo_fk-doesnt-exist-or-the-value-12312154-115959-pm-in-field-employment-end-date-is-not-found-in-the-related-table-employment-what-should-i-do"></a>고용을 동기화할 때 "CompanyInfo_FK가 없습니다" 또는 "'고용 종료일' 필드의 '12/31/2154 11:59:59 pm' 값을 관련 테이블 '고용'에서 찾을 수 없습니다"라는 오류가 표시됩니다. 어떻게 해야 합니까?

올바른 법인에 매핑하고 있는지 확인하십시오. 법인 동기화는 기본 템플릿의 일부가 아니므로 Human Resources 및 Dataverse에 있는 각 법인도 Finance에 있어야 합니다. 또한 연결된 연결 세트에 대해 올바른 법인을 선택해야 합니다.

## <a name="after-setting-up-my-project-the-field-mapping-for-finance-appears-to-be-empty-what-should-i-do"></a>프로젝트를 설정한 후 Finance에 대한 필드 매핑이 비어 있는 것으로 나타납니다. 어떻게 해야 합니까?

**데이터 관리 \> 프레임워크 매개 변수 \> 엔티티 설정 \> 엔티티 목록 새로 고침** 으로 이동하여 Finance에서 데이터 엔티티를 새로 고치십시오. 이 작업을 완료하는 데 몇 분이 걸릴 것입니다. 그런 후에 매핑을 볼 수 있습니다. 이 문제는 새 프로젝트를 만들 때 발생합니다.

![필드 매핑이 누락되었습니다.](media/MissingFieldMapping.png)

## <a name="additional-resources"></a>추가 리소스

- 데이터 통합자(DI): 

  - [Microsoft Dataverse로 데이터 통합](/powerapps/administrator/data-integrator)

  - [데이터 통합자 오류 관리 및 문제 해결](/powerapps/administrator/data-integrator-error-management)

  - [Power Apps, Microsoft Power Automate, Dataverse의 시스템 생성 로그를 위한 DSR 요청에 응답](/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs)

- 데이터 관리:

  - [데이터 관리](/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=%2ffin-and-ops%2ftoc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
