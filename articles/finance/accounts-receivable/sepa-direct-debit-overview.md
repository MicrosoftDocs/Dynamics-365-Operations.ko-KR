---
title: SEPA 자동 이체 개요
description: 단일 유로 결제 지역(SEPA)는 유럽 집행위원회(European Commission)에 의해 설정되었으며 개인, 기업 또는 조직 및 은행이 위치한 국가/지역과 관계없이 모든 전자 지불이 국내로 간주되도록 규정합니다. 국내 및 국경 간 지불에 차이가 없습니다. SEPA에는 유럽 연합(EU)의 28개 회원국과 아이슬란드, 리히텐슈타인, 노르웨이, 스위스, 모나코 및 산마리노가 포함됩니다. SEPA는 유럽 경제 지역(EEA) 내에서 지불 거래를 위한 단일 시장을 형성하는 데 도움이 됩니다. 궁극적으로 SEPA는 은행, 기업 및 개인이 함께 작업해야 하는 지불 형식의 수를 줄일 것으로 예상됩니다.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, CustBankAccounts, CustParameters, CustTable
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "11144"
- intro-internal
ms.assetid: 3277c9b6-e46e-40c9-aa76-9b0449467842
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f71eca0ca9ee07d43bdf737874f442f0029e87e
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451429"
---
# <a name="sepa-direct-debit-overview"></a>SEPA 자동 이체 개요

[!include [banner](../includes/banner.md)]

단일 유로 결제 지역(SEPA)는 유럽 집행위원회(European Commission)에 의해 설정되었으며 개인, 기업 또는 조직 및 은행이 위치한 국가/지역과 관계없이 모든 전자 지불이 국내로 간주되도록 규정합니다. 국내 및 국경 간 지불에 차이가 없습니다. SEPA에는 유럽 연합(EU)의 28개 회원국과 아이슬란드, 리히텐슈타인, 노르웨이, 스위스, 모나코 및 산마리노가 포함됩니다. SEPA는 유럽 경제 지역(EEA) 내에서 지불 거래를 위한 단일 시장을 형성하는 데 도움이 됩니다. 궁극적으로 SEPA는 은행, 기업 및 개인이 함께 작업해야 하는 지불 형식의 수를 줄일 것으로 예상됩니다.   

## <a name="what-is-the-goal-of-sepa-direct-debits"></a>SEPA 자동 이체의 목표는 무엇인가요?

SEPA 자동 이체를 사용하면 고객이 채권자에게 서명한 위임장을 부여한 경우 채권자가 고객의 은행 계좌에서 자금을 회수할 수 있습니다. 고객이 서명하는 위임장은 채권자가 지불금을 받을 권한을 부여하고 고객의 은행에 금액을 지불하도록 지시합니다. 

SEPA 자동 이체는 처음으로 32개 SEPA 국가/지역에서 국내 및 국경 간 유로 자동 이체 모두에 사용할 수 있는 결제 수단이 되었습니다. 

SEPA 핵심 자동 이체 체계와 SEPA B2B(기업 간) 자동 이체 체계의 두 가지 체계를 사용할 수 있습니다. 두 체계 모두 같은 파일 형식을 사용합니다.

## <a name="what-is-the-core-direct-debit-scheme"></a>핵심 자동 이체 체계란 무엇인가요?
SEPA 핵심 자동 이체 체계는 기본 체계입니다. 다음 특성이 있습니다.
-   자금 이체는 유로로 이루어집니다(은행 계좌가 다른 통화로 자금을 보유할 수 있는 경우에도).
-   고객과 채권자는 각각 SEPA 내에 위치한 신용 기관에 계좌를 보유해야 합니다.
-   고객은 채권자에게 서명된 위임장을 부여해야 합니다.
-   위임장은 마지막으로 수금이 시작된 후 36개월이 지나면 만료됩니다.
-   채권자는 위임장이 유효한 동안 그리고 마지막 수금 후 최소 14개월 동안 위임장을 보관해야 합니다.
-   이 체계는 단일(일회성) 또는 반복 자동 이체 수금에 사용할 수 있습니다.
-   고객은 계정에서 인출된 후 최대 8주 동안 환불받을 수 있는 "불문" 권리가 있습니다.

