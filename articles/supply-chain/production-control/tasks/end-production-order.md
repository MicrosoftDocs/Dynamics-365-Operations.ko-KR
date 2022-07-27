---
title: 생산 주문 종료
description: 이 절차에는 생산 주문을 종료하는 방법을 보여줍니다.
author: johanhoffmann
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bb87a8df77ecced213b4bd61c40fa372b092ab765528e1cd96274cf79537d521
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8447160"
---
# <a name="end-a-production-order"></a>생산 주문 종료

[!include [banner](../../includes/banner.md)]

이 절차에는 생산 주문을 종료하는 방법을 보여줍니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 생산 주문 수명 주기를 설명하는 7가지 중 최종 절차입니다.


## <a name="end-a-production-order"></a>생산 주문 종료
1. 생산 관리 > 생산 주문 > 모든 생산 주문으로 이동합니다.
    * 상태가 완료됨으로 보고된 생산 주문을 선택합니다.  
2. 작업 창에서 생산 주문을 클릭합니다.
3. 종료를 클릭합니다.
    * 이 페이지에서 생산 주문을 종료할 의사가 있음을 확인할 수 있습니다.  
4. 일반 탭을 클릭합니다.
5. 날짜 필드에 날짜를 입력합니다.
6. 스크랩 방법 필드에서 '할당'을 선택합니다.
    * 배부 방식을 선택하면 폐기된 자재의 원가가 완제품에 추가됩니다.  
7. 확인을 클릭합니다.

## <a name="validate-calculation-results"></a>계산 결과 유효성 검사
1. 작업 창에서 비용 관리를 클릭합니다.
2. 비용 비교 보기를 클릭합니다.
    * 생산 주문을 종료한 후 예상 원가를 실현 원가와 비교하여 생산 차이에 대한 개요를 얻을 수 있습니다.  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]