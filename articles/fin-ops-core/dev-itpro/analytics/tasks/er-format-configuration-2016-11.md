---
title: ER 형식 구성 생성(2016년 11월)
description: 이번에는 전자 보고(ER)에 대한 형식 구성을 만드는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5d59f0f7c914cc6d59ae441e6f6b8ff249a3e9c03c6ee4b4a75421d875f826a0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460890"
---
# <a name="er-create-a-format-configuration-november-2016"></a>ER 형식 구성 생성(2016년 11월)

[!include [banner](../../includes/banner.md)]

이번에는 시스템 관리자 또는 전자 보고 개발자 역할의 사용자가 전자 보고(ER)에 대한 형식 구성을 생성할 수 있는 방법에 대해 설명합니다. 이 형식 구성은 지급 처리에 사용되는 전자 문서 형식을 정의합니다. 이 예시에서는 샘플 회사인 Litware, Inc.에 대한 형식 구성을 생성합니다. 이 단계를 완료하려면 먼저 '선택한 데이터 소스에 모델 매핑' 절차의 단계를 완료해야 합니다.


## <a name="create-a-new-format-configuration"></a>새 형식 구성 만들기
1. **조직 관리 > 작업 영역 > 전자 보고** 로 이동합니다.
2. **보고 구성** 을 클릭합니다.
3. 트리에서 **결제(단순화 모델)** 를 선택합니다.
4. **구성 만들기** 를 클릭하여 드롭 대화 상자를 엽니다.

 > [!NOTE]
 > **구성 만들기** 가 표시되지 않으면 **전자 보고 매개 변수** 페이지에서 디자인 모드를 활성화해야 합니다. 
 
5. **새로 만들기** 필드에 **데이터 모델 PaymentModel 기반 형식** 을 입력합니다.
6. **이름** 필드에 **BACS(영국 가상)** 를 입력합니다.
7. **설명** 필드에 **BACS 공급 업체 지급 형식(영국 가상)** 을 입력합니다.
    * 활성 구성 공급자가 여기에 자동으로 입력됩니다. 이 공급자는 이 구성을 유지할 수 있습니다. 다른 공급자는 이 구성을 사용할 수 있지만 유지할 수는 없습니다.  
    * 전자 문서의 특정 형식을 정의할 수 있습니다. 런타임에 형식을 선택하려면 이 필드를 비워 둡니다.  
8. **데이터 모델 정의** 필드에서 값을 입력하거나 선택하십시오.
9. **구성 만들기** 를 클릭합니다. 새 구성이 생성되었습니다. 초안 버전은 전자 문서 관리를 위한 디자인 형식을 저장하는 데 사용할 수 있습니다.  

