---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 3월 22일)
description: 이 항목에서는 2021년 3월 22일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: marcelbf
ms.date: 03/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f08dc966353cc612c8145f29e2cd8c303da5b359292a8f928d97f0e0de99585
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451921"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-22-2021"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2021년 3월 22일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 항목에서는 Dynamics 365 Human Resources의 새로운 기능, 변경된 기능, 곧 제공될 기능에 관해 설명합니다.

업데이트 프로세스 및 일정에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

새로운 기능 및 예상 일반 공급 날짜에 대한 자세한 내용은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="in-this-release"></a>이번 릴리스에서 달라진 점

이 릴리스에는 다음과 같은 새로운 기능과 버그 수정이 포함되어 있습니다. 빌드 번호 8.1.4049에 적용된 변경 사항.

### <a name="new-features"></a>새 기능

이 릴리스에서는 다음 기능이 정식으로 제공됩니다.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 중단된 일괄 작업을 강제로 취소하고 재설정하는 옵션(560976) | NA | [중단된 일괄 작업 재설정](./hr-admin-troubleshooting-batch-execution.md) |
| 새로운 복리후생 계획 생성을 위한 사소한 UX 업데이트(419941) | NA | [복리후생 계획 만들기](hr-benefits-plans-setup.md) |

### <a name="bug-fixes"></a>버그 수정

이 릴리스에는 다음 버그 수정 사항이 포함되어 있습니다.

> [!NOTE]
> 우리의 목표는 이 정보를 최대한 빨리 제공하는 것입니다. 이 항목이 처음 게시된 후 빌드에 포함된 버그 수정을 포함하도록 이 항목이 업데이트될 수 있습니다.

| 문제 번호 | 문제 |  설명 |
| --- | --- | --- |
| 554239 | **BusinessProcessTaskAssignment** 테이블과 연관된 엔터티의 성능 향상 | 테이블에 제안된 인덱스를 추가하여 **BusinessProcessTaskAssignment** 테이블과 연관된 엔터티의 성능을 향상했습니다. |
| 566061 | 야간 동기화에서 V2 엔터티 대체 코드 제거 | 야간 Dataverse 동기화를 위한 V2 대체 코드를 제거합니다. 대체는 더는 필요하지 않으며 필터링된 동기화가 제대로 작동하지 않도록 합니다. 이 변경으로 Dataverse 데이터 동기화의 일관성이 향상됩니다. |
| 538024 | 작업자 복리후생 계획 > 체크아웃 제거에서 오류 발생 | 작업자 복리후생 양식에서 복리후생 계획 옵션에 대한 체크아웃을 제거하는 동안 오류가 수정되었습니다. |
| 557965 | **연결** 섹션에 **복리후생** 작업 영역: **활성 생활 이벤트** 링크가 표시되어야 함 | **활성 생활 이벤트** 링크가 **링크** 섹션에 표시되지만 **(미리 보기) 복리후생 관리 작업 영역** 기능이 활성화되지 않은 경우 탐색을 시도하는 동안 오류가 발생하는 문제가 수정되었습니다. 작업 영역 활성화에 대한 자세한 내용은 [복리후생 관리 작업 영역](hr-benefits-management-workspace.md)을 참조하세요. |
| 556672 | 기능 관리에서 **간소화된 직원 입력** 이 활성화된 경우 해고된 직원에 대한 적립을 처리할 수 없음 | 기능 관리에서 **간소화된 직원 입력** 이 활성화된 경우 휴가 및 부재 계획을 적립하는 옵션이 직원의 **근무 이력** 아래 **추가 옵션** 에 추가되었습니다. |
| 562656 | **SystemExternalBasicMaintain** 보안 의무의 보안 권한과 확장에 **SysRecordChangeLogValidTimeState** 메뉴 항목이 포함되어야 함. | 시스템 관리자가 아닌 역할의 경우 날짜 관리자 양식에 **변경 내용 보기** 버튼이 누락되었습니다. |
| 505989 | 생활 이벤트 처리: 사용 날짜로 인해 자격 변경이 올바르게 처리되지 않음 | 자격 처리의 변경이 현재 직위뿐만 아니라 직위 시작 날짜에 따라 달라지는 문제가 수정되었습니다. |
| 562286 | 작업자를 해고하면 Dataverse로 여러 업데이트가 전송됨 | 작업자가 해고되면 둘 이상의 업데이트 작업이 Dataverse로 전송되어 동일한 변경에 대해 두 개의 업데이트 알림이 발생합니다. 작업에서 Power Automate 흐름이 트리거되도록 구성된 경우 이로 인해 여러 트리거가 발생할 수 있습니다. |
| 527340 | 휴가 및 부재 등록을 열 때 "나타낼 수 없는 날짜/시간" 오류가 표시됨 | 휴가 및 부재 등록을 선택할 때 더는 오류가 표시되지 않습니다. |
| 561663 | 클러스터 프로비저닝을 위한 대기 시간 간격 증가 | 클러스터 프로비저닝 업데이트로 인프라 안정성과 프로비저닝 일관성을 개선합니다. |
| 486129 | **직위 > 변경 관리** 의 사용자 지정 필드를 편집할 수 없음 | **직위** 의 **변경 관리** 탭에서 사용자 지정 필드를 편집할 수 없는 문제를 해결했습니다. |

## <a name="in-preview"></a>미리 보기

다음과 같은 새로운 기능이 미리 보기로 제공됩니다. 기능을 켜거나 끄는 데 대한 자세한 내용은 [기능 관리](hr-admin-manage-features.md)를 참조하세요.

| 기능 | 릴리스 계획 | 설명서 |
| --- | --- | --- |
| 복리후생 관리 작업 영역 | [복리후생 관리 작업 영역(미리 보기)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [복리후생 관리 작업 영역](hr-benefits-management-workspace.md) |
| 직원이 비즈니스 연락처 세부 정보를 편집하지 못하도록 제한 | [직원이 비즈니스 연락처 세부 정보를 편집하지 못하도록 제한](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [개인 정보 편집 제한](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>업데이트 예정

| 기능 | 세부 정보 |
| --- | --- |
| 관리자가 직원을 위해 입력한 기술은 워크플로에서 자동 승인될 수 있음 | 업데이트 예정. |

계획된 기능 및 예정된 릴리스의 전체 목록은 [Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2021 릴리스 웨이브 1 개요](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]