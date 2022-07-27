---
title: 예외 조사 또는 해결
description: 공급업체 송장 정책은 공급업체 송장 페이지를 사용하여 공급업체 송장을 게시할 때와 공급업체 송장 정책 위반 페이지를 열 때 실행됩니다.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendParameters,  SysPolicyListPage, SysPolicyParameters, SysPolicySourceDocumentRuleType, SysPolicy, SysPolicySourceDocumentRule, SysQueryForm, SysQueryTableLookUp, SysQueryPrefixLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32ff53198f61e1d1af3c437e9488c2a246cf820a
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451567"
---
# <a name="research-or-resolve-exceptions"></a>예외 조사 또는 해결

[!include [banner](../../includes/banner.md)]

공급업체 송장 정책은 **공급업체 송장** 페이지를 사용하여 공급업체 송장을 게시할 때와 공급업체 송장 **정책 위반** 페이지를 열 때 실행됩니다. 송장을 워크플로에 제출할 때마다 공급업체 송장 정책을 실행하도록 공급업체 송장 워크플로를 구성할 수도 있습니다. 

공급업체 송장 정책은 **송장 등록** 또는 **송장 분개장** 에서 생성된 송장에는 적용되지 않습니다. 

송장 매칭 검증은 공급업체 송장 정책을 사용하지 않지만 **지급 계정 매개 변수** 페이지에서 설정합니다.

이 레코딩은 USMF 데모 회사를 사용합니다. 지급 계정 관리자 또는 회계 관리자 역할이 이러한 단계를 수행합니다. 시작하기 전에 **송장 매칭 구성** 키가 선택되어 있는지 확인하세요.


## <a name="prepare-to-create-vendor-invoice-policies"></a>공급업체 송장 정책 만들기 준비
1. **지급 계정 > 설정 > 지급 계정 매개 변수** 로 이동합니다.
2. **송장 유효성 검사** 탭을 클릭합니다.
3. **송장 헤더 상태 자동 업데이트** 확인란을 선택하거나 선택 취소합니다.
4. **확인** 을 클릭합니다.
5. **불일치하는 송장 게시** 필드에서 옵션을 선택합니다.
6. 페이지를 닫습니다.
7. **지급 계정 > 정책 설정> 공급업체 송장 정책** 으로 이동합니다.
8. **매개 변수** 를 클릭합니다.
9. **추가** 를 클릭합니다.
10. 페이지를 닫습니다.

## <a name="create-policy-rule-types-for-vendor-invoices"></a>공급업체 송장에 대한 정책 규칙 유형 만들기
1. **지급 계정 > 정책 설정> 공급업체 송장 정책 규칙 유형** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **규칙 이름** 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다.
5. **쿼리 이름** 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
6. 목록에서 원하는 레코드를 찾아 선택합니다.
7. 목록에서 선택한 행의 링크를 클릭합니다.
8. **저장** 을 클릭합니다.
9. 페이지를 닫습니다.

## <a name="define-a-vendor-invoice-policy"></a>공급업체 송장 정책 정의
1. **지급 계정 > 정책 설정> 공급업체 송장 정책** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **이름** 필드에 값을 입력합니다.
4. **설명** 필드에 값을 입력합니다.
5. **정책 조직** 섹션을 확장하거나 축소합니다.
6. 트리에서 'Contoso Entertainment System USA'를 선택합니다.
7. **추가** 를 클릭합니다.
8. **정책 규칙** 섹션을 확장하거나 축소합니다.
9. **정책 규칙 만들기** 를 클릭합니다.
10. **정책 규칙 설명** 필드에 값을 입력합니다.
11. **필터** 를 클릭합니다.
12. **추가** 를 클릭합니다.
13. 목록에서 선택한 행을 표시합니다.
14. **테이블** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
15. 목록에서 선택한 행의 링크를 클릭합니다.
16. **파생 테이블** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
17. 목록에서 선택한 행의 링크를 클릭합니다.
18. **필드** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
19. **필드** 필드에 값을 입력합니다.
20. 페이지를 닫습니다.
21. **기준** 필드에 값을 입력합니다.
22. **확인** 을 클릭합니다.
23. **확인** 을 클릭합니다.
24. 페이지를 닫습니다.
25. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
