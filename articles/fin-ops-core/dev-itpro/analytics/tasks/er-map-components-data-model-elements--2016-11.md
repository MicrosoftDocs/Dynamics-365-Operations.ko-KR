---
title: ER 생성된 형식의 구성 요소를 데이터 모델 요소에 매핑(2016년 11월)
description: 이번에는 생성된 전자 보고(ER) 구성의 구성 요소에 데이터 모델 요소를 매핑하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ae4b3123660d123fc5c06cbe0a69d5c66d306252ec2a117a1e6045505022f5a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460687"
---
# <a name="er-map-components-of-the-created-format-to-data-model-elements-november-2016"></a>ER 생성된 형식의 구성 요소를 데이터 모델 요소에 매핑(2016년 11월)

[!include [banner](../../includes/banner.md)]

다음 절차는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 지급 비즈니스 도메인에 대한 전자 문서 형식을 정의하는 생성된 전자 보고(ER) 구성의 구성 요소에 데이터 모델 요소를 매핑하는 방법을 보여줍니다. 이 형식은 나중에 지급 처리를 위한 전자 문서를 생성하는 데 사용됩니다. 이 예시에서는 샘플 회사인 'Litware, Inc.'에 대한 형식 구성을 생성합니다. ER 구성은 모든 회사에서 공유되므로 이러한 단계는 모든 회사에서 수행할 수 있습니다. 이 단계를 완료하려면 먼저 '형식 구성 만들기' 작업 가이드의 단계를 완료해야 합니다.


## <a name="select-a-format-configuration"></a>형식 구성 선택
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
2. 보고 구성을 클릭합니다.
3. 트리에서 '결제(단순화된 모델)'를 확장합니다.
4. 트리에서 '결제(간략한 모델)\BACS(영국 가상)'를 선택합니다.
5. 디자이너를 클릭합니다.

## <a name="map-format-components-to-data-model-elements"></a>데이터 모델 요소에 형식 구성 요소 매핑
1. 확장/축소를 클릭합니다.
2. 매핑 탭을 클릭합니다.
3. 트리에서 '모델'을 확장합니다.
4. 트리에서 'Xml\Message\ProcessingDate\DateTime'을 선택합니다.
5. 트리에서 'model\ProcessingDateTime'을 선택합니다.
6. 바인딩을 클릭합니다.
7. 트리에서 'Xml\Message\MessageId\스트링'을 선택합니다.
8. 트리에서 'model\MessageIdentification'을 선택합니다.
9. 바인딩을 클릭합니다.
10. 트리에서 '모델\결제'를 확장합니다.
11. 트리에서 'Xml\Message\Payments\Item\Amount\스트링'을 선택합니다.
12. 트리에서 'model\Payments\InstructedAmount'를 선택합니다.
13. 바인딩을 클릭합니다.
14. 트리에서 'Xml\Message\Payments\Item\TransDate\DateTime'을 선택합니다.
15. 트리에서 'model\Payments\TransactionDate'를 선택합니다.
16. 바인딩을 클릭합니다.
17. 트리에서 'Xml\Message\Payments\Item\Description\스트링'을 선택합니다.
18. 트리에서 'model\Payments\Description'을 선택합니다.
19. 바인딩을 클릭합니다.
20. 트리에서 'Xml\Message\Payments\Item\Currency\스트링'을 선택합니다.
21. 트리에서 'model\Payments\Currency'를 선택합니다.
22. 바인딩을 클릭합니다.
23. 트리에서 'Xml\Message\Payments\Item\Id'를 선택합니다.
24. 트리에서 'model\Payments\End2EndID'를 선택합니다.
25. 바인딩을 클릭합니다.
26. 트리에서 '모델\결제\채권자'를 확장합니다.
27. 트리에서 '모델\결제\채권자\계정'을 확장합니다.
28. 트리에서 '모델\결제\채권자\에이전트'를 확장합니다.
29. 트리에서 'Xml\Message\Payments\Item\Vendor\Name\String'을 선택합니다.
30. 트리에서 'model\Payments\Creditor\Name'을 선택합니다.
31. 바인딩을 클릭합니다.
32. 트리에서 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber\스트링'을 선택합니다.
33. 트리에서 'model\Payments\Creditor\Agent\RoutingNumber'를 선택합니다.
34. 바인딩을 클릭합니다.
35. 트리에서 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber\스트링'을 선택합니다.
36. 트리에서 'model\Payments\Creditor\Account\Number'를 선택합니다.
37. 바인딩을 클릭합니다.
38. 트리에서 'Xml\Message\Payments\Item\Payer\Name\스트링'을 선택합니다.
39. 트리에서 'model\Payments\Debtor'를 확장합니다.
40. 트리에서 'model\Payments\Debtor\Account'를 확장합니다.
41. 트리에서 'model\Payments\Debtor\Agent'를 확장합니다.
42. 트리에서 '모델\결제\채무자\이름'을 선택합니다.
43. 바인딩을 클릭합니다.
44. 트리에서 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber\스트링'을 선택합니다.
45. 트리에서 'model\Payments\Debtor\Agent\RoutingNumber'를 선택합니다.
46. 바인딩을 클릭합니다.
47. 트리에서 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber\스트링'을 선택합니다.
48. 트리에서 'model\Payments\Debtor\Account\Number'를 선택합니다.
49. 바인딩을 클릭합니다.
50. 트리에서 'Xml\Message\Payments\Item'을 선택합니다.
51. 트리에서 '모델\결제'를 선택합니다.
52. 바인딩을 클릭합니다.
53. 저장을 클릭합니다.

## <a name="validate-format-mapping"></a>형식 매핑 확인
1. 확인을 클릭합니다.
    * 모든 바인딩이 정상인지 확인하기 위해 새 매핑의 유효성을 검사합니다.  
2. 페이지를 닫습니다.

## <a name="change-status-of-the-current-version-of-format-configuration"></a>형식 구성의 현재 버전 상태 변경
다음 단계에서는 형식 구성 상태를 초안에서 완료로 변경하여 지급 문서 생성에 사용할 수 있도록 합니다.  
1. 상태 변경을 클릭합니다.
2. 완료를 클릭합니다.
3. 설명 필드에 값을 입력합니다.
    * 예: '버전 1'.  
4. '확인'을 클릭합니다.
5. 현재 구성의 완료된 버전을 선택하십시오.
    * 구성은 데이터 모델의 버전 1을 기반으로 하는 형식의 완성된 버전 1.1: 버전 1로 저장됩니다.  

## <a name="define-effective-date-for-completed-version-of-format"></a>형식의 완료된 버전에 대한 유효 날짜 정의
각 형식 버전은 특정 날짜부터 사용 가능하도록 구성할 수 있습니다. 특정 날짜에 둘 이상의 형식 버전이 활성화된 경우 최신 형식(버전 번호 기반)이 선택되어 사용됩니다. 세션 날짜 값은 적절한 버전 선택을 위해 사용됩니다.  

## <a name="restrict-access-to-created-format-from-companies"></a>회사에서 만든 형식에 대한 액세스 제한
1. ISO 국가/지역 코드 섹션을 확장합니다.
    * 각 형식에 대한 액세스는 형식이 적용되는 특정 국가/지역을 식별하여 제한할 수 있습니다. 특정 형식의 국가/지역 목록이 비어 있는 경우 이 형식은 모든 회사에서 사용할 수 있습니다. 일부 ISO 국가/지역 코드가 국가/지역 목록에 삽입되면 기본 주소가 국가/지역에 있는 경우 회사에서만 형식을 사용할 수 있습니다.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]