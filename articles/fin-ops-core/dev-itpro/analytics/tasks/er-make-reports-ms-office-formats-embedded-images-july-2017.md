---
title: 이미지가 포함된 Office 형식의 보고서를 생성하기 위한 디자인 구성
description: 이번에는 포함된 이미지가 포함된 Excel 및 Word 형식의 전자 문서를 생성하는 구성을 설계하는 방법에 대해 설명합니다.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 03a514c5b616d761ef3eb6347e67e645b23eaa1794911775835e77cded4500ac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460910"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a>이미지가 포함된 Office 형식의 보고서를 생성하기 위한 디자인 구성

[!include [banner](../../includes/banner.md)]

이 절차의 단계를 완료하려면 먼저 'ER 구성 공급자를 만들고 활성으로 표시' 절차를 완료하십시오. 이 절차에서는 포함된 이미지가 포함된 Microsoft Excel Word 문서를 생성하기 위해 전자 보고(ER) 구성을 설계하는 방법을 설명합니다. 이 절차에서는 샘플 회사 Litware, Inc.에 필요한 ER 구성을 생성합니다. 이러한 단계는 USMF 데이터 세트를 사용하여 완료할 수 있습니다. 이번에는 시스템 관리자 또는 전자 보고 개발자 역할이 할당된 사용자를 위해 생성됩니다. 시작하기 전에 다음 파일을 다운로드하여 저장합니다. 

| 설명                                          | 파일 이름                   |
|------------------------------------------------------|-----------------------------|
| ER 데이터 모델 구성                          | [cheques.xml용 모델](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| ER 형식 구성                              | [format.xml 인쇄 확인](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| 회사 로고 이미지                                   | [회사 로고.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| 서명 이미지                                      | [서명 이미지.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| 대체 서명 이미지                          | [서명 이미지 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Microsoft Word 지급 수표 인쇄용 템플릿  | [템플릿 Word.docx 확인](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a>전제 조건 확인  
 1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.  
 2. 샘플 회사인 Litware, Inc.의 구성 제공자가 사용 가능하고 활성으로 표시되어 있는지 확인하십시오. 이 구성 공급자가 표시되지 않으면 '구성 공급자를 만들고 활성으로 표시' 절차의 단계를 완료하십시오.   
 3. 보고 구성을 클릭합니다.  
 
## <a name="add-a-new-er-model-configuration"></a>새 ER 모델 구성 추가  
 1. 새 모델을 생성하는 대신 이전에 저장한 ER 모델 구성 파일(cheques.xml용 모델)을 로드할 수 있습니다. 이 파일에는 지급 확인을 위한 샘플 데이터 모델과 Dynamics 365 for Operations 애플리케이션의 데이터 구성 요소에 대한 데이터 모델 매핑이 포함되어 있습니다.   
 2. 버전 FastTab에서 Exchange를 클릭합니다.   
 3. XML 파일에서 로드를 클릭합니다.  
 4. 찾아보기를 클릭한 다음 cheques.xml에 대한 모델을 선택하십시오.   
 5. '확인'을 클릭합니다.  
 6. 로드된 모델은 Excel 및 Word의 이미지가 포함된 문서를 생성하기 위한 정보의 데이터 소스로 사용됩니다.  

## <a name="add-a-new-er-format-configuration"></a>새 ER 형식 구성 추가  
 1. 새 형식을 만드는 대신 이전에 저장한 ER 형식 구성 파일(수표 인쇄 format.xml)을 로드할 수 있습니다. 이 파일에는 미리 인쇄된 양식을 사용하여 수표를 인쇄하는 형식의 샘플 레이아웃과 이 형식을 '수표 모델' 데이터 모델에 매핑하는 내용이 포함되어 있습니다.   
 2. 교환을 클릭합니다.  
 3. XML 파일에서 로드를 클릭합니다.  
 4. 찾아보기를 클릭하고 검사 인쇄 format.xml 파일을 선택합니다.   
 5. '확인'을 클릭합니다.  
 6. 트리에서 '수표 모델'을 확장합니다.  
 7. 트리에서 '수표 모델\수표 인쇄 형식'을 선택합니다.  
 8. 로드된 형식은 Excel 및 Word의 이미지가 포함된 문서를 생성하는 데 사용됩니다.   

## <a name="configure-er-user-parameters"></a>ER 사용자 매개 변수 구성  
 1. 작업 창에서 구성을 클릭합니다.  
 2. 사용자 매개 변수를 클릭합니다.  
 3. 실행 설정 필드에서 예를 선택합니다.  
  '초안 실행' 플래그를 켜서 완료된 형식 대신 선택한 형식의 초안 버전을 시작합니다.  
 4. '확인'을 클릭합니다.  

## <a name="configure-cash--bank-management-parameters"></a>현금 및 은행 관리 매개 변수 구성  
 1. 현금 및 은행 관리 > 은행 계좌 > 은행 계좌로 이동합니다.  
 2. 빠른 필터를 사용하여 값이 'USMF OPER'인 은행 계좌 필드를 필터링합니다.  
 3. 작업 창에서 설정을 클릭합니다.  
 4. 확인을 클릭합니다.  
 5. 설정 섹션을 확장합니다.  
 6. 편집을 클릭합니다.  
 7. 회사 로고 필드에서 예를 선택합니다.  
 8. 회사 로고를 클릭합니다.  
 9. 변경을 클릭합니다.  
 10. 찾아보기를 클릭하고 이전에 다운로드한 파일인 Company logo.png를 선택합니다.   
 11. 저장을 클릭합니다.  
 12. 페이지를 닫습니다.  
 13. 서명 섹션을 확장합니다.  
 14. 첫 번째 서명 인쇄 필드에서 예를 선택합니다.  
 15. 변경을 클릭합니다.  
 16. 찾아보기를 클릭하고 이전에 다운로드한 파일 서명 image.png를 선택합니다.   
 17. 복사본 섹션을 확장합니다.  
 18. 워터마크 필드에서 옵션을 선택합니다.  
 19. 일반 전자 내보내기 형식 필드에서 예를 선택합니다.  
 20. '수표 인쇄 양식' 구성을 선택합니다.  
 21. 이제 선택한 ER 형식이 수표 인쇄에 사용됩니다.  
 22. 첨부를 클릭합니다.  
 23. 새로 만들기를 클릭합니다.  
 24. 파일을 클릭합니다.  
 25. 찾아보기를 클릭하고 이전에 다운로드한 파일인 서명 이미지 2.png를 선택합니다.   
 26. 페이지를 닫습니다.  
 27. 페이지를 닫습니다.  
 28. 페이지를 닫습니다.  
 29. 현금 및 은행 관리 > 설정 > 현금 및 은행 관리 매개 변수로 이동합니다.  
 30. 비활성 은행 계좌에 대한 사전 메모 생성 허용: 필드에서 예를 선택합니다.  
 31. 저장을 클릭합니다.  
 32. 페이지를 닫습니다.  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
