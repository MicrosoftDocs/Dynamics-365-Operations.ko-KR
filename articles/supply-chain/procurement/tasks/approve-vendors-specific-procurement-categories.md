---
title: 특정 조달 범주에 대한 공급업체 승인
description: 이 항목에서는 특정 Dynamics 365 Supply Chain Management의 조달 범주에 대한 공급업체를 승인하는 방법에 대해 설명합니다.
author: Henrikan
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1a885ba924137c56583db9f81b34db9a20f33bc4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448210"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a>특정 조달 범주에 대한 공급업체 승인

[!include [banner](../../includes/banner.md)]

이 항목에서는 특정 Dynamics 365 Supply Chain Management의 조달 범주에 대한 공급업체를 승인하는 방법에 대해 설명합니다. 구매 요청이 생성되면 구매 정책 설정 방식에 따라 승인된 공급업체 또는 선호하는 공급업체를 선택해야 할 수 있습니다. 이 절차에서는 공급업체가 특정 조달 범주에 대해 승인되거나 선호되도록 지정하는 방법을 보여줍니다. 이 작업은 일반적으로 조달 전문가가 수행합니다. 데모 데이터 회사 USMF에서 이 절차를 사용할 수 있습니다.

1. 탐색 창에서 **모듈 > 조달 및 소싱 > 공급업체 > 모든 공급업체** 로 이동합니다.
2. 범주에 대해 승인되거나 선호되는 공급업체로 설정할 공급업체를 선택합니다.
3. 작업 창에서 **일반** 을 선택합니다.
4. **범주** 를 선택합니다.
5. **범주 추가** 를 선택합니다.
6. **범주** 필드에서 **사무실 및 책상 액세서리(사무실 및 책상 액세서리)** 를 선택합니다.
7. **공급업체 범주 상태** 필드에서 **기본** 을 선택합니다. 범주에 대해 둘 이상의 기본 공급업체를 지정할 수 있습니다.  
8. **저장** 을 선택합니다.
9. 탐색 창에서 **모듈 > 조달 및 소싱 > 조달 범주** 로 이동합니다.
10. 트리에서 **기업 조달 카테고리\사무실 및 책상 액세서리** 를 선택합니다.
11. **공급업체** 섹션을 펼칩니다. 선택한 공급업체가 사무실 및 책상 액세서리 카테고리에 대한 선호 공급업체로 나타나는지 확인합니다. 이 절차를 작업 가이드로 실행하는 경우 **잠금 해제** 버튼을 선택하여 공급업체 목록까지 아래로 스크롤해야 할 수도 있습니다.  이 페이지에서 선호 및 승인된 공급업체를 추가할 수도 있습니다.  
12. 트리에서 **사무실 및 책상 액세서리** 를 펼치고 **가위** 를 선택합니다.
13. **상위 범주의 상속 공급업체:** 필드에서 **아니요** 를 선택합니다.
14. **상위 범주의 상속 공급업체:** 필드에서 **예** 를 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]