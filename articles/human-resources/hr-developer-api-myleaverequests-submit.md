---
title: 워크플로에 휴가 요청 제출
description: Microsoft Dynamics 365 Human Resources에서 MyLeaveRequests submit() API(애플리케이션 프로그래밍 인터페이스)를 사용하여 워크플로에 휴가 요청을 제출할 수 있습니다.
author: andreabichsel
ms.date: 02/03/2020
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
ms.openlocfilehash: f9ca716f37b90e22983b2dddc2c426a2b4e251ec
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8452362"
---
# <a name="submit-a-leave-request-to-workflow"></a>워크플로에 휴가 요청 제출


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources에서 MyLeaveRequests submit() API(애플리케이션 프로그래밍 인터페이스)를 사용하여 워크플로에 휴가 요청을 제출할 수 있습니다. 이 API는 MyLeaveRequests OData 엔터티에 작업으로 노출됩니다.

## <a name="prerequisites"></a>전제 조건

휴가 요청은 데이터베이스에 저장되어야 하고 MyLeaveRequests 엔터티를 통해 검색할 수 있어야 합니다.

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 사용 권한 중 하나가 필요합니다. 사용 권한과 사용 권한 선택 방법에 대한 자세한 내용은 [인증](hr-developer-api-authentication.md)을 참조하세요.

| 사용 권한 유형                    | 사용 권한(최소 권한에서 최고 권한으로) |
|------------------------------------|--------------------------------------------------------|
| 위임됨(회사 또는 학교 계정) | 사용자\_가장                                    |

## <a name="https-request"></a>HTTPS 요청

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

요청은 OData 표준을 따릅니다. {requestId}, {leaveType}, {leaveDate} 및 {dataArea} 매개 변수는 MyLeaveRequests 엔터티에 대한 복합 자연 키를 구성하는 필드를 참조합니다.

> [!NOTE]
> MyLeaveRequests 엔터티의 필드는 휴가 요청의 개별 라인을 참조하지만 제출 API를 호출하면 전체 휴가 요청(모든 라인)이 워크플로에 제출됩니다.

### <a name="request-headers"></a>요청 헤더

| 머리글         | 값                     |
|----------------|---------------------------|
| Authorization  | 전달자 {token}(필수) |
| Content-Type   | application/json          |

### <a name="request-body"></a>요청 본문

이 메소드에 요청 본문을 제공하지 마세요.

### <a name="response"></a>응답

성공적인 응답은 항상 **204 콘텐츠 없음** 응답입니다.

권한이 없는 호출자는 **401 권한 없음** 또는 **403 금지됨** 응답을 받습니다.

제출이 실패하면(예: 유효성 검사로 인해) 응답은 **500 서버 오류** 가 되고 응답 본문에는 추가 세부 정보가 포함된 JSON 개체가 포함됩니다.

## <a name="example"></a>예

```http
POST https://aos-rts-sf-550e5c091f6-prod-westus2.hr.talent.dynamics.com/namespaces/b2eb8003-334f-4a84-ab63-edbe23569090/data/MyLeaveRequests(RequestId='USMF-000065', LeaveType='Vacation', LeaveDate=2019-10-04T12:00:00Z, dataAreaId='USMF')/Microsoft.Dynamics.DataEntities.submit
```

```json
{
  "error": {
    "code": "",
    "message": "An error has occurred.",
    "innererror": {
      "message": "Exception occurred while executing action submit on Entity MyLeaveRequest: The request would put the 'Vacation' balance below the allowed minimum balance on 9/10/2019.",
      "type": "System.InvalidOperationException",
      "stacktrace": "   at Microsoft.Dynamics.Platform.Integration.Services.OData.Action.ActionInvokable.Invoke()   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateProcessor.ActionInvocation(ChangeOperationContext context, ActionInvokable action)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.<>c__DisplayClass13_0.<ScheduleInvokable>b__0(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActionsInCompanyContext(IEnumerable`1 actionList, ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActions(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.SaveChanges()   at Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataDelegatingHandler.<SaveChangesAsync>d__3.MoveNext()"
    }
  }
}
```

## <a name="validation-and-error-messages"></a>유효성 검사 및 오류 메시지

Human Resources는 제출 API에 대한 호출의 일부로 제출 전에 비즈니스 논리 유효성 검사를 수행하여 휴가 요청이 제출에 유효한 상태인지 확인합니다. 유효성 검사가 실패하면 응답에서 받을 수 있는 오류 메시지는 다음과 같습니다.

 - 요청은 '{LeaveTypeId}' 잔액을 {date}에 허용된 최소 잔액 미만으로 설정합니다.
 - 완료 상태의 휴가 요청은 제출할 수 없습니다.
 - 변경 사항이 없으므로 요청을 제출하거나 저장할 수 없습니다. 잔액 또는 휴가 유형을 추가하거나 업데이트하고 다시 시도하세요.
 - 입력한 휴가 요청에 기존 보류 중인 요청과 날짜 및 휴가 유형이 동일한 날짜가 하나 이상 포함되어 있습니다. 기존 요청을 불러오고 수정하세요.
 - 이유 코드 '{ReasonCodeId}'는 요청의 휴가 유형에 적용되지 않습니다.
 - 휴가 유형 '{LeaveTypeId}'에는 이유 코드가 필요합니다. 적절한 유형과 이유 코드를 선택하세요.
 - 휴가가 성공적으로 제출되지 않았습니다. 휴가가 임시 요청으로 저장되었습니다.

## <a name="see-also"></a>참고 항목

- [MyLeaveRequests 개요](hr-developer-api-myleaverequests-overview.md)
- [인증](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
