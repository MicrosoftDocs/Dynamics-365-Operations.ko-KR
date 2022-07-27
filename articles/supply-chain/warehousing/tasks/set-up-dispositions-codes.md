---
title: 처분 코드 설정
description: 이 절차는 반품 주문 수신 프로세스를 위해 모바일 디바이스에서 사용할 수 있는 처리 코드 설정에 중점을 둡니다.
author: Mirzaab
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSDispositionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb83108c934e864da0df39ec4ee36a0bc7ba7588
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448687"
---
# <a name="set-up-dispositions-codes"></a>처분 코드 설정

[!include [banner](../../includes/banner.md)]

이 절차는 반품 주문 수신 프로세스를 위해 모바일 디바이스에서 사용할 수 있는 처리 코드 설정에 중점을 둡니다. 처분 코드는 항목을 받을 때 사용할 수 있는 규칙 모음입니다. 예를 들어, 직장 사용자가 모바일 디바이스를 사용하여 손상된 항목을 수신하는 경우 사용자는 손상된 항목에 대한 처분 코드를 스캔해야 합니다. 입고된 상품의 재고 상태, 작업 템플릿, 위치 지시 등을 스캔한 처분 코드에서 확인할 수 있습니다. 구매 주문 입고 프로세스 및 완료 프로세스로 생산 주문 보고의 경우 처분 코드 사용은 선택 사항입니다. 판매 주문 반품 접수 과정에서 모바일로 상품을 등록하는 경우 처분 코드 사용은 필수입니다.  이 가이드는 데모 데이터 회사 USMF를 사용하여 작성되었습니다. 이 절차는 창고 관리자를 위한 것입니다. 

1. 창고 관리 > 설정 > 모바일 디바이스 > 폐기 코드로 이동합니다.
2. 새로 만들기를 클릭합니다.
    * 고객 반품에 사용할 새 처리 코드를 만듭니다.  
3. 처분 코드 필드에 값을 입력합니다.
4. 인벤토리 상태 필드에서 인벤토리 차단이 있는 인벤토리 상태를 선택합니다.
    * USMF를 사용하는 경우 '차단'을 선택할 수 있습니다. 처분 코드에 인벤토리 상태를 추가하여 주문 라인에 있는 기본 상태를 재정의할 수 있습니다.  
5. 작업 템플릿 필드에 값을 입력합니다.
    * 선택 사항: 반품 주문과 연결된 작업 템플릿 코드를 선택합니다. 값이 제공되지 않으면 시스템에 구성된 표준 규칙을 사용하여 작업 템플릿이 해결됩니다. 작업 템플릿을 선택하면 이 처리 코드를 사용할 수 있는 프로세스가 제한됩니다. 예를 들어 처분 코드에 구매 주문 유형의 작업 주문이 있는 작업 템플릿이 있는 경우 고객이 반환한 항목을 등록하는 데 사용할 수 없습니다.  
6. 반품 처분 코드 필드에 값을 입력합니다.
    * 반품 처리 코드는 등록된 항목에 대한 반품 주문 프로세스의 나머지 부분을 결정합니다. 이 예에서 고객은 크레딧 노트를 받아야 합니다. 작업 크레딧이 포함된 반품 처리 코드를 추가합니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]