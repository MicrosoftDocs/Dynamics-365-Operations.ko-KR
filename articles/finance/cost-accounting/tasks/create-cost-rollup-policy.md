---
title: 비용 롤업 정책 만들기
description: 이 절차에서는 비용 롤업 정책을 만들고 정책에 대한 규칙을 만드는 방법을 보여줍니다.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd7a390ced7b7b4997d9c86b9218f1fa83ee14729e450e1ae1cb53dbbd605edb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450583"
---
# <a name="create-a-cost-rollup-policy"></a>비용 롤업 정책 만들기

[!include [banner](../../includes/banner.md)]

이 절차에서는 비용 롤업 정책을 만들고 정책에 대한 규칙을 만드는 방법을 보여줍니다. 이 절차를 만드는 데 사용된 데모 데이터는 USP2입니다.


## <a name="create-a-policy"></a>정책 만들기
1. 원가 회계 > 정책 > 비용 롤업 정책으로 이동합니다.
2. 새로 만들기를 클릭합니다.
3. 정책 이름 필드에 값을 입력합니다.
4. 설명 필드에 값을 입력합니다.
5. 비용 개체 차원 계층 필드에서 값을 입력하거나 선택합니다.
    * 비용 롤업 CC를 선택합니다.  
6. 비용 요소 차원 계층 필드에서 값을 입력하거나 선택합니다.
    * 비용 롤업 CC를 선택합니다.  
7. 저장을 클릭합니다.

## <a name="create-rules-for-the-cost-rollup-policy"></a>비용 롤업 정책에 대한 규칙 만들기
1. 새로 만들기를 클릭합니다.
2. 목록에서 선택한 행을 표시합니다.
3. 비용 개체 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
    * 007을 선택합니다.  
4. 비용 요소 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
    * 비용 롤업 CE를 선택합니다.  
5. 보조 비용 요소 필드에 값을 입력하거나 선택합니다.
    * 이 예에서는 보조 비용 요소 CC-007을 비용 센터에 매핑합니다.  
6. 새로 만들기를 클릭합니다.
7. 목록에서 선택한 행을 표시합니다.
8. 비용 개체 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
    * 008을 선택합니다.  
9. 비용 요소 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
    * 비용 롤업 CE를 선택합니다.  
10. 보조 비용 요소 필드에 값을 입력하거나 선택합니다.
    * 이 예에서는 보조 비용 요소 CC-008을 비용 센터에 매핑합니다.  
11. 새로 만들기를 클릭합니다.
12. 목록에서 선택한 행을 표시합니다.
13. 비용 개체 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
    * 009를 선택합니다.  
14. 비용 요소 차원 계층 노드 필드에서 값을 입력하거나 선택합니다.
    * 비용 롤업 CE를 선택합니다.  
15. 보조 비용 요소 필드에 값을 입력하거나 선택합니다.
    * 이 예에서는 보조 비용 요소 CC-009를 비용 센터에 매핑합니다.  
    * 모든 비용 센터가 해당 보조 비용 요소에 매핑될 때까지 계속합니다.  
16. 저장을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]