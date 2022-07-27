---
title: 정확한 재고 추적 정보
description: 이 절차는 재고 추적 정보를 수정하기 위해 재고 이전 분개를 만들고 전기하는 프로세스를 안내합니다.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69921651ecd0969e9cdd3cdd3740db212a1953e1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448657"
---
# <a name="correct-inventory-tracking-information"></a>정확한 재고 추적 정보

[!include [banner](../../includes/banner.md)]

이 절차는 재고 추적 정보를 수정하기 위해 재고 이전 분개를 만들고 전기하는 프로세스를 안내합니다. 이 예에서는 잘못 등록된 배치를 다른 배치로 변경하여 배치 제어 항목의 정보를 업데이트합니다. 데모 데이터 회사 USPI에서 이 절차를 수행하거나 자신의 데이터를 사용할 수 있습니다. 자체 데이터를 사용하는 경우 일괄 처리가 가능한 항목이 있어야 하며 위치 제어가 되지 않아야 합니다. 또한 재고 이전을 위해 재고 저널 이름을 설정해야 합니다. 이러한 작업은 일반적으로 창고 직원이 수행합니다.


## <a name="create-an-inventory-transfer-journal"></a>재고 이전 분개장 생성
1. 전송으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 이름 필드에 값을 입력하거나 선택합니다.
4. 확인을 클릭합니다.

## <a name="create-journal-lines"></a>분개 라인 생성
1. 새로 만들기를 클릭합니다.
2. 품목 번호 필드에서 값을 입력하거나 선택합니다.
    * USPI를 사용하는 경우 항목 M5003을 선택합니다.  
3. 수량 필드에 숫자를 입력합니다.
4. 재고 차원 탭을 클릭합니다.
5. 일괄 번호 필드에서 값을 입력하거나 선택합니다.
6. 사이트 필드에 값을 입력하거나 선택합니다.
7. 창고 필드 필드에 값을 입력하거나 선택합니다.
8. 일괄 번호 필드에서 값을 입력하거나 선택합니다.

## <a name="post-the-journal"></a>분개 전기
1. 전기를 클릭합니다.
2. 확인을 클릭합니다.

## <a name="check-tracing-information"></a>추적 정보 확인
1. 인벤토리를 클릭합니다.
2. 추적을 클릭합니다.
3. 확인을 클릭합니다.
    * 이 추적 정보를 사용하여 재고를 수정한 배치를 역추적할 수 있습니다.  항목 추적 페이지를 사용하여 이 정보를 볼 수도 있습니다.  
4. 페이지를 닫습니다.

## <a name="check-inventory-transactions"></a>재고 이전 확인
1. 인벤토리를 클릭합니다.
2. 거래를 클릭합니다.
    * 여기에서 분개장을 게시할 때 생성된 거래를 볼 수 있습니다.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]