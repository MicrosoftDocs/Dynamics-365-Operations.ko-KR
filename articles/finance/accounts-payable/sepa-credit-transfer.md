---
title: SEPA 계좌 이체 개요
description: 이 문서에서는 SEPA(Single Euro Payments Area) 계좌 이체 및 공급업체에 대한 기타 전자 지불을 포함하는 ISO 20022 계좌 이체에 관한 일반적인 정보를 제공합니다. SEPA 계좌 이체는 한 회사 또는 개인의 다른 회사 또는 개인에 대한 특정한 유형의 유로 지불 방식입니다. 이 항목에서는 계좌 이체 지불 파일을 설정하고 전송하는 방법도 설명합니다.
author: sunfzam
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, VendPaymMode
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "11124"
- intro-internal
ms.assetid: 36b0f870-16d4-4bbb-8da5-e747e69b970d
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc37dde8829abdd26a224adbd788538834f4d320
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451423"
---
# <a name="sepa-credit-transfer-overview"></a>SEPA 계좌 이체 개요

[!include [banner](../includes/banner.md)]

이 문서에서는 SEPA(Single Euro Payments Area) 계좌 이체 및 공급업체에 대한 기타 전자 지불을 포함하는 ISO 20022 계좌 이체에 관한 일반적인 정보를 제공합니다. SEPA 계좌 이체는 한 회사 또는 개인의 다른 회사 또는 개인에 대한 특정한 유형의 유로 지불 방식입니다. 이 항목에서는 계좌 이체 지불 파일을 설정하고 전송하는 방법도 설명합니다.

## <a name="what-is-a-credit-transfer-message"></a>계좌 이체 메시지란 무엇인가요?
계좌 이체 메시지는 개시 당사자(회사)가 자신의 계정에서 채권자에게 자금을 이체하기 위해 보내는 요청입니다. 국가/지역별 및 은행별 계좌 이체 메시지 구현이 많이 있습니다. 그중 일부는 한 국가/지역 내에서 사용되고 일부는 표준이 되고 있습니다. 잘 정립된 글로벌 표준 중 하나로 ISO 20022 및 계좌 이체와 같은 개시 메시지가 있습니다. 다음 그림은 선택한 계좌 이체 메시지에 대한 관계 및 적용 범위를 보여줍니다. 
![계좌 이체.](./media/credit-transfer.jpg) 계좌 이체 메시지 

## <a name="what-are-iso-20022-and-sepa-payments"></a>ISO 20022 및 SEPA 지불이란 무엇인가요?
단일 유로 결제 지역(SEPA)는 유럽 집행위원회(European Commission)에 의해 설정되었으며 개인, 기업 또는 조직 및 은행이 위치한 국가/지역과 관계없이 모든 전자 지불이 국내로 간주되도록 규정합니다. 국내 지불과 국경 간 지불 간에 차이가 없습니다. SEPA에는 유럽 연합(EU)의 28개 회원국과 아이슬란드, 리히텐슈타인, 노르웨이, 스위스, 모나코 및 산마리노가 포함됩니다. SEPA는 유럽 경제 지역(EEA) 내에서 지불 거래를 위한 단일 시장을 형성하는 데 도움이 됩니다. 궁극적으로 SEPA는 은행, 기업 및 개인이 함께 작업해야 하는 지불 형식의 수를 줄일 것으로 예상됩니다. 유럽 집행위원회는 지불 서비스 지침(PSD)을 통해 SEPA 지불에 대한 법적 기반을 마련했습니다. 유럽결제위원회(EPC)는 다음 활동을 통해 SEPA를 지원합니다.

-   ISO 20022 범용 금융 업계 메시지 체계 XML 형식을 사용하여 SEPA 전자 지불에 대한 표준을 설정합니다.
-   유로 지불 처리에 대한 규칙과 지침을 설정합니다.

유럽 은행으로 구성된 EPC는 SEPA 결제 수단을 위한 상업 및 기술 프레임워크를 개발합니다. 세 가지 유형의 SEPA 지불이 사용됩니다.

-   계좌 이체
-   자동 이체
-   카드

