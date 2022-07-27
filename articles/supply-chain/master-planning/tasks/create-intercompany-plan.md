---
title: 회사 간 계획 생성
description: 이 절차에서는 내부 거래 계획을 생성하는 방법을 보여줍니다.
author: ChristianRytt
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ef1484e6925427454f819a5effdc911f762b48b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449092"
---
# <a name="create-an-intercompany-plan"></a>회사 간 계획 생성

[!include [banner](../../includes/banner.md)]

이 절차에서는 내부 거래 계획을 생성하는 방법을 보여줍니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.

## <a name="set-up-an-intercompany-planning-group"></a>회사간 계획 그룹 설정

1. **탐색 창** 에서 **모듈 > 기준 계획 > 설정 > 내부 거래 계획 그룹** 으로 이동합니다.
2. 빠른 필터를 사용해 기록을 찾습니다. 예를 들어 값이 '10'인 이름 필드를 필터링합니다.
3. 목록에서 선택한 행을 표시합니다.
4. **삭제** 를 선택합니다. 이 단계는 회사 간 계획 실행을 단축하기 위해 필요합니다.   본지사 계획은 가장 낮은 일정 순서부터 시작하여 계획 그룹의 모든 회사에서 기준 계획을 실행합니다.  
5. **예** 를 선택합니다.
6. 페이지를 닫습니다.

## <a name="create-an-intercompany-master-plan"></a>회사 간 기준 계획 생성

1. **탐색 창** 에서 **모듈 > 기준 계획 > 작업 영역 > 기준 계획** 으로 이동합니다.
2. **회사 간 마스터 플랜** 을 선택합니다.  
3. **회사 간 계획 그룹** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다.
4. 목록에서 선택한 행의 링크를 선택합니다. 회사 간 플랜 그룹 10을 선택합니다.  
5. **본지사 계획 반복 수** 필드에 '2'를 입력합니다. 회사 간 계획 그룹 10에는 2명의 구성원이 있습니다. 원본 회사(USMF)에서 고객 회사(DEMF)로 지연을 전파하려면 두 회사에서 내부 거래를 두 번 실행해야 합니다. 첫 번째 반복은 수요를 전파하고 소스 회사(USMF)의 지연을 식별합니다. 두 번째 반복은 지연을 USMF에서 DEMF로 전파합니다.  
6. **첫 번째 반복** 필드에서 '재생성'을 선택합니다.
7. **이후 반복** 필드에서 '재생성'을 선택합니다.
8. **스레드 수** 필드에 숫자를 입력합니다. 계획에 사용되는 병렬 스레드 수를 나타냅니다.  
9. **확인** 을 선택합니다.

## <a name="view-the-result-of-the-plan"></a>계획 결과 보기

1. **플랜** 필드에서 드롭다운 단추를 선택하여 조회를 엽니다.
2. 목록에서 선택한 행의 링크를 선택합니다. StaticPlan에 대한 링크를 선택합니다. USMF 회사에 있어야 합니다.  
3. **계획된 주문** 을 선택합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]