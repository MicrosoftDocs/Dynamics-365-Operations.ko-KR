---
title: 운임을 수동으로 조정
description: 이번에는 운임을 수동으로 조정하는 방법을 보여줍니다.
author: Henrikan
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1342f8b26d3f629c9fe4439761ffc26372dce061
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448588"
---
# <a name="reconcile-freight-manually"></a>운임을 수동으로 조정

[!include [banner](../../includes/banner.md)]]

이번에는 운임을 수동으로 조정하는 방법을 보여줍니다. 일반적으로 운송 조정자가 수행합니다. USMF 데모 데이터 회사에서 이 절차를 사용할 수 있습니다.


## <a name="select-a-load-to-reconcile"></a>조정할 부하 선택
1. 운송 관리 > 계획 > 적재 계획 워크벤치로 이동합니다.
2. 배송 및 수령 확인 확인란의 선택을 취소합니다. 
3. 목록에서 부하 ID가 00006인 부하를 선택합니다.

## <a name="create-a-carrier-invoice"></a>운송업체 송장 생성
운임을 수동으로 조정하고 운송업체 송장을 자동으로 받지 못하는 경우 운임 청구서를 기반으로 송장을 생성할 수 있습니다.  
1. 관련 정보를 클릭합니다.
2. 운송비 세부 정보를 클릭합니다.
3. 운임 청구서 송장 생성을 클릭합니다.
4. 송장 필드에 값을 입력합니다.
5. 확인을 클릭합니다.

## <a name="reconcile-the-invoice"></a>송장 조정
운송업체 송장과 운임 청구서를 조정하면 라인별로 이루어집니다.  
1. 운송비 청구서 및 송장 일치를 클릭합니다.
2. 송장 세부 정보 섹션을 확장합니다.
3. 일치하지 않는 운임 청구서 세부 정보 섹션을 확장합니다.
4. 목록에서 선택한 행을 표시합니다.
5. 일치를 클릭합니다.
6. 일치하는 운임 청구서 세부 정보 섹션을 확장합니다.

## <a name="submit-the-invoice-for-approval"></a>승인을 위해 송장 제출
1. 승인을 위해 제출을 클릭합니다.
2. 페이지를 닫습니다.
3. 승인된 품목 숨기기 확인란의 선택을 취소합니다. 
4. 공급업체 송장 분개를 클릭합니다.
5. 참조 저널 번호 필드에 있는 링크를 따라가려면 클릭하세요.
6. 라인을 클릭합니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]