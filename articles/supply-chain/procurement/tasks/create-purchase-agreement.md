---
title: 구매 계약 생성
description: 이 항목은 구매 계약 작성을 안내합니다.
author: Henrikan
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchAgreement, PurchAgreementCreate, InventItemIdLookupSimple, AgreementConfirmRunForm, PurchAgreementHistory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee2cf437446f2e4c2cdd3cc0cd3be863bbafa132
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447814"
---
# <a name="create-a-purchase-agreement"></a>구매 계약 생성

[!include [banner](../../includes/banner.md)]

이 항목은 구매 계약 작성을 안내합니다. 이것은 일반적으로 구매 관리자가 수행합니다. 데모 데이터 회사 USMF 또는 자체 데이터에서 이 절차를 사용할 수 있습니다. 시작하기 전에 구매 계약 분류를 설정해야 합니다. 계약을 생성하면 PO를 생성할 때 이를 사용할 수 있습니다. 그러면 구매 계약 조건이 헤더와 계약의 영향을 받는 주문의 모든 라인에 복사됩니다.


## <a name="create-a-new-purchase-agreement"></a>새 구매 계약 생성
1. **탐색 창 > 모듈 > 조달 및 소싱 > 구매 계약 > 구매 계약** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **공급업체 계정** 필드의 드롭다운 메뉴를 선택하고 원하는 레코드의 행을 선택합니다.
4. **구매 계약 분류** 필드의 드롭다운 메뉴를 선택하고 원하는 레코드의 행을 선택합니다.
5. **일반** 빠른 탭을 확장합니다.
6. **만료 날짜** 필드에 날짜를 입력합니다.

    - 이 만료 날짜는 모든 약정 라인의 기본값이 되며 각 특정 약정이 유효한 기간을 결정합니다.  

7. **문서 제목** 필드에 구매 계약의 이름을 입력합니다.

    - **기본 약정** 필드를 **제품 수량 약정** 으로 둡니다(또는 이것이 설정되지 않은 경우 변경).  
    - 기본 약정 값은 계약 라인에 대한 옵션을 결정합니다. 계약 라인을 생성할 때 새로운 약정 유형이 필요한 경우 헤더의 기본 약정을 변경해야 합니다. 약정에는 4가지 유형이 있습니다. **제품 수량 약정** - 특정 수량의 제품에 대해. **제품 가치 약속** - 제품의 특정 통화 금액에 대해. **제품 카테고리 가치 약속** - 금액이 카탈로그 항목 또는 비카탈로그 항목에 대한 것일 수 있는 조달 범주의 특정 통화 금액에 대해. **가치 약속** - 모든 제품 또는 조달 범주에 의해 이행될 수 있는 특정 통화 금액.  

8. **확인** 을 선택합니다.

## <a name="add-a-commitment"></a>약정 추가
1. **라인 추가** 를 선택합니다.
2. **품목 번호** 필드의 드롭다운 메뉴에서 원하는 레코드를 선택합니다.
3. **수량** 필드에 숫자를 입력합니다. 이것은 공급업체로부터 구매하기로 동의한 총 수량입니다.  
4. **단가 필드** 에 숫자를 입력합니다.
5. **라인 세부 정보** 섹션을 확장합니다.
6. **최대 적용됨** 옵션을 **네** 로 설정합니다. **최대 적용됨** 옵션은 약정 사용을 제한합니다. 라인의 **수량** 필드에 명시된 수량까지만 구매하실 수 있습니다.  

## <a name="add-header-conditions"></a>헤더 조건 추가
1. 작업 창에서 **옵션** 을 선택합니다.
2. **보기 변경** 을 선택합니다.
3. **헤더 보기** 를 선택합니다.
4. **사용 약관** 섹션을 확장합니다.
5. **결제 수단** 필드의 드롭다운 메뉴에서 원하는 레코드를 선택합니다. 기본적으로 공급업체 계정의 지불 조건이 여기에 표시됩니다.  
6. **배송 모드** 필드의 드롭다운 메뉴에서 원하는 레코드를 선택합니다.
7. **배송 약관** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다.

## <a name="confirm-and-activate-the-agreement"></a>계약 확인 및 활성화
1. 작업 창에서 **구매 계약** 을 선택합니다.
2. **확인** 을 선택합니다. **계약을 유효한 것으로 표시** 옵션을 **예** 로 설정합니다.  
3. **확인** 을 선택합니다.
4. 작업 창에서 **구매 계약** 을 선택합니다.
5. **구매 계약 확인** 을 선택합니다. **미리 보기/인쇄** 옵션을 사용하면 구매 계약에 대한 문서를 생성한 다음 인쇄하거나 공급업체에 보낼 수 있습니다. 나중에 계약을 업데이트하고 다시 확인하면 두 버전이 여기에 표시됩니다.  
6. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]