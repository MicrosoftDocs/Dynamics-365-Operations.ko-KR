---
title: 조달 카탈로그 만들기
description: 이 항목에서는 카탈로그 조달을 만드는 방법을 설명합니다.
author: Henrikan
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProcCategoryHierarchyManagement, CatProcureCatalogListPage, CatProcureCatalogCreate, CatProcureCatalogEdit, SysPolicyListPage, SysPolicy, CatCatalogPolicyRule, PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqAddItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef3747874d43143925bd08dbecc2d60f4e38701a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447820"
---
# <a name="create-a-procurement-catalog"></a>조달 카탈로그 만들기

[!include [banner](../../includes/banner.md)]

이 항목에서는 카탈로그 조달을 만드는 방법을 설명합니다. 이 작업은 일반적으로 조달 전문가가 수행합니다. 또한 직원이 요청을 작성할 때 카탈로그를 사용하는 방법을 배우게 됩니다. 카탈로그를 생성하기 전에 시스템에 조달 범주 계층이 있어야 합니다. 계층 구조는 계층 구조에 있는 모든 제품과 함께 새 카탈로그에 의해 상속됩니다. 이 가이드는 조달 범주 계층 구조가 제공되는 데모 데이터 회사 USMF와 절차 단계에 사용된 예에서 사용할 수 있습니다.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>조달 범주 계층이 존재하는지 확인
1. **탐색 창 > 모듈 > 조달 및 소싱 > 조달 범주** 로 이동합니다. USMF 데모 데이터 회사에서 조달 범주 계층을 사용할 수 있으며 제품이 **사무기기/컴퓨터** 범주에 추가되었습니다. 범주를 둘러보려는 경우 노드를 선택하기 위해 작업 가이드의 잠금을 해제해야 할 수 있습니다. 계층 구조를 사용할 수 없는 경우 **새로 만들기** 를 클릭하여 생성합니다. 이 작업은 한 번만 수행할 수 있습니다.  
2. 페이지를 닫습니다.

## <a name="create-a-catalog"></a>카탈로그 생성
1. **탐색 창 > 모듈 > 조달 및 소싱 > 카탈로그 > 카탈로그 조달** 로 이동합니다.
2. **새로운 조달 카탈로그** 를 선택하여 드롭 대화 상자를 엽니다.
3. **이름** 필드에 값을 입력합니다.
4. **확인** 을 선택합니다.
5. 트리에서 **기업 조달 카테고리** 를 확장합니다.
6. 트리에서 **사무용 기계** 를 확장합니다.
7. 트리에서 **컴퓨터** 를 선택합니다.

  - 조달 카테고리의 제품이 목록에 표시됩니다. 카테고리에 제품을 추가하려면 **조달 카테고리 계층** 페이지 또는 **항목 세부 정보** 페이지에서 이 작업을 수행해야 합니다.  
  - **기본** 업데이트 유형은 조달 범주 계층 구조에 추가된 새 제품이 카탈로그에 즉시 표시되는지 여부를 결정합니다. 업데이트 유형이 **동적** 으로 설정되면 변경 사항이 즉시 표시됩니다. 업데이트 유형이 **정적** 이면 새 제품은 카탈로그가 다시 게시된 후에 카탈로그를 사용하는 사람들에게만 표시됩니다. **게시** 작업은 페이지 상단의 작업 창에서 사용할 수 있습니다. 제품이 조달 범주 계층 구조에서 제거되면 **기본** 업데이트 유형 필드의 값에 상관없이 변경 사항이 즉시 표시됩니다.  

8. 작업 창에서 **카테고리 탐색** 을 선택하고 **사용** 이 선택되어 있는지 확인합니다.
9. **카탈로그 활성화** 를 선택합니다.
10. 페이지를 닫습니다.

## <a name="make-the-catalog-visible"></a>카탈로그 표시
1. **탐색 창 > 모듈 > 조달 및 소싱 > 설정 > 정책 > 구매 정책** 으로 이동합니다.
2. **조달 정책 USMF** 를 선택합니다. 사용자 프로필에 연결된 작업자가 제품을 주문할 수 있는 법인에 대한 구매 정책을 선택해야 합니다. USMF 데모 데이터에서 관리 사용자 **Julia Funderburk** 라는 작업자에 연결되며, 그녀는 기본적으로 USMF에서 제품을 주문합니다.  
3. 방금 생성한 카탈로그를 선택합니다.
4. **확인** 을 선택합니다.

## <a name="use-the-catalog"></a>카탈로그 사용
1. **탐색 창 > 모듈 > 조달 및 소싱 > 구매 요청 > 모든 구매 요청** 으로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **이름** 필드에 값을 입력합니다.
4. **확인** 을 선택합니다.
5. **제품 추가** 를 선택합니다.
6. 목록에서 원하는 레코드를 찾아 선택합니다. 왼쪽의 카테고리 계층 구조 또는 목록 상단의 필터를 사용하여 제품을 필터링할 수 있습니다.  
7. **라인에 추가** 를 선택합니다.
8. **확인** 을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]