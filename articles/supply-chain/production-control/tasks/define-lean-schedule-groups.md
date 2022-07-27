---
title: 린 스케줄 그룹 정의
description: 린 스케줄 그룹은 칸반 스케줄링에서 제품을 그룹화하고 구별하기 위해 정의됩니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9d16c0d3192773c32c8dcc57a430607c6b60f97
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448723"
---
# <a name="define-lean-schedule-groups"></a>린 스케줄 그룹 정의

[!include [banner](../../includes/banner.md)]

린 스케줄 그룹은 칸반 스케줄링에서 제품을 그룹화하고 구별하기 위해 정의됩니다. 그룹화는 회사당 일반 연결로 수행하거나 작업 셀에 따라 수행할 수 있습니다. 각 그룹에는 칸반 일정 목록 페이지에서 시각적 표시를 위해 할당된 색상 코드가 있습니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다.


## <a name="define-lean-scheduling-group"></a>린 스케줄 그룹 정의
1. 제품 정보 관리 > 린 제조 > 린 스케줄 그룹으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 스케줄 그룹 필드에 값을 입력합니다.
    * 스케줄 그룹은 전역 그룹으로 정의하거나 작업 셀에 특정할 수 있습니다. 이 간단한 예에서는 전역 그룹을 정의하고 작업 셀은 비어 있습니다. 이 그룹의 설정은 특정 스케줄 그룹이 없는 모든 작업 셀에 적용됩니다.  
4. 색상 선택에서 색상을 선택합니다.
    * 색상은 칸반 스케줄 목록 페이지 또는 칸반 프로세스 보드에서 작업을 강조 표시하는 데 사용됩니다.  
5. 목록에서 선택한 행을 표시합니다.
6. 목록에서 선택한 행의 링크를 클릭합니다.

## <a name="associate-product"></a>제품 연결
1. 특정 제품 연결
    * 특정 제품(항목 관계 유형 = 항목) 또는 항목 할당 키(항목 관계 유형 = 그룹)의 일부로 제품을 린 스케줄 그룹에 연결하는 두 가지 방법이 있습니다.    
2. 항목 관계 유형 필드에서 항목을 선택합니다.
3. 품목 번호 필드에 값을 입력합니다.
4. 처리량 비율 필드에 숫자를 입력합니다.
    * 기본 처리량 비율은 1이며, 이는 관련 제품이 생산 흐름의 프로세스 활동에 지정된 용량을 정확히 소비한다는 것을 의미합니다. 처리량 비율 > 1은 더 높은 리소스 소비를 정의하고, 처리량 비율 < 1은 더 낮은 리소스 소비를 정의합니다. 이 비율은 비용 계산 및 칸반 작업 소비 계산에 사용됩니다.  

## <a name="associate-item-allocation-key"></a>항목 할당 키 연결
1. 단일 항목 할당 키 연결
    * 항목 관계 유형 그룹을 사용하여 항목 할당 키에 연결을 추가합니다.   이 프로세스의 경우 데이터에 정의된 예측 항목 할당 키가 필요합니다.  
2. 항목 관계 유형 필드에서 그룹을 선택합니다.
3. 항목 할당 필드에서 드롭다운 단추를 클릭하여 조회를 엽니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]