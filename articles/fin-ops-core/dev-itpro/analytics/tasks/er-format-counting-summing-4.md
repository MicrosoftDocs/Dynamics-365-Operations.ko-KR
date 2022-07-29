---
title: ER 카운팅 및 합산을 수행하는 형식 구성(파트 4 - 실행 형식)
description: 이번에는 이미 생성된 텍스트 출력의 데이터를 기반으로 계산 및 합산을 수행하도록 전자 보고 형식을 구성하는 방법에 대해 설명합니다. (4부)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, IntrastatParameters, Intrastat, InventItemIdLookupSimple, IntrastatCommodityLookup, ERFormatMappingRunLogTable, DocuView
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5202f8be275df08142c9848a2381fe5bc2ed7289a1f1fe1f8e6d349e38c2b14d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460886"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-4---run-format"></a>ER 카운팅 및 합산을 수행하는 형식 구성(파트 4 - 실행 형식)

[!include [banner](../../includes/banner.md)]

다음 단계에서는 시스템 관리자 또는 전자 보고 개발자 역할에 할당된 사용자가 이미 생성된 텍스트 출력의 데이터를 기반으로 계산 및 합산을 수행하도록 전자 보고(ER) 형식을 구성할 수 있는 방법을 설명합니다. 이러한 단계는 DEMF 회사에서 수행할 수 있습니다.

이 단계를 완료하려면 먼저 'ER Configure format to do counting and summing(파트 3: 계산을 사용하여 출력)' 절차를 따르십시오.

이번에는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.


## <a name="test-this-configuration-for-generation-of-the-intrastat-reports"></a>Intrastat 보고서 생성을 위해 이 구성을 테스트합니다.
1. 조직 관리 > 작업 영역 > 전자 보고로 이동합니다.
2. 보고 구성을 클릭합니다.
3. 트리에서 'Intrastat 모델'을 확장합니다.
4. 트리에서 'Intrastat model\Intrastat(DE)'를 확장합니다.
5. 트리에서 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'을 선택합니다.
6. 작업 창에서 구성을 클릭합니다.
7. 사용자 매개 변수를 클릭합니다.
8. 실행 설정 필드에서 예를 선택합니다.
9. '확인'을 클릭합니다.
10. 편집을 클릭합니다.
11. 초안 실행 필드에서 예를 선택합니다.
12. 저장을 클릭합니다.
13. 세금 > 설정 > 해외 무역 > 해외 무역 매개 변수로 이동합니다.
14. 전자 보고 섹션을 확장합니다.
15. '카운팅 및 합산 포함 Intrastat(DE)' 구성을 선택합니다.
16. '카운팅 및 합산 포함 Intrastat(DE)' 구성을 선택합니다.
17. 저장을 클릭합니다.
18. 페이지를 닫습니다.
19. 세금 > 신고 > 대외 무역 > Intrastat로 이동합니다.
20. 출력을 클릭합니다.
21. 신고를 클릭합니다.
    * Intrastat 보고서 생성 프로세스를 실행합니다.  
22. 시작 날짜 필드에서 날짜를 '2000-01-01'로 설정합니다.
    * 양식 트랜잭션에 있는 기존 날짜를 포함하는 보고 기간의 시작 날짜와 종료 날짜를 정의합니다.  
23. 종료 날짜 필드에서 날짜를 '2022-12-31'로 설정합니다.
    * 양식 트랜잭션에 있는 기존 날짜를 포함하는 보고 기간의 시작 날짜와 종료 날짜를 정의합니다.  
24. 방향 필드에서 '도착'을 선택합니다.
25. 파일 생성 필드에서 예를 선택합니다.
26. '확인'을 클릭합니다.
    * 마지막에 요약 라인이 있는 생성된 출력을 검토합니다.  
27. 새로 만들기를 클릭합니다.
28. 목록에서 선택한 행을 표시합니다.
29. 방향 필드에서 '디스패치'를 선택합니다.
30. 항목 번호 필드에 값을 입력하거나 선택합니다.
31. 상품 필드에서 값을 입력하거나 선택합니다.
32. 가중치를 '10'으로 설정합니다.
33. 송장 금액을 '10000'으로 설정합니다.
34. 통계량을 '10000'으로 설정합니다.
35. 출력을 클릭합니다.
36. 신고를 클릭합니다.
37. 방향 필드에서 '디스패치'를 선택합니다.
38. '확인'을 클릭합니다.
    * 마지막에 요약 라인이 있는 생성된 출력을 검토합니다. 첫 번째 실행과 비교하여 변경되었음을 유의하십시오.  

## <a name="run-this-configuration-in-debug-mode-to-review-the-collected-counting--summing-data"></a>디버그 모드에서 이 구성을 실행하여 수집된 계수 및 합산 데이터를 검토하십시오.
1. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
2. 트리에서 'Intrastat 모델'을 확장합니다.
3. 트리에서 'Intrastat model\Intrastat(DE)'를 확장합니다.
4. 트리에서 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'을 선택합니다.
5. 작업 창에서 구성을 클릭합니다.
6. 사용자 매개 변수를 클릭합니다.
7. 디버그 모드에서 실행 필드에서 예를 선택하십시오.
8. '확인'을 클릭합니다.
9. 페이지를 닫습니다.
10. 세금 > 신고 > 대외 무역 > Intrastat로 이동합니다.
11. 출력을 클릭합니다.
12. 신고를 클릭합니다.
13. '확인'을 클릭합니다.
14. 페이지를 닫습니다.
15. 조직 관리 > 전자 보고 > 구성으로 이동합니다.
16. 트리에서 'Intrastat 모델'을 확장합니다.
17. 트리에서 'Intrastat model\Intrastat(DE)'를 확장합니다.
18. 트리에서 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'을 선택합니다.
19. 디버그 로그를 클릭합니다.
    * 선택한 구성의 실행 프로세스에 대한 디버그 로그 기록이 생성되었습니다.  
20. 첨부를 클릭합니다.
21. 열기를 클릭합니다.
    * 선택한 구성을 실행하는 동안 수집된 집계 및 합계 세부 정보가 포함된 생성된 XML 파일을 검토합니다.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]