---
title: ER 형식 출력에서 문서 관리 파일 사용(5부 - 형식 수정 및 실행)
description: 이번에는 ER 출력에서 문서 관리 파일(첨부 파일)을 사용하도록 전자 보고(ER) 형식을 구성하는 방법에 대해 설명합니다. (5부)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 48175de4e58f9def15bf2bf8b10a1348036c88a1af284eb2a3e5f9fbefd649c1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460709"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a>ER 형식 출력에서 문서 관리 파일 사용(5부 - 형식 수정 및 실행)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 ER 출력에서 문서 관리 파일(첨부 파일)을 사용하도록 전자 보고(ER) 형식을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 DEMF 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 'ER 형식 출력에서 문서 관리 파일 사용(파트 4: 실행 형식)' 절차를 따르십시오.

이번에는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a>이진 형식으로 메시지를 생성하도록 첨부 파일을 채우는 형식 수정
1. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
2. 트리에서 '고객 송장 모델'을 확장합니다.
3. 트리에서 '고객 송장 모델\고객 송장 모델(사용자 지정)'을 확장합니다.
4. 트리에서 '고객 송장 모델\고객 송장 모델(사용자 지정)\전자 송장 샘플 메시지'를 선택합니다.
5. 디자이너를 클릭합니다.
    * 유니코드 인코딩을 사용하여 생성 출력의 송장 메시지를 XML 파일로 채웁니다.  
6. 루트 추가를 클릭하여 드롭 대화 상자를 엽니다.
7. 트리에서 '공통\파일'을 선택합니다.
8. 이름 필드에 'Xml 메시지'를 입력합니다.
    * XML 메시지  
9. 인코딩 필드에 'UTF-8'을 입력합니다.
    * UTF-8  
10. '확인'을 클릭합니다.
    * 생성 출력을 압축 파일로 구성합니다.  
11. 루트 추가를 클릭하여 드롭 대화 상자를 엽니다.
12. 트리에서 '공통\폴더'를 선택합니다.
13. 이름 필드에 'Zip 출력'을 입력합니다.
    * 지퍼 출력  
14. '확인'을 클릭합니다.
15. 트리에서 'Zip 출력'을 선택합니다.
    * 생성하는 압축 파일에 첨부 파일을 원래 이름과 확장자를 가진 파일로 추가합니다.  
16. 추가를 클릭하여 드롭 대화 상자를 엽니다.
17. 트리에서 '공통\파일'을 선택합니다.
18. 이름 필드에 '첨부 파일'을 입력합니다.
    * 파일 첨부  
19. '확인'을 클릭합니다.
20. 트리에서 'Zip output\Attached file'을 선택합니다.
21. 추가를 클릭하여 드롭 대화 상자를 엽니다.
22. 트리에서 'Text\Base64'를 선택합니다.
23. '확인'을 클릭합니다.

## <a name="map-new-format-elements-to-data-model"></a>데이터 모델에 새 형식 요소 매핑
1. 매핑 탭을 클릭합니다.
2. 트리에서 '모델'을 확장합니다.
3. 트리에서 '모델\송장 첨부 파일'을 확장합니다.
4. 트리에서 'Zip output\Attached file\Base64'를 선택합니다.
5. 트리에서 '모델\송장 첨부 파일\파일 내용'을 선택합니다.
6. 바인딩을 클릭합니다.
7. 트리에서 'Zip output\Attached file'을 선택합니다.
8. 파일 이름 편집을 클릭합니다.
9. 트리에서 '모델'을 확장합니다.
10. 트리에서 '모델\송장 첨부 파일'을 확장합니다.
11. 트리에서 '모델\송장 첨부\파일 이름'을 선택합니다.
12. 데이터 소스 추가를 클릭합니다.
13. 저장을 클릭합니다.
14. 페이지를 닫습니다.
15. 트리에서 '모델\송장 첨부 파일'을 선택합니다.
16. 바인딩을 클릭합니다.
17. 저장을 클릭합니다.
18. 페이지를 닫습니다.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>선택한 송장에 대해 설계된 보고서 실행
1. 실행을 클릭합니다.
2. 포함할 기록() 섹션을 확장합니다.
3. 필터를 클릭합니다.
4. 고객 송장 분개 및 판매 주문 필드의 행을 선택합니다.
5. 기준 필드에 '판매 주문' 기준 필드에 주문 번호 000148을 입력합니다.
    * 000148  
6. '확인'을 클릭합니다.
7. '확인'을 클릭합니다.
    * 생성된 출력을 검토합니다. XML 형식의 송장 메시지 외에도 각 첨부 파일에 대해 단일 파일이 생성되었습니다. 첨부 파일은 바이너리 형식의 압축된 출력으로 채워집니다.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]