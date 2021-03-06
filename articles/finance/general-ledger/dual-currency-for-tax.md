---
title: 세금에 대한 이중 통화 지원
description: 이 항목에서는 세금 도메인에서 이중 통화 회계 기능을 확장하는 방법과 세금 계산 및 게시에 대한 영향을 설명합니다.
author: EricWang
ms.date: 12/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 449ebe55b8be7ee7ea22b4be7c44162d83fc3c2affbd4d20f4cad235ddb0f772
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450433"
---
# <a name="dual-currency-support-for-sales-tax"></a>판매세에 대한 이중 통화 지원
[!include [banner](../includes/banner.md)]

이 항목에서는 판매세에 대한 이중 통화 회계를 확장하는 방법과 판매세 계산, 게시 및 정산에 미치는 영향을 설명합니다.

Dynamics 365 Finance의 이중 통화 기능은 버전 8.1(2018년 10월)에 도입되었습니다. 이로써 통화 보고에서 회계 항목이 계산되는 방식이 달라졌습니다.

이전 버전에서는 거래가 다음 순서에 따라 보고 통화로 변환되었습니다. 

- 거래 통화 > 거래 금액에 계산된 거래 총액이 회계 통화 > 회계 통화 금액으로 변환되고 보호 통화로 변환되었습니다.

이중 통화 기능을 활성화한 후에는 거래가 다음 순서에 따라 보고 통화로 변환되었습니다.

- 거래 통화 금액 > 보고 통화 금액

이중 통화에 대한 자세한 내용은 [이중 통화](dual-currency.md)를 참조하십시오.

이중 통화가 지원됨에 따라 기능 관리에서 두 가지 새로운 기능을 사용할 수 있습니다. 

- 판매세 변환(버전 10.0.13의 새로운 기능)
- 실현 통화 조정 손익 계정에 판매세 정산을 위한 재무 차원 입력(버전 10.0.17의 새로운 기능)

판매세에 대한 이중 통화 지원은 세금이 세금 통화로 정확하게 계산되고 판매세 정산 잔액이 회계 통화와 보고 통화로 모두 정확하게 계산되도록 합니다.

## <a name="sales-tax-conversion"></a>판매세 변환

**판매세 변환** 매개 변수는 세액을 거래 통화에서 세금 통화로 변환하는 두 가지 옵션을 제공합니다. 

- 회계 통화: 경로는 "거래 통화 금액 > 회계 통화 금액 > 세금 통화 금액"입니다. 회계 통화 환율 유형(원장 설정에서 구성됨)이 통화 변환에 사용됩니다.
- 보고 통화: 경로는 "거래 통화 금액 > 보고 통화 금액 > 세금 통화 금액"입니다. 보고 통화 환율 유형(원장 설정에서 구성됨)이 통화 변환에 사용됩니다.

### <a name="example"></a>예

이 기능을 보여주는 간단한 예는 다음과 같습니다.

원장 및 세금에 대한 통화 설정

| 거래 통화 | 회계 통화 | 보고 통화 | 세금 통화 |
| -------------------- | ------------------- | ------------------ | ------------ |
| EUR                  | USD                 | GBP                | GBP          |

환율

| 원래 통화 | 변환 통화 | 계수 | 환율 |
| ------------- | ----------- | ------ | ------------- |
| EUR           | USD         | 1      | 1.11          |
| EUR           | GBP         | 1      | 0.83          |
| USD           | GBP         | 1      | 0.75          |

다양한 매개 변수 옵션에서 세액 계산

세액 = 100EUR

