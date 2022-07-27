---
title: 휴가 구매 및 판매 요청 워크플로 만들기
description: Dynamics 365 Human Resources에서 휴가 구매 및 판매 요청 워크플로를 만들어 휴가 요청을 일관되게 구매하고 판매할 수 있습니다.
author: andreabichsel
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b9e56c130cd831e6a1ad258c679562cb6de57d9b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452653"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a>휴가 구매 및 판매 요청 워크플로 만들기


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources에서 워크플로를 만들어 휴가 구매 및 판매 요청을 일관되게 관리할 수 있습니다. **휴가 구매 및 판매** 워크플로로 다음 작업을 수행할 수 있습니다.

- 작업 정의
- 누가 작업을 완료해야 하는지 결정
- 요청을 승인하거나 거부할 수 있는 사람 지정

## <a name="create-a-buy-and-sell-leave-request-workflow"></a>휴가 구매 및 판매 요청 워크플로 만들기

1. **휴가 및 휴직** 페이지에서 **연결** 탭을 선택합니다.

2. **설정** 에서 **인적 자원 워크플로** 를 선택합니다.

3. **새로 만들기** 를 선택한 다음 **휴가 구매 및 판매 요청** 을 선택합니다. 

4. **이 파일을 여시겠습니까?** 메시지 상자가 나타나면 **열기** 를 선택하고 회사 자격 증명으로 로그인합니다.

5. 워크플로 편집기를 사용하여 휴가 요청을 위한 워크플로를 만듭니다. 워크플로 작업에 대한 자세한 내용은 [워크플로 만들기 개요](../fin-ops-core/fin-ops/organization-administration/create-workflow.md?toc=%2fdynamics365%2fcommerce%2ftoc.json.)를 참조하세요.

## <a name="leave-and-absence-request-workflow-data-elements"></a>휴가 및 휴직 요청 워크플로 데이터 요소

다음 데이터 요소를 사용하여 휴가 구매 및 판매 요청의 워크플로에서 조건부 또는 자동 승인을 만들 수 있습니다.

- **금액**
- **휴가 구매 및 판매 정책**
- **회사**
- **만든 사람**
- **생성 날짜 및 시간**
- **종료 날짜**
- **휴가 유형**
- **수정한 사람**
- **수정 날짜 및 시간**
- **요청 ID**
- **시작 날짜**
- **상태** 
- **제출 날짜**
- **제출한 사람**
- **Human Resources에서 제출됨**
- **관리자가 제출함**
- **대신 제출됨**
- **작업자**

## <a name="workflow-examples"></a>워크플로 예

다음 예에서는 다음 데이터 요소를 사용하여 다양한 유형의 워크플로 조건을 생성하는 방법을 보여줍니다.

- 자동 작업에서 **Human Resources에서 제출됨** 및 **관리자가 제출함** 을 사용하여 이러한 역할이 직원 대신 제출하는 휴가 구매 및 판매 요청을 자동으로 승인합니다. 자동 작업에 대한 자세한 내용은 [워크플로에서 승인 프로세스 구성](../fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow.md)을 참조하세요.

- 워크플로가 특정 휴가 유형으로 요청을 라우팅하는 방법을 제어하려면 조건문 또는 자동 작업에서 **휴가 유형** 을 사용합니다.

## <a name="see-also"></a>참고 항목

[휴가 및 휴직 개요](hr-leave-and-absence-overview.md)<br>
[휴가 구매 및 판매 정책 관리](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)<br>
[휴가 구매 및 판매](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
