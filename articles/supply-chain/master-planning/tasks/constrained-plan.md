---
title: 제약 있는 계획 생성
description: 이 항목에서는 자재 및 용량 제약을 모두 고려하는 계획을 생성하는 방법에 대해 설명합니다.
author: ChristianRytt
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5fea315d41d01cb578d7d60c9eb7006e4b6c3362
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449101"
---
# <a name="generate-a-constrained-plan"></a>제약 있는 계획 생성

[!include [banner](../../includes/banner.md)]

이 항목에서는 자재 및 용량 제약을 모두 고려하는 계획을 생성하는 방법에 대해 설명합니다. 이 계획은 자재를 사용할 수 있고 리소스가 초과 예약되기 전에 제조가 시작되지 않도록 합니다. 

이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이 절차는 생산 계획자를 위한 것입니다.


## <a name="set-up-a-constrained-plan"></a>제약 있는 계획 설정
1. 홈 페이지에서 **마스터 플래닝** 작업 영역을 선택합니다.
2. 작업 공간의 맨 오른쪽에 있는 링크 목록에서 **마스터 플랜** 을 선택합니다.
3. 목록에서 원하는 레코드를 찾아 선택합니다. 예: **StaticPlan**  
4. **유한 용량** 필드에서 **예** 를 선택합니다.
5. **유한 용량 타임 펜스** 필드에 `30`을 입력합니다.
6. **일 단위 타임 펜스** 섹션을 확장합니다.
7. **용량** 필드에서 **예** 를 선택합니다.
8. **용량 스케줄링 타임 펜스(일)** 필드에 숫자를 입력합니다. 예: `60`  
9. **계산된 지연** 필드에서 **예** 를 선택합니다.
10. **계산된 지연 타임 펜스(일)** 필드에 숫자를 입력합니다. 예: `60` 
11. **계산된 지연** 섹션을 확장합니다.
12. 모든 **요구 날짜에 계산된 지연 추가** 필드에서 **예** 를 선택합니다.
13. 페이지를 닫습니다.

## <a name="create-a-constrained-plan"></a>제약 있는 계획 만들기
1. **실행** 을 선택합니다.
2. **마스터 플랜** 필드에 제약 조건을 설정한 계획을 입력하거나 선택합니다.  
3. **확인** 을 선택합니다.
4. **계획된 주문** 을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]