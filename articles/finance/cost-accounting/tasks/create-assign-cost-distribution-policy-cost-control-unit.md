---
title: 비용 분배 정책을 만들고 비용 제어 장치에 할당
description: 비용 분배 규칙은 집합 비용 센터에서 재정적으로 계산된 비용을 분배하는 데 사용됩니다.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostDistributionRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9230410d7b8cd4c94fdab5465e542e16fd286c530a8189d5cd1eca825bb1faf4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450793"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>비용 분배 정책을 만들고 비용 제어 장치에 할당

[!include [banner](../../includes/banner.md)]

비용 분배 규칙은 집합 비용 센터에서 재정적으로 계산된 비용을 분배하는 데 사용됩니다. 원가 회계사는 선택한 할당 기준에 따라 비용을 비용 센터에 분배합니다. 정책 및 해당 규칙은 비용 제어 장치에 할당됩니다. 이 작업 가이드는 비용 분배 정책 및 해당 규칙을 생성하는 방법을 보여주기 위해 예를 사용합니다.


## <a name="create-a-policy"></a>정책 만들기
1. 원가 회계 > 정책 > 비용 분배 정책으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 정책 이름 필드에 값을 입력합니다.
4. 설명 필드에 값을 입력합니다.
5. 비용 개체 차원 계층 필드에서 값을 입력하거나 선택합니다.
    * 조직을 선택합니다.  
6. 비용 요소 차원 계층 필드에서 값을 입력하거나 선택합니다.
    * CDS P/L을 선택합니다.  
7. 통계 차원 필드에서 값을 입력하거나 선택합니다.
    * 통계 요소를 선택합니다.  
8. 저장을 클릭합니다.

## <a name="create-rules-for-the-policy"></a>정책에 대한 규칙 만들기
1. 새로 만들기를 클릭합니다.
2. 목록에서 선택한 행을 표시합니다.
3. 비용 개체 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
    * 계층을 확장하여 094를 선택합니다.  
4. 비용 요소 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
    * 기타 운영 비용을 선택한 다음 605110 클리닝을 선택합니다.  
5. 비용 행동 필드에서 옵션을 선택합니다.
    * 고정 비용을 선택합니다.  
6. 할당 기준 필드에 값을 입력하거나 선택합니다.
7. 새로 만들기를 클릭합니다.
8. 목록에서 선택한 행을 표시합니다.
9. 비용 개체 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
    * 계층을 확장하여 094를 선택합니다.  
10. 비용 요소 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
    * 기타 운영 비용을 선택한 다음 605150 임대료를 선택합니다.  
11. 비용 행동 필드에서 옵션을 선택합니다.
    * 고정 비용을 선택합니다.  
12. 할당 기준 필드에 값을 입력하거나 선택합니다.
13. 저장을 클릭합니다.

## <a name="assign-rules-to-a-cost-control-unit"></a>비용 제어 장치에 규칙 할당
1. 비용 제어 장치에 대한 정책 할당을 클릭합니다.
2. 새로 만들기를 클릭합니다.
3. 목록에서 선택한 행을 표시합니다.
4. 회계 적용 날짜 필드에 날짜를 입력합니다.
    * 유효한 회계 연도의 9월 1일을 선택합니다.  
5. 비용 제어 장치 필드에 값을 입력하거나 선택합니다.
6. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]