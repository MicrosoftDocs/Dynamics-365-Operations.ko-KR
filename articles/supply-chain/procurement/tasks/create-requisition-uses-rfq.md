---
title: 견적 요청을 사용하는 요청 만들기
description: 이 항목에서는 견적 요청 절차에서 구매 요청에 가격 및 공급업체 정보를 추가하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f88d50c24e84b94128aa3fd567562f3240832910
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449071"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a>견적 요청을 사용하는 요청 만들기

[!include [banner](../../includes/banner.md)]

이 항목에서는 견적 요청 절차에서 구매 요청에 가격 및 공급업체 정보를 추가하는 방법에 대해 설명합니다. 이 가이드에 표시된 예제는 USMF 데모 데이터 회사에서 사용할 수 있으며 모든 단계를 완료하려면 관리자로 로그인해야 합니다. 이 가이드의 작업은 일반적으로 조달 전문가가 수행합니다.


## <a name="create-a-requisition"></a>요청 만들기
1. 탐색 창에서 **모듈 > 조달 및 소싱 > 구매 요청 > 내가 준비한 구매 요청** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **이름** 필드에 값을 입력합니다.
4. **요청한 날짜** 필드에 날짜를 입력합니다.
5. **회계 날짜** 필드에 날짜를 입력합니다.
6. **확인** 을 선택합니다.
7. **사유** 필드에 값을 입력하거나 선택합니다.
8. **라인 추가** 를 선택합니다.
9. **조달 범주** 필드의 트리에서 범주를 선택한 다음 **확인** 을 선택합니다.
10. **제품 이름** 필드에 값을 입력합니다.
11. **수량** 필드에 숫자를 입력합니다.
12. **단위** 필드에 값을 입력하거나 선택합니다.
13. **저장** 을 선택합니다.
14. **워크플로** 를 선택하여 드롭 대화 상자를 엽니다.
15. **제출** 을 선택합니다.
16. 페이지를 닫습니다.
17. **제출** 을 선택합니다.

## <a name="reassign-a-workflow-task"></a>워크플로 작업 재할당
다음 작업은 제품에 대한 공급업체로부터 입찰을 받기 위해 견적 요청을 작성하는 것입니다. USMF 데모 데이터에서는 공급업체가 선택되지 않았거나 라인의 단가가 0인 경우 특정 작업자에게 작업이 할당되어 견적 요청 생성하도록 요청 워크플로가 규칙으로 설정됩니다. 이 가이드를 계속하려면 해당 작업을 다른 사용자(자신)에게 다시 할당해야 합니다. 관리자로 로그인한 경우에만 이 작업을 수행할 수 있습니다.  

1. **워크플로** 를 선택하여 드롭 대화 상자를 엽니다.
2. **기록 보기** 를 선택합니다.
3. 페이지를 새로 고칩니다.
4. **추적 세부 정보** 섹션을 확장합니다.
5. 트리에서 "라인 워크플로 활성화됨"으로 시작하는 라인을 선택합니다.
6. **워크플로 세부 정보 보기** 를 선택합니다.
7. **작업 항목** 섹션을 펼칩니다.
8. **재할당** 을 선택합니다.
9. **사용자 필드** 에서 **관리자** 를 선택합니다.
10. **재할당** 을 선택합니다.
11. 두 페이지를 닫습니다.

## <a name="create-an-rfq"></a>견적 요청 만들기

1. 페이지를 새로 고칩니다.
2. **견적 요청** 을 선택합니다.
3. **구매 법인** 필드에서 **USMF** 를 선택합니다. 요청 라인에 있는 동일한 법인을 선택해야 합니다.  
4. 목록에서 선택한 행을 표시합니다. 구매 요청에 여러 라인이 있는 경우 견적 요청에 추가할 모든 라인을 선택합니다.  
5. **확인** 을 선택합니다.
6. 페이지를 새로 고칩니다.
7. 팩트 상자가 열려 있는지 확인한 다음 **관련 문서** 섹션을 확장합니다.
8. **견적 요청** 필드에서 링크를 선택하여 방금 생성된 견적 요청을 엽니다.
9. **헤더** 를 선택합니다.
10. **추가** 를 선택합니다.
11. **공급업체 계정** 필드에서 값을 입력하거나 선택합니다.
12. **추가** 를 선택합니다.
13. **공급업체 계정** 필드에서 값을 입력하거나 선택합니다.
14. **보내기** 를 선택합니다.
15. **확인** 을 선택합니다.
16. **회신 입력** 을 선택합니다.
17. 작업 창에서 **회수** 를 선택합니다.
18. **회신할 데이터 복사** 를 선택합니다. 이렇게 하면 견적 요청에서 회신으로 수량 및 날짜와 같은 데이터가 복사됩니다.  
19. **단가 필드** 에 숫자를 입력합니다. 판매자로부터 받은 가격입니다. 공급업체로부터 추가 정보를 입력할 수도 있습니다.  
20. **수락** 을 선택합니다.
21. **확인** 을 선택합니다.

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a>공급업체와 가격이 구매요청으로 전송되었는지 확인하기
1. 페이지를 닫습니다.
2. **라인** 을 선택합니다.
3. **관련 정보** 를 선택합니다.
4. **구매 요청** 을 선택합니다.
5. 견적 요청으로 이전된 라인을 선택합니다. 가격과 공급업체가 구매요청에 복사되었는지 확인합니다.  
6. **워크플로** 를 선택하여 드롭 대화 상자를 엽니다.
7. 완료를 선택합니다.
8. 페이지를 선택합니다.
9. 완료를 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]