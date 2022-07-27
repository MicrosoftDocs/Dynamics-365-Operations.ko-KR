---
title: 판매 견적 생성 및 편집
description: 이 절차는 판매 견적을 생성하고 업데이트하는 방법을 보여줍니다.
author: Henrikan
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable, CustQuotationConfirmationJournal, CustQuotationJournal, CustSalesLines, SalesQuotationCopying, SalesQuotationDeleteQuotations, SalesQuotationListPagePreviewPane, SalesQuotationTypeGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1c409d294565f89eac95e42f6207573d22859100
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8449164"
---
# <a name="create-and-edit-sales-quotations"></a>판매 견적 생성 및 편집

[!include [banner](../../includes/banner.md)]

이 절차는 판매 견적을 생성하고 업데이트하는 방법을 보여줍니다. 자신의 데이터 또는 데모 데이터 회사 USMF에서 이 절차를 실행할 수 있습니다.


## <a name="create-a-sales-quotation"></a>판매 견적 만들기
1. **탐색 창 > 모듈 > 영업 및 마케팅 > 판매 견적 > 모든 견적** 으로 이동합니다.
2. **새로 만들기** 를 클릭합니다.
3. **계정 유형** 필드에서 '잠재 고객'을 선택합니다.
4. **잠재 고객** 필드에서 값을 입력하거나 선택합니다.
5. **일반** 섹션을 확장합니다. 영업 및 마케팅 영역에서 견적을 생성하도록 선택했으므로 유형이 자동으로 '판매 견적'으로 설정됩니다. 프로젝트에 대한 견적을 생성하려면 **프로젝트 관리 및 회계** 기준 치수에서 액세스해야 합니다.
6. **확인** 을 클릭합니다. 견적 라인의 필드 및 작업은 판매 주문 라인의 필드와 작업과 매우 유사합니다.   판매 주문과 마찬가지로 특정 품목에 대한 견적을 생성할 수 있으며, 견적 생성 시 품목 번호를 모르거나 존재하지 않는 경우 판매 범주에 대한 견적을 생성할 수 있습니다.     
7. **항목** 필드에 값을 입력하거나 선택합니다.
8. **사이트** 필드에 값을 입력합니다.
9. **수량** 필드에 숫자를 입력합니다. 라인에서 선택한 품목에 대해 유효한 거래 계약이 있는 경우 해당 가격 및 할인이 자동으로 견적 라인에 복사됩니다. 단가 필드에 값이 포함되어 있는지 확인하고 원하는 경우 할인 값을 입력할 수도 있습니다. 
10. **저장** 을 클릭합니다.
11. **작업 창** 에서 **판매 견적** 을 클릭합니다.
12. **합계** 를 클릭합니다.
13. **확인** 을 클릭합니다.
14. 판매 견적 라인을 선택합니다.
15. **작업 창** 에서 **견적** 을 클릭합니다.
16. **가격 시뮬레이션** 을 클릭합니다.
    - **가격 시뮬레이션 실행** 페이지에서 원하는 단가, 할인 금액, 할인 비율, 총액, 마진 또는 기여 비율을 기반으로 견적의 예상 수익 또는 수익성을 조정하는 실험을 할 수 있습니다. 목표 수치에 만족하면 견적 라인에 제안을 적용하고 그에 따라 가격 관련 필드가 업데이트됩니다.  
    - 원하는 만큼 가격 시뮬레이션을 생성할 수 있습니다. **새로 만들기** 를 클릭하면 현재 견적 라인의 가격 조건이 페이지에 복사됩니다. 그런 다음 가격 관련 필드의 값을 대상 값으로 수정할 수 있습니다. 필드 중 하나를 변경하면 다른 모든 필드에서 재계산이 트리거됩니다. 시스템이 판매 마진과 기여 비율을 계산하려면 제품의 단가를 알아야 합니다. 원래 가격, 제안된 변경 사항 및 견적 합계에 대한 영향을 자세히 보려면 시뮬레이션된 가격 탭을 사용하세요. 일반적으로 새 금액을 설정하는 시뮬레이션이 견적 라인에 적용되면 시스템이 다시 계산하여 단가 필드에 새 값을 입력합니다. 시뮬레이션이 새 마진 또는 새 기여 비율을 기반으로 하는 경우 순 금액 필드만 업데이트되고 단가는 비어 있습니다. 두 경우 모두 시뮬레이션 전에 견적 라인에 있었던 모든 할인이 삭제됩니다.
17. **작업 창** 에서 **견적** 을 클릭합니다.
18. **견적 보내기** 를 클릭합니다.
19. **견적 인쇄** 필드에서 '예'를 선택합니다.
20. **확인** 을 클릭합니다. 보고서를 생성하는 데 1분 정도 걸릴 수 있습니다. 완료될 때까지 페이지를 닫지 마세요.

## <a name="update-a-sales-quotation"></a>판매 견적 업데이트
1. **탐색 창 > 모듈 > 영업 및 마케팅 > 판매 견적 > 모든 견적** 으로 이동합니다.
2. **작업 창** 에서 **후속작업** 을 클릭합니다.
3. **고객으로 전환** 을 클릭합니다.
4. **고객 계정** 필드에 값을 입력합니다.
5. **검사** 를 클릭합니다. 입력한 계좌 번호를 무료로 사용할 수 있다는 메시지가 표시되는지 확인합니다.  
6. **확인** 을 클릭합니다. 시스템은 이제 견적에 대한 잠재 고객에 대한 새 고객 계정을 생성했습니다.  
7. 페이지를 닫습니다.
8. **작업 창** 에서 **후속작업** 을 클릭합니다.
9. **확인** 을 클릭합니다.
10. **사유** 필드에 값을 입력하거나 선택합니다.
11. **확인** 을 클릭합니다.
12. **작업 창** 에서 **일반** 을 클릭합니다.
13. **판매 주문** 을 클릭합니다.
14. 페이지를 닫습니다.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]