| 판매세 변환 매개 변수 | 거래 통화(EUR) | 회계 통화(USD) | 보고 통화(GBP) | 세금 통화(GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| 회계 통화             | 100                        | 111                       | 83                       | **83.25**          |
| 보고 통화              | 100                        | 111                       | 83                       | **83**             |

이 매개 변수는 세무 당국의 규정 준수 요구 사항에 따라 구성할 수 있습니다.


### <a name="upgrade-consideration"></a>업그레이드 고려 사항

이 기능은 신규 거래에만 적용됩니다. TAXTRANS 테이블에 이미 저장되어 있지만 아직 정산되지 않은 세금 거래의 경우, 세금 게시 시점의 환율이 이미 누락되어 있으므로 시스템에서 세액을 세금 통화로 다시 계산하지 않습니다.

앞의 시나리오를 방지하려면 미결 세금 거래가 포함되지 않은 새로운(깨끗한) 세금 정산 기간에 이 매개 변수 값을 변경하는 것이 좋습니다. 세금 정산 기간에 이 값을 변경하려면 이 매개 변수 값을 변경하기 전에 현재 세금 정산 기간에 대해 "판매세 정산 및 게시" 프로그램을 실행하십시오.

이 기능은 환전으로 인한 손익이 명확히 나오는 회계 항목을 추가합니다. 판매세 정산 중 재평가가 이루어지면 실현 통화 조정 손익 계정에 항목이 입력됩니다. 자세한 내용은 이 항목의 뒷부분에서 [보고 통화로 세금 정산 자동 잔액 계산](#tax-settlement-auto-balance-in-reporting-currency) 섹션을 참조하십시오.

> [!NOTE]
> 결산 중 대차 대조표 계정인 판매세 계정에서 재무 차원에 대한 정보가 검색되고 손익 계산서 계정인 통화 조정 손익 계정에 입력됩니다. 재무 차원의 값에 대한 제한은 대차 대조표 계정과 손익 계산서 계정 간에 다르므로 판매세 정산 및 게시 프로세스 중에 오류가 발생할 수 있습니다. 계정 구조를 수정하지 않으려면 "실현된 통화 조정 손익 계정에 판매세 정산을 위한 재무 차원 채우기" 기능을 켤 수 있습니다. 이 기능은 통화 조정 손익 계정에 대한 재무 차원을 강제로 파생합니다. 

## <a name="track-reporting-currency-tax-amount"></a>보고 통화 세액 추적

보고 통화로 금액을 추적하기 위해 세금 관련 테이블에 세 개의 새 필드가 추가되었습니다. 이러한 필드는 TAXUNCOMMITTED 및 TAXTRANS 테이블에 있습니다.

- TaxAmountRep: 보고 통화 기준 세액
- TaxBaseAmountRep: 보고 통화 기준 기본 금액
- TaxInCostPriceRep: 보고 통화 기준 공제 불가 금액

TAXUNCOMMITTED 테이블에만 저장되었지만 아직 게시되지 않은 세금에 대해 시스템은 제시 시점의 보고 통화로 세액을 다시 계산하고 TAXTRANS 테이블에 저장합니다.

이 릴리스에는 보고 통화로 세액을 표시하는 보고서 및 양식에 대한 변경 사항이 포함되지 않습니다. 보고서 및 양식에 대한 변경 사항은 향후 릴리스에서 제공될 예정입니다.



## <a name="tax-settlement-auto-balance-in-reporting-currency"></a>보고 통화로 세금 정산 자동 잔액 계산

판매세 변환 경로가 "회계 통화"이거나 단일 세금 정산 기간의 환율 변동과 같은 특정한 이유 때문에 세금 정산 잔액이 보고 통화가 아닌 경우 시스템은 자동으로 회계 항목을 생성하여 세액 차이를 조정하고 원장 설정에서 구성된 실현된 환전 손익 계정에 대해 상쇄합니다.

이 기능을 설명하기 위해 게시 당시 TAXTRANS 테이블의 데이터가 다음과 같다고 가정하고 앞의 예제를 사용해보겠습니다.

| 판매세 변환 매개 변수 | 거래 통화(EUR) | 회계 통화(USD) | 보고 통화(GBP) | 세금 통화(GBP) |
| ------------------------------- | -------------------------- | ------------------------- | ------------------------ | ------------------ |
| 회계 통화             | 100                        | 111                       | 83                       | **83.25**          |
| 보고 통화              | 100                        | 111                       | 83                       | **83**             |

월말에 판매세 정산 프로그램을 실행할 때 회계 항목은 다음과 같습니다.
#### <a name="scenario-sales-tax-conversion--accounting-currency"></a>시나리오: 판매세 변환 = "회계 통화"

| 주 계정           | 거래 통화(GBP) | 회계 통화(USD) | 보고 통화(GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| 미지급 세금/미수 세금 | -83.25                     | -111                      | -83.25                   |
| 세금 정산         | 83.25                      | 111                       | 83.25                    |
| 실현 이익/손실     | 0                          | 0                         | -0.25                    |
| 미지급 세금/미수 세금 | 0                          | 0                         | 0.25                     |

#### <a name="scenario-sales-tax-conversion--reporting-currency"></a>시나리오: 판매세 변환 = "보고 통화"


| 주 계정           | 거래 통화(GBP) | 회계 통화(USD) | 보고 통화(GBP) |
| ---------------------- | -------------------------- | ------------------------- | ------------------------ |
| 미지급 세금/미수 세금 | -83                        | -110.67                   | -83                      |
| 세금 정산         | 83                         | 110.67                    | 83                       |
| 실현 이익/손실     | 0                          | 0.33                      | 0                        |
| 미지급 세금/미수 세금 | 0                          | -0.33                     | 0                        |



자세한 내용은 다음 항목을 참조하세요.

- [이중 통화](dual-currency.md)
- [판매세 개요](indirect-taxes-overview.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