## <a name="what-is-a-sepa-credit-transfer"></a>SEPA 계좌 이체란 무엇인가요?
SEPA 계좌 이체는 한 회사 또는 개인의 다른 회사 또는 개인에 대한 지불 방식입니다. 지불은 유로로 이루어져야 하며 양 당사자의 IBAN(International Bank Account Number)과 BIC(Bank Identifier Code)를 포함해야 합니다. (BIC는 SWIFT\[Society for Worldwide Interbank Financial Telecommunication\] 코드라고도 알려짐) 또한 거래 비용은 양 당사자 간에 공유되어야 합니다. 당사자 간에 발생하는 계좌 이체는 EPC에서 지정한 대로 ISO 20022 지불 처리 표준 및 XML 형식을 준수하는 XML 파일을 사용해야 합니다.

## <a name="how-is-a-credit-transfer-implemented"></a>계좌 이체는 어떻게 구현됩니까?
유럽 국가의 계좌 이체 지불 형식은 Microsoft Dynamics 365 Finance의 전자 보고(ER) 및 지불 방법 기능을 사용하여 구현됩니다. 다른 지역에서 사용되는 몇 가지 계좌 이체 형식은 여전히 기존 지불 프레임워크를 사용합니다. 다른 많은 형식 중에서 사용할 수 있는 ISO 20022 계좌 이체 파일 형식이 12가지 있습니다. 이러한 내보내기 형식은 SEPA ISO 20022 XML 표준을 따릅니다. EPC가 발표한 SEPA Credit Transfer Scheme Rulebook의 버전 8.2에 지정된 대로 사용되는 국가/지역에 대한 비-유로 지불 이체 및 유로 지불을 생성하는 데 사용됩니다. 계좌 이체를 구현하기 전에 은행에 연락하여 전자 뱅킹 파일을 업로드하는 데 필요한 소프트웨어를 받아야 합니다. 해당 소프트웨어를 사용하여 지불 주문이 포함된 XML 파일을 은행으로 전송합니다.

## <a name="what-credit-transfer-formats-are-currently-supported"></a>현재 지원되는 계좌 이체 형식은 무엇인가요?
항상 Microsoft Dynamics Lifecycle Services(LCS)의 공유 자산 라이브러리로 이동하여 자산 유형이 **GER 구성** 인 사용 가능한 파일의 최신 목록을 확인해야 합니다. 다음 섹션인 "무엇을 설정해야 하나요?"에는 사용 가능한 구성을 검토하고 선택한 구성을 가져올 수 있도록 LCS 리포지토리를 만드는 방법을 설명하는 항목에 대한 링크를 제공합니다.

## <a name="what-do-i-have-to-set-up"></a>무엇을 설정해야 하나요?
-   계좌 이체 파일을 만들려면 먼저 하나 이상의 활성 계좌 이체 구성을 ER 구성으로 가져와야 합니다. 이에 대한 지침은 [Lifecycle Services에서 전자 보고 구성 다운로드](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md)를 참조하세요.
-   지급 계정 지불 방법을 구성할 때 **일반 전자 보고** 확인란을 선택하고 적절한 신용 이체 형식(예: **ISO 20022 계좌 이체(AT)**)을 내보내기 형식 구성으로 선택합니다.
-   법인 및 은행 계좌 정보도 설정해야 합니다.
-   유효한 계좌 이체 지불을 생성하려면 은행 계좌 번호, IBAN 및 SWIFT 코드(BIC) 또는 기타 ID가 필요합니다. 따라서 공급업체 은행 계좌와 이체를 요청하는 조직의 은행 계좌를 설정해야 합니다.
-   계좌 이체 메시지에 참조된 당사자의 부가가치세(VAT) 번호와 같은 추가 정보가 필요할 수 있습니다. 이 정보는 요청 시 공급업체 및 법인에 대해 설정해야 합니다.
-   대부분 ISO 20022 기반 결제 방법인 일부 지급 계정 지불 방법에는 **서비스 유형** = **SLEV** 와 같은 **지불 형식 코드 세트** 에 대한 추가 설정이 필요할 수 있습니다. 이러한 코드는 지불 처리 중 지불 거래에 대한 추가 태깅으로 사용됩니다. **범주 목적**, **요금 부담자**, **현지 수단** 및 **서비스 수준** 과 같은 결제 코드의 기본값은 두 곳에서 설정할 수 있습니다. 첫 번째는 **지급 계정 지불 분개장 헤더** 이고 두 번째는 **지급 계정 지불 방법** 입니다. 지불 분개장 라인 생성 시 지불 분개장 헤더에 설정된 지불 코드 값은 분개장 라인으로 이전되며, 설정되지 않은 경우 지불 방법의 값이 사용됩니다.

