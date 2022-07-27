---
title: 더 이상 사용되지 않는 제품 변형 찾기
description: 이 절차에서는 사용되지 않는 출시 제품 또는 제품 변형을 찾는 방법과 제품 수명 주기 상태를 사용되지 않는 제품에 연결하는 방법을 보여줍니다.
author: t-benebo
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 13db6620575b4c97b3f8079ac94f5231a2fd9c1b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448990"
---
# <a name="find-obsolete-product-variants"></a>더 이상 사용되지 않는 제품 변형 찾기 

[!include [banner](../../includes/banner.md)]

이 절차에서는 사용되지 않는 출시 제품 또는 제품 변형을 찾는 방법과 제품 수명 주기 상태를 사용되지 않는 제품에 연결하는 방법을 보여줍니다. 전제 조건: 이 작업 가이드를 재생하기 전에 계획을 위해 비활성화된 제품 수명 주기 상태를 하나 이상 정의해야 합니다.


## <a name="run-a-simulation"></a>시뮬레이션 실행
1. 제품 정보 관리 > 정기 작업 > 단종 제품의 수명 주기 상태 변경으로 이동합니다.
2. 새 제품 수명 주기 상태 필드에서 값을 입력하거나 선택합니다.
3. 제품 데이터를 업데이트하지 않고 시뮬레이션 실행 필드에서 예를 선택합니다.
4. 이 기간 내에 생성된 제품 제외 필드에 숫자를 입력합니다.
5. 거래에 사용된 제품 제외(일수) 필드에 숫자를 입력합니다.
6. 포함할 레코드 섹션을 펼칩니다.
7. 필터를 클릭합니다.
8. 목록에서 선택한 행을 표시합니다.
9. 기준 필드에 값을 입력합니다.
10. 확인을 클릭합니다.
11. 확인을 클릭합니다.

> [!NOTE]
> 많은 수의 제품을 검색할 것으로 예상되는 경우 시뮬레이션을 일괄적으로 실행하는 것이 좋습니다. 또한 회사에서 가장 활동적인 근무 시간에는 시뮬레이션이 실행되지 않도록 하세요.  

## <a name="review-the-simulation-results"></a>시뮬레이션 결과 검토
1. 제품 정보 관리 > 문의 및 보고 > 제품 수명 주기 상태 유지 관리 기록으로 이동합니다.
   
> [!NOTE]
> 이 페이지에서 시뮬레이션 결과를 검토하고 시뮬레이션 없이 업데이트를 실행할 때 얼마나 많은 제품 및 제품 변형이 새 제품 수명 주기 상태와 연관되는지 평가할 수 있습니다.  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a>더 이상 사용되지 않는 제품에 대한 제품 수명 주기 상태 업데이트 실행
1. 페이지를 닫습니다.
2. 제품 정보 관리 > 정기 작업 > 단종 제품의 수명 주기 상태 변경으로 이동합니다.
3. 포함할 레코드 섹션을 펼칩니다.

> [!NOTE]
> 마지막 선택이 저장되었습니다.  

4. 제품 데이터를 업데이트하지 않고 시뮬레이션 실행 필드에서 아니요를 선택합니다.
5. 백그라운드에서 실행 섹션을 확장합니다.

> [!NOTE]
> 영향을 받는 제품 및 제품 변형 수에 따라 이 작업을 일괄적으로 실행하는 것이 좋습니다. 회사에서 가장 활동적인 근무 시간 동안 대규모 업데이트 작업을 실행하고 있지 않은지 확인하세요.  

6. 확인을 클릭합니다.
7. 제품 정보 관리 > 문의 및 보고 > 제품 수명 주기 상태 유지 관리 기록으로 이동합니다.

> [!NOTE]
> 변경된 출시 제품 및 제품 변형을 검토합니다.  

8. 목록에서 원하는 레코드를 찾아 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]