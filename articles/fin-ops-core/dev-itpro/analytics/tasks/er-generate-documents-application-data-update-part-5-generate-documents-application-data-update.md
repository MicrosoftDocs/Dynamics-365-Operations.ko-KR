---
title: 애플리케이션 데이터가 있는 문서 생성
description: 이 절차의 단계를 완료하려면 먼저 '애플리케이션 데이터 업데이트로 문서 생성(4부 - 형식 수정)' 절차를 완료해야 합니다.
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
ms.openlocfilehash: 0166e0afb542baea063f2d563e1eaeb0cdbfd6f62d77898fd9916afbeca90e48
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460880"
---
# <a name="generate-documents-that-have-application-data"></a>애플리케이션 데이터가 있는 문서 생성

[!include [banner](../../includes/banner.md)]

이 절차의 단계를 완료하려면 먼저 '애플리케이션 데이터 업데이트로 문서 생성(4부: 형식 수정)'을 참조하십시오.



이 절차의 단계에서는 전자 문서를 생성하고 애플리케이션 데이터를 업데이트하기 위해 전자 보고(ER) 구성을 설계하는 방법을 설명합니다. 이 절차에서는 ER 형식 구성을 실행하여 Intrastat 보고서를 생성하고 보고 프로세스의 세부 정보를 보관하기 위해 애플리케이션 데이터를 업데이트합니다.



이번에는 시스템 관리자 또는 전자 보고 개발자 역할이 할당된 사용자를 위해 생성됩니다. 이러한 단계는 DEMF 데이터 세트를 사용하여 완료할 수 있습니다. 시작하기 전에 DEMF 회사의 국가 컨텍스트가 BEL(벨기에)인지 확인하십시오.


## <a name="set-up-foreign-trade-parameters"></a>대외 무역 매개 변수 설정
1. 세금 > 설정 > 해외 무역 > 해외 무역 매개 변수로 이동합니다.
2. 숫자 시퀀스 탭을 클릭합니다.

    Intrastat 보고 프로세스의 세부 정보를 보관하려면 생성한 각 보관 파일의 기록을 식별해야 합니다. 이를 위해 특수 번호 시퀀스를 구성해야 합니다.  

3. 'Intrastat 아카이브 ID' 참조를 선택하십시오.
4. 번호 시퀀스 코드 필드에 값을 입력합니다.

    '번호 시퀀스 코드' 필드에 'Fore_2' 값을 입력하거나 선택합니다.  

5. 해결번호 시퀀스 코드를 변경합니다.
6. 저장을 클릭합니다.
7. 페이지를 닫습니다.

## <a name="run-modified-er-format"></a>수정된 ER 형식 실행
1. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
2. 트리에서 'Intrastat(모델)'을 확장합니다.
3. 트리에서 'Intrastat(모델)\Intrastat(형식)'을 선택합니다.
4. 실행을 클릭합니다.
5. 파일 이름 입력 필드에 'intrastat2.xml'을 입력합니다.
6. '확인'을 클릭합니다.

## <a name="review-er-format-executions-results"></a>ER 형식 실행 결과 검토
생성된 XML 파일을 검토합니다.  
1. 페이지를 닫습니다.
2. 세금 > 신고 > 대외 무역 > Intrastat로 이동합니다.

    생성된 전자 문서에 포함된 Intrastat 거래가 포함된 이 양식을 엽니다.  

3. Intrastat 아카이브를 클릭합니다.

    실행된 ER 형식에는 이제 애플리케이션 데이터 업데이트에 대한 설정이 포함되어 있으므로 완료된 Intrastat 보고의 세부 정보가 보관되었습니다. 이 양식에서는 생성된 아카이브의 헤더 기록을 볼 수 있습니다.  

4. 세부 정보를 클릭합니다.

    이 양식에서 생성된 아카이브에 대한 세부 정보를 볼 수 있습니다.  

5. 페이지를 닫습니다.
6. 페이지를 닫습니다.
7. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]