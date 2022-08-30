---
title: 재무 보고 FAQ
description: 이 문서에서는 재무 보고에 대해 자주 묻는 몇 가지 질문에 대한 답변을 제공합니다.
author: jinniew
ms.date: 07/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5981946a4bba2c58402f4cf566bfa008de67363b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901374"
---
# <a name="financial-reporting-faq"></a>재무 보고 FAQ

이 문서에서는 재무 보고에 대해 자주 묻는 질문에 대한 답변을 제공합니다.

## <a name="how-do-i-restrict-access-to-a-report-by-using-tree-security"></a>트리 보안을 사용하여 보고서에 대한 액세스를 제한하려면 어떻게 하나요?

다음 예에서는 트리 보안을 사용하여 보고서에 대한 액세스를 제한하는 방법을 보여줍니다.

USMF 데모 회사는 일부 재무 보고 사용자가 액세스할 필요는 없는 **대차 대조표** 보고서를 갖고 있습니다. 트리 보안을 사용하여 특정 사용자만 액세스할 수 있도록 단일 보고서에 대한 액세스를 제한할 수 있습니다.

1. Financial Reporter Report Designer에 로그인합니다.
2. **파일 \> 새로 만들기 \> 트리 정의** 를 각각 선택하여 새 트리 정의를 생성합니다.
3. **단위 보안** 열에서 **요약** 라인을 두 번 탭(또는 두 번 클릭)합니다.
4. **사용자 및 그룹** 을 선택합니다.
5. 보고서에 액세스해야 하는 사용자 또는 그룹을 선택합니다.
6. **저장** 을 선택합니다.
7. 보고서 정의에서 새 트리 정의를 추가합니다.
8. 트리 정의에서 **설정** 을 선택합니다. 그런 다음, **보고 단위 선택** 에서 **모든 단위 포함** 을 선택합니다.

## <a name="how-do-i-identify-which-accounts-dont-match-my-balances"></a>내 잔액과 일치하지 않는 계정은 어떻게 식별하나요?

일치하는 잔액이 없는 보고서가 있다면 다음 절차를 사용하여 각 계정과 차이를 확인합니다.

### <a name="in-financial-reporter-report-designer"></a>Financial Reporter Report Designer에서

1. 새 행 정의를 생성합니다.
2. **편집 \> 차원에서 행 삽입** 을 선택합니다.
3. **MainAccount** 를 선택합니다.
4. **확인** 을 선택합니다.
5. 행 정의를 저장합니다.
6. 새 열 정의를 생성합니다.
7. 새 보고서 정의를 생성합니다.
8. **설정** 을 선택하고 이 옵션의 표시를 해제합니다.
9. 보고서를 생성합니다. 
10. 보고서를 Microsoft Excel로 내보냅니다.

### <a name="in-dynamics-365-finance"></a>Dynamics 365 Finance에서

1. **총계정원장 \> 문의 및 신고 \> 시산표** 로 이동합니다.
2. 다음 필드를 설정합니다.

    - **시작 날짜** – 회계 연도의 시작 날짜를 입력합니다.
    - **종료 날짜** – 보고서를 생성할 기간의 날짜를 입력합니다.
    - **재무 차원** – 이 필드를 **주 계정 집합** 으로 설정합니다.

3. **계산** 을 선택합니다.
4. 보고서를 Excel로 내보냅니다.

이제 Financial Reporter Excel 보고서의 데이터를 **시산표** 보고서로 복사하면 **결산 잔액** 열을 비교할 수 있습니다.

## <a name="when-i-design-a-report-in-report-designer-or-when-i-generate-a-financial-report-i-received-the-following-message-the-operation-could-not-be-completed-due-to-a-problem-in-the-data-provider-framework-how-should-i-respond"></a>Report Designer에서 보고서를 디자인하거나 재무 보고서를 생성할 때 '데이터 공급자 프레임워크의 문제로 인해 작업을 완료할 수 없습니다'라는 메시지가 나타납니다. 어떻게 대응해야 할까요?

이 메시지는 재무 보고를 사용하는 동안 시스템이 데이터 마트에서 재무 메타데이터를 검색하려고 할 때 문제가 발생했음을 나타냅니다. 이 문제에 대응하는 방법은 다음의 두 가지가 있습니다.

- Report Designer에서 **도구 \> 통합 상태** 로 이동하여 데이터의 통합 상태를 검토합니다. 통합이 완료되지 않았다면 완료될 때까지 기다리십시오. 그런 다음, 메시지를 받았을 때 진행하던 작업을 다시 시도하십시오.
- 문제를 확인하고 해결하려면 지원팀에 문의하세요. 시스템에 일치하지 않는 데이터가 존재할 수 있습니다. 지원 엔지니어는 서버에서 해당 문제를 확인하고 업데이트가 필요할 수 있는 특정 데이터를 찾는 데 도움을 줄 수 있습니다.