## <a name="design-the-format-of-an-electronic-document"></a>전자 문서 형식 디자인
1. **디자이너** 를 클릭합니다.
2. **루트 추가** 를 클릭하여 드롭 대화 상자를 엽니다.
3. 트리에서 **Common\File** 을 선택합니다.
4. **이름** 필드에 **Xml** 을 입력합니다.
5. **인코딩** 필드에 **UTF-8** 을 입력합니다.
6. **확인** 을 클릭합니다.
7. **추가** 를 클릭합니다.
8. 트리에서 **XML\요소** 를 선택합니다.
9. **이름** 필드에 **메시지** 를 입력합니다.
10. **확인** 을 클릭합니다.
11. 트리에서 **Xml\Message** 를 선택합니다.
12. **요소 추가** 를 클릭합니다.
13. **이름** 필드에 **ProcessingDate** 를 입력합니다.
14. **확인** 을 클릭합니다.
15. **요소 추가** 를 클릭합니다.
16. 이름 필드에 **MessageId** 를 입력합니다.
17. **확인** 을 클릭합니다.
18. **요소 추가** 를 클릭합니다.
19. **이름** 필드에 **지급** 을 입력하십시오.
20. **확인** 을 클릭합니다.
21. 트리에서 **Xml\Message\Payments** 를 선택합니다.
22. **요소 추가** 를 클릭합니다.
23. **이름** 필드에 **항목** 을 입력하십시오.
24. **확인** 을 클릭합니다.
25. 트리에서 **Xml\Message\Payments\Item** 을 선택합니다.
26. **추가** 를 클릭합니다.
27. 트리에서 **XML\특성** 을 선택합니다.
28. 이름 필드에 **ID** 를 입력합니다.
29. **확인** 을 클릭합니다.
30. **추가** 를 클릭합니다.
31. 트리에서 **XML\요소** 를 선택합니다.
32. 이름 필드에 **공급 업체** 를 입력합니다.
33. **확인** 을 클릭합니다.
34. 트리에서 **Xml\Message\Payments\Item\Vendor** 를 선택합니다.
35. **요소 추가** 를 클릭합니다.
36. 이름 필드에 **이름** 을 입력합니다.
37. **확인** 을 클릭합니다.
38. **요소 추가** 를 클릭합니다.
39. **이름** 필드에 **은행** 을 입력하십시오.
40. **확인** 을 클릭합니다.
41. 트리에서 **Xml\Message\Payments\Item\Vendor\Bank** 를 선택합니다.
42. **요소 추가** 를 클릭합니다.
43. **이름** 필드에 **RoutingNumber** 를 입력하십시오.
44. **확인** 을 클릭합니다.
45. **요소 추가** 를 클릭합니다.
46. **이름** 필드에 **AccountNumber** 를 입력하십시오.
47. **확인** 을 클릭합니다.
48. 트리에서 **Xml\Message\Payments\Item\Vendor** 를 선택합니다.
49. **복사** 를 클릭합니다.
50. 트리에서 **Xml\Message\Payments\Item** 을 선택합니다.
51. **붙여넣기** 를 클릭합니다.
52. **이름** 필드에 **지급인** 을 입력하십시오.
53. 트리에서 **Xml\Message\Payments\Item** 을 선택합니다.
54. **요소 추가** 를 클릭합니다.
55. **이름** 필드에 **통화** 를 입력합니다.
56. **확인** 을 클릭합니다.
57. **요소 추가** 를 클릭합니다.
58. **이름** 필드에 **설명** 을 입력합니다.
59. **확인** 을 클릭합니다.
60. **요소 추가** 를 클릭합니다.
61. 이름 필드에 **TransDate** 를 입력합니다.
62. **확인** 을 클릭합니다.
63. **요소 추가** 를 클릭합니다.
64. 이름 필드에 **금액** 을 입력합니다.
65. **확인** 을 클릭합니다.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>데이터 모델 요소에 매핑하기 위한 형식 구성 요소 준비
1. 트리에서 **Xml\Message\ProcessingDate** 를 선택합니다.
2. **추가** 를 클릭하여 드롭 대화 상자를 엽니다.
3. 트리에서 **Text\DateTime** 을 선택합니다.
4. **형식** 필드에 **yyyy-MM-dd** 를 입력합니다.
5. **확인** 을 클릭합니다.
6. 트리에서 **Xml\Message\Payments\Item\TransDate** 를 선택합니다.
7. **날짜/시간 추가** 를 클릭합니다.
8. **형식** 필드에 **yyyy-MM-dd** 를 입력합니다.
9. **날짜/시간** 유형 필드에서 **날짜** 를 선택합니다.
10. **확인** 을 클릭합니다.
11. 트리에서 **Xml\Message\MessageId** 를 선택합니다.
12. **추가** 를 클릭하여 드롭 대화 상자를 엽니다.
13. 트리에서 **Text\스트링** 을 선택합니다.
14. **확인** 을 클릭합니다.
15. 트리에서 **Xml\Message\Payments\Item\Vendor\Name** 을 선택합니다.
16. **스트링 추가** 를 클릭합니다.
17. **확인** 을 클릭합니다.
18. 트리에서 **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber** 를 선택합니다.
19. **스트링 추가** 를 클릭합니다.
20. **확인** 을 클릭합니다.
21. 트리에서 **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber** 를 선택합니다.
22. **스트링 추가** 를 클릭합니다.
23. **확인** 을 클릭합니다.
24. 트리에서 **Xml\Message\Payments\Item\Payer\Name** 을 선택합니다.
25. **스트링 추가** 를 클릭합니다.
26. **확인** 을 클릭합니다.
27. 트리에서 **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber** 를 선택합니다.
28. **스트링 추가** 를 클릭합니다.
29. **확인** 을 클릭합니다.
30. 트리에서 **Xml\Message\Payments\Item\Payer\Bank\AccountNumber** 를 선택합니다.
31. **스트링 추가** 를 클릭합니다.
32. **확인** 을 클릭합니다.
33. 트리에서 **Xml\Message\Payments\Item\Currency** 를 선택합니다.
34. **스트링 추가** 를 클릭합니다.
35. **확인** 을 클릭합니다.
36. 트리에서 **Xml\Message\Payments\Item\Description** 을 선택합니다.
37. **스트링 추가** 를 클릭합니다.
38. **확인** 을 클릭합니다.
39. 트리에서 **Xml\Message\Payments\Item\Amount** 를 선택합니다.
40. **스트링 추가** 를 클릭합니다.
41. **확인** 을 클릭합니다.
42. **저장** 을 클릭합니다.
43. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]