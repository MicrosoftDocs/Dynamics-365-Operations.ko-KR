---
title: 연말 결산 누락 개시 잔액
description: 이 항목에서는 연도를 결산할 때 개시 잔액이 누락될 수 있는 이유와 누락된 경우 해당 잔액을 복구하는 방법을 설명합니다.
author: kweekley
ms.date: 05/12/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4478f2b46f984c97ff01588098d64953dedf476e7f3f76aeecb29a0ff0074b9d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8452746"
---
# <a name="year-end-close-missing-opening-balances"></a>연말 결산 누락 개시 잔액

[!include [banner](../includes/banner.md)]

이 항목에서는 연도를 결산할 때 개시 잔액이 누락될 수 있는 이유와 누락된 경우 해당 잔액을 복구하는 방법을 설명합니다.

### <a name="symptom"></a>증상

총계정원장 연말 결산을 실행한 후에 개시 잔액이 없는 이유는 무엇입니까? 

### <a name="resolution"></a>해결책

총계정원장에서 1년을 결산한 뒤 다음 회계 연도의 개시 잔액을 표시하지 않는 시산표를 생성한 경우 확인해야 할 사항은 다음과 같습니다.

**이전 결산 실행 취소** 필드가 **예** 로 설정되어 있으면 동일한 회계 연도에 대한 전년도 결산이 반전됩니다. 연말 결산을 반전하는 프로세스를 실행하면 결산 잔액과 개시 잔액에 대한 모든 기입이 마치 해당 연도가 결산된 적이 없는 것처럼 삭제됩니다. 쿠폰도 삭제됩니다. 연말 결산 프로세스는 자동으로 다시 실행되지 않습니다. 프로세스를 다시 시작해야 합니다. 이번에는 **이전 결산 실행 취소** 옵션을 **아니요** 로 업데이트합니다.

이 시나리오는 연말 결산 FAQ 항목에서 다룹니다. 자세한 내용은 [연말 활동 FAQ](faq-year-end-activities.md)를 참조하세요.

### <a name="symptom"></a>증상

**이전 결산 실행 취소** 옵션이 **아니요** 로 설정되어 있는 상태에서 연말 결산을 실행했는데, 여전히 회계 연도에 대한 개시 잔액이 없습니다.

### <a name="resolution"></a>해결책

먼저 일괄 처리 작업의 상태를 확인합니다. 한 해를 결산하는 데는 여러 가지 개별 작업이 포함되지만, 가장 중요한 단계는 작업 설명 **단계 5.0.0** 이 포함된 일괄 처리 작업입니다. 개시 거래와 선택적으로 마감 거래를 총계정원장에 게시하는 작업이 이 단계에서 발생합니다. 

[![일괄 처리 기록 목록](./media/yec-mssng-open-blnces-01.png)](./media/yec-mssng-open-blnces-01.png)

이 단계가 성공적으로 종료되었지만 **시산표 조회** 페이지에 개시 잔액이 표시되지 않으면(**총계정원장 > 조회 및 보고서 > 시산표**) 연말 결산 일괄 처리 작업의 결과를 검토하여 잔액 복구 단계가 성공적으로 완료되었는지 확인합니다.

[![연말 결산 일괄 처리 작업의 결과](./media/yec-mssng-open-blnces-02.png)](./media/yec-mssng-open-blnces-02.png)

어떤 이유로든 이 단계가 실패한 경우 개시(선택적으로 마감 포함) 거래가 성공적으로 게시되었을 수 있습니다. 결산한 해에 대해 연말 결산 대화 상자에 제공된 쿠폰 번호와 날짜를 지정하는 방법으로(**총계정원장 > 조회 및 보고서 > 쿠폰 거래**) **쿠폰 거래 조회** 를 사용하여 총계정원장 거래가 성공적으로 게시되었는지 확인할 수 있습니다.

[![상품권 거래 조회](./media/yec-mssng-open-blnces-03.png)](./media/yec-mssng-open-blnces-03.png)

개시(선택적으로 마감 포함) 쿠폰이 있는 경우 연말 결산을 다시 실행할 필요가 없습니다. 대신 계속 진행하는 방법에 대한 정보는 다음 섹션을 참조하세요.

### <a name="symptom"></a>증상

연말 결산의 '잔액 복구' 단계가 실패했습니다. 전체 연말 결산 프로세스를 다시 실행해야 합니까?

### <a name="resolution"></a>해결책

잔액 복구 단계는 시산표 조회가 생성될 때 사용되는 총계정원장 잔액을 업데이트합니다.  연말 결산 프로세스의 마지막 단계입니다.  이 단계가 실패한 유일한 단계인 경우 총계정원장 거래가 성공적으로 게시된 것입니다.  연말 결산을 다시 실행할 필요가 없습니다. **재무 차원 집합** 페이지를 사용하여 수동으로 잔액을 복구하는 프로세스를 실행할 수 있습니다(**총계정원장 > 계정 차트 > 차원 > 재무 차원 집합**).

[![재무 차원 집합 페이지의 잔액 복구 단추](./media/yec-mssng-open-blnces-04.png)](./media/yec-mssng-open-blnces-04.png)

이 단계를 처리하는 데 시간이 오래 걸리면 [재무 차원 집합 업데이트 모범 사례](https://community.dynamics.com/365/financeandoperations/b/dynamics-365-finance-blog/posts/best-practices-for-updating-financial-dimension-set-dimension-sets)에 설명된 대로 재무 차원 집합에 대한 모범 사례를 검토하는 것이 좋습니다. 

