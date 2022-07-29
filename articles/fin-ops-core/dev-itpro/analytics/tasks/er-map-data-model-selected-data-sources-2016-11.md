---
title: ER 데이터 모델을 선택한 데이터 소스에 매핑
description: 이번에는 ER(전자 보고) 데이터 모델을 선택한 Microsoft Dynamics 365 Finance 데이터 원본에 매핑하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 60c20f6616d406bdd1ccdf42ac62eb4c1c5d27040f32469fa6dd370c41830450
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460686"
---
# <a name="er-map-data-model-to-selected-data-sources"></a>ER 데이터 모델을 선택한 데이터 소스에 매핑

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 전자 보고(ER) 데이터 모델을 선택한 데이터 소스에 매핑하는 방법을 설명합니다. 이 모델 매핑은 나중에 전자 지급 문서를 관리하는 데 사용할 형식 구성의 데이터 소스로 사용됩니다. 이 예시에서는 샘플 회사 Litware, Inc.의 데이터 모델을 데이터 소스에 매핑합니다. 이 단계를 완료하려면 먼저 '모델 매핑을 위한 데이터 소스 선택' 절차의 단계를 완료해야 합니다.


## <a name="open-er-configurations-tree"></a>ER 구성 트리 열기
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
2. 구성을 클릭합니다.

## <a name="select-created-model-mapping"></a>생성된 모델 매핑 선택
1. 트리에서 '결제(단순화 모델)'를 선택합니다.
    * 모델 구성 '결제(간이 모델)'가 미리 생성되었는지 확인하십시오. 그렇지 않으면 지금 중지하고 작업 가이드 '선택한 도메인의 데이터 모델로 새 구성 만들기' 완료 후 돌아갑니다.  
2. 모델 디자이너를 클릭합니다.
3. 데이터 소스에 모델 매핑을 클릭합니다.
4. 'CT 매핑' 기록을 선택합니다.
    * CT 매핑  

