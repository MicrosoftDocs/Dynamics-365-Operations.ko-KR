---
title: 창고의 재고 수준 조정(기본 창고)
description: 이 절차는 창고에 있는 제품의 재고 수준을 조정하기 위해 재고 조정 분개를 만들고 전기하는 프로세스를 안내합니다.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 02458d588c9925a1f4cb9afeada793dfc55a2071
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448660"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a>창고의 재고 수준 조정(기본 창고)

[!include [banner](../../includes/banner.md)]

이 절차는 창고에 있는 제품의 재고 수준을 조정하기 위해 재고 조정 분개를 만들고 전기하는 프로세스를 안내합니다. 이 작업을 시작하기 전에 재고 조정을 위해 재고 저널 이름을 설정해야 합니다. 데모 데이터 회사 USMF에서 이 절차를 수행하거나 자신의 데이터를 사용할 수 있습니다. 이러한 작업은 일반적으로 창고 직원이 수행합니다.


## <a name="create-an-inventory-adjustment-journal"></a>재고 조정 분개 생성
1. 재고 관리 > 분개 > 항목 > 재고 조정으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
4. 목록에서 사용하려는 재고 조정 분개 이름을 클릭합니다.
    * 일부 다른 필드는 선택한 재고 조정 분개 이름 설정에 따라 채워집니다.  
5. 확인을 클릭합니다.

## <a name="create-journal-lines"></a>분개 라인 생성
1. 새로 만들기를 클릭합니다.
2. 목록에서 품목 번호 필드를 표시합니다.
3. 품목 번호 필드에서 항목을 선택합니다. 데모 데이터 회사 USMF를 사용하는 경우 'D0001'을 입력합니다.
4. 사이트 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
5. 목록에서 사이트를 선택합니다.
6. 창고 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
7. 목록에서 창고를 선택합니다.
    * 위치가 필수 차원인 항목을 선택한 경우 여기에 위치를 지정해야 합니다.  
8. 수량 필드에 숫자를 입력합니다.
    * 비용 가격 필드는 재고 입고의 단위당 비용을 지정합니다. 품목 번호에 대한 비용이 지정되지 않았거나 수동으로 변경하려는 경우 여기에서 수행합니다.  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a>재고 조정 분개 검증 및 전기
1. 유효성 검사를 클릭합니다.
2. 확인을 클릭합니다.
3. 게시를 클릭합니다.
    * 이러한 종류의 분개를 전기하면 재고 입고 또는 출고가 전기되고 재고 수준과 값이 변경되며 원장 트랜잭션이 생성됩니다.  
4. 확인을 클릭합니다.
5. 양식을 닫습니다.
6. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]