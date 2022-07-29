---
title: 애플리케이션 데이터가 있는 문서를 생성하도록 형식 수정
description: 이번에는 전자 문서를 생성하고 애플리케이션 데이터를 업데이트하기 위한 보고 구성을 설계하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 312a49fc524cc7359d2c1815597214656df11c018034da384d30bfb9d9efee4b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460881"
---
# <a name="modify-formats-to-generate-documents-that-have-application-data"></a>애플리케이션 데이터가 있는 문서를 생성하도록 형식 수정

[!include [banner](../../includes/banner.md)]

이 절차의 단계를 완료하려면 먼저 '애플리케이션 데이터 업데이트로 문서 생성(3부: 모델 및 매핑 수정)'.

이 절차의 단계에서는 전자 문서를 생성하고 애플리케이션 데이터를 업데이트하기 위해 전자 보고(ER) 구성을 설계하는 방법을 설명합니다. 이 절차에서는 ER 구성을 수정하여 전자 문서를 생성할 뿐만 아니라 애플리케이션 데이터를 업데이트합니다. 이번에는 시스템 관리자 또는 전자 보고 개발자 역할이 할당된 사용자를 위해 생성됩니다. 이러한 단계는 DEMF 데이터 세트를 사용하여 완료할 수 있습니다.


## <a name="modify-format-to-collect-details-of-reporting"></a>보고 내용 수집 형식 수정
1. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
2. 트리에서 'Intrastat(모델)'을 확장합니다.
3. 트리에서 'Intrastat(모델)\Intrastat(형식)'을 선택합니다.
4. 디자이너를 클릭합니다.
5. 트리에서 '파일'을 확장합니다.
6. 트리에서 'File\Declaration'을 확장합니다.
7. 트리에서 'File\Declaration\Data'를 선택합니다.
8. 다중도 필드에서 '일대일'을 선택합니다.
    * Intrastat 보고 프로세스의 세부 정보를 보관하려면 이 형식 요소를 구성합니다. 이번에는 아카이브의 헤더 기록을 나타냅니다.  
9. 트리에서 'File\Declaration\Data'를 확장합니다.
10. 트리에서 'File\Declaration\Data\Item'을 선택합니다.
11. 다중도 필드에서 '0개'를 선택합니다.
    * Intrastat 보고 프로세스의 세부 정보를 보관하려면 이 형식 요소를 구성합니다. 이번에는 보관된 라인 목록을 나타냅니다.  
12. 트리에서 'File\Declaration\Data\Item'을 확장합니다.
13. 트리에서 'File\Declaration\Data\Item\Dim1'을 선택합니다.
14. 게시 필드에서 예를 선택합니다.
    * 이 데이터를 보관하지 않으므로 Intrastat 보고 세부정보의 데이터 소스에서 이 형식 요소를 제외할 수 있습니다.  
15. 트리에서 'File\Declaration\Data\Item\Dim1'을 확장합니다.
16. 트리에서 'File\Declaration\Data\Item\Dim1\property'를 선택합니다.
17. 게시 필드에서 예를 선택합니다.
18. 트리에서 'File\Declaration\Data\Item\Dim1\date'를 선택합니다.
19. 게시 필드에서 예를 선택합니다.
20. 트리에서 'File\Declaration\Data\Item\Dim2'를 선택합니다.
21. 게시 필드에서 예를 선택합니다.
22. 트리에서 'File\Declaration\Data\Item\Dim2'를 확장합니다.
23. 트리에서 'File\Declaration\Data\Item\Dim2\property'를 선택합니다.
24. 게시 필드에서 예를 선택합니다.
25. 트리에서 'File\Declaration\Data\Item\Dim2\code'를 선택합니다.
26. 게시 필드에서 예를 선택합니다.
27. 트리에서 'File\Declaration\Data\Item\Dim3'을 선택합니다.
    * 여러 형식 요소가 동일한 이름을 가질 수 있습니다. 예를 들어, 딤. Intrastat 보고 세부 정보를 보관하기 위한 데이터 소스로 이 형식을 사용할 때 명시적으로 인식할 수 없으므로 이러한 형식 요소에 대한 대체 이름을 정의해야 합니다.   
28. 이름 필드에 '금액'을 입력합니다.
    * 금액  
29. 다중도 필드에서 '정확히 하나'를 선택합니다.
30. 트리에서 'File\Declaration\Data\Item\Dim4'를 선택합니다.
31. 이름 필드에 '항목'을 입력합니다.
    * 항목  
32. 다중도 필드에서 '정확히 하나'를 선택합니다.
    * 디자인 형식 요소 외에도 다음과 같은 Intrastat 보고 세부 정보를 보관해야 합니다. 보고된 각 상품 항목의 고유 기록 식별 및 생성된 파일 이름. 이 데이터는 Intrastat 보고서에 채워지지 않으므로 이러한 세부 요소와 관련된 형식을 데이터 소스 항목으로 추가해야 합니다.  
33. 트리에서 'File\Declaration\Data'를 선택합니다.
34. 추가를 클릭하여 드롭 대화 상자를 엽니다.
35. 트리에서 '데이터 소스\항목'을 선택합니다.
36. 이름 필드에 '파일 이름'을 입력합니다.
    * 파일 이름  
