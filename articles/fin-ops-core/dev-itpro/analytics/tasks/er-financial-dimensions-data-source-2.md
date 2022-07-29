---
title: ER 재무 차원을 데이터 소스로 사용(2부 - 모델 매핑)
description: 이번에는 재무 차원을 ER 보고서의 데이터 소스로 사용하도록 전자 보고(ER) 모델을 구성하는 방법에 대해 설명합니다. (2부)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc7c6bc299dd0af83db3b09b06276a210ecfada5
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "8460706"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a>ER 재무 차원을 데이터 소스로 사용(2부 - 모델 매핑)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 재무 차원을 ER 보고서의 데이터 소스로 사용하도록 전자 보고(ER) 모델을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 모든 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 'ER 재무 차원을 데이터 원본으로 사용(1부: 디자인 데이터 모델' 절차.


## <a name="add-required-data-sources-to-model-mapping"></a>모델 매핑에 필요한 데이터 소스 추가
1. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
2. 트리에서 '재무 차원 샘플 모델'을 선택합니다.
3. 디자이너를 클릭합니다.
4. 데이터 소스에 모델 매핑을 클릭합니다.
5. 새로 만들기를 클릭합니다.
6. 정의 필드에서 항목을 선택하십시오.
7. 이름 필드에 '차원 데이터 매핑'을 입력합니다.
8. 설명 필드에 '차원 데이터 매핑'을 입력합니다.
9. 저장을 클릭합니다.
10. 디자이너를 클릭합니다.
11. 트리에서 'Dynamics 365 for Operations\Table'을 선택합니다.
12. 루트 추가를 클릭합니다.
13. 이름 필드에 '회사'를 입력합니다.
14. 테이블 필드에 'CompanyInfo'를 입력합니다.
15. '확인'을 클릭합니다.
16. 트리에서 'Functions\Financial dimension details'를 선택합니다.
17. 루트 추가를 클릭합니다.
    * 이 데이터 소스는 이 모델을 데이터 소스로 사용할 보고서에 대해 재무 차원의 범위를 정의하는 방법을 지정합니다.  
18. 송장 필드에 값을 입력합니다.
19. 차원 요청 필드에서 예를 선택합니다.
    * 사용자가 사용자 대화 상자 양식에서 런타임 시 차원을 선택할 수 있도록 하려면 예를 선택합니다. 아니요로 설정하면 현재 인스턴스의 모든 재무 차원이 기본적으로 사용됩니다.  
20. 재무 차원 선택 필드에서 '법인'을 선택합니다.
    * 사용자가 조회 필드에서 현재 인스턴스에 대해 원하는 차원을 선택할 수 있도록 하려면 모두를 선택합니다.  사용자가 조회 필드에서 회사의 차원을 선택할 수 있도록 하려면 법인을 선택합니다.  사용자가 단일 차원 집합을 사용하여 차원을 선택할 수 있도록 하려면 차원을 선택합니다.  
21. 기본 계정 요청 필드에서 예를 선택합니다.
    * 사용자가 차원 목록의 일부로 기본 계정을 선택할 수 있도록 하려면 '기본 계정 요청'을 예로 설정합니다.   아니요로 설정하면 기본 계정이 차원 목록에 포함되지 않고 '기본 계정은 필수임' 옵션이 활성화됩니다. '주 계정은 필수 항목임'이 예로 설정된 경우 사용자의 선택에 관계없이 차원 목록에 주 계정을 포함합니다.  
22. '확인'을 클릭합니다.
![재무 차원의 세부 정보 데이터 소스 속성이 슬라이드 아웃됩니다.](../media/er-financial-dimensions-guides-model-mapping1.png)
23. 트리에서 'Dynamics 365 for Operations\테이블 레코드'를 선택합니다.
24. 루트 추가를 클릭합니다.
25. 이름 필드에 'LedgerJournal'을 입력합니다.
26. 쿼리 요청 필드에서 예를 선택합니다.
27. 테이블 필드에 'LedgerJournalTable'을 입력합니다.
28. '확인'을 클릭합니다.
![<모델 매핑 디자이너 페이지, 테이블은 데이터 소스 유형을 기록합니다.](../media/er-financial-dimensions-guides-model-mapping2.png)

