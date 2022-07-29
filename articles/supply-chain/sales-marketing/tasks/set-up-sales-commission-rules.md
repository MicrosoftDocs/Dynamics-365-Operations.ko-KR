---
title: 판매 수수료 규칙 설정
description: 이 절차는 판매 수수료 계산 및 추적을 설정하고 사용 설정하는 방법을 보여줍니다.
author: Henrikan
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CommissionCustomerGroup, CommissionItemGroup, CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, CommissionCalc, InventPosting, CustTable, EcoResProductDetailsExtended, CommissionEmplSalesGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8f42f2fbe22124dbaaf2c4bd2f4394f734d166d5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449158"
---
# <a name="set-up-sales-commission-rules"></a>판매 수수료 규칙 설정

[!include [banner](../../includes/banner.md)]

이 절차는 판매 수수료 계산 및 추적을 설정하고 사용 설정하는 방법을 보여줍니다. 절차는 고객 및 항목 수수료 그룹을 모두 생성한 다음 선택한 고객 및 제품을 해당 그룹에 연결하는 방법을 보여줍니다. 그런 다음 이러한 그룹은 수수료 계산 설정에서 영업 직원에게 수수료를 부여하기 위해 판매 주문과 일치해야 하는 고객, 항목 및 영업 담당자 조합을 생성하는 데 사용됩니다. 수수료 계산은 개별 고객 및/또는 항목에 대해서도 수행할 수 있으므로 고객 및 항목 수수료 그룹 생성은 선택 사항입니다. 데모 데이터 회사 USMF 또는 자체 데이터에서 이 절차를 실행할 수 있습니다.


## <a name="set-up-commission-groups-and-commission-rates"></a>수수료 그룹 및 수수료율 설정
1. **탐색 창 > 모듈 > 영업 및 마케팅 > 수수료 > 수수료에 대한 고객 그룹** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **그룹** 필드에 값을 입력합니다.
4. **이름** 필드에 값을 입력합니다.
5. **저장** 을 선택합니다.
6. 페이지를 닫습니다.
7. **탐색 창 > 모듈 > 영업 및 마케팅 > 수수료 > 항목 그룹** 으로 이동합니다.
8. **새로 만들기** 를 선택합니다.
9. **그룹** 필드에 값을 입력합니다.
10. **이름** 필드에 값을 입력합니다.
11. **저장** 을 선택합니다.
12. 페이지를 닫습니다.
13. **영업 및 마케팅 > 수수료 > 판매 그룹** 으로 이동합니다.
    - 수수료 판매 그룹은 관련 판매 그룹과 연결된 고객이 특정 항목을 구매할 때 수수료를 받을 수 있는 영업 담당자 역할의 직원을 지정합니다.  
    - USMF 데모 데이터 회사에는 "Sales reps US"라는 판매 그룹이 있습니다.  
14. **작업 창** 에서 **일반** 을 선택합니다.
15. **영업 담당자** 를 클릭합니다. 영업 담당자입니다. 페이지는 특정 수수료 그룹과 연관된 회사의 영업 사원 목록을 표시합니다. 동일한 그룹에 여러 영업 담당자를 할당하고 총 수수료 중 각자의 몫을 백분율 값으로 정의할 수 있습니다. 모든 직원의 총 수수료 몫은 100을 초과할 수 없습니다. 
16. 목록에서 선택한 행을 표시합니다.
17. **편집** 을 선택합니다.
18. **수수료 몫** 을 '50'으로 설정합니다.
19. **새로 만들기** 를 클릭합니다.
20. **이름** 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
21. **빠른 필터** 를 사용해 기록을 찾습니다. 예를 들어 값이 'Susan Burk'인 이름 필드를 필터링합니다.
22. **선택** 을 클릭합니다.
23. **수수료 몫** 을 '50'으로 설정합니다.
24. **저장** 을 클릭합니다.
25. **영업 및 마케팅 > 수수료 > 수수료 계산** 으로 이동합니다. **수수료 계산** 페이지에서 고객과 제품의 사전 설정 조합이 포함된 판매 거래에 대해 직원이 받는 수수료 비율을 정의합니다. 수수료율 설정의 일부로 수수료 계산 기준과 할인을 포함할지 제외할지 여부를 지정해야 합니다. 수수료율이 활성화된 경우 유효 기간을 입력할 수도 있습니다.  
26. **새로 만들기** 를 클릭합니다.
27. **항목 코드** 필드에서 '그룹'을 선택합니다.
28. **항목 관계** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
29. 목록에서 이전에 만든 그룹을 찾아 선택합니다.
30. **고객 코드** 필드에서 '그룹'을 선택합니다.
31. **고객 관계** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
32. 목록에서 이전에 설정한 그룹을 선택합니다.
33. **영업 담당자 관계** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
34. 목록에서 원하는 레코드를 찾아 선택합니다.
    - "라인 할인 전" 옵션을 유지하세요.  
    - 수수료 값 계산의 기초로 "수익" 옵션을 유지하세요.    
35. 수수료 백분율 필드에 숫자를 입력합니다.
36. **저장** 을 클릭합니다.

## <a name="setting-up-commission-posting"></a>수수료 기장 설정
1. **탐색 창 > 영업 및 마케팅 > 수수료 > 수수료 기장** 으로 이동합니다. 수수료 금액은 직원에게 지불해야 하므로 **총계정원장** 의 해당 계정에 올바른 재무 전기를 제공하도록 설정해야 합니다. 이는 **수수료 기장** 페이지에서 할 수 있습니다. 현재 회사에서 사용할 수 있는 설정을 검토합니다. 일반적으로 수수료 금액은 전용 비용 계정에 전기되고 전용 지불 계정으로 상계됩니다. 수수료 게시 규칙이 설정되어 있지 않으면 시스템에서 적격 수수료가 있는 판매 주문의 송장 발행을 완료하지 못합니다.  
2. 페이지를 닫습니다.

## <a name="assign-a-commission-group-to-a-customer-and-a-product"></a>고객 및 제품에 수수료 그룹 할당
1. **탐색 창 > 모듈 > 영업 및 마케팅 > 고객 > 모든 고객** 으로 이동합니다.
2. 목록에서 원하는 레코드를 찾아 선택합니다.
3. 목록에서 선택한 행의 링크를 클릭합니다.
4. **편집** 을 클릭합니다.
5. **판매 주문 기본값** 섹션을 확장합니다.
6. **수수료 그룹** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
7. 목록에서 이전에 생성한 그룹을 선택합니다.
8. **판매 그룹** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
9. 목록에서 원하는 레코드를 찾아 선택합니다.
10. **저장** 을 클릭합니다.
11. **탐색 창 > 모듈 > 제품 정보 관리 > 제품 > 출시된 제품** 으로 이동합니다.
12. **필터** 를 사용해 기록을 찾습니다. 예를 들어 값이 'T0020'인 품목 번호 필드를 필터링합니다.
13. 목록에서 선택한 행의 링크를 클릭합니다.
14. **편집** 을 클릭합니다.
15. **판매** 섹션을 확장합니다.
16. **수수료 그룹** 에서 드롭다운 단추를 클릭하여 조회를 엽니다.
17. 목록에서 이전에 만든 수수료 그룹을 선택합니다.
18. **저장** 을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]