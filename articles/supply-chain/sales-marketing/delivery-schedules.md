---
title: 배달 일정
description: 배달 일정을 사용하면 단일 판매 주문, 판매 견적 또는 구매 주문에 대해 여러 납품을 사용할 때 주문 라인 수량을 추적할 수 있습니다.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b50558c5da71351082d36276a3185e1f91543f2b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448621"
---
# <a name="delivery-schedules"></a>배달 일정

[!include [banner](../includes/banner.md)]

배달 일정을 사용하면 단일 판매 주문, 판매 견적 또는 구매 주문에 대해 여러 납품을 사용할 때 주문 라인 수량을 추적할 수 있습니다.

주문 또는 견적 라인의 총 수량을 여러 배달로 배달해야 하는 경우 배달 일정을 사용합니다. 개별 배달은 배달 라인으로 표시됩니다. 두 개 이상의 배달 라인이 하나의 배달 일정을 구성합니다. 배달 라인은 배달 날짜, 수량, 배달 모드 및 보관 차원(예: 사이트 및 창고)이 다를 수 있습니다.  

**배달 일정의 예**

| 항목                              | 값                                    |
|-----------------------------------|------------------------------------------|
| 총 주문(원래 주문 라인) | 의자 600개                               |
| 요청된 배달 일정       | 월별 의자 100개                     |
| 요청된 배달 시간 프레임 | 6개월, 매월 1일 |

이 시나리오에서 고객은 6개월 동안 100개로 구성된 의자 배치로 600개의 의자를 요청합니다. 배달 요구 사항을 추적하기 위해 배달 일정을 만듭니다. 배달 일정 페이지에서 6개의 개별 배달 라인을 생성합니다. 각 배달 라인에는 100개의 의자가 포함되어 있으며 100개의 의자에 대한 배달 날짜를 나타냅니다. 이 경우 각 행은 연속 6개월 동안 매월 1일에 상쇄됩니다.  

배달 일정을 생성하면 원래 주문 라인의 유형이 **여러 배달이 있는 주문 라인** 으로 자동 변경됩니다. 이 유형의 라인을 상업 라인이라고 하며 아이콘으로 표시됩니다. 배달 라인은 다른 아이콘으로 표시됩니다. 배달 라인의 수량을 변경하면 상업 라인이 배달 일정의 총 수량으로 업데이트됩니다. 무역 계약에서 주문에 대한 총 할인을 정의한 경우 주문이 별도의 배달로 분할된 경우에도 배달 일정을 통해 주문이 총 주문 할인을 받을 수 있습니다.  

배달 일정이 있는 주문은 배달 라인에 대해 처리됩니다. 처리에는 포장 전표, 제품 영수증 및 청구서 발행이 포함됩니다.  

배달 일정이 있는 주문 및 견적의 문서 출력물에는 배달 라인만 표시됩니다. 원래 라인(상업 라인)을 표시하지 않습니다. **참고**: 또한 다음 조치를 수행하면 배달 라인만 표시됩니다.

-   게시
-   페이지 복사
-   목록 페이지 및 보고서 찾아보기

판매 견적을 확인하면 결과 판매 주문에 전체 배달 일정이 표시되며 여러 배달이 있는 주문 라인도 표시됩니다. 또한 전체 배달 일정은 판매 주문, 판매 견적, 구매 주문 등 모든 주요 페이지에 표시됩니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]