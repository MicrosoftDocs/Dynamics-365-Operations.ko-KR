---
title: 조달 범주 계층 설정
description: 이 절차에서는 조달 범주 계층 구조에서 새 노드를 만드는 방법과 조달 프로세스에서 사용할 조달 범주를 구성하는 방법을 보여줍니다.
author: Henrikan
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a625ae5acc6d47b40a31b986da25df8f2d3fdbc8
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448969"
---
# <a name="set-up-a-procurement-category-hierarchy"></a>조달 범주 계층 설정

[!include [banner](../../includes/banner.md)]

이 절차에서는 조달 범주 계층 구조에서 새 노드를 만드는 방법과 조달 프로세스에서 사용할 조달 범주를 구성하는 방법을 보여줍니다. 이러한 작업은 일반적으로 구매 관리자가 수행합니다. 이 절차를 시작하려면 먼저 조달 유형의 범주 계층이 있어야 합니다. 데모 데이터 회사를 사용하는 경우 USMF 회사에서 이 절차를 실행할 수 있습니다.


## <a name="add-a-new-procurement-category"></a>새 조달 범주 추가
1. **탐색 창 > 모듈 > 조달 및 소싱 > 위탁 > 조달 범주** 로 이동합니다.
2. 작업 창에서 **범주 계층 편집** 를 선택합니다. 현재 조달 범주 계층이 페이지 왼쪽에 표시됩니다. 계층을 수정하려고 합니다.  
3. 작업 창에서 **새 범주 노드** 를 선택합니다. 시스템은 기본적으로 최상위 노드를 선택합니다. 이 절차를 작업 가이드로 실행하는 경우 잠금 해제 단추를 클릭하고 새 노드를 삽입할 다른 상위 노드를 선택할 수 있습니다. 완료되면 작업 가이드를 다시 잠그고 새 범주 노드를 클릭합니다.  
4. **이름** 필드에 값을 입력합니다.
5. **설명** 필드에 값을 입력합니다.
6. **식별 이름** 필드에 값을 입력합니다. 식별 이름은 선택 사항입니다. 식별 이름은 범주 이름과 함께 범주 조회에 표시됩니다.  
7. **저장** 을 선택합니다.

## <a name="add-products-to-your-new-procurement-category"></a>새 조달 범주에 제품 추가
1. **조달 및 소싱 > 위탁 > 조달 범주** 로 이동합니다. 방금 추가한 노드를 선택합니다. 이 절차를 작업 가이드로 실행하는 경우 노드를 선택하기 위해 작업 가이드의 잠금을 해제해야 할 수 있습니다.  
2. **상품** 섹션의 확장을 토글합니다.
3. **추가** 를 선택하여 제품을 조달 범주와 연결합니다.
4. 구매 범주에 추가할 제품을 선택합니다.
5. 화살표를 선택하여 제품을 **선택됨** 테이블에 추가합니다.
6. **확인** 을 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]