## <a name="what-is-the-sepa-business-to-business-b2b-direct-debit-scheme"></a>SEPA B2B(기업 간) 자동 이체 체계란 무엇인가요?
SEPA B2B 자동 이체 체계는 B2B 거래에 적용되며 SEPA 핵심 자동 이체 체계에 기반을 둡니다. 주요 차이점은 다음과 같습니다.
-   SEPA B2B 자동 이체 체계는 고객이 개인(소비자)인 경우 허용되지 않습니다.
-   고객은 승인된 거래에 대해 환불받을 자격이 없습니다.
-   고객 은행은 위임장 정보에 대한 수집을 확인하여 수금이 승인되었는지 확인해야 합니다. 고객 은행과 고객은 각 자동 이체에 대해 수행할 확인에 동의해야 합니다.
-   이 체계는 자동 이체 처리 시간과 반환 기간을 단축합니다.

## <a name="can-i-use-the-cor1-scheme-for-direct-debit-mandates"></a>자동 이체 위임장에 COR1 체계를 사용할 수 있나요?
예. 오스트리아, 벨기에, 독일, 프랑스, 이탈리아, 스페인 및 네덜란드에서 SEPA 자동 이체 위임장에 COR1 체계를 사용할 수 있습니다. 이 체계는 채권자에 대한 자동 이체 수금을 위한 사전 통지 기간을 단축시켜 줍니다.

## <a name="what-are-international-bank-account-numbers-iban-and-bank-identifier-codes-bic"></a>IBAN(International Bank Account Number)과 BIC(Bank Identifier Code)란 무엇인가요?
IBAN(International Bank Account Number) 및 BIC(Bank Identifier Code)는 전 세계 32개 국가/지역에서 모든 계정을 식별하는 데 사용됩니다. SWIFT 코드 필드에 BIC를 입력하고 IBAN 필드에 IBAN을 입력합니다. 두 필드 모두 은행 계좌 페이지의 은행 계좌 탭에 있는 추가 ID 빠른 탭에 있습니다. 이는 채권자의 은행 계좌와 고객의 은행 계좌 모두에 해당됩니다.

## <a name="where-do-i-enter-creditor-identifiers-direct-debit-ids"></a>채권자 식별자(자동 이체 ID)는 어디에 입력하나요?
SEPA에서 각 채권자는 고유한 채권자 식별자로 식별됩니다. 이 식별자를 통해 고객과 고객 은행은 각 자동 이체를 필터링한 다음 고객 지침에 따라 자동 이체를 처리하거나 거부할 수 있습니다. 채권자는 은행을 통해 이 식별자를 요청해야 합니다. 법인의 은행 계좌에 대한 자동 이체 ID 필드에 이 식별자를 입력합니다.

## <a name="what-are-mandates"></a>위임장은 무엇인가요?
고객이 서명하는 위임장은 채권자가 지불금을 받을 권한을 부여하고 고객의 은행에 금액을 지불하도록 지시합니다. 고객은 종이 양식 또는 전자적으로 위임장을 발행할 수 있습니다. 기본적으로 위임장은 자동 이체가 마지막으로 수행된 후 36개월이 지나면 만료됩니다.

## <a name="where-do-i-specify-the-sepa-direct-debit-file-format-iso-20022"></a>SEPA 자동 이체 파일 형식(ISO 20022)은 어디에서 지정하나요?
SEPA 데이터 형식은 ISO 20022 메시지 표준에 기반을 둡니다. 수취 계정 지불 방법을 구성할 때 일반 전자 보고 확인란을 선택하고 SEPA 자동 이체 형식을 내보내기 형식 구성으로 선택합니다. 고객 지불 분개장에서 지불 파일을 생성할 때 해당 지불 방법을 사용합니다.

## <a name="in-what-file-formats-can-i-generate-sepa-direct-debit-payment-files"></a>SEPA 자동 이체 지불 파일은 어떤 파일 형식으로 생성할 수 있나요?
다음 형식으로 SEPA 자동 이체를 전자 지불 파일을 생성할 수 있습니다.
-   벨기에, 독일, 스페인, 프랑스, 이탈리아 및 네덜란드용 PAIN.008.001.02 XML 파일 형식의 SEPA 자동 이체 지불 파일.
-   오스트리아용 PAIN.008.001.02 XML 파일 형식의 SEPA 자동 이체 지불 파일, 독일용 PAIN.008.003.02 XML 파일 형식.

## <a name="how-do-refunds-and-returns-work-with-sepa-direct-debits"></a>SEPA 자동 이체에서 환불 및 반환은 어떻게 하나요?
두 SEPA 자동 이체 방식에 따라 고객은 환불에 대한 특정 권리가 있습니다. 고객은 기한 이후 8주 동안 승인된 거래를 이유 없이 회수할 수 있습니다. 미승인 거래의 경우 기한으로부터 13개월까지 기간이 연장됩니다. 지불 취소는 고객 거래 페이지에서 지불 취소 버튼을 사용하여 수동으로 수행됩니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]