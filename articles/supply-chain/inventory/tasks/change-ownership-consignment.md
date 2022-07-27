---
title: 생산 수요에 따른 위탁재고 소유권 변경
description: 이 절차는 생산 재고에 대한 수요가 있을 때 위탁 재고 소유자를 공급업체에서 법인으로 변경하는 방법을 보여줍니다.
author: yufeihuang
ms.date: 08/14/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalOwnershipChange, InventJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e735a9003f2859ed173f399525297506ec458e8d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447862"
---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a>생산 수요에 따른 위탁재고 소유권 변경

[!include [banner](../../includes/banner.md)]

이 절차는 생산 재고에 대한 수요가 있을 때 위탁 재고 소유자를 공급업체에서 법인으로 변경하는 방법을 보여줍니다. 이 소유권 변경은 재고 소유권 변경 분개를 생성하고 게시하여 수행됩니다. 소유권 변경 분개 라인은 수동으로 생성하거나 이 기록에 표시된 대로 기존 생산 수요를 기반으로 생성할 수 있습니다. 일반적으로 작업 현장 감독자가 이 작업을 수행합니다. 데모 데이터 회사 USMF 또는 자체 데이터에서 이 절차를 사용할 수 있습니다. 자체 데이터를 사용하는 경우 다음 전제 조건이 있는지 확인합니다. 재고 소유권 변경을 위해 설정된 재고 분개 이름, 물리적으로 기록된 공급업체 소유 현재고 품목 및 재료. 이 절차는 Dynamics 365 for Operations 버전 1611에 추가된 기능에 대한 것입니다.

> [!NOTE]
> 아웃바운드 위탁 프로세스는 즉시 지원되지 않으며 자동 소유권 분개 처리는 지원되지 않습니다.

## <a name="create-an-inventory-ownership-journal"></a>재고 소유권 분개 생성
1. 재고 관리 > 분개 > 항목 > 재고 소유권 변경으로 이동합니다.
2. 새로 만들기를 클릭합니다.
    * 재고 소유권 변경 분개는 위탁 재고 소유자를 공급업체에서 현재 법인으로 변경하는 데 사용됩니다. 이러한 소유권 변경은 공급업체가 소유한 보유 재고를 해제한 다음 현재 법인에서 해당 재고를 수신하여 수행됩니다.  
3. 이름 필드에 값을 입력하거나 선택합니다.
    * 분개장 유형이 소유권 변경인 인벤토리 분개장 이름만 선택할 수 있습니다.  
4. 확인을 클릭합니다.
5. 기능을 클릭합니다.
6. 생산 주문에서 분개 라인 생성을 누릅니다.
    * 원자재 소비에 대한 수요가 있는 모든 생산 라인을 조회하여 소유권 변경 프로세스를 시작할 수 있습니다.  
7. 포함할 인벤토리 문제 상태 필드에서 옵션을 선택합니다.
    * 이 옵션을 사용하면 재고 트랜잭션의 발행 상태를 기준으로 필터링할 수 있습니다. 예를 들어, 물리적 상태가 선택됨 및 예약됨인 재고에 대한 분개 라인을 생성할 수 있습니다.  
8. 포함할 레코드 섹션을 펼칩니다.
    * 이 섹션에서는 추가 필터링을 적용할 수 있습니다. 예를 들어 특정 원자재 날짜를 선택할 수 있습니다.  
9. 확인을 클릭합니다.

## <a name="post-the-inventory-ownership-change-journal"></a>재고 소유권 변경 분개 게시
1. 게시를 클릭합니다.
    * 저널이 게시되면 "소유권 변경" 참조를 사용하여 공급업체 소유 인벤토리가 해제됩니다. 그런 다음 구매 주문 제품 영수증으로 업데이트되는 재고 트랜잭션을 사용하여 재고가 현재고로 입고됩니다. 게시된 분개와 관련된 트랜잭션만 생성됩니다. 예상 재고 트랜잭션이 생성되지 않습니다.  
2. 확인을 클릭합니다.
3. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]