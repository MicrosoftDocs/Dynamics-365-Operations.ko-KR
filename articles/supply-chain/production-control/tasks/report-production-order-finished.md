---
title: 생산 주문이 완료된 것으로 보고
description: 이 절차는 생산 주문을 완료된 것으로 보고하는 방법을 보여줍니다.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa27691942b27886e85c52b7b3a736a62db7b7bd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449329"
---
# <a name="report-a-production-order-as-finished"></a>생산 주문이 완료된 것으로 보고

[!include [banner](../../includes/banner.md)]

이 절차는 생산 주문을 완료된 것으로 보고하는 방법을 보여줍니다. 이 절차를 만드는 데 사용된 데모 데이터 회사는 USMF입니다. 이것은 생산 주문 수명 주기를 설명하는 7가지 절차 중 6번째입니다.


## <a name="report-a-production-order-as-finished"></a>생산 주문이 완료된 것으로 보고
1. 생산 관리 > 생산 주문 > 모든 생산 주문으로 이동합니다.
    * 시작됨 상태의 생산 주문을 선택합니다.  
2. 작업 창에서 생산 주문을 클릭합니다.
3. 완료로 보고를 클릭합니다.
    * 이 페이지에서 완료로 보고되는 완제품의 수량을 확인할 수 있습니다.  
4. 일반 탭을 클릭합니다.
5. 수량을 '18'로 설정합니다.
6. 오류 수량을 '2'로 설정합니다.
7. 오류 원인 필드에서 '재료'를 선택합니다.
8. 작업 종료 확인란을 선택하거나 선택 취소합니다.
9. 오류 수락 확인란을 선택하거나 선택 취소합니다.
10. 확인을 클릭합니다.

## <a name="verify-the-report-as-finished-journal"></a>완료된 분개장으로 보고 확인
1. 작업 창에서 보기를 클릭합니다.
2. 완료로 보고를 클릭합니다.
3. 목록에서 선택한 행을 표시합니다.
4. 목록에서 선택한 행의 링크를 클릭합니다.
    * 완료된 분개장으로 보고가 게시되었습니다. 분개장을 조정하려는 경우 변경할 수 있는 새 분개장을 수동으로 만들 수 있습니다.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]