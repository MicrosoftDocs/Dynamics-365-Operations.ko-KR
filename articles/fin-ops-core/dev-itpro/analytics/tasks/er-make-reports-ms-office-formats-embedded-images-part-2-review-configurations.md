---
title: 이미지가 포함된 Office 형식의 보고서를 생성하기 위한 구성 검토
description: 이번에는 포함된 이미지가 포함된 전자 문서를 생성하기 위해 보고 구성을 설계하는 방법에 대해 설명합니다. (파트 1 - 매개 변수 설정).
author: NickSelin
ms.date: 06/13/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f209fcbac310dffb654f7830a4d4b12fa95d7a461b681864b8c9b547f4a4986c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460911"
---
# <a name="review-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>이미지가 포함된 Office 형식의 보고서를 생성하기 위한 구성 검토

[!include [banner](../../includes/banner.md)]

이 단계를 완료하려면 먼저 'ER이 포함된 이미지가 있는 MS Office 형식으로 보고서 작성(1부: 매개 변수 설정)' 작업 가이드를 참조하십시오.

이 절차에서는 Microsoft Excel 및 Microsoft Word에 포함된 이미지가 포함된 전자 문서를 생성하기 위해 전자 보고(ER) 구성을 설계하는 방법을 보여줍니다. 이 예시에서는 샘플 회사 Litware, Inc.의 ER 구성을 검토합니다. 

이번에는 시스템 관리자 또는 전자 보고 개발자 역할이 할당된 사용자를 위한 것입니다. USMF 데이터 세트를 사용하여 단계를 완료할 수 있습니다.


## <a name="review-the-imported-data-model"></a>가져온 데이터 모델 검토
1. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
2. 트리에서 '수표 모델'을 선택합니다.
3. 디자이너를 클릭합니다.
    * 이 모델은 비즈니스 관점에서 지급 수표를 나타내고 이 모델을 애플리케이션의 데이터 소스에 매핑하도록 설계되었습니다. ER 운영 디자이너가 이 모델을 검토합니다. 표시되는 모델 요소의 속성(구조, 이름, 설명, 데이터 유형 등)에 유의하십시오.   
4. 트리에서 '루트'를 확장합니다.
5. 트리에서 '루트\수표'를 선택합니다.
6. 트리에서 '루트\수표'를 확장합니다.
7. 트리에서 'root\cheques\attributes'를 확장합니다.
8. 트리에서 'root\payer'를 확장합니다.
9. 트리에서 'root\istestrun'을 선택합니다.
10. 트리에서 '루트\레이아웃'을 선택합니다.
    * 이 모델의 레이아웃 요소는 선택한 은행 계좌에 대한 인쇄 수표 레이아웃의 세부 정보를 나타냅니다. 또한 이미지를 저장하기 위한 컨테이너 데이터 유형의 두 노드도 포함합니다.   
11. 트리에서 '루트\레이아웃'을 확장합니다.
12. 트리에서 '루트\레이아웃\회사 로고'를 선택합니다.
13. 트리에서 'root\layout\company logo'를 확장합니다.
14. 트리에서 '루트\레이아웃\회사 로고\이미지'를 선택합니다.
15. 트리에서 'root\layout\company logo\isprinted'를 선택합니다.
16. 트리에서 '루트\레이아웃\서명'을 선택합니다.
17. 트리에서 'root\layout\signature'를 확장합니다.
18. 트리에서 'root\layout\signature\image'를 선택합니다.
19. 트리에서 'root\layout\signature\isprinted'를 선택합니다.
    * 두 개의 이미지 데이터 모델 요소가 바이너리 형식의 회사 로고 이미지와 승인된 사람의 서명이 포함된 테이블의 필드에 바인딩됩니다.  
20. 트리에서 '루트\레이아웃\워터마크'를 확장합니다.
21. 데이터 소스에 모델 매핑을 클릭합니다.
22. 디자이너를 클릭합니다.
23. 트리에서 'checksselected'를 확장합니다.
24. 트리에서 '레이아웃'을 확장합니다.
25. 트리에서 '레이아웃\회사 로고'를 확장합니다.
26. 트리에서 '레이아웃\서명'을 확장합니다.
27. 트리에서 '레이아웃\워터마크'를 확장합니다.
28. '세부정보 표시'를 켭니다.
    * 검사 데이터 모델 요소는 런타임에 사용자가 인쇄를 위해 선택한 검사에 대한 기록을 포함하는 TmpChequePrintout 테이블에 바인딩됩니다.   
29. 페이지를 닫습니다.
30. 페이지를 닫습니다.
31. 페이지를 닫습니다.

## <a name="review-the-imported-format"></a>가져온 형식 검토
1. 트리에서 '수표 모델'을 확장합니다.
2. 트리에서 '수표 모델\수표 인쇄 형식'을 선택합니다.
3. 디자이너를 클릭합니다.
4. 첨부 파일을 클릭합니다.
5. 열기를 클릭합니다.
    * 첨부된 보고서의 템플릿을 Excel에서 엽니다.  
    * 수표를 인쇄하는 데 사용할 첨부된 보고서의 Excel 템플릿을 검토합니다. 템플릿에는 페이지당 두 개의 수표가 포함되어 있으며 사전 인쇄된 양식에 수표를 인쇄하도록 설계되었습니다. 두 개의 빈 이미지가 포함되어 있습니다. 이 빈 이미지는 회사 로고와 지급을 승인하는 사람의 서명을 위한 것입니다. Excel에서 이미지의 이름이 각각 CompLogo 및 SignatureImage인지 확인합니다.   
6. 페이지를 닫습니다.
7. 트리에서 '신고'를 확장합니다.
8. 트리에서 'Report\ChequeLines'를 확장합니다.
9. 트리에서 'Report\ChequeLines\CompLogo'를 선택합니다.
10. '세부정보 표시'를 켭니다.
    * 'CompLogo' 형식의 셀 요소는 보고서에서 회사 로고 이미지를 채우는 데 사용되는 Excel 항목을 나타냅니다. 이 형식 요소는 런타임 시 바이너리 형식의 회사 로고 이미지를 포함하는 이미지 데이터 모델 요소에 바인딩됩니다.   
11. 매핑 탭을 클릭합니다.
12. 편집 활성화를 클릭합니다.
    * 더 이상 활성화되지 않도록 'CompLogo' 형식의 셀 요소를 만들 수 있습니다. 이 경우 연결된 Excel 이미지 요소는 생성된 보고서에서 회사 로고를 숨깁니다. 활성화된 표현식이 TRUE를 반환하고 정의된 바인딩이 이미지를 가져오지 않으면 연결된 Excel 이미지 요소에 Excel 템플릿에 저장된 이미지가 표시됩니다.   
13. 페이지를 닫습니다.
14. 트리에서 'labels: 포함:
    * 미리 인쇄된 수표 양식에 제공된 일부 레이블은 테스트 목적으로 보고서를 작성할 때 보고서에 포함됩니다. 그러나 미리 인쇄된 양식에 이미 포함되어 있기 때문에 실제 인쇄 중에는 이러한 레이블이 인쇄되지 않습니다.  
15. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]