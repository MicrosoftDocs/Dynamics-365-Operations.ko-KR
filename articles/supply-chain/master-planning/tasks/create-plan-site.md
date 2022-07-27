---
title: 사이트에 대한 계획 만들기
description: 생산 계획자는 특정 품목의 생산을 위한 자재 및 능력 요구사항을 계산합니다.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f7da319d4c28af311d79dc01bb93a9fe2f76480
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448126"
---
# <a name="create-a-plan-for-a-site"></a>사이트에 대한 계획 만들기

[!include [banner](../../includes/banner.md)]

생산 계획자는 특정 품목의 생산을 위한 자재 및 능력 요구사항을 계산합니다. 소싱 제안이 생성되면 계획 중인 사이트에서 주문을 찾고 긴급한 것부터 시작하여 주문을 확정합니다. 가장 긴급한 주문은 현재 날짜에 확정되어야 하는 주문입니다. 데모 데이터 회사 USMF를 사용하여 이러한 작업을 수행하세요.


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a>항목에 대한 자재 및 용량 계획 생성
1. 기준 계획을 클릭합니다.
    * 기본 대시보드로 이동해야 합니다.  
2. 실행을 클릭합니다.
3. 포함할 레코드 섹션을 펼칩니다.
4. 필터를 클릭합니다.
5. 목록에서 선택한 행을 표시합니다.
6. 기준 필드에 값을 입력합니다.
    * 예: D0001  
7. 확인을 클릭합니다.
8. 확인을 클릭합니다.
    * 이 작업은 몇 분 정도 걸릴 수 있습니다.  
9. 페이지를 새로 고칩니다.

## <a name="identify-the-urgent-planned-orders-for-the-item"></a>품목에 대한 긴급 계획 주문 식별
1. 품목 번호 열 필터를 엽니다.
2. "다음으로 시작" 필터 연산자를 사용하여 "D0001" 값으로 "품목 번호" 필드에 필터를 적용합니다.
3. 주문 날짜 열 필터를 엽니다.
4. "정확함" 필터 연산자를 사용하여 현자 날짜 값으로 "주문 날짜" 필드에 필터를 적용합니다.

## <a name="firm-all-the-urgent-orders-for-the-item"></a>품목에 대한 긴급 주문 확장
1. 목록에서 모든 행을 표시하거나 표시 해제합니다.
2. 확정을 클릭합니다.
3. 확인을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]