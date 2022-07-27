---
title: 공급업체 VAT 등록 날짜
description: 이 항목에서는 공급업체 VAT 등록 날짜를 활성화하는 기능에 대한 정보를 제공합니다.
author: anasyash
ms.date: 01/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: global
ms.author: anasyash
ms.search.validFrom: 2022-01-15
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 882d5a8718d819cff80bfa5b86e054a39e9db159
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451402"
---
# <a name="date-of-vendor-vat-register"></a>공급업체 VAT 등록 날짜

Microsoft Dynamics 365 Finance 버전 10.0.24에서는 공급업체 송장에 대해 새로운 **공급업체 VAT 레지스터** 필드를 사용할 수 있습니다. 이 필드는 구매에 대한 과세 대상 공급 날짜를 지정합니다.

새 필드를 활성화하려면 **기능 관리** 작업영역으로 이동하여 **공급업체 송장에 대한 공급업체 VAT 레지스터의 날짜 활성화** 기능을 찾아 선택한 다음 **지금 사용** 을 선택합니다.

공급업체로부터 수신되는 송장은 공급업체가 송장을 발행한 날짜와 과세 대상 공급 날짜(즉, 공급업체가 미지불 부가가치세[VAT]를 부과한 날짜)의 두 가지 날짜를 가질 수 있습니다. 일부 시나리오에서는 이 두 날짜가 다를 수 있습니다.

구매 인보이스에 대해 들어오는 VAT 금액을 공제하고 이전에 언급한 날짜와 다른 날짜에 나중에 VAT 보고서에 해당 인보이스를 포함할 수 있습니다. 이 날짜는 일부 시나리오에 대해 연기된 수입 VAT 공제에 대한 현지 법률 규칙에 의해 제어됩니다. 국가나 지역에 따라 다릅니다.

체코 공화국의 [VAT 통제 명세서 보고서](emea-cze-vat-declaration-tax-declaration-model.md#vat-control-statement)와 같은 일부 VAT 보고서는 구매 문서에 대해 과세 대상 공급 날짜를 보고하도록 요구합니다. 세무 당국이 거래 상대방 간의 VAT 보고를 조정할 수 있도록 이 날짜를 보고해야 합니다.

Finance에서는 다음 필드에 날짜를 정의할 수 있습니다.

- **송장 날짜** – 공급자가 송장을 발행한 날짜.
- **VAT 등록 날짜** – 구매 인보이스에 대한 VAT 금액 공제 날짜.
- **공급업체 VAT 등록 날짜** – 판매자의 과세 대상 공급 날짜.
- **서류 접수일** – 송장을 받은 날짜.

이러한 필드는 다음 페이지에 포함되어 있습니다.

- 공급업체 송장
- 공급업체 송장 레지스터
- 공급업체 송장 승인
- 공급업체 송장 분개장

공급업체 송장이 게시된 후 **송장 저널** 및 **공급업체 트랜잭션** 페이지에서 날짜를 검토할 수 있습니다.
