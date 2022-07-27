---
title: 창고의 재고 수준 초기화
description: 이 절차에서는 재고 이동 분개장을 사용하여 수동으로 현재고를 업데이트하는 방법을 보여줍니다.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalMovement, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 264dabf9c1c10c3d2cee3e0c942abbfa249f21f5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447865"
---
# <a name="initialize-stock-levels-in-the-warehouse"></a>창고의 재고 수준 초기화

[!include [banner](../../includes/banner.md)]

이 절차에서는 재고 이동 분개장을 사용하여 수동으로 현재고를 업데이트하는 방법을 보여줍니다. (데이터 엔터티의 트랜잭션을 가져와서 현재고를 업데이트하는 것도 가능합니다.) 분개장 이름, 항목 설정, 전기 프로필 및 계정과 같은 모든 전제 조건을 사용할 수 있는 데모 데이터 회사 USMF에서 이 가이드를 실행할 수 있습니다. 이 가이드는 사용되는 항목 및 치수에 대한 특정 값을 제안합니다. 다른 항목을 선택하는 경우 다른 치수에 대한 값을 입력해야 할 수 있습니다.

1. 재고 관리 > 분개 > 항목 > 이동으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
4. IMov. 선택
    * 비즈니스 목적에 따라 다른 분개장 이름 템플릿을 사용하는 것이 좋습니다.  
5. 목록에서 선택한 행의 링크를 클릭합니다.
6. 상쇄 계정에서 원하는 값인 '140200'을 지정합니다.
    * 이것은 분개장 라인의 기본 계정이 될 상계 계정입니다. 라인마다 다른 상쇄 계정을 할당하도록 기본값을 무시할 수 있습니다.  
7. 확인을 클릭합니다.
8. 새로 만들기를 클릭합니다.
9. 품목 번호 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
10. 항목 A0001을 선택합니다.
11. 목록에서 선택한 행의 링크를 클릭합니다.
12. 재고 차원 탭을 클릭합니다.
13. 사이트 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
14. 사이트 1을 선택합니다.
15. 창고 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
16. 창고 13을 선택합니다.
17. 목록에서 선택한 행의 링크를 클릭합니다.
18. 위치 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
19. 위치 13을 선택합니다.
20. 수량 필드에 숫자를 입력합니다.
21. 저장을 클릭합니다.
22. 전기를 클릭합니다.
23. 모든 전기 오류를 새 분개장으로 이전 확인란을 선택하거나 선택 취소합니다.
    * 이 옵션을 사용하면 전기에 실패한 모든 라인이 새 분개장에 복사됩니다. 로그의 정보를 사용하여 문제를 수정한 다음 라인을 다시 게시할 수 있습니다.  
24. 확인을 클릭합니다.
25. 페이지를 닫습니다.
26. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]