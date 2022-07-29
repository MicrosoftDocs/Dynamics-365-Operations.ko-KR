---
title: ER 형식 출력에서 문서 관리 파일 사용(3부 - 형식 만들기)
description: 이번에는 ER 출력에서 문서 관리 파일을 사용하도록 전자 보고 형식을 구성하는 방법에 대해 설명합니다. (3부)
author: NickSelin
ms.date: 08/29/2018
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
ms.openlocfilehash: 0cb052e2895cd0eb7f5c3bea9f33d988ef54dfb11e2e31c4212706b7fdaada79
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460712"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a>ER 형식 출력에서 문서 관리 파일 사용(3부 - 형식 만들기)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 ER 출력에서 문서 관리 파일(첨부 파일)을 사용하도록 전자 보고(ER) 형식을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 모든 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 'ER 형식 출력에서 문서 관리 파일 사용(2부: 데이터 모델 확장' 절차.

이번에는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="create-a-format-to-process-invoices"></a>송장을 처리하는 형식 만들기
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
2. 보고 구성을 클릭합니다.
3. 트리에서 '고객 송장 모델'을 확장합니다.
4. 트리에서 '고객 송장 모델\고객 송장 모델(사용자 지정)'을 선택합니다.
    * 전자적으로 처리되는 송장과 관련된 판매 주문에 첨부된 모든 파일에 대한 정보가 포함된 전자 메시지를 생성하는 형식을 생성합니다.  
5. 구성 만들기를 클릭하여 드롭 대화 상자를 엽니다.
6. 새로 만들기 필드에 '데이터 모델 고객 송장 모델(사용자 지정) 기반 형식'을 입력합니다.
7. 이름 필드에 '전자 송장 샘플 메시지'를 입력합니다.
    * 전자 송장 샘플 메시지  
8. 데이터 모델 정의 필드에서 값을 입력하거나 선택하십시오.
    * 송장 고객  
9. 구성 만들기를 클릭합니다.

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a>MIME 형식의 메시지 생성을 위해 첨부 파일을 채우는 형식 설계
1. 디자이너를 클릭합니다.
2. 루트 추가를 클릭하여 드롭 대화 상자를 엽니다.
3. 트리에서 'XML\요소'를 선택합니다.
4. 이름 필드에 '송장'을 입력합니다.
    * 송장  
5. '확인'을 클릭합니다.
6. 추가를 클릭하여 드롭 대화 상자를 엽니다.
7. 트리에서 'XML\Attribute'를 선택합니다.
8. 이름 필드에 'SalesOrder'를 입력합니다.
    * 판매 주문  
9. '확인'을 클릭합니다.
10. 속성 추가를 클릭합니다.
11. 이름 필드에 'InvoiceNumber'를 입력합니다.
    * 송장 번호  
12. '확인'을 클릭합니다.
13. 속성 추가를 클릭합니다.
14. 이름 필드에 'InvoiceAmount'를 입력합니다.
    * 송장 금액  
15. '확인'을 클릭합니다.
16. 추가를 클릭하여 드롭 대화 상자를 엽니다.
17. 트리에서 'XML\요소'를 선택합니다.
18. 이름 필드에 'EnclosedDocs'를 입력합니다.
    * 동봉된 문서  
19. '확인'을 클릭합니다.
20. 트리에서 'Invoice\EnclosedDocs'를 선택합니다.
21. 요소 추가를 클릭합니다.
22. 이름 필드에 '문서'를 입력합니다.
    * 문서  
23. '확인'을 클릭합니다.
24. 트리에서 'Invoice\EnclosedDocs\Document'를 선택합니다.
25. 추가를 클릭하여 드롭 대화 상자를 엽니다.
26. 트리에서 'XML\Attribute'를 선택합니다.
27. 이름 필드에 '파일 이름'을 입력합니다.
    * 파일 이름  
28. '확인'을 클릭합니다.
29. 추가를 클릭하여 드롭 대화 상자를 엽니다.
30. 트리에서 'XML\요소'를 선택합니다.
31. 이름 필드에 'FileContent'를 입력합니다.
    * 파일 내용  
32. '확인'을 클릭합니다.
33. 트리에서 'Invoice\EnclosedDocs\Document\FileContent'를 선택합니다.
34. 추가를 클릭하여 드롭 대화 상자를 엽니다.
35. 트리에서 'Text\Base64'를 선택합니다.
36. '확인'을 클릭합니다.

## <a name="map-format-elements-to-data-model-as-data-source"></a>데이터 소스로 데이터 모델에 형식 요소 매핑
1. 트리에서 'Invoice\SalesOrder'를 선택합니다.
2. 매핑 탭을 클릭합니다.
3. 트리에서 '모델'을 확장합니다.
4. 트리에서 'model\Sales order number(SalesId)'를 선택합니다.
5. 바인딩을 클릭합니다.
6. 트리에서 'Invoice\InvoiceNumber'를 선택합니다.
7. 트리에서 'model\Base 송장(InvoiceBase)'을 확장합니다.
8. 트리에서 '모델\기본 송장(InvoiceBase)\송장 번호(Id)'를 선택합니다.
9. 바인딩을 클릭합니다.
10. 트리에서 'Invoice\InvoiceAmount'를 선택합니다.
11. 트리에서 '모델\기준 송장(InvoiceBase)\송장 금액(Amount)'을 선택합니다.
12. 바인딩을 클릭합니다.
13. 트리에서 '모델\송장 첨부 파일'을 확장합니다.
14. 트리에서 '모델\송장 첨부 파일\파일 내용'을 선택합니다.
15. 트리에서 'Invoice\EnclosedDocs\Document\FileContent\Base64'를 선택합니다.
16. 바인딩을 클릭합니다.
17. 트리에서 '모델\송장 첨부\파일 이름'을 선택합니다.
18. 트리에서 'Invoice\EnclosedDocs\Document\FileName'을 선택합니다.
19. 바인딩을 클릭합니다.
20. 트리에서 '모델\송장 첨부 파일'을 선택합니다.
21. 트리에서 'Invoice\EnclosedDocs\Document'를 선택합니다.
22. 바인딩을 클릭합니다.
23. 저장을 클릭합니다.
24. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]