## <a name="map-data-model-elements-to-added-data-sources"></a>데이터 모델 요소를 추가된 데이터 소스에 매핑
1. 트리에서 '분개'을 확장합니다.
2. 트리에서 'Journal\Transaction'을 확장합니다.
3. 트리에서 'Journal\Transaction\Dimensions data'를 확장합니다.
4. 트리에서 '차원 설정'을 확장합니다.
5. 트리에서 'LedgerJournal'을 확장합니다.
6. 트리에서 'Ledger\<Journal'을 확장합니다.
7. 트리에서 'chequesaccount\<Relations\ 원장저널트랜스'을 확장합니다.
8. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'를 선택합니다.
9. 트리에서 'Journal\Transaction\Voucher'를 선택합니다.
10. 바인딩을 클릭합니다.
11. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'을 선택합니다.
    * 예를 들어 LedgerDimension으로 설정된 재무 차원에 대한 참조의 경우 해당 데이터 소스 항목을 사용할 수 있습니다(LedgerDimension.Dimension). 이 데이터 소스 항목은 기록 목록으로 설정된 해당 차원의 재무 차원을 제공합니다.  
12. 트리에서 'LedgerJournalR\<elations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'을 확장합니다.
13. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main 계정 및 차원'을 확장합니다.
14. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account andDimensions\Value'를 확장합니다.
15. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account andDimensions\Definition'을 확장합니다.
16. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account anddimensional\Definition\Name'을 선택합니다.
17. 트리에서 'Journal\Transaction\Dimensions data\Name'을 선택합니다.
18. 바인딩을 클릭합니다.
19. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account andDimensions\Value\Description'을 선택합니다.
20. 트리에서 'Journal\Transaction\Dimensions data\Description'을 선택합니다.
21. 바인딩을 클릭합니다.
22. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account andDimensions\Value\Code'를 선택합니다.
23. 트리에서 'Journal\Transaction\Dimensions data\Code'를 선택합니다.
24. 바인딩을 클릭합니다.
25. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\메인 계정 및 차원'을 선택합니다.
26. 트리에서 'Journal\Transaction\Dimensions data'를 선택합니다.
27. 바인딩을 클릭합니다.
!모델 매핑 디자이너 페이지, 매핑 탭, 데이터 소스 트리.](../media/er-financial-dimensions-guides-model-mapping3.png)
28. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'를 선택합니다.
29. 트리에서 'Journal\Transaction\Debit'를 선택합니다.
30. 바인딩을 클릭합니다.
31. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'를 선택합니다.
32. 트리에서 'Journal\Transaction\Date'를 선택합니다.
33. 바인딩을 클릭합니다.
34. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'를 선택합니다.
35. 트리에서 'Journal\Transaction\Currency'를 선택합니다.
36. 바인딩을 클릭합니다.
37. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'을 선택합니다.
38. 트리에서 'Journal\Transaction\Credit'을 선택합니다.
39. 바인딩을 클릭합니다.
40. 트리에서 'LedgerJournal\<Relations\LedgerJournalTrans'를 선택합니다.
41. 트리에서 'Journal\Transaction'을 선택합니다.
42. 바인딩을 클릭합니다.
43. 트리에서 'LedgerJournal\Journal 배치 번호(JournalNum)'를 선택합니다.
44. 트리에서 'Journal\Batch'를 선택합니다.
45. 바인딩을 클릭합니다.
46. 트리에서 'LedgerJournal'을 선택합니다.
47. 트리에서 '분개'을 선택합니다.
48. 바인딩을 클릭합니다.
49. 트리에서 '차원'을 확장합니다.
50. 트리에서 '차원\기본 계정 및 차원'을 확장합니다.
51. 트리에서 '차원\기본 계정 및 차원\정의'를 확장합니다.
52. 트리에서 '차원\기본 계정 및 차원\정의\이름'을 선택합니다.
53. 트리에서 '차원 설정\코드'를 선택합니다.
54. 바인딩을 클릭합니다.
55. 트리에서 '차원\주 계정 및 차원\정의\보고서 열 이름'을 선택합니다.
56. 트리에서 '차원 설정\이름'을 선택합니다.
57. 바인딩을 클릭합니다.
58. 트리에서 '차원\기본 계정 및 차원'을 선택합니다.
59. 트리에서 '치수 설정'을 선택합니다.
60. 바인딩을 클릭합니다.
61. 트리에서 '회사'를 선택합니다.
62. 편집을 클릭합니다.
63. expressionAs스트링Text 필드에 'Company.'find()'.'name()''을 입력합니다.
    * 회사.'찾기()'.'이름()'  
64. 저장을 클릭합니다.
![ER 모델 매핑 디자이너 페이지.](../media/er-financial-dimensions-guides-model-mapping4.png)
65. 페이지를 닫습니다.
66. 저장을 클릭합니다.
67. 페이지를 닫습니다.

## <a name="complete-this-draft-models-version"></a>이 초안 모델 버전 완료
1. 페이지를 닫습니다.
2. 페이지를 닫습니다.
3. 상태 변경을 클릭합니다.
4. 완료를 클릭합니다.
5. '확인'을 클릭합니다.
![ER 구성 페이지.](../media/er-financial-dimensions-guides-model-mapping5.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
