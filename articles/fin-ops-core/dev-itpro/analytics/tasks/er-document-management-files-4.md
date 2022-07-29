---
title: ER 형식 출력에서 문서 관리 파일 사용(4부 - 형식 실행)
description: 이번에는 ER 출력에서 문서 관리 파일을 사용하도록 전자 보고 형식을 구성하는 방법에 대해 설명합니다. (4부)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 11b446d21a7ae57ffa2cccf983777beb882bf77de6b54c2d1aef810028a6d343
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460710"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a>ER 형식 출력에서 문서 관리 파일 사용(4부 - 형식 실행)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 ER 출력에서 문서 관리 파일(첨부 파일)을 사용하도록 전자 보고(ER) 형식을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 DEMF 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 'ER 형식 출력에서 문서 관리 파일 사용(파트 3: 형식 만들기)' 절차를 따르십시오.

이번에는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a>단일 송장의 판매 주문에 필요한 첨부 파일 추가
1. 미수금 > 송장 > 고객 송장 열기로 이동합니다.
2. 빠른 필터를 사용하여 기록을 찾습니다. 예를 들어 값이 'CIV-000148'인 송장 필드를 필터링합니다.
    * CIV-000148  
3. 선택한 송장의 링크를 클릭하여 따르십시오.
    * CIV-000148  
4. 판매 주문 필드의 링크를 클릭하여 따르십시오.
    * 000148  
5. 라인 또는 헤더 필드에서 헤더 옵션을 선택합니다.
    * 헤더를 선택하여 첨부 파일을 추가할 대상임을 나타냅니다.  
6. 첨부를 클릭합니다.
    * 이 판매 주문에 대한 첨부 파일로 몇 개의 파일을 추가하십시오. 문서 관리에서 지원하는 문서 유형의 파일을 사용하십시오(파일 확장자 DOCX, DPF, XML, JPG 등). 첨부할 파일을 찾아보고 선택하고 ER 전자 메시지에서 관련 송장과 함께 추가 처리합니다.  
7. 새로 만들기를 클릭합니다.
8. 파일을 클릭합니다.
9. 새로 만들기를 클릭합니다.
10. 파일을 클릭합니다.
11. 페이지를 닫습니다.
12. 페이지를 닫습니다.
13. 페이지를 닫습니다.
14. 페이지를 닫습니다.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>선택한 송장에 대해 설계된 보고서 실행
1. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
2. 트리에서 '고객 송장 모델'을 확장합니다.
3. 트리에서 '고객 송장 모델\고객 송장 모델(사용자 지정)'을 확장합니다.
4. 트리에서 '고객 송장 모델\고객 송장 모델(사용자 지정)\전자 송장 샘플 메시지'를 선택합니다.
5. 실행을 클릭합니다.
6. 포함할 기록() 섹션을 확장합니다.
7. 필터를 클릭합니다.
8. 고객 송장 분개 및 판매 주문 필드의 행을 선택합니다.
9. 기준 필드에 '000148'을 입력합니다.
    * '판매 주문' 기준 필드에 주문 번호 000148을 입력합니다.  
10. '확인'을 클릭합니다.
11. '확인'을 클릭합니다.
    * 생성된 출력을 검토합니다. 각 첨부 파일에 대해 단일 XML 노드가 생성되었습니다. 첨부 파일의 내용은 MIME(base64) 텍스트 형식의 XML 출력으로 채워집니다.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]