## <a name="how-does-the-selection-of-historical-rate-translation-affect-report-performance"></a>거래발생일 환율 환산의 선택은 보고 실적에 어떤 영향을 미치나요?

거래발생일 환율은 대체로 이익 잉여금, 재산, 공장 및 설비, 지분 계정에 적용됩니다. 거래발생일 환율은 FASB(미국재무회계기준심의회) 또는 GAAP(일반적으로 인정된 회계 원칙)의 제반 지침에 따라 필요할 수 있습니다. 자세한 내용은 [재무 보고의 통화 기능](financial-reporting-currency-capability.md)을 참조하세요.

## <a name="how-many-types-of-currency-rate-are-there"></a>환율은 몇 가지 유형이 있습니까?

다음의 세 가지 유형이 있습니다.

- **현재 환율** – 이 유형은 대체로 대차 대조표 계정에 사용됩니다. 이 환율은 일반적으로 *현물 환율* 로 알려져 있으며 매월 말일 또는 미리 정해진 다른 날짜의 환율일 수 있습니다.
- **평균 환율** – 이 유형은 대체로 손익 계산서(수익/손실) 계정에 사용됩니다. 단순 평균 또는 가중 평균을 계산하도록 평균 환율을 설정할 수 있습니다.
- **거래발생일 환율** – 이 유형은 대체로 이익 잉여금, 재산, 공장 및 설비, 지분 계정에 적용됩니다. FASB 또는 GAAP 지침에 따라 이러한 계정이 필요할 수 있습니다.

## <a name="how-does-historical-currency-translation-work"></a>거래발생일 통화 환산은 어떻게 이루어지나요?

환율은 거래 날짜에 따라 다릅니다. 따라서 각 거래 건은 가장 근접한 환율을 기준으로 하여 개별 환산됩니다.

거래발생일 통화 환산의 경우, 개별 거래 내역 대신 미리 계산된 기간 잔액을 적용할 수 있습니다. 이 동작은 현재 환율 환산의 동작과는 다릅니다.

## <a name="how-does-historical-currency-translation-affect-performance"></a>거래발생일 통화 환산은 실적에 어떤 영향을 미치나요?

보고서에 제시된 데이터가 업데이트되면 거래 내역을 확인하여 금액을 다시 계산해야 하기 때문에 지연이 발생할 수 있습니다. 이러한 지연은 환율이 업데이트되거나 더 많은 거래 건이 기장될 때마다 발생합니다. 예를 들어, 수천 개의 계정이 하루에 두 번씩 거래발생일 환산을 수행하도록 설정된 경우, 보고서의 데이터가 업데이트되기까지 최대 1시간이 지연될 수 있습니다. 반면에 특정 계정의 수가 적다면 보고서 데이터 업데이트 처리 시간을 몇 분 이하로 단축할 수 있습니다.

마찬가지로, 과거 유형 계정에 대한 통화 환산을 적용하여 보고서를 생성하는 경우에는 트랜잭션별 추가 계산이 있습니다. 계정 수에 따라 보고서 생성 시간이 2배 이상 소요될 수 있습니다.

## <a name="what-are-the-estimated-data-mart-integration-intervals"></a>예상되는 데이터 마트 통합 간격은 얼마인가요?

Financial Reporter는 16개의 작업을 사용하여 Dynamics 365 Finance에서 Financial Reporter 데이터베이스로 데이터를 복사합니다. 다음 표는 이러한 16개의 작업을 나열하고 각 작업이 실행되는 빈도를 지정하는 간격을 보여줍니다. 간격은 변경할 수 없습니다.

| 이름                                                       | 간격 | 간격 타이밍 |
|------------------------------------------------------------|----------|-----------------|
| AX 2012 계정 카테고리에서 계정 카테고리로            | 41       | 분         |
| AX 2012 계정에서 계정으로                                | 7        | 분         |
| AX 2012 기업에서 기업으로                               | 300      | 초         |
| AX 2012 기업에서 조직으로                          | 23       | 분         |
| AX 2012 차원 결합에서 차원 결합으로    | 1        | 분         |
| AX 2012 차원 값에서 차원 값으로                | 11       | 분         |
| AX 2012 차원에서 차원으로                            | 31       | 분         |
| AX 2012 환율에서 환율로                    | 17       | 분         |
| AX 2012 회계 연도에서 회계 연도로                        | 13       | 분         |
| AX 2012 총계정원장 거래에서 팩트로                | 1        | 분         |
| AX 2012 조직 계층 구조에서 트리로                   | 3,600    | 초         |
| AX 2012 시나리오에서 시나리오로                              | 29       | 분         |
| AX 2012 트랜잭션 유형 한정자에서 팩트 유형 한정자로 | 19       | 분         |
| 유지 관리 작업                                           | 1        | 분         |
| MR 보고서 정의에서 AX7 재무 보고서로             | 45       | 초         |
| MR 보고서 버전에서 AX 재무 보고서 버전으로         | 45       | 초         |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
