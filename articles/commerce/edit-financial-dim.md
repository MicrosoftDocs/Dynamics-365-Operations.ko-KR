---
title: 소매 거래의 재무 차원 편집
description: 이 문서에서는 Microsoft Dynamics 365 Commerce에서 소매 거래에 대한 재무 차원을 편집하는 방법에 대해 설명합니다.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: b382907cd79a13319601dd694261319875565947
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268399"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a>소매 거래의 재무 차원 편집

[!include [banner](../includes/banner.md)]

이 문서에서는 Microsoft Dynamics 365 Commerce에서 소매 거래에 대한 재무 차원을 편집하는 방법에 대해 설명합니다.

## <a name="edit-financial-dimensions"></a>재무 차원 편집

Commerce Headquarters에서 소매 거래에 대한 재무 차원을 편집하려면 다음 단계를 따르십시오.

1. **응용 프로그램 통합을 위한 재무 차원 구성** 페이지를 엽니다.
1. 활성 상태의 **기본 차원 통합** 레코드를 선택합니다.
1. **재무 차원** 빠른 탭에서 Excel 워크시트에서 편집할 모든 차원이 **선택됨** 목록에 있는지 확인합니다. 자세한 내용은 [데이터 엔터티](../fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration.md#data-entities)를 참조하세요.
1. **명세서** 페이지, **소매 거래** 페이지나 **매장 재무** 작업 영역의 **거래 유효성 검사 실패** 타일에서 Excel 파일을 다운로드하고 엽니다.
1. 거래 재무 차원을 변경하려면 **설계** 를 선택한 다음, **거래(감사 가능)** 행 옆에 있는 연필 기호를 선택합니다.
1. **FinancialDimensionDisplayValue** 필드를 찾아 선택하고 Excel 워크시트의 헤더 부분에서 셀을 선택한 다음, **레이블 추가** 를 선택합니다.
1. 이전 단계에서 선택한 셀 아래에 있는 하나의 셀을 선택하고 **값 추가** 를 선택한 다음, **새로 고침** 을 선택합니다. 재무 차원은 Excel 워크시트에 추가된 후 편집 및 게시할 수 있습니다.
1. 거래 라인의 차원을 변경하려면 **판매 거래(감사 가능)** 행에서 연필 기호를 선택한 후 6단계와 7단계를 반복합니다.
1. 결제 라인의 차원을 변경하려면 **결제 거래(감사 가능)** 행에서 연필 기호를 선택한 후 6단계와 7단계를 반복합니다.

## <a name="additional-resources"></a>추가 리소스

[현금 판매 거래 및 현금 관리 거래 편집 및 감사](edit-cash-trans.md)

[온라인 주문 및 비동기 고객 주문 거래 편집 및 감사](edit-order-trans.md)

[Excel 통합 문서를 만들어 소매 거래 편집](create-excel-edit.md)

[Excel 통합 문서에 필드를 추가해 소매 거래 편집](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