37. 데이터 유형 필드에서 '스트링'을 선택합니다.
38. '확인'을 클릭합니다.
39. 트리에서 'File\Declaration\Data\Item'을 선택합니다.
40. 항목 추가를 클릭합니다.
41. 이름 필드에 '상품 기록 ID'를 입력합니다.
    * 상품 등록 ID  
42. 데이터 유형 필드에서 'Int64'를 선택합니다.
43. '확인'을 클릭합니다.
44. 매핑 탭을 클릭합니다.
45. 트리에서 'File\Declaration\Data\File name'을 선택합니다.
46. 바인딩을 클릭합니다.
47. 트리에서 '모델'을 확장합니다.
48. 트리에서 'model\Transactions'를 확장합니다.
49. 트리에서 'File\Declaration\Data\Item = model.Transactions\Commodity rec ID'를 선택합니다.
50. 트리에서 'model\Transactions\Commodity rec ID'를 선택합니다.
51. 바인딩을 클릭합니다.
52. 저장을 클릭합니다.

## <a name="modify-format-to-memorize-details-of-reporting"></a>보고내용 외우기 형식 수정

1. 모델링할 형식 매핑을 클릭합니다.
2. 새로 만들기를 클릭합니다.
3. 정의 필드에서 '애플리케이션 데이터 업데이트용' 루트 항목을 입력하거나 선택합니다.
    * 애플리케이션 데이터 업데이트용.
4. 이름 필드에 '데이터 업데이트를 위한 매핑'을 입력합니다.
    * 데이터 업데이트를 위한 매핑  
5. 저장을 클릭합니다.
    * 이 매핑은 Intrastat 보고서의 세부 정보가 데이터 모델에서 수집되는 방식을 정의하며, 그 구조는 '애플리케이션 데이터 업데이트용' 선택한 루트 항목에 의해 지정됩니다. 이러한 세부 정보, 동일한 루트 항목 'For application data update' 및 'To destination' 방향이 애플리케이션 데이터 업데이트에 사용되는 모델 매핑이 사용됩니다. 애플리케이션 데이터 업데이트는 발신 Intrastat 보고서가 생성된 직후 시작됩니다. 애플리케이션 데이터 업데이트는 런타임에 건너뛸 수 있지만 데이터 모델은 비어 있어야 합니다(빈 기록 목록 포함).
6. 디자이너를 클릭합니다.
    * 나가는 Intrastat 보고서 형식은 기본적으로 이 모델 매핑에 대한 데이터 소스로 추가됩니다.  
    * 선택한 모델의 루트 항목을 기반으로 필터링되는 데이터 모델의 요소에 디자인된 보고서의 요소(데이터 소스로 표시됨)를 바인딩합니다.  
7. 트리에서 '아카이브 헤더'를 확장합니다.
8. 트리에서 '아카이브 헤더\아카이브 라인'을 확장합니다.
9. 트리에서 '형식'을 확장합니다.
10. 트리에서 'format\Declaration: XML 요소(선언)'.
11. 트리에서 'format\Declaration: XML 요소(선언)\데이터: XML 요소 1..* 데이터.
12. 트리에서 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)'.
13. 트리에서 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)'.
14. 트리에서 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)'.
15. 트리에서 'Archive header\Number of lines'을 선택합니다.
16. 편집을 클릭합니다.
17. 트리에서 'List\COUNT'를 선택합니다.
18. 함수 추가를 클릭합니다.
19. 트리에서 '형식'을 확장합니다.
20. 트리에서 'format\Declaration: XML 요소(선언)'.
21. 트리에서 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`을 확장합니다.
22. 트리에서 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`을 선택합니다.
23. 데이터 소스 추가를 클릭합니다.
24. 수식 필드에 'COUNT(format.Declaration.Data.Item)'을 입력합니다.
    * COUNT(형식.선언.데이터.항목)  
25. 저장을 클릭합니다.
26. 페이지를 닫습니다.
27. 트리에서 '아카이브 헤더\파일 이름'을 선택합니다.
28. 트리에서 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\File name: Item String(File name)'.
29. 바인딩을 클릭합니다.
30. 트리에서 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim4: XML Element 1..1 (Item)\number: String(number)`을 선택합니다.
31. 트리에서 '아카이브 헤더\아카이브 라인\항목 번호'를 선택합니다.
32. 바인딩을 클릭합니다.
33. 트리에서 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Dim3: XML Element 1..1 (Amount)\value: Numeric Real(value)`을 선택합니다.
34. 트리에서 '아카이브 헤더\아카이브 라인\금액'을 선택합니다.
35. 바인딩을 클릭합니다.
36. 트리에서 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)\Commodity rec ID: Item Int64(Commodity rec ID)`을 선택합니다.
37. 트리에서 'Archive header\Archivelines\Commodity rec ID'를 선택합니다.
38. 바인딩을 클릭합니다.
39. 트리에서 '아카이브 헤더\아카이브 라인'을 선택합니다.
40. 트리에서 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)\Item: XML Element 0..* (Item)`을 선택합니다.
41. 바인딩을 클릭합니다.
42. 트리에서 '아카이브 헤더'를 선택합니다.
43. 트리에서 `format\Declaration: XML Element(Declaration)\Data: XML Element 1..* (Data)`을 선택합니다.
44. 바인딩을 클릭합니다.
45. 저장을 클릭합니다.
46. 페이지를 닫습니다.
47. 페이지를 닫습니다.
48. 페이지를 닫습니다.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]