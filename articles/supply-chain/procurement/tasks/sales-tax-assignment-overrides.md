---
title: 판매세 할당 및 재정의
description: 이 절차는 판매세 그룹을 상거래 채널에 할당하는 방법을 보여줍니다.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f72c9ffde760c1bc151ee15fe050f3704e43d83e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448981"
---
# <a name="sales-tax-assignment-and-overrides"></a>판매세 할당 및 재정의

[!include [banner](../../includes/banner.md)]

이 절차는 판매세 그룹을 상거래 채널에 할당하는 방법을 보여줍니다. 또한 새 판매세 재정의를 만들고 이를 기존 판매세 재정의 그룹에 지정하는 프로세스를 안내합니다. 이 절차에서는 데모 데이터에서 USRT 회사를 사용합니다.

1. 소매 및 상거래 > 채널 > 매장 > 모든 매장으로 이동합니다.
2. 목록에서 '휴스턴'에 대한 채널 ID 링크를 클릭합니다.
3. 편집을 클릭합니다.
    * "판매세 그룹" 필드에는 현재 회사의 판매세 그룹 목록이 포함됩니다. 현재 할당된 그룹은 일반 "세금" 판매세 그룹입니다. "워싱턴" 및 "워싱턴, 킹 카운티"에 대한 판매세 그룹도 있습니다. 판매세 그룹에는 여러 지방 자치 단체에 적용되는 세금이 포함될 수 있습니다.  
    * "판매세 재정의" 필드는 판매세 재정의 그룹이 채널에 매핑될 수 있는 곳입니다. 판매세 재정의 그룹을 사용하여 여러 상점에서 작동하는 판매세 재정의를 그룹화할 수 있습니다. 판매세 재정의를 하나씩 수동으로 할당하는 대신 그룹을 만들고 채널에 직접 할당하여 시간을 절약할 수 있습니다.  
4. 저장을 클릭합니다.
5. 페이지를 닫습니다.
6. 소매 및 상업 > 채널 설정 > 판매세 > 판매세 재정의로 이동합니다.
7. 새로 만들기를 클릭합니다.
8. 판매세 재정의 필드에 새 재정의의 이름을 제공합니다.
9. 설명 필드에 재정의에 대한 설명을 제공합니다.
10. 상태를 "사용"으로 설정합니다.
11. 재정의 섹션을 펼치거나 접습니다.
12. 유형 필드에서 옵션을 선택합니다.
    * 항목 판매세 그룹을 사용하여 그룹에 속한 특정 항목에 대한 세금을 재정의할 수 있습니다. 예를 들어 식품 항목은 일반적으로 단단한 제품과 다르게 과세되며 자체 판매세 그룹이 있을 수 있습니다. 판매세 그룹은 특정 채널에 적용되는 세금 그룹입니다. 예를 들어 채널에서 소매 및 B2B를 모두 판매하는 경우 다른 항목 판매세 그룹이 사용될 수 있습니다. 모든 해당 세금은 판매세 그룹에 매핑됩니다.  
    * 이제 "시작" 및 "끝" 세금 또는 "시작 세금 그룹" 및 "끝 세금 그룹"을 선택하여 판매세 재정의를 생성할 수 있습니다. "시작" 필드는 재정의할 세금 또는 세금 그룹을 나타냅니다. 항목 판매세 그룹으로 대체는 판매세 그룹으로 대체와 다른 옵션을 제공합니다. 판매세 재정의는 전체 거래 또는 거래의 특정 행에 대한 세금을 재정의하도록 설정할 수 있습니다.  
13. 저장을 클릭합니다.
14. 페이지를 닫습니다.
15. 소매 및 상업 > 채널 설정 > 판매세 > 판매세 재정의 그룹으로 이동합니다.
    * 이 단계에서는 새로 생성된 판매세 재정의를 휴스턴 채널에 할당된 판매세 재정의 그룹에 할당합니다.  
16. 편집을 클릭합니다.
17. 설정 섹션을 펼치거나 접습니다.
18. 추가를 클릭합니다.
19. 판매세 재정의 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
20. 목록에서 이전에 생성된 판매세 재정의를 선택합니다.
21. 목록에서 선택한 행의 링크를 클릭합니다.
22. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]