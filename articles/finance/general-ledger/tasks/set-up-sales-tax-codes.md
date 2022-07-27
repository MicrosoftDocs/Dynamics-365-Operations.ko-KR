---
title: 판매세 코드 설정
description: 이 항목에서는 Dynamics 365 Finance에서 판매세 코드를 설정하는 방법을 설명합니다.
author: twheeloc
ms.date: 09/27/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2539d701dda4ef5e1484d095b2d86d1f68a0dc98
ms.sourcegitcommit: 86f0574363fb869482ef73ff294f345f81d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8450997"
---
# <a name="set-up-sales-tax-codes"></a>판매세 코드 설정

[!include [banner](../../includes/banner.md)]

이 항목에서는 판매 세법 설정 방법에 대해 설명합니다. 판매세 코드는 법인이 계산, 징수 및 판매세 당국에 지불해야 하는 모든 간접세 또는 관세에 대해 생성됩니다.

이 작업에는 USMF 데모 회사를 사용합니다.

1. **탐색 창 > 세금 > 간접세 > 판매세 > 판매세 코드** 로 이동합니다.
2. **새로 만들기** 를 선택합니다.
3. **판매세 코드 필드** 에 값을 입력합니다.
4. **이름** 필드에 값을 입력합니다.
5. 이 판매세를 신고하고 납부해야 하는 판매세 권한과 기간을 지정하려면 풀다운 목록을 열어 **정산 기간** 을 선택합니다.
6. **원장 게시 그룹** 을 선택하여 총계정원장에 판매세를 게시할 주요 계정을 지정합니다.
7. **계산** 빠른 탭을 확장합니다. 여기에는 판매세 산정 방식을 제어하는 여러 분야가 포함됩니다. 필요에 따라 다음 필드를 입력합니다.  
8. 인터페이스 상단의 **작업 창** 에서 **판매 세금 코드** 를 선택합니다.
9. **값** 을 선택합니다.
10. **값** 열에 이 세금 코드의 값을 입력하십시오.

    **계산** 빠른 탭의 **원본** 필드에서 **단위당 금액** 을 선택하면 트랜잭션 수량에 값을 곱하여 판매세 금액을 계산합니다.  세금 코드가 단위 기반 세금이 아닌 경우 값은 판매세 금액을 계산하기 위해 이 세금 코드의 출처에 적용되는 백분율입니다.     

11. **저장** 을 선택합니다.
12. 페이지를 닫습니다
13. **저장** 을 선택합니다.

Microsoft Dynamics 365 Finance 버전 10.0.22에서 [세금 서비스](../../localizations/global-tax-calcuation-service-overview.md)를 사용하고 있고 다중 [**VAT 등록 번호 지원**](../../localizations/emea-multiple-vat-registration-numbers.md) 기능이 **기능 관리** 작업 공간에서 활성화된 경우 세금 정보 유형을 사용할 수 있습니다. **세금 유형** 필드를 사용하여 세금 코드의 유형을 지정할 수 있습니다. 다음 값을 사용할 수 있습니다.

- 표준 VAT
- 인하된 VAT
- VAT 0%
- 소비세
- 기타

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
