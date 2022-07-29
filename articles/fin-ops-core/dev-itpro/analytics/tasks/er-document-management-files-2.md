---
title: ER 형식 출력에서 문서 관리 파일 사용(2부 - 데이터 모델 확장)
description: 이번에는 ER 출력에서 문서 관리 파일(첨부 파일)을 사용하도록 전자 보고(ER) 형식을 구성하는 방법에 대해 설명합니다. (2부)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d20738fbdfd85390870c935576d954d3050029f557fe8b5b690329f9e4a0aab4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460711"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a>ER 형식 출력에서 문서 관리 파일 사용(2부 - 데이터 모델 확장)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 ER 출력에서 문서 관리 파일(첨부 파일)을 사용하도록 전자 보고(ER) 형식을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 모든 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 'ER 형식 출력에서 문서 관리 파일 사용(1부: 데이터 모델 준비)' 작업 가이드를 참조하십시오.

이번에는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a>문서 관리 파일을 표시하도록 데이터 모델 확장
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
2. 보고 구성을 클릭합니다.
3. 트리에서 '고객 송장 모델'을 확장합니다.
4. 트리에서 '고객 송장 모델\고객 송장 모델(사용자 지정)'을 선택합니다.
5. 디자이너를 클릭합니다.
6. 트리에서 '고객송장(InvoiceCustomer)'을 선택합니다.
    * 우리는 이 데이터 모델을 확장하여 전자적으로 처리되는 송장과 관련된 판매 주문에 첨부된 모든 파일을 노출할 것입니다.  
7. 새로 만들기를 클릭하여 드롭 대화 상자를 엽니다.
8. 이름 필드에 '송장 첨부 파일'을 입력합니다.
    * 송장 첨부 파일  
9. 항목 유형 필드에서 '기록 목록'을 선택합니다.
10. 추가를 클릭합니다.
11. 새로 만들기를 클릭하여 드롭 대화 상자를 엽니다.
12. 이름 필드에 '파일 내용'을 입력합니다.
    * 파일 내용  
13. 항목 유형 필드에서 '컨테이너'를 선택합니다.
14. 추가를 클릭합니다.
15. 새로 만들기를 클릭하여 드롭 대화 상자를 엽니다.
16. 이름 필드에 '파일 이름'을 입력합니다.
    * 파일 이름  
17. 항목 유형 필드에서 '스트링'을 선택합니다.
18. 추가를 클릭합니다.

## <a name="map-new-data-model-elements-to-data-sources"></a>새 데이터 모델 요소를 데이터 소스에 매핑
1. 데이터 소스에 모델 매핑을 클릭합니다.
2. 빠른 필터를 사용하여 값이 'InvoiceCustomer'인 정의 필드를 필터링합니다.
    * 송장 고객  
    * 새 모델 요소를 적절한 데이터 소스에 매핑합니다.  
3. 디자이너를 클릭합니다.
4. 트리에서 '송장 첨부 파일'을 선택합니다.
5. 트리에서 '송장 첨부 파일'을 확장합니다.
6. 트리에서 '청구서 첨부\파일 이름'을 선택합니다.
7. 편집을 클릭합니다.
8. 수식 필드에 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''을 입력합니다.
    * CustInvoiceJour.'>관계'.SalesTable.'<관계'.'<문서'.'originalFileName()'  
9. 저장을 클릭합니다.
10. 페이지를 닫습니다.
11. 트리에서 '청구서 첨부\파일 내용'을 선택합니다.
12. 편집을 클릭합니다.
13. 수식 필드에 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''를 입력합니다.
    * CustInvoiceJour.'>관계'.SalesTable.'<관계'.'<문서'.'getFileContentAsContainer()'  
14. 저장을 클릭합니다.
15. 페이지를 닫습니다.
16. 트리에서 '송장 첨부 파일'을 선택합니다.
17. 편집을 클릭합니다.
18. 수식 필드에 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''를 입력합니다.
    * CustInvoiceJour.'>관계'.SalesTable.'<관계'.'<문서'  
19. 저장을 클릭합니다.
20. 페이지를 닫습니다.
21. 저장을 클릭합니다.
22. 페이지를 닫습니다.
23. 페이지를 닫습니다.
24. 페이지를 닫습니다.
25. 상태 변경을 클릭합니다.
26. 완료를 클릭합니다.
27. '확인'을 클릭합니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]