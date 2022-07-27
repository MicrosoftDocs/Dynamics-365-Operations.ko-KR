---
title: 비용 할당 정책을 만들고 비용 제어 장치에 할당
description: 이 절차를 사용하여 비용 할당 정책 및 해당 규칙을 생성하고 비용 제어 장치에 할당합니다.
author: ShylaThompson
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: de50191a7be30364236ee82b99d207e6f131cce26097a39728fea25e3ef7df9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450142"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>비용 할당 정책을 만들고 비용 제어 장치에 할당

[!include [banner](../../includes/banner.md)]

이 절차를 사용하여 비용 할당 정책 및 해당 규칙을 생성하고 비용 제어 장치에 할당합니다. 이 레코딩은 USP2 데모 데이터 회사를 사용합니다.


## <a name="create-a-policy"></a>정책 만들기
1. 원가 회계 > 정책 > 비용 할당 정책으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 정책 이름 필드에 값을 입력합니다.
4. 비용 개체 차원 계층 필드에서 값을 입력하거나 선택합니다.
    * 조직을 선택합니다.  
5. 통계 차원 필드에서 값을 입력하거나 선택합니다.
6. 저장을 클릭합니다.

## <a name="create-allocation-rules"></a>할당 규칙 만들기
1. 새로 만들기를 클릭합니다.
2. 목록에서 선택한 행을 표시합니다.
3. 비용 개체 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
4. 비용 행동 필드에서 '합계'를 선택합니다.
5. 할당 기준 필드에 값을 입력하거나 선택합니다.
6. 새로 만들기를 클릭합니다.
7. 목록에서 선택한 행을 표시합니다.
8. 비용 개체 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
9. 비용 행동 필드에서 '합계'를 선택합니다.
10. 할당 기준 필드에 값을 입력하거나 선택합니다.
11. 새로 만들기를 클릭합니다.
12. 목록에서 선택한 행을 표시합니다.
13. 비용 개체 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
14. 비용 행동 필드에서 '합계'를 선택합니다.
15. 할당 기준 필드에 값을 입력하거나 선택합니다.
    * 모든 규칙을 만들 때까지 계속합니다.  
16. 저장을 클릭합니다.

## <a name="assign-the-policy-to-a-cost-control-unit"></a>비용 제어 장치에 정책 할당
1. 비용 제어 장치에 대한 정책 할당을 클릭합니다.
2. 새로 만들기를 클릭합니다.
3. 목록에서 선택한 행을 표시합니다.
4. 회계 적용 날짜 필드에 날짜를 입력합니다.
    * 규칙은 날짜부터 유효합니다. 새 버전이 생성되면 사용자 또는 시스템이 규칙을 만료시킬 수 있습니다.  
5. 비용 제어 장치 필드에 값을 입력하거나 선택합니다.
6. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]