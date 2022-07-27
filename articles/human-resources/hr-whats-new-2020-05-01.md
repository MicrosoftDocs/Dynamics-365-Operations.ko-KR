---
title: Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 5월 1일)
description: 이 항목에서는 2020년 5월 1일 Microsoft Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다.
author: andreabichsel
ms.date: 05/01/2020
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
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae4b0619a7006bad623e3cee4d9f099e2632b10eeabb78aac16abe53b0911b3a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8451924"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a>Dynamics 365 Human Resources의 새로운 기능 또는 변경된 기능(2020년 5월 1일)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

이 문서에서는 Dynamics 365 Human Resources의 새로 추가되거나 변경된 기능에 관해 설명합니다. 빌드 번호 8.1.3196에 적용된 변경 사항. 일부 제목에서 괄호 안의 숫자는 참조를 위한 LCS의 지원 번호를 나타냅니다.

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a>DMF(Data Management Framework)에서 새로운 성과 관리 엔터티를 사용할 수 있음

이제 다음 엔터티를 사용할 수 있습니다. 엔터티 목록에 이러한 엔터티가 표시되지 않으면 **프레임워크 매개 변수 > 엔터티 설정 > 엔터티 목록 새로 고침** 의 **엔터티 새로 고침** 을 사용하세요.

- **토론 역량**
- **토론 목표**
- **토론 측정**
- **토론 주제**
- **성과 분개장**
- **측정**
- **목표 측정**

**총 점수** 와 **평균 점수** 가 **토론** 엔터티에 추가되었습니다.

## <a name="increase-length-of-leave-request-comments-275641"></a>휴가 요청 코멘트의 길이 증가(275641)

휴가 요청에 대한 코멘트가 이제 100자 넘게 허용합니다.

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a>관리자 또는 직원이 다른 회사에 로그인한 경우 검토에 대한 최종 코멘트가 표시되지 않음(431688)

이제 검토를 볼 때 모든 코멘트가 표시됩니다.

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a>새 작업자 양식에서 사용자 정의 링크가 지원되지 않음(390374)

이제 간소화된 **작업자** 양식에서 사용자 정의 링크가 활성화됩니다.

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a>HcmRatingLevelEntity가 OData API 충돌을 일으킴(439476)

이 변경은 API 충돌을 수정합니다. 중복된 이름이 이 오류를 일으켰습니다.

## <a name="in-preview"></a>미리 보기

## <a name="leave-suspension"></a>휴가 일시 중단

Human Resources에서 직원의 휴가 및 부재를 일시 중단할 수 있습니다. 휴가를 일시 중단하면 선택한 휴가 유형에 대한 휴가 적립이 중지됩니다. 휴가 적립이 처리된 후 일시 중단이 발생한 경우 휴가를 일시 중단하면 직원의 휴가 잔액에 비례하여 조정됩니다. 자세한 내용은 [휴가 일시 중단](hr-leave-and-absence-suspend-leave.md)을 참조하세요.

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>적립 일시 중단을 표시하도록 사용자 환경 업데이트(429550)

이제 사용자 환경에 계획에 대한 적립 일시 중단이 표시됩니다.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>지정된 휴가 유형에 대한 휴가 적립 일시 중단(272447)

이 릴리스에서 HR은 무급 휴가를 위한 입력한 휴가 요청이 있는 직원의 휴가 적립을 일시 중단하는 규칙을 만들 수 있습니다. 무급 휴가는 한 유형일 수 있지만 반드시 그래야 하는 것은 아닙니다. 다른 휴가 유형에 따라 휴가를 일시 중단할 수 있습니다.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>DMF 엔터티를 적립 일시 중단에 사용할 수 있음(429549)

이제 DMF 엔터티를 적립 일시 중단에 사용할 수 있습니다.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>적립 일시 중단에 사유 코드 추가(429547)

적립 일시 중단에 사유 코드가 추가되었습니다.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Human Resources 매개 변수에서 휴가 및 부재 매개 변수로 전환 시작

이 릴리스에서는 Human Resources 매개 변수를 휴가 및 부재 매개 변수와 결합하기 시작합니다.

## <a name="carry-forward-rules"></a>이월 규칙

이월 조정이 이전되는 이월 잔액에 대해 이월 휴가 유형을 지정할 수 있습니다. 예를 들어 직원이 10일을 이월한 경우 해당 10일에 대해 다른 휴가 유형을 선택할 수 있습니다. 자세한 내용은 [휴가 및 부재 매개 유형 구성](hr-leave-and-absence-types.md)을 참조하세요.

## <a name="known-issues"></a>알려진 문제

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