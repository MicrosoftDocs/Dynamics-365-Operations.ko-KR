---
title: ER 형식 구성을 사용하여 지불을 위한 전자 문서 생성
description: 이번에는 새로운 전자 보고(ER) 형식 구성을 사용하여 지급 처리를 위한 전자 문서를 생성하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 05295ff36ffd194b3f50fcdd9d7528c787c80f39104f46f9c51890a75a852735
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460708"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a>ER 형식 구성을 사용하여 지불을 위한 전자 문서 생성

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 새로운 전자 보고(ER) 형식 구성을 사용하여 지급 처리를 위한 전자 문서를 생성하는 방법을 설명합니다. 이러한 단계는 GBSI 샘플 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 '지급 문서 형식으로 구성 생성' 절차의 단계를 완료해야 합니다.


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>전자결제수단 설정 변경
1. 미지급금 > 지급 설정 > 지급 방법으로 이동하십시오.
2. 필요한 경우 파일 형식 섹션을 전환하여 확장합니다.
3. 빠른 필터를 사용하여 기록을 찾습니다. 예를 들어 값이 '전자'인 지급 방법 필드를 필터링합니다.
4. 편집을 클릭합니다.
5. 일반 전자 보고 필드를 예로 설정합니다.
    * 지급 파일 생성에 일반 전자 보고 패턴을 사용하려면 예를 선택합니다.  
6. 이름 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
7. BACS(영국 가상) 형식 구성을 선택합니다.
8. 저장을 클릭합니다.
9. 페이지를 닫습니다.

## <a name="test-the-format-of-generated-payment-files"></a>생성된 결제 파일의 형식 테스트
1. 미지급금 > 지급 > 지급 분개로 이동하십시오.
2. 새로 만들기를 클릭합니다.
3. 목록에서 선택한 행을 표시합니다.
4. 이름 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
5. 목록에서 선택한 행의 링크를 클릭합니다.
    * VendPay를 선택합니다.  
6. 저장을 클릭합니다.
7. 라인을 클릭합니다.
8. 회사 필드에 'DEMF'를 입력합니다.
    * DEMF  
9. 계정 필드에서 'DE-01001' 값을 지정하십시오.
    * DE-01001  
10. 설명 필드에 '결제'를 입력합니다.
    * 지급  
11. 차변 필드에 숫자를 입력합니다.
    * 1000  
12. 결제 탭을 클릭합니다.
13. 지급 방법 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
14. 목록에서 원하는 기록을 찾아 선택합니다.
    * 전자 값을 선택합니다.  
15. 목록에서 선택한 행의 링크를 클릭합니다.
16. 저장을 클릭합니다.
17. 결제 생성을 클릭합니다.
18. 지급 방법 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
19. 목록에서 원하는 기록을 찾아 선택합니다.
    * 전자 값을 선택합니다.  
20. 목록에서 선택한 행의 링크를 클릭합니다.
    * 전자 값을 선택합니다.  
21. 운전자 이름 필드에 값을 입력합니다.
    * 예를 들어 '결제'를 입력합니다.  
22. 은행 계좌 필드에서 드롭다운 버튼을 클릭하여 조회를 엽니다.
23. 목록에서 선택한 행의 링크를 클릭합니다.
    * GBSI OPER 값을 선택합니다.  
24. '확인'을 클릭합니다.
25. '확인'을 클릭합니다.
    * 생성된 결제 파일을 XML 형식으로 분석합니다. 디자인된 문서 레이아웃 및 정의된 결제 거래 속성과 비교합니다.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]