## <a name="what-parameters-are-available-for-generating-credit-transfer-payments"></a>계좌 이체 지불을 생성하는 데 사용할 수 있는 매개 변수는 무엇인가요?
특정 매개 변수 목록은 계좌 이체 형식에 따라 다릅니다. 다음 표는 공급업체 지불 분개장에서 독일에 대한 ISO 20022 계좌 이체 지불 파일을 생성할 때 사용할 수 있는 매개 변수를 보여줍니다. **백그라운드에서 실행** 탭에 있는 옵션을 사용하여 일괄 처리 모드로 지불 생성을 실행할 수 있습니다.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>필드</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>일괄 예약</td>
<td>XML 파일에 일괄 예약 태그를 포함하려면 이 확인란을 선택합니다.</td>
</tr>
<tr class="even">
<td>처리 날짜</td>
<td>은행에서 지불을 처리해야 하는 날짜를 입력합니다.</td>
</tr>
<tr class="odd">
<td>포맷</td>
<td>국가/지역 또는 은행의 요구 사항에 따라 송금 정보 형식을 선택합니다.
<ul>
<li><strong>Strd</strong> – 하나의 결제 라인이 하나의 송장에 대해 정산될 때 구조적 형식을 사용하려면 이 옵션을 선택합니다. 이 옵션은 프랑스, 독일 또는 네덜란드의 국가/지역별 내보내기 형식에는 사용할 수 없습니다.</li>
<li><strong>Ustrd</strong> – 여러 송장에 대해 지불이 정산될 때 비구조적 형식을 사용하려면 이 옵션을 선택합니다. 정산된 송장의 송장 번호를 연결하여 송금 정보로 사용합니다. ISO 20022 가이드라인에 따라 비구조적 송금 정보는 140자로 제한됩니다.</li>
</ul></td>
</tr>
<tr class="even">
<td>송장 수</td>
<td><strong>지불 안내</strong> 보고서가 인쇄되는 송장의 수를 입력합니다.</td>
</tr>
<tr class="odd">
<td>시퀀스 번호</td>
<td>파일을 식별하기 위한 시퀀스 번호를 입력합니다. 시퀀스 번호는 <strong>출석 통지</strong> 보고서에 나타납니다.</td>
</tr>
<tr class="even">
<td>출석 통지 인쇄</td>
<td><strong>출석 통지</strong> 보고서를 인쇄하려면 이 확인란을 선택합니다.</td>
</tr>
<tr class="odd">
<td>인쇄 제어 보고서</td>
<td>지불 정보가 포함된 보고서를 인쇄하려면 이 확인란을 선택합니다.</td>
</tr>
<tr class="even">
<td>첨부 편지 인쇄</td>
<td><strong>지급통지</strong> 보고서를 인쇄하려면 이 확인란을 선택합니다.</td>
</tr>
</tbody>
</table>

## <a name="what-are-ibans-and-bics"></a>IBAN과 BIC란 무엇인가요?
IBAN(International Bank Account Number) 및 BIC(Bank Identifier Code)는 전 세계의 여러 국가/지역에서 모든 계정을 식별하는 데 사용됩니다. 여기에는 34개의 SEPA 국가/지역이 포함됩니다. **SWIFT 코드** 필드에 BIC를 입력하고 **IBAN** 필드에 IBAN을 입력합니다. 채권자의 은행 계좌와 고객의 은행 계좌 모두에 대해 이 필드는 **은행 계좌** 페이지의 **은행 계좌** 탭에 있는 **추가 ID** 빠른 탭에 있습니다. SEPA 지불을 위한 BIC 사용은 더는 시행되지 않습니다.

## <a name="how-do-i-transmit-a-payment-file-to-the-bank"></a>은행에 지불 파일을 전송하려면 어떻게 하나요?
지불을 생성할 때 지불 파일이 생성되고 웹 브라우저에서 사용 가능한 위치에 저장하라는 메시지가 표시됩니다. 다음 단계는 XML 파일을 은행으로 보내는 것입니다. 이 절차는 은행마다 다릅니다. 은행의 지시에 따라 처리를 위해 파일을 은행에 제출하세요.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
