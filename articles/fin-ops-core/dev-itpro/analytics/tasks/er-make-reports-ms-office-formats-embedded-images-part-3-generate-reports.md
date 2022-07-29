---
title: 이미지가 포함된 Office 형식의 보고서 생성
description: 이번에는 포함된 이미지가 포함된 Excel 및 Word에서 전자 문서를 생성하기 위해 전자 보고(ER) 구성을 설계하는 방법에 대해 설명합니다.
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
ms.openlocfilehash: 6ec9f3013c1e365a3ca1a4c6cabe71a22e3e8b730eac38155ef023fe68107524
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460689"
---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a>이미지가 포함된 Office 형식의 보고서 생성

[!include [banner](../../includes/banner.md)]

다음 단계에서는 '시스템 관리자' 또는 '전자 보고 개발자' 역할을 수행하는 사용자가 ER(전자 보고) 구성을 설계하여 포함된 이미지가 포함된 MS Office 형식(Excel 및 Word)의 전자 문서를 생성하는 방법을 설명합니다.

이 예시에서는 샘플 회사인 'Litware, Inc.'에 대해 생성된 ER 구성을 사용합니다.  이 단계를 완료하려면 먼저 'ER이 포함된 이미지가 있는 MS Office 형식으로 보고서 작성(2부: 구성 검토)' 작업 가이드를 참조하십시오. 이 단계는 'USMF' 회사에서 수행할 수 있습니다.


## <a name="run-format-with-initial-model-mapping"></a>초기 모델 매핑으로 형식 실행
1. 현금 및 은행 관리 > 은행 계좌 > 은행 계좌로 이동합니다.
2. 빠른 필터를 사용하여 값이 'USMF OPER'인 은행 계좌 필드를 필터링합니다.
3. 작업 창에서 설정을 클릭합니다.
4. 확인을 클릭합니다.
5. 테스트 인쇄를 클릭합니다.
    * 테스트 목적으로 형식을 실행합니다.  
6. 협상 가능한 수표 형식 필드에서 예를 선택합니다.
7. '확인'을 클릭합니다.
    * 생성된 출력을 검토합니다. 회사 로고는 승인된 사람의 서명과 함께 보고서에 표시됩니다. 서명 이미지는 선택한 은행 계좌와 연결된 수표 레이아웃 기록의 '컨테이너' 데이터 유형 필드에서 가져옵니다.  
8. 복사본 섹션을 확장합니다.
9. 편집을 클릭합니다.
10. 워터마크 필드에 '워터마크를 무효로 인쇄'를 입력합니다.
    * Excel 모양 요소에서 문서 생성 시 워터마크 텍스트가 표시되도록 워터마크 레이아웃 설정을 변경합니다.  
11. 테스트 인쇄를 클릭합니다.
12. '확인'을 클릭합니다.
    * 생성된 출력을 검토합니다. 선택한 옵션에 따라 생성된 보고서에 워터마크가 표시됩니다.  
13. 페이지를 닫습니다.
14. 작업 창에서 결제 관리를 클릭합니다.
15. 확인을 클릭합니다.
16. 필터 표시를 클릭합니다.
17. 다음 필터를 적용합니다. '다음 중 하나' 필터 연산자를 사용하여 '확인 번호' 필드에 '381','385','389'의 필터 값을 입력합니다.
18. 목록에서 모든 행을 표시하십시오.
19. 수표 사본 인쇄를 클릭합니다.
    * 포맷을 실행하여 선택한 수표를 다시 인쇄하십시오.  
    * 생성된 출력을 검토합니다. 선택한 수표가 다시 인쇄되었습니다. 회사로고와 라벨은 미리 출력된 형태로 제시되어 출력되지 않습니다.  

## <a name="modify-the-mapping-of-the-imported-data-model"></a>가져온 데이터 모델의 매핑 수정
1. 페이지를 닫습니다.
2. 페이지를 닫습니다.
3. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
4. 트리에서 '수표 모델'을 선택합니다.
5. 디자이너를 클릭합니다.
6. 데이터 소스에 모델 매핑을 클릭합니다.
7. 디자이너를 클릭합니다.
    * 데이터 모델의 서명 항목 바인딩을 변경하여 선택한 은행 계좌와 연결된 수표 레이아웃 기록에 첨부된 파일에서 서명 이미지를 가져옵니다.  
8. 세부정보 표시를 끕니다.
9. 트리에서 '레이아웃'을 확장합니다.
10. 트리에서 '레이아웃\서명'을 확장합니다.
11. 트리에서 'layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'를 선택합니다.
12. 트리에서 '수표 계정'을 확장합니다.
13. 트리에서 '수표\<계정'을 확장합니다.
14. 트리에서 'chequesaccount\<Relations\BankChequeLayout'을 확장합니다.
15. 트리에서 'chequesaccount\<Relations\BankCheque\<Layout'을 확장합니다.
16. 트리에서 'chequesaccount\<Relations\Bank\<Cheque\<Layout'을 확장합니다.
17. 트리에서 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()'을 확장합니다.
18. 바인딩을 클릭합니다.
19. 저장을 클릭합니다.
20. 페이지를 닫습니다.
21. 페이지를 닫습니다.
22. 페이지를 닫습니다.
23. 페이지를 닫습니다.

## <a name="run-format-using-the-adjusted-model-mapping"></a>조정된 모델 매핑을 사용하여 형식 실행
1. 현금 및 은행 관리 > 은행 계좌 > 은행 계좌로 이동합니다.
2. 빠른 필터를 사용하여 기록을 찾습니다. 예를 들어, 값이 'USMF OPER'인 은행 계좌 필드를 필터링합니다.
3. 작업 창에서 설정을 클릭합니다.
4. 확인을 클릭합니다.
5. 테스트 인쇄를 클릭합니다.
6. '확인'을 클릭합니다.
    * 생성된 출력을 검토합니다. 문서 관리 첨부 파일의 이미지는 승인된 사람의 서명으로 표시됩니다.  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a>가져온 형식의 템플릿으로 MS Word 문서 사용
1. 페이지를 닫습니다.
2. 페이지를 닫습니다.
3. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
4. 트리에서 '수표 모델'을 확장합니다.
5. 트리에서 '수표 모델\수표 인쇄 형식'을 선택합니다.
6. 디자이너를 클릭합니다.
7. 첨부 파일을 클릭합니다.
8. 삭제를 클릭합니다.
9. “예.
10. 새로 만들기를 클릭합니다.
11. 파일을 클릭합니다.
    * 찾아보기를 클릭하고 미리 다운로드한 '수표 템플릿 Word.docx' 파일을 선택합니다.  
12. 페이지를 닫습니다.
13. 템플릿 필드에서 값을 입력하거나 선택합니다.
14. 저장을 클릭합니다.
15. 페이지를 닫습니다.
16. 편집을 클릭합니다.
17. 초안 실행 필드에서 예를 선택합니다.
18. 페이지를 닫습니다.
19. 현금 및 은행 관리 > 은행 계좌 > 은행 계좌로 이동합니다.
20. 빠른 필터를 사용하여 값이 'USMF OPER'인 은행 계좌 필드를 필터링합니다.
21. 확인을 클릭합니다.
22. 테스트 인쇄를 클릭합니다.
23. '확인'을 클릭합니다.
    * 생성된 출력을 검토합니다. 출력은 회사 로고, 승인된 사람의 서명 및 워터마크의 선택된 텍스트를 나타내는 이미지가 포함된 Word 문서로 생성되었습니다.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]