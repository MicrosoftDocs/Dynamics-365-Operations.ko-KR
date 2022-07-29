---
title: ER 모델 매핑을 정의하고 이에 대한 데이터 소스 선택
description: 이번에는 시스템 관리자 또는 전자 보고 개발자가 전자 보고 데이터 모델에 대한 데이터 소스를 선택하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 69fb025b273aca6a0cf7733732f2849686eaa470ded6804a10b793cff9837562
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460718"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a>ER 모델 매핑을 정의하고 이에 대한 데이터 소스 선택

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 전자 보고(ER) 데이터 모델에 대한 데이터 소스를 선택하는 방법을 설명합니다. 데이터 소스는 디자인 타임에 선택한 데이터 모델의 개별 구성 요소에 바인딩되고 런타임에 해당 데이터 모델에 비즈니스 데이터를 채웁니다. 이 예시에서는 샘플 회사 Litware, Inc.에 대해 생성된 기존 데이터 모델에 대한 데이터 원본을 선택합니다. 이 단계를 완료하려면 먼저 '새 데이터 모델 생성' 절차의 단계를 완료해야 합니다.


## <a name="open-the-electronic-reporting-configurations-tree"></a>전자 보고 구성 트리 열기
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
2. 보고 구성을 클릭합니다.

## <a name="insert-a-new-model-mapping"></a>새 모델 매핑 삽입
1. 트리에서 '결제(단순화 모델)'를 선택합니다.
2. 디자이너를 클릭합니다.
3. 데이터 소스에 모델 매핑을 클릭합니다.
4. 새로 만들기를 클릭합니다.
    * 이렇게 하면 데이터 모델을 데이터 원본에 매핑하는 새 기록이 생성됩니다. 이 예시에서는 데이터 모델을 원하는 지급 유형인 신용 이체에 대한 데이터 소스에 매핑합니다.     특정 데이터 모델에 대해 둘 이상의 매핑을 디자인할 수 있습니다. 예를 들어 자동 이체 또는 신용 이체와 같은 다양한 지급 유형에 대한 매핑을 생성할 수 있습니다. 이 예시에서는 신용 전송에 대한 매핑을 생성합니다.  
5. 이름 필드에 'CT 매핑'을 입력합니다.
    * CT 매핑  
6. 설명 필드에 '결제 모델 매핑 CT'를 입력합니다.
    * 결제 모델 매핑 CT  
7. 정의 필드에 'CustomerCreditTransferInitiation'을 입력합니다.
    * CustomerCreditTransferInitiation  
8. 해결은 정의를 변경합니다.
9. 저장을 클릭합니다.

## <a name="define-required-data-sources-for-the-current-model-mapping"></a>현재 모델 매핑에 필요한 데이터 소스 정의
1. 디자이너를 클릭합니다.
2. 트리에서 'Dynamics 365 for Operations\테이블 레코드'를 선택합니다.
3. 루트 추가를 클릭합니다.
    * 결제 거래에 액세스하려면 이 데이터 소스를 입력하십시오.  
4. 이름 필드에 '트랜잭션'을 입력합니다.
    * 트랜잭션  
5. 레이블 필드에 '거래'를 입력합니다.
    * 트랜잭션  
6. 도움말 필드에 '원장 분개 라인'을 입력합니다.
    * 원장 분개 라인  
7. 쿼리 요청 필드에서 예를 선택합니다.
    * 예를 선택합니다.  
8. 테이블 필드에 'LedgerJournalTrans'를 입력합니다.
    * 원장분개트랜스  
9. '확인'을 클릭합니다.
    * LedgerJournalTrans 테이블을 현재 데이터 모델의 데이터 소스로 선택하십시오.  
10. 트리에서 'Functions\Calculated field'를 선택합니다.
11. 추가를 클릭합니다.
    * 추가를 클릭하여 새 계산된 필드를 추가합니다.  
12. 이름 필드에 '$EndToEndID'를 입력합니다.
    * $EndToEndID  
13. 수식 편집을 클릭합니다.
14. 트리에서 '스트링\CONCATENATE'를 선택합니다.
15. 함수 추가를 클릭합니다.
16. 트리에서 '트랜잭션'을 확장합니다.
17. 트리에서 'Transactions\Voucher'을 선택합니다.
18. 데이터 소스 추가를 클릭합니다.
19. 수식 필드에 'CONCATENATE(Transactions.Voucher, '-', '를 입력합니다.
    * 수식 끝에 [ , '-', ]를 입력합니다.  