## <a name="bind-created-data-sources-to-data-model-elements"></a>생성된 데이터 소스를 데이터 모델 요소에 바인딩
1. 디자이너를 클릭합니다.
2. 트리에서 '처리 날짜 및 시간(ProcessingDateTime)'을 선택합니다.
3. 트리에서 '처리 날짜(ProcessingDateTime)'를 선택합니다.
4. 바인딩을 클릭합니다.
5. 트리에서 '결제 메시지 식별(MessageIdentification)'을 선택합니다.
6. 트리에서 '트랜잭션'을 확장합니다.
7. 트리에서 'Transactions\Journal batch number(JournalNum)'를 선택합니다.
8. 바인딩을 클릭합니다.
9. 트리에서 '결제'를 선택합니다.
10. 트리에서 '트랜잭션'을 선택합니다.
11. 바인딩을 클릭합니다.
12. 트리에서 '결제=거래'를 확장합니다.
13. 트리에서 'Payments= Transactions\Creditor'를 확장합니다.
14. 트리에서 'Payments= Transactions\Creditor\Account'를 확장합니다.
15. 트리에서 'Payments= Transactions\Creditor\Account\Currency code(Currency)'를 선택합니다.
16. 트리에서 'Transactions\vendBankAccountInTransactionCompany()'를 확장합니다.
17. 트리에서 'Transactions\vendBankAccountInTransactionCompany()\Currency(CurrencyCode)'를 선택합니다.
18. 바인딩을 클릭합니다.
19. 트리에서 'Payments= Transactions\Creditor\Account\IBAN code(IBAN)'를 선택합니다.
20. 트리에서 'Transactions\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)'을 선택합니다.
21. 바인딩을 클릭합니다.
22. 트리에서 'Payments= Transactions\Creditor\Account\Number'를 선택합니다.
23. 트리에서 'Transactions\vendBankAccountInTransactionCompany()\Bank account number(AccountNum)'를 선택합니다.
24. 바인딩을 클릭합니다.
25. 트리에서 'Payments= Transactions\Creditor\Agent'를 확장합니다.
26. 트리에서 'Payments= Transactions\Creditor\Agent\Name'을 선택합니다.
27. 트리에서 'Transactions\vendBankAccountInTransactionCompany()\Name'을 선택합니다.
28. 바인딩을 클릭합니다.
29. 트리에서 'Payments= Transactions\Creditor\Agent\Routing number(RoutingNumber)'를 선택합니다.
30. 트리에서 'Transactions\vendBankAccountInTransactionCompany()\Routing number(RegistrationNum)'을 선택합니다.
31. 바인딩을 클릭합니다.
32. 트리에서 'Payments= Transactions\Creditor\Agent\SWIFT code(SWIFT)'를 선택합니다.
33. 트리에서 'Transactions\vendBankAccountInTransactionCompany()\SWIFT code(SWIFTNo)'를 선택합니다.
34. 바인딩을 클릭합니다.
35. 트리에서 'Payments= Transactions\Creditor\Name'을 선택합니다.
36. 트리에서 'Transactions\findVendTable()'을 확장합니다.
37. 트리에서 'Transactions\findVendTable()\name()'을 선택합니다.
38. 바인딩을 클릭합니다.
39. 트리에서 'Payments= Transactions\Currency code(Currency)'를 선택합니다.
40. 트리에서 '트랜잭션\>목록'을 확장합니다.
41. 트리에서 'Transactions\>Relations\Currency table(Currency)'를 확장합니다.
42. 트리에서 'Transactions\>Relations\Currency table(Currency)\Currency code(CurrencyCodeISO)'를 선택합니다.
43. 바인딩을 클릭합니다.
44. 트리에서 'Payments= Transactions\Debtor'를 확장합니다.
45. 트리에서 'Payments= Transactions\Debtor\Account'를 확장합니다.
46. 트리에서 'Payments= Transactions\Debtor\Account\Currency code(Currency)'를 선택합니다.
47. 트리에서 '은행계좌(BankAccount)'를 선택합니다.
48. 트리에서 '은행 계좌(BankAccount)'를 확장합니다.
49. 트리에서 '은행계좌(BankAccount)\Currency(CurrencyCode)'를 선택합니다.
50. 바인딩을 클릭합니다.
51. 트리에서 '은행계좌(BankAccount)\IBAN'을 선택합니다.
52. 트리에서 '결제=트랜잭션\채무자\계정\IBAN 코드(IBAN)'를 선택합니다.
53. 바인딩을 클릭합니다.
54. 트리에서 'Payments= Transactions\Debtor\Account\Number'를 선택합니다.
55. 트리에서 '은행계좌(BankAccount)\은행계좌번호(AccountNum)'를 선택합니다.
56. 바인딩을 클릭합니다.
57. 트리에서 'Payments= Transactions\Debtor\Agent'를 확장합니다.
58. 트리에서 'Payments= Transactions\Debtor\Agent\Name'을 선택합니다.
59. 트리에서 '은행계좌(BankAccount)\이름'을 선택합니다.
60. 바인딩을 클릭합니다.
61. 트리에서 'Payments= Transactions\Debtor\Agent\Routing number(RoutingNumber)'를 선택합니다.
62. 트리에서 '은행계좌(BankAccount)\라우팅번호(RegistrationNum)'를 선택합니다.
63. 바인딩을 클릭합니다.
64. 트리에서 'Payments= Transactions\Debtor\Agent\SWIFT code(SWIFT)'를 선택합니다.
65. 트리에서 '은행계좌(BankAccount)\SWIFT 코드(SWIFTNo)'를 선택합니다.
66. 바인딩을 클릭합니다.
67. 트리에서 '결제=트랜잭션\채무자\이름'을 선택합니다.
68. 트리에서 '회사정보(회사)'를 선택합니다.
69. 트리에서 '회사정보(회사)'를 확장합니다.
70. 트리에서 '회사정보(회사)\이름'을 선택합니다.
71. 바인딩을 클릭합니다.
72. 트리에서 '결제=트랜잭션\설명'을 선택합니다.
73. 트리에서 '트랜잭션\설명(Txt)'을 선택합니다.
74. 바인딩을 클릭합니다.
75. 트리에서 '결제=트랜잭션\종료 식별 코드(End2EndID)'를 선택합니다.
76. 트리에서 'Transactions\$EndToEndID'을 선택합니다.
77. 바인딩을 클릭합니다.
78. 트리에서 'Payments= Transactions\Instructed amount(InstructedAmount)'를 선택합니다.
79. 트리에서 'Transactions\$Amount'을 선택합니다.
80. 바인딩을 클릭합니다.
81. 트리에서 'Payments= Transactions\Transaction date(TransactionDate)'를 선택합니다.
82. 트리에서 'Transactions\Date(TransDate)'를 선택합니다.
83. 바인딩을 클릭합니다.

## <a name="validate-created-mapping"></a>생성된 매핑 확인
1. 확인을 클릭합니다.
    * 모든 바인딩이 정상인지 확인하기 위해 새 매핑의 유효성을 검사합니다.  
2. 화살표를 클릭하여 오류 목록 섹션을 확장하거나 축소합니다.
3. 저장을 클릭합니다.
4. 페이지를 닫습니다.
5. 페이지를 닫습니다.
6. 페이지를 닫습니다.

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a>모델 구성의 현재 버전 상태 변경
1. 상태 변경을 클릭합니다.
    * 디자인된 모델 구성의 상태를 초안에서 완료로 변경하여 지급 형식 디자인에 사용할 수 있도록 합니다.  
2. 완료를 클릭합니다.
    * 완료를 선택합니다.  
3. 설명 필드에 값을 입력합니다.
    * 예: '버전 1'.  
4. '확인'을 클릭합니다.
5. 현재 구성의 완료된 버전을 선택합니다.
    * 생성된 구성은 완료된 버전 1로 저장됩니다.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]