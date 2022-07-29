---
title: 애플리케이션 데이터가 있는 문서를 생성하기 위해 구성 가져오기
description: 이 절차의 단계를 완료하려면 먼저 'ER 구성 공급자를 만들고 활성으로 표시' 절차를 완료해야 합니다.
author: NickSelin
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 08ab90d6f53dbb9eabeea3c2cf020792e8957c7b71ed27fc491008fcad114c72
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460885"
---
# <a name="import-configurations-to-generate-documents-that-have-application-data"></a>애플리케이션 데이터가 있는 문서를 생성하기 위해 구성 가져오기

[!include [banner](../../includes/banner.md)]

이 절차의 단계를 완료하려면 먼저 'ER 구성 공급자를 만들고 활성으로 표시' 절차를 완료해야 합니다.

이 절차의 단계에서는 전자 문서를 생성하기 위해 전자 보고(ER) 구성을 설계하는 방법을 설명합니다. 이 절차에서는 샘플 회사인 Litware, Inc.에 대해 생성된 필수 ER 구성을 가져와 전자 문서를 생성하는 데 사용합니다. 이번에는 시스템 관리자 또는 전자 보고 개발자 역할이 할당된 사용자를 위해 생성됩니다. 이러한 단계는 DEMF 데이터 세트를 사용하여 완료할 수 있습니다. 시작하기 전에 도움말 항목 'ER 도구를 사용하여 전자 문서 생성 및 애플리케이션 데이터 업데이트'(generate-electronic-documents-update-application-data/)에 나열된 파일을 다운로드하고 저장합니다. 파일은 Intrastat(model).xml, Intrastat(mapping).xml 및 Intrastat(format).xml입니다.

1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
    * 샘플 회사인 Litware, Inc.의 구성 제공자가 사용 가능하고 활성으로 표시되어 있는지 확인하십시오. 이 구성 공급자가 표시되지 않으면 구성 공급자 만들기 절차의 단계를 완료하고 활성으로 표시합니다.  
    * 이 절차의 단계는 ER 기능을 사용하여 애플리케이션 데이터 업데이트를 완료하는 방법과 Intrastat 보고서를 생성하는 방법을 보여줍니다. 보고 프로세스의 세부 정보는 애플리케이션 테이블에 보관됩니다. 현재 Intrastat 보고 프로세스가 Intrastat 양식에서 활성화되면 기존 소스 코드에 프로그래밍된 로직을 기반으로 아카이빙이 수행됩니다. 이 절차에서는 ER 프레임워크만 사용하여 유사하지만 단순화된 애플리케이션 데이터 논리를 구성합니다. 소스 코드는 변경되지 않습니다.   

## <a name="import-er-configurations"></a>ER 구성 가져오기
1. 보고 구성을 클릭합니다.
2. 교환을 클릭합니다.
3. XML 파일에서 로드를 클릭합니다.
    * Intrastat 보고서를 생성하기 위한 데이터 소스로 사용하도록 설계된 데이터 모델이 포함된 ER 모델 구성을 가져옵니다. 나중에 이 데이터 모델 정의를 확장하여 Intrastat 보고 프로세스의 세부 정보를 보관하는 애플리케이션 데이터 업데이트에 사용할 것입니다.   
    * 찾아보기를 클릭하고 Intrastat(model).xml 파일을 선택하십시오.  
4. '확인'을 클릭합니다.
5. 트리에서 'Intrastat(모델)'을 선택합니다.
6. 디자이너를 클릭합니다.
7. 트리에서 '보내는 문서용'을 확장합니다.
8. 트리에서 '보내는 문서\트랜잭션의 경우'를 확장합니다.
    * 가져온 데이터 모델의 구조를 검토합니다. 루트 항목 'For outgoing document'는 애플리케이션에서 데이터를 가져오고 이를 데이터 소스로 사용하여 Intrastat 보고서를 생성하기 위한 데이터 흐름을 지정하도록 정의됩니다. '트랜잭션(기록 목록)'은 보고해야 하는 Intrastat 트랜잭션 목록을 나타내는 데 사용됩니다. 보고된 상품 코드를 보관하므로 이 데이터 흐름에는 단일 상품 코드 '상품 인식 ID(Int64)'의 고유 식별자가 필요합니다.   
9. 페이지를 닫습니다.
10. 교환을 클릭합니다.
11. XML 파일에서 로드를 클릭합니다.
    * 애플리케이션에서 데이터를 가져온 다음 이를 사용하여 Intrastat 보고서를 생성하기 위한 데이터 흐름을 지정하는 ER 매핑 구성을 가져옵니다. 나중에 이 모델 매핑 정의를 확장하여 Intrastat 보고서에서 데이터를 가져와 애플리케이션 데이터 업데이트에 사용하여 Intrastat 보고 프로세스의 세부 정보를 보관합니다.   
    * 찾아보기를 클릭하고 Intrastat(mapping).xml 파일을 선택하십시오.  
12. '확인'을 클릭합니다.
13. 트리에서 'Intrastat(모델)'을 확장합니다.
14. 트리에서 'Intrastat(모델)\Intrastat(mapping)'을 선택합니다.
15. 디자이너를 클릭합니다.
    * 현재 모델 매핑에는 방향 필드에 'To model' 값이 포함되어 있습니다. 이는 이 모델 매핑이 애플리케이션에서 데이터를 가져와 데이터 모델에 저장하도록 설계되었음을 의미합니다.  
16. 디자이너를 클릭합니다.
17. 트리에서 '목록'을 확장합니다.
18. 트리에서 '트랜잭션=목록'을 확장합니다.
    * '보내는 문서의 경우' 루트 항목을 기준으로 필터링된 데이터 모델을 사용하는 모델 매핑의 구조를 검토합니다. 추가된 데이터 소스 '목록'은 Intrastat 테이블의 기록 목록인 필수 애플리케이션 데이터에 대한 액세스를 제공합니다.  
19. 페이지를 닫습니다.
20. 페이지를 닫습니다.
21. 교환을 클릭합니다.
22. XML 파일에서 로드를 클릭합니다.
    * Intrastat 보고서의 레이아웃과 보고서에 데이터를 채우는 프로세스를 지정하는 ER 형식 구성을 가져옵니다. 나중에 이 형식 정의를 확장하여 Intrastat 보고서의 데이터를 데이터 모델에 넣은 다음 이를 사용하여 애플리케이션 데이터를 업데이트하여 Intrastat 보고 프로세스의 세부 정보를 보관합니다.   
    * 찾아보기를 클릭하고 Intrastat(형식).xml 파일을 선택합니다.  
23. '확인'을 클릭합니다.
24. 트리에서 'Intrastat(모델)\Intrastat(형식)'을 선택합니다.
25. 디자이너를 클릭합니다.
26. 확장/축소를 클릭합니다.
27. 트리에서 'File\Declaration'을 선택합니다.
28. 매핑 탭을 클릭합니다.
29. 트리에서 '파일'을 선택합니다.
    * Intrastat 보고서를 생성하는 데 사용된 형식의 구조를 검토합니다. 'For outgoing document' 루트 항목을 기반으로 하는 데이터 모델에서 데이터를 채워 XML 파일을 생성하도록 설계되었습니다. 생성된 파일의 이름이 사용자 대화 상자 양식에 정의되어 있는지 확인합니다('fn' 데이터 소스가 사용됨).   
30. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]