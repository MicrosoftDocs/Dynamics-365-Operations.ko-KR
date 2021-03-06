---
title: 판매 견적 대량 생성
description: 이 절차는 여러 고객에게 보낼 제품 또는 서비스 세트를 제공하는 견적을 효율적으로 생성하는 방법을 보여줍니다.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm, SalesQuickQuote
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: acb2b49c7cb2024aec1140d04150bd1ab9d75c14
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448612"
---
# <a name="mass-create-sales-quotations"></a>판매 견적 대량 생성

[!include [banner](../../includes/banner.md)]

이 절차는 여러 고객에게 보낼 제품 또는 서비스 세트를 제공하는 견적을 효율적으로 생성하는 방법을 보여줍니다. 이 대량 견적 생성은 견적 템플릿을 기반으로 합니다. 자신의 데이터 또는 데모 데이터 회사 USMF에서 이 절차를 실행할 수 있습니다.


## <a name="create-a-quotation-template"></a>견적 템플릿 만들기
1. 영업 및 마케팅 > 설정 > 견적 > 템플릿 그룹으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 그룹 ID 필드에 원하는 ID를 입력합니다.
4. 설명 필드에 값을 입력합니다.
5. 저장을 클릭합니다.
6. 페이지를 닫습니다
7. 영업 및 마케팅 > 판매 견적 > 모든 견적으로 이동합니다.
8. 새로 만들기를 클릭합니다.
9. 계정 유형 필드에서 '고객'을 선택합니다.
10. 고객 계정 필드에서 값을 입력하거나 선택합니다.
11. 확인을 클릭합니다.
    * 견적이 템플릿이 되려면 견적 헤더에서 설정 단계를 수행해야 합니다. 견적에 라인을 추가하기 전에 이 작업을 수행해야 합니다.   
12. 작업 창에서 옵션을 클릭합니다.
13. 보기 변경을 클릭합니다.
14. 헤더 보기를 클릭합니다.
15. 설정 섹션을 확장합니다.
16. 그룹 ID 필드에 값을 입력하거나 선택합니다.
17. 템플릿 이름 필드에 값을 입력합니다.
18. 활성 필드에서 예를 선택합니다.
    * 템플릿을 새 판매 견적에 적용할 때 활성 템플릿만 사용할 수 있습니다.  
19. 작업 창에서 옵션을 클릭합니다.
20. 보기 변경을 클릭합니다.
21. 라인 보기를 클릭합니다.
22. 항목 필드에 값을 입력하거나 선택합니다.
23. 항목 필드에 값을 입력합니다.
24. 페이지를 닫습니다
25. 할인율 필드에 숫자를 입력합니다.
26. 라인 추가를 클릭합니다.
27. 항목 필드에 값을 입력하거나 선택합니다.
28. 항목 필드에 값을 입력합니다.
29. 페이지를 닫습니다
30. 단가 필드에 새 가격을 입력하거나 현재 가격을 변경합니다.
31. 라인 추가를 클릭합니다.
32. 항목 필드에 값을 입력하거나 선택합니다.
33. 항목 필드에 값을 입력합니다.
34. 페이지를 닫습니다
35. 수량 필드에 숫자를 입력합니다.
36. 할인 필드에 숫자를 입력합니다.
37. 저장을 클릭합니다.

## <a name="apply-the-template-to-create-a-single-quotation"></a>템플릿을 적용하여 작은따옴표 만들기
1. 영업 및 마케팅 > 판매 견적 > 모든 견적으로 이동합니다.
    * 방금 생성한 견적이 템플릿으로 표시됩니다.  
2. 새로 만들기를 클릭합니다.
3. 계정 유형 필드에서 '고객'을 선택합니다.
4. 고객 계정 필드에서 값을 입력하거나 선택합니다.
5. 템플릿 섹션을 확장합니다.
6. 그룹 ID 필드에 값을 입력하거나 선택합니다.
7. 템플릿 이름 필드에 값을 입력하거나 선택합니다.
8. 계산 방법 필드에서 '템플릿 값 기반'을 선택합니다.
9. 확인을 클릭합니다.
    * 이제 템플릿의 데이터와 조건을 기반으로 새 견적이 생성되었습니다.  
10. 페이지를 닫습니다
11. 페이지를 닫습니다

## <a name="apply-the-template-to-mass-create-quotations"></a>템플릿을 적용하여 견적을 대량 생성
1. 영업 및 마케팅 > 판매 견적 > 견적 업데이트 > 견적 대량 생성으로 이동합니다.
2. 계정 유형 필드에서 '고객'을 선택합니다.
3. 그룹 ID 필드에 값을 입력하거나 선택합니다.
4. 템플릿 이름 필드에 값을 입력하거나 선택합니다.
5. 계산 방법 필드에서 '템플릿 값 기반'을 선택합니다.
6. 포함할 레코드 섹션을 펼칩니다.
7. 필터를 클릭합니다.
8. 기준 필드에서 이 대량 견적 생성에 포함할 고객 범위를 포함하도록 필터를 설정합니다. 다음 형식을 사용하세요. "Customer1..CustomerN.
    * 예를 들어 필터를 US-001..US-004로 설정할 수 있습니다.  
9. 확인을 클릭합니다.
10. 확인을 클릭합니다.
11. 영업 및 마케팅 > 판매 견적 > 모든 견적으로 이동합니다.
    * 선택한 템플릿을 기반으로 대량 업데이트 루틴에 지정된 모든 고객에 대해 견적이 생성되었는지 확인합니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]