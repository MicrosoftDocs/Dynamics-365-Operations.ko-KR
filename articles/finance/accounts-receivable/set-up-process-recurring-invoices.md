---
title: 반복 송장 설정 및 처리
description: 이 문서에서는 반복 송장을 설정하고 처리하는 방법을 설명합니다. 정기적으로 고객에게 동일한 금액을 청구해야 하는 경우 반복 송장을 사용할 수 있습니다.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 53b667b8a5aef0a788abd6a9d5d4a3b4d8d890e2a18bb5f74e58bb198fab5fa8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450472"
---
# <a name="set-up-and-process-recurring-invoices"></a>반복 송장 설정 및 처리

[!include [banner](../includes/banner.md)]

이 문서에서는 반복 송장을 설정하고 처리하는 방법을 설명합니다. 정기적으로 고객에게 동일한 금액을 청구해야 하는 경우 반복 송장을 사용할 수 있습니다.

## <a name="create-a-recurring-free-text-invoice-template"></a>반복 무료 텍스트 송장 템플릿 만들기

정기적으로 동일한 서비스에 대해 고객에게 송장을 작성하려면 송장 생성에 재사용할 수 있는 자유 텍스트 송장 템플릿을 정의해야 합니다. 이 템플릿에는 다음 정보가 포함되어 있습니다.

-   세금 그룹, 지불 조건 및 지불 방법과 같은 헤더 정보
-   서비스 설명, 수익 계정, 단가 및 송장 금액과 같은 라인 정보
-   배송 또는 취급 비용
-   비용 센터, 비즈니스 단위와 같은 재무 차원 정보와 함께 회계 분포

실제로 전체 송장을 만들고 템플릿으로 저장하는 것입니다. **반복 송장** 페이지를 사용하여 템플릿을 설정할 수 있습니다.

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a>고객에게 무료 텍스트 송장 템플릿을 할당하고 반복 세부 정보 입력
템플릿을 만든 후에는 송장을 발행할 고객에게 템플릿을 할당해야 합니다. 또한 송장이 사용되는 시기와 빈도를 지정해야 합니다. **고객** 페이지의 **송장** 탭에서 템플릿을 할당할 수 있습니다. 목록에 템플릿을 추가하고 다음 정보를 업데이트합니다.

-   반복 청구의 시작 날짜 및 종료 날짜(선택 사항)
-   반복 청구 빈도(예: 매일 또는 한 달에 한 번)
-   최대 청구 금액(이 정보가 필요한 경우)

고객은 빈도가 다른 여러 템플릿을 가질 수 있습니다.

## <a name="generate-the-recurring-invoices"></a>반복 송장 생성
**반복 송장** 페이지에서 반복 송장 템플릿을 처리하는 작업이 있습니다. 송장 날짜와 송장을 생성할 템플릿을 지정합니다. 송장이 생성되고 처리되는 각 송장 그룹에 대해 단일 반복 ID 번호가 할당됩니다.

## <a name="post-recurring-free-text-invoices"></a>반복 자유 텍스트 송장 게시

반복 송장이 생성되면 **반복 송장** 페이지의 게시 작업에 송장 반복 ID가 표시됩니다. 링크를 클릭하면 반복 ID에 대한 모든 인보이스를 볼 수 있습니다. 반복 ID에 대한 송장을 검토하는 동안 개별 송장을 삭제할 수 있습니다. 나중에 다시 생성할 수 있도록 해당 템플릿에 대한 고객의 반복 설정이 재설정됩니다. 반복 ID에 대해 하나, 여러 개 또는 모든 송장을 게시할 수 있습니다. 워크플로가 활성화된 경우 송장을 게시하려면 먼저 **제출** 을 클릭해야 합니다.

## <a name="print-recurring-free-text-invoices"></a>반복 자유 텍스트 송장 인쇄

반복 송장이 전기된 후 자유 텍스트 송장 목록 페이지에서 송장을 인쇄할 수 있습니다. 선택한 송장을 인쇄하거나 인쇄할 송장 범위를 선택할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]