---
title: 이자 처리
description: 이 절차는 이자 메모를 생성, 인쇄 및 게시하는 방법을 보여줍니다.
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b97515e29d04866172216fc29af9a8d992568276c5e01acd67ad9d0028ea0c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450673"
---
# <a name="process-interest"></a>이자 처리

[!include [banner](../../includes/banner.md)]

이 절차는 이자 메모를 생성, 인쇄 및 게시하는 방법을 보여줍니다. 이 작업에는 USMF 데모 회사를 사용합니다.


## <a name="set-up-interest-on-the-posting-profile"></a>게시 프로필에 이자 설정
1. **탐색 창** 에서 **모듈 > 크레딧 및 수집 > 설정 > 고객 게시 프로필** 로 이동합니다.
2. **편집** 을 클릭합니다.
3. **설정 fastTab** 의 **이자 코드** 필드의 드롭다운 목록에서 이자 코드를 선택합니다. 이 게시 프로필을 사용하여 트랜잭션에 대해 이자를 계산하지 않으려면 필드를 비워 두십시오. **테이블 제한** fastTab을 사용하면 이자가 처리되는 방식을 변경할 수 있습니다. 이 필드를 예로 설정하면 이 게시 프로필에 대한 이자가 계산됩니다.  

## <a name="calculate-interest"></a>이자 계산
1. **탐색 창** 에서 **모듈 > 크레딧 및 수집 > 이자 > 이자 노트 생성** 으로 이동합니다.
2. 이자를 계산할 트랜잭션 유형을 선택해야 합니다. 이러한 유형의 모든 미결 트랜잭션이 계산에 포함됩니다.  
3. **이자** 를 '예'로 설정하면 이자에 대한 이자를 계산합니다. 이러한 트랜잭션을 포함하기 전에 이자에 대한 이자 계산을 관리하는 법을 확인할 수 있습니다.  
4. **시작 날짜** 필드에 이자를 계산할 날짜를 입력합니다. **시작 날짜** 를 지정하지 않으면 게시되지 않은 모든 이자 노트가 취소되고 이자는 트랜잭션 날짜부터 다시 계산됩니다.
5. **종료 날짜** 필드에 이자를 계산할 날짜를 입력합니다.
6. **게시 프로필 사용 위치** 필드에서 옵션을 선택합니다. 세 가지 게시 프로필 옵션이 있습니다.
    - 계정 - 각 이자 계산서에 고객 계정에 할당된 게시 프로필을 사용합니다. 
    - 선택 - 게시 프로필 필드에서 선택한 게시 프로필을 사용합니다.
    - 트랜잭션 – 각 이자 노트에 대해 이자가 계산되는 트랜잭션의 개별 게시 프로필을 사용합니다. 할당된 게시 프로필이 없는 트랜잭션의 경우 수취 계정 매개 변수 양식의 원장 및 판매세 영역에 지정된 게시 프로필을 사용합니다.  
7. **포함할 레코드** fastTab을 확장합니다.
8. **필터** 를 클릭합니다.
9. **기준** 필드에 고객 ID를 입력합니다. 예를 들어 'US-001'을 입력합니다.
6. **확인** 을 클릭합니다.
7. **확인** 을 클릭합니다.

## <a name="print-interest-notes"></a>이자 노트 인쇄
1. **탐색 창** 에서 **모듈 > 크레딧 및 수집 > 이자 > 이자 노트 검토 및 처리** 로 이동합니다.
2. **상태** 필드에서 '생성됨'을 선택합니다.
3. **인쇄** 필드에서 '인쇄 안 함'을 선택합니다.
4. **인쇄** 를 클릭합니다.
5. **포함할 레코드** fastTab을 확장합니다.
6. **확인** 을 클릭합니다.
7. 페이지를 닫습니다.

## <a name="post-the-interest-note"></a>이자 노트 게시
1. 게시할 준비가 된 이자 노트를 선택합니다(상태가 생성됨).
2. **게시** 를 클릭합니다.
3. 이자 노트의 게시 날짜를 입력합니다. 각 이자 노트에 대한 총계정원장 트랜잭션을 만들려면 예를 선택합니다. 예를 선택하지 않으면 고객에 대한 모든 이자 노트에 대한 이자가 누적되어 한 번의 트랜잭션으로 총계정원장에 게시됩니다.  
4. **포함할 레코드** fastTab을 확장합니다.
5. **확인** 을 클릭합니다.
6. **상태** 필드에서 '게시됨'을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]