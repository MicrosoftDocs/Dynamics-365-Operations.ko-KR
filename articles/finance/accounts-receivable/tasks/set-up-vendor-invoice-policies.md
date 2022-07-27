---
title: 공급업체 송장 정책 설정
description: 이 항목에서는 공급업체 송장 정책을 설정하는 방법에 대해 설명합니다.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f9707c7b283f42729126efa57e890e0df65ca8b
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451543"
---
# <a name="set-up-vendor-invoice-policies"></a>공급업체 송장 정책 설정

[!include [banner](../../includes/banner.md)]

이 항목에서는 공급업체 송장 정책을 설정하는 방법에 대해 설명합니다. 공급업체 송장 정책은 **공급업체 송장** 페이지를 사용하여 공급업체 송장을 게시할 때와 공급업체 송장 **정책 위반** 페이지를 열 때 실행됩니다. 송장을 워크플로에 제출할 때마다 공급업체 송장 정책을 실행하도록 공급업체 송장 워크플로를 구성할 수도 있습니다. 

- 공급업체 송장 정책은 송장 레지스터 또는 송장 분개장에 생성된 송장에는 적용되지 않습니다.  
- 송장 일치 확인은 공급업체 송장 정책을 사용하지 않고 대신 **지급 계정 매개 변수** 페이지에서 설정됩니다.  
- 이 레코딩은 USMF 데모 회사를 사용합니다. 지급 계정 관리자 또는 회계 관리자 역할이 이러한 단계를 수행합니다. 시작하기 전에 **송장 매칭** 구성 키가 선택되어 있는지 확인합니다.


## <a name="prepare-to-create-vendor-invoice-policies"></a>공급업체 송장 정책 만들기 준비
1. **탐색 창 > 모듈 > 지급 계정 > 설정 > 지금 계정 매개 변수** 로 이동합니다.
2. **송장 유효성 검사** 탭을 선택합니다.
3. **송장 헤더 상태 자동 업데이트** 확인란을 선택하거나 선택 취소합니다.
4. **확인** 을 선택합니다.
5. **불일치하는 송장 게시** 필드에서 옵션을 선택합니다.
6. 페이지를 닫습니다
7. **탐색 창 > 모듈 > 미지급 계정 > 정책 설정 > 공급업체 송장 정책** 으로 이동합니다.
8. **매개 변수** 를 선택합니다.
9. **추가** 를 선택합니다.
10. 홈 페이지로 돌아가려면 페이지를 닫습니다.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>공급업체 송장에 대한 정책 규칙 유형 만들기
1. **탐색 창 > 모듈 > 계정 > 정책 설정 > 공급업체 송장 정책 규칙 유형** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **규칙 이름** 및 **설명** 필드에 값을 입력합니다.
4. **쿼리 이름** 필드에서 드롭다운 버튼을 선택하여 룩업을 연 다음 원하는 레코드를 선택합니다.
5. **저장** 을 선택합니다.
6. 홈 페이지로 돌아가려면 페이지를 닫습니다.

## <a name="define-a-vendor-invoice-policy"></a>공급업체 송장 정책 정의
1. **탐색 창 > 모듈 > 미지급 계정 > 정책 설정 > 공급업체 송장 정책** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **이름** 및 **설명** 필드에 값을 입력합니다.
4. **정책 조직** 섹션을 확장하거나 축소합니다.
5. 트리에서 **Contoso Entertainment System USA** 를 선택합니다.
6. **추가** 를 선택합니다.
7. **정책 규칙** 섹션을 확장하거나 축소합니다.
8. **정책 규칙 만들기** 를 선택합니다.
9. **정책 규칙 설명** 필드에 값을 입력합니다.
10. **필터** 를 선택합니다.
11. **추가** 를 선택합니다. 원하는 레코드를 선택합니다.
12. **테이블**, **파생 테이블**, **필드** 필드의 드롭다운 메뉴에서 옵션을 선택하거나 입력합니다.
13. 페이지를 닫습니다
14. **기준** 필드에 값을 입력합니다.
15. **확인** 을 선택합니다.
16. **확인** 을 선택합니다.
17. 홈 페이지로 돌아가려면 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
