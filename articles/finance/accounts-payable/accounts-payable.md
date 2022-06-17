---
title: 지급 계정 홈페이지
description: 이 주제에서는 지급 계정에 대해 간단히 설명합니다.
author: sunfzam
ms.date: 02/15/2019
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "21901"
- intro-internal
ms.assetid: 1e4c2ac4-077b-4678-8733-5cec8f6ff659
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: ce768ecaa668f2c69d6753401eaa145b6fddc5ec
ms.sourcegitcommit: e40a9fac5bac9f57a6dcfe73a1f21856eab9b6a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2021
ms.locfileid: "8452899"
---
# <a name="accounts-payable-home-page"></a>지급 계정 홈페이지

[!include [banner](../includes/banner.md)]

이 주제에서는 지급 계정에 대해 간단히 설명합니다. 

공급업체 송장은 수동으로 입력하거나 데이터 엔터티를 통해 전자 양식으로 받을 수 있습니다. 송장을 입력하거나 받은 후에는 송장 승인 분개장이나 **공급업체 송장** 페이지에서 송장을 검토하고 승인할 수 있습니다. 송장 매칭, 공급업체 송장 정책 및 워크플로를 사용하여 검토 프로세스를 자동화하여, 특정 기준을 충족하는 송장은 자동으로 승인되고 나머지 송장은 승인된 사용자가 검토하도록 플래그를 지정할 수 있습니다.

**비즈니스 프로세스**

[![비즈니스 프로세스 다이어그램](./media/AP-process.PNG)](./media/AP-process.PNG)

## <a name="set-up-accounts-payable"></a>지급 계정 설정

공급업체 그룹, 공급업체, 기장 프로필, 다양한 결제 방법, 그리고 공급업체, 요금, 배송 및 목적지, 약속 어음 및 기타 유형의 지급 계정 정보에 관한 매개변수를 설정합니다. 

[지급 계정 구성 개요](accounts-payable-overview.md)

[공급업체 송장용 회계 분포 및 보조 원장 분개장 기입](accounting-distributions-subledger-journal-entries-vendor-invoices.md) 

[지급 계정 및 수취 계정에 대한 외화 재평가](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md)

## <a name="configure-vendor-invoices"></a>공급업체 송장 구성

지급 계정을 사용하여 송장 및 공급업체에 대한 지출을 추적합니다.

[지급 계정 송장 매칭 개요](accounts-payable-invoice-matching.md)

[공급업체 기장 프로필](vendor-posting-profiles.md)

[지급 계정 송장 매칭 유효성 검사 설정](tasks/set-up-accounts-payable-invoice-matching-validation.md)

[3방향 매칭 정책](three-way-matching-policies.md)

[송장 매칭 및 관계회사간 구매 주문](invoice-matching-intercompany-purchase-orders.md)

[송장 합계 매칭 중 불일치 항목 해결 개요](resolve-invoice-totals-invoice-matching-discrepancies.md)

[공급업체 송장 분개장 및 송장 승인 분개장용 기본 상쇄 계정](default-offset-accounts-vendor-invoice-journals.md)

[모바일 송장 승인](mobile-invoice-approvals.md)

[공급업체 협업 송장 작성 작업 영역](vendor-portal-invoicing-workspace.md)

[공급업체 송장 자동화](vendor-invoice-automation.md)

## <a name="configure-vendor-payments"></a>공급업체 결제 구성 

사용자 정의 결제 방법에 수표, 전자 결제, 약속 어음 같은 시스템에서 정의한 결제 유형을 지정합니다. 결제 유형은 선택 사항이지만, 쉽게 전자 결제의 유효성을 확인하고 결제에서 사용하는 결제 유형을 빠르게 판단할 수 있습니다. 

[공급업체 결제 작업 영역](vendor-payments-workspace.md)

[공급업체 결제 수수료 정의](tasks/define-vendor-payment-fees.md)

[공급업체 결제 조건 정의](tasks/define-vendor-payment-terms.md)

[포지티브 페이 개요](positive-pay-overview.md)

[포지티브 페이 파일 설정 및 생성](set-up-generate-positive-pay-files.md)

[결제 제안을 사용하여 공급업체 결제 생성](create-vendor-payments-payment-proposal.md)

[부분 금액에 대한 공급업체 결제](vendor-payments-partial-amount.md)

[공급업체 결제에 계산된 할인 이상으로 할인](take-discount-more-calculated-discount-vendor-payment.md)

[현금 할인 기간이 아닐 때의 현금 할인](take-cash-discount-outside-cash-discount-timeframe.md)

[전자 보고 샘플 공급업체 확인](electronic-reporting-sample-vendor-checks.md)

[공급업체 결제 취소](reverse-vendor-payment.md)

[선불 송장과 선불 비교](prepayments-invoices-vs-prepayments.md)

[지급 계정의 중앙 집중식 결제](centralized-payments-accounts-payable.md)

## <a name="settlements"></a>정산

다음 항목은 정산 관련 정보를 제공합니다. 정산은 송장을 이용해 결제를 정산하는 프로세스입니다. 

[정산 구성](../cash-bank-management/configure-settlement.md)

[할인일 이전의 부분 공급업체 결제를 할인일 이후의 최종 결제로 정산](settle-partial-vendor-payment-before-discount-or-final-payment-after.md)

[공급업체 대변 전표에 할인 금액이 있는 부분 공급업체 결제 정산](settle-partial-vendor-payment-discounts-vendor-credit-notes.md)

[여러 할인 기간이 있는 부분 공급업체 결제 정산](settle-partial-vendor-payment-multiple-discount-periods.md)

[할인일 이전의 부분 공급업체 결제와 최종 결제를 모두 정산](settle-partial-vendor-payment-or-final-payment-before-discount.md)

[여러 고객 또는 공급업체 레코드가 있는 단일 쿠폰](single-voucher-multiple-customer-vendor-records.md)



### <a name="additional-resources"></a>추가 리소스

#### <a name="whats-new-and-in-development"></a>신규 및 개발 중인 기능

[Microsoft Dynamics 365 릴리스 계획](/dynamics365/release-plans/)으로 이동하여 예정된 신규 기능을 확인하세요. 

#### <a name="blogs"></a>블로그

[Microsoft Dynamics 365 블로그](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) 및 [Microsoft Dynamics 365 Finance - 재무 블로그](https://community.dynamics.com/365/financeandoperations/b/financials)에서 지급 계정 및 기타 솔루션에 관한 의견과 뉴스 및 기타 정보를 확인할 수 있습니다.

[Microsoft Dynamics 운영 파트너 커뮤니티 블로그](https://community.dynamics.com/partner/b/operationspartnercommunityblog)에서 Microsoft Dynamics 파트너는 단일 리소스를 통해 Dynamics 365의 새로운 소식과 동향을 확인할 수 있습니다.

#### <a name="community-blogs"></a>커뮤니티 블로그

[Dynamics 365 Finance에서 지급 계정을 관리하는 방법](https://financefunction.tech/2019/02/15/how-to-manage-payables-in-dynamics-365-for-finance-and-operations)

#### <a name="task-guides"></a>작업 가이드
애플리케이션 내에서 작업 가이드 형태로 추가 도움말이 제공됩니다. 작업 가이드에 액세스하려면 아무 페이지에서 도움말 버튼을 클릭하세요.

#### <a name="videos"></a>비디오

[Microsoft Dynamics 365 YouTube Channel](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ)에서 제공하는 방법 강좌 비디오를 확인해보세요.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
