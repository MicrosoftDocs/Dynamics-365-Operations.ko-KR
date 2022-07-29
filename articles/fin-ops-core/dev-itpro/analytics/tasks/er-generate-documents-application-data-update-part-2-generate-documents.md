---
title: 애플리케이션 데이터가 있는 문서를 생성하기 위한 설계 구성
description: 이번에는 전자 문서를 생성하기 위해 전자 보고(ER) 구성을 설계하는 방법에 대해 설명합니다. (1부 - 구성 가져오기).
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
ms.openlocfilehash: 3f335721ee97919af20e73fc9da6c9bf07dcae50aca8f8904d144d75c2f4d7b1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460883"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a>애플리케이션 데이터가 있는 문서를 생성하기 위한 설계 구성

[!include [banner](../../includes/banner.md)]

이 절차의 단계를 완료하려면 먼저 절차를 완료해야 합니다. ER 애플리케이션 데이터 업데이트로 문서 생성(1부: 구성 가져오기).



이 절차의 단계에서는 전자 문서를 생성하기 위해 전자 보고(ER) 구성을 설계하는 방법을 설명합니다. 이 절차에서는 샘플 회사인 Litware, Inc.가 전자 문서를 생성하도록 만든 ER 가져오기 형식 구성을 실행합니다.



이번에는 시스템 관리자 또는 전자 보고 개발자 역할이 할당된 사용자를 위해 생성됩니다. 이러한 단계는 DEMF 데이터 세트를 사용하여 완료할 수 있습니다. 



시작하기 전에 DEMF 회사의 국가 컨텍스트를 DEU(독일)에서 BEL(벨기에)로 변경하십시오. 조직 관리 > 조직 > 법인을 클릭하여 법인 DEMF의 기본 주소에서 국가 코드를 업데이트하십시오. 애플리케이션을 다시 시작합니다.


## <a name="run-imported-er-format"></a>가져온 ER 형식 실행
1. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
2. 트리에서 'Intrastat(모델)'을 확장합니다.
3. 트리에서 'Intrastat(모델)\Intrastat(형식)'을 선택합니다.
4. 실행을 클릭합니다.
    * ER 형식 구성의 초안 버전을 실행하여 Intrastat 보고서를 생성합니다.  
5. 파일 이름 입력 필드에 'intrastat.xml'을 입력합니다.
    * 파일 이름을 지정합니다.  
6. '확인'을 클릭합니다.
    * 생성된 XML 파일을 검토합니다.  
7. 페이지를 닫습니다.
8. 세금 > 신고 > 대외 무역 > Intrastat로 이동합니다.
    * 생성된 전자 문서에 포함된 Intrastat 거래를 보려면 이 양식을 엽니다.  
9. Intrastat 아카이브를 클릭합니다.
    * 실행된 ER 형식에는 애플리케이션 데이터 업데이트에 대한 설정이 포함되어 있지 않기 때문에 완료된 Intrastat 보고서의 세부 정보는 보관되지 않았습니다.  
10. 페이지를 닫습니다.
11. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]