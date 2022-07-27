---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 4월 13일)
description: 이 항목에서는 2020년 4월 13일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b5af74329fa741a443932a1007a6c2ef6abd3445
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452032"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 4월 13일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



이 문서에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3136에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 LCS의 지원 번호를 나타냅니다.

## <a name="new-production-release-cadence"></a>새로운 프로덕션 릴리스 주기

이번 주 릴리스에서 Human Resources의 릴리스 주기가 주간 업데이트에서 격주 업데이트로 변경됩니다. 안전한 배포 관행을 유지하고 높은 수준의 서비스 안정성과 신뢰성을 유지하기 위해 이제 모든 지역에 서비스 업데이트를 배포하는 프로세스는 2주 동안 롤아웃됩니다. 프로세스의 각 단계에서 성공적인 배포를 확인하기 위해 추가 테스트와 모니터링이 배치됩니다. 릴리스 주기에 대한 자세한 내용은 [업데이트 프로세스](hr-admin-setup-update-process.md)를 참조하세요.

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a>반올림 유형을 지정한 후 반올림 자릿수 필드를 편집할 수 없음(435616)

이 변경으로 **반올림 유형** 필드를 업데이트한 후 **반올림 자릿수** 필드를 사용할 수 있습니다.

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a>휴가 계획에 적립 기간이 없으면 휴가 등록 종료 날짜를 편집할 수 없음(413628)

이제 "적립 날짜 기준 필드를 입력해야 합니다." 오류가 발생하지 않고 등록 종료 날짜를 편집할 수 있습니다.

## <a name="employment-entity-doesnt-sync-to-dataverse-430834"></a>고용 엔터티가 Dataverse와 동기화되지 않음(430834)

이 변경은 재무 차원을 추가한 후 고용 데이터가 Dataverse와 동기화되지 않는 문제를 수정합니다. 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a>작업 일정 시간 간격 엔터티에 대한 다중 부모 제거(431775)

이 변경으로 **작업 일정 시간 간격** 엔터티에 대한 다중 부모가 제거되었습니다.

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a>CAST 기능이 있는 필터가 OData 호출 직위 작업자 할당 엔터티에서 작동하지 않음(431699)

이 업데이트에는 **직위 작업자 할당** 엔터티에 대해 OData 내에서 CAST 기능이 있는 필터를 허용하는 변경이 포함됩니다.

## <a name="in-preview"></a>미리 보기

## <a name="leave-suspension"></a>휴가 일시 중단

Human Resources에서 직원의 휴가 및 부재를 일시 중단할 수 있습니다. 휴가를 일시 중단하면 선택한 휴가 유형에 대한 휴가 적립이 중지됩니다. 휴가 적립이 처리된 후 일시 중단이 발생한 경우 휴가를 일시 중단하면 직원의 휴가 잔액에 비례하여 조정됩니다. 자세한 내용은 [휴가 일시 중단](hr-leave-and-absence-suspend-leave.md)을 참조하세요.

## <a name="carry-forward-rules"></a>이월 규칙

이월 조정이 이전되는 이월 잔액에 대해 이월 휴가 유형을 지정할 수 있습니다. 예를 들어 직원이 10일을 이월한 경우 해당 10일에 대해 다른 휴가 유형을 선택할 수 있습니다. 자세한 내용은 [휴가 및 부재 매개 유형 구성](hr-leave-and-absence-types.md)을 참조하세요.

## <a name="known-issues"></a>알려진 문제

## <a name="employment-details-entity"></a>고용 세부 정보 엔터티

**고용 세부 정보** 엔터티가 다음 필드를 포함하도록 업데이트되었습니다.

- **지급 빈도**
- **고용 범주 ID**
- **고용 유형**
- **고용 유형 ID**
- **복리후생 등록 상태**

이 필드의 설정 데이터는 **기능 관리** 작업 영역에서 활성화된 복리후생 관리에 의존합니다. 가져오는 동안 오류가 발생하므로 **고용 세부 정보** 엔터티의 이러한 필드를 채우거나 업데이트하면 안 됩니다.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>일부 환경에서 SharePoint 미리 보기가 작동하지 않음

SharePoint에 저장된 문서의 문서 미리 보기가 작동하지 않는 경우 다음 절차를 시도하세요.

1. 관리 사용자 계정에 사용자 레코드와 연결된 이메일이 있는지 확인합니다. 이 정보는 **사용자** 페이지에서 볼 수 있습니다. 이메일이 설정되지 않은 경우 OData Excel 추가 기능으로 이메일 및 공급자를 추가해야 합니다. 기본적으로 이메일 주소는 Excel 디자인에 표시되지 않습니다. Excel 디자인을 편집하고 모든 필드를 추가하고 적용하고 새로 고쳐야 합니다. 이러한 단계를 완료하면 관리자 계정을 업데이트할 수 있습니다.

2. 관리자 계정에 이메일 계정을 연결한 후에는 관리자 자격 증명으로 Human Resources에 로그인합니다.

3. 문서 미리 보기를 시작하려면 SharePoint의 첨부 파일에 액세스합니다.

4. 첨부 파일에 대한 액세스 권한이 있는 다른 사용자 계정으로 로그인하고 미리 보기가 정상적으로 작동하는지 확인합니다.

## <a name="see-also"></a>참고 항목

[Human Resources의 새로운 기능 또는 변경된 기능](hr-admin-whats-new.md)</br>
[Dynamics 365 Human Resources 2019 릴리스 웨이브 2 개요](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[업데이트 프로세스](hr-admin-setup-update-process.md)</br>
[기능 관리](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]