20. 트리에서 '스트링\TEXT'를 선택합니다.
21. 함수 추가를 클릭합니다.
22. 트리에서 'Transactions\Record-ID(RecId)'를 선택합니다.
23. 데이터 소스 추가를 클릭합니다.
24. 수식 필드에 'CONCATENATE(Transactions.Voucher, '-', TEXT(Transactions.RecId))'를 입력합니다.
    * 수식 끝에 [))]를 입력합니다.  
25. 저장을 클릭합니다.
    * 생성된 수식에 대해 오류가 발견되지 않았는지 확인합니다. 수식 편집기 컨트롤 아래의 오류 탭을 참조하십시오.  
26. 페이지를 닫습니다.
27. '확인'을 클릭합니다.
    * 이 데이터 원본에 계산된 필드를 추가합니다.  
28. 추가를 클릭합니다.
    * 추가를 클릭하여 새 계산된 필드를 추가합니다.  
29. 이름 필드에 '$Amount'를 입력합니다.
    * $금액  
30. 수식 편집을 클릭합니다.
31. 트리에서 '트랜잭션'을 확장합니다.
32. 트리에서 'Transactions\Debit(AmountCurDebit)'를 선택합니다.
33. 데이터 소스 추가를 클릭합니다.
34. 수식 필드에 'Transactions.AmountCurDebit - '를 입력합니다.
    * 수식 끝에 [ - ]를 입력합니다.  
35. 트리에서 'Transactions\Credit(AmountCurCredit)'을 선택합니다.
36. 데이터 소스 추가를 클릭합니다.
37. 저장을 클릭합니다.
38. 페이지를 닫습니다.
39. '확인'을 클릭합니다.
    * 그러면 현재 데이터 모델에 대해 선택한 데이터 원본에 $Amount 계산된 필드가 추가됩니다.  
40. 트리에서 'Transactions\$Amount'을 선택합니다.
41. 트리에서 '트랜잭션'을 확장합니다.
42. 트리에서 'Transactions\$Amount'을 펼치거나 접습니다.
43. 트리에서 '트랜잭션'을 펼치거나 접습니다.
44. 트리에서 'Dynamics 365 for Operations\테이블 레코드'를 선택합니다.
45. 루트 추가를 클릭합니다.
    * 회사의 은행 계좌 세부 정보에 액세스하려면 이 데이터 소스를 입력하십시오.  
46. 이름 필드에 'BankAccount'를 입력합니다.
    * 은행 계좌  
47. 레이블 필드에 '은행 계좌'를 입력합니다.
    * 은행 계좌  
48. 도움말 필드에 '은행 계좌'를 입력합니다.
    * 은행 계좌  
49. 쿼리 요청 필드에서 예를 선택합니다.
    * 예를 선택합니다.  
50. 테이블 필드에 'BankAccountTable'을 입력합니다.
    * 은행 계좌 테이블  
51. '확인'을 클릭합니다.
    * BankAccountTable 테이블을 현재 데이터 모델의 데이터 원본으로 선택합니다.  
52. 루트 추가를 클릭합니다.
    * 회사의 요구 사항에 액세스하려면 이 데이터 소스를 입력하십시오.  
53. 이름 필드에 '회사'를 입력합니다.
    * 회사  
54. 송장 필드에 값을 입력합니다.
    * 회사 정보  
55. 도움말 필드에 '회사 정보'를 입력합니다.
    * 회사 정보  
56. 쿼리 요청 필드에서 예를 선택합니다.
    * 예를 선택합니다.  
57. 테이블 필드에 'CompanyInfo'를 입력합니다.
    * 회사 정보  
58. '확인'을 클릭합니다.
    * 현재 데이터 모델에 대한 데이터 원본으로 CompanyInfo 테이블을 선택합니다.  
59. 트리에서 'Functions\Calculated field'를 선택합니다.
60. 루트 추가를 클릭합니다.
    * 계산된 필드를 새 데이터 원본으로 삽입합니다.  
61. 이름 필드에 'ProcessingDateTime'을 입력합니다.
    * 처리날짜시간  
62. 레이블 필드에 '처리 날짜 및 시간'을 입력합니다.
    * 처리 날짜 및 시간  
63. 수식 편집을 클릭합니다.
64. 트리에서 '날짜/시간\SESSIONNOW'를 선택합니다.
65. 함수 추가를 클릭합니다.
66. 저장을 클릭합니다.
67. 페이지를 닫습니다.
68. '확인'을 클릭합니다.
    * ProcessingDateTime 계산된 필드를 현재 데이터 모델의 데이터 원본으로 추가합니다.  
69. 저장을 클릭합니다.
70. 페이지를 닫습니다.
71. 페이지를 닫습니다.
72. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]