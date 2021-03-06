---
title: 임대 게시 유형
description: 이 항목에서는 자산 임대 거래에 사용되는 게시 유형에 관해 설명합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 721463000c05eb1774335ccce1af39468c2aed9f179e5e88d8725f4d265d6870
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450172"
---
# <a name="lease-posting-types"></a>임대 게시 유형

[!include [banner](../includes/banner.md)]

이 항목에서는 자산 임대 거래에 사용되는 게시 유형에 관해 설명합니다.

## <a name="lease-asset"></a>임대 자산

계정은 사용권(ROU) 자산과 연결됩니다. 이 계정은 새로운 리스 회계 표준인 회계 표준 목록 항목 842(ASC 842) 및 국제 재무 보고 표준 16(IFRS 16)에 따라 임대가 처음 인식될 때 출금됩니다. 수정된 임대의 경우 수정으로 인해 임대 부채가 증가하거나 감소하는지에 따라 이 계정이 출금되거나 입금될 수 있습니다.

**분개장 항목 예시:** 초기 인식<br>
**출금:** 임대 자산 XXX<br>
**입금:** 임대 부채 XXX

## <a name="lease-liability"></a>임대 부채

계정은 새로운 IFRS 16 및 ASC 842 표준에 따라 지불이 할인될 때 발생하는 임대 부채와 연결됩니다. 이 계정은 새로운 표준에 따라 임대가 처음 인식될 때 입금됩니다. 임대료에 대해 출금에 기입하고 이자 발생에 대해 입금에 기입합니다.

**분개장 항목 예시:** 초기 인식<br>
**출금:** 임대 자산 XXX<br>
**입금:** 임대 부채 XXX

**분개장 항목 예시:** 이자 발생<br>
**출금:** 이자 비용 XXX<br>
**입금:** 임대 부채 XXX

**분개장 항목 예시:** 임대료<br>
**출금:** 임대 부채 XXX<br>
**입금:** 공급업체 지불/임대료 XXX

## <a name="short-term-lease-liability"></a>단기 임대 부채

계정은 단기 임대 부채 재분류 분개장 기입이 게시될 때 단기 임대 부채와 연결됩니다. 이 계정은 해당 월 말일의 상각 일정에서 단기 부채에 대해 입금됩니다. 단, 익월 1일에 같은 금액이 출금됩니다.

**분개장 항목 예시:** 단기 임대 부채 재분류<br>
**출금:** 임대 부채 XXX<br>
**입금:** 단기 임대 부채 XXX<br>
**출금:** 단기 임대 부채 XXX<br>
**입금:** 임대 부채 XXX

## <a name="depreciation-expense"></a>감가상각 비용

계정은 IFRS 16, ASC 842에 따른 ROU 자산 및 IAS 17 및 ASC 840에 따른 금융 리스의 감가상각과 관련된 비용과 연결되어 있습니다. 이 계정은 ROU 자산이 매월 감가상각될 때 출금됩니다.

**분개장 항목 예시:** 감가상각 발생<br>
**출금:** 감가상각 비용 XXX<br>
**입금:** 감가상각 누계 XXX

## <a name="gainloss-on-lease-modification"></a>임대 변경 손익

계정은 임대 변경으로 인해 발생하는 모든 손익과 연결되어 있습니다. 임대 변경으로 인해 ROU 자산의 장부금액을 초과하는 금액만큼 임대 부채가 감소하는 경우 임대 변경 중에 이익이 발생할 수 있습니다.

예를 들어 임대 부채의 현재 장부 가치가 $150,000이고 ROU 자산의 장부 가치가 $100,000인 임대가 있습니다. 임대가 수정되고 이 수정으로 $40,000의 미래 최소 임대료(PVFMLP)의 새로운 현재 가치가 생성됩니다. 따라서 임대 부채는 $110,000($150,000 – $40,000)로 차감됩니다. ROU 자산은 $100,000에 불과하기 때문에 $110,000가 감소하면 자산이 0(영)을 초과하여 감소합니다. 따라서 회계 지침에서는 나머지를 이익 계정에 기재해야 한다고 명시하고 있습니다. 이 경우 최종 분개장 기입은 $110,000에 대한 임대 부채에 대한 출금, $100,000에 대한 임대 자산에 대한 입금, $10,000에 대한 이익 계정에 대한 입금이 됩니다.

**분개장 항목 예시:** 임대 변경<br>
**출금:** 임대 부채 XXX<br>
**입금:** 임대 자산 XXX<br>
**입금:** 이득 XXX

## <a name="accumulated-depreciation"></a>감가상각 누계

계정은 ROU 자산의 반대 자산 계정과 연결됩니다. 이 계정은 감가상각비가 게시될 때 입금됩니다.

**분개장 항목 예시:** 감가상각 발생<br>
**출금:** 감가상각 비용 XXX<br>
**입금:** 감가상각 누계 XXX

## <a name="variable-payment"></a>변동 지불

계정은 ASC 842, ASC 840 및 IAS 17 임대에 따른 지수 재평가에 의해 생성된 변동 임대료와 연결되어 있습니다. 임대료 납부 일정에서 **변동 납부** 열에 변동 납부가 포함됩니다. 이 계정은 변동 지급이 포함된 지급 일정 라인에 대해 송장이 생성될 때 출금됩니다.

**분개장 항목 예시:** 임대료<br>
**출금:** 임대 부채 XXX<br>
**출금:** 변동 지불 XXX<br>
**입금:** 공급업체 지불/임대료 XXX

## <a name="deferred-rent-asset-liability"></a>지연 임대 자산(부채)

계정은 지연 임대 처리 리스로 생성된 지연 임대 자산 또는 부채와 연결되어 있습니다. 이 계정은 임대 지불 금액이 기간의 정액 임대료 비용보다 많은 경우 지연 임대 처리 리스에 대해 송장이 게시될 때 출금됩니다. 임대료가 해당 기간의 정액 임대료보다 적은 경우에 입금됩니다.

**분개장 항목 예시:** 임대료(지연 임대 처리 리스)<br>
**출금:** 임대 비용 XXX<br>
**입금:** 지연 임대 부채 XXX<br>
**입금:** 공급업체 지불/임대료 XXX

## <a name="lease-expense"></a>임대 비용

계정은 임대가 지연 임대 처리 리스로 분류되는 경우 임대 비용과 연결됩니다. 이 계정은 지연 임대 처리 리스에 대해 송장이 게시될 때 출금됩니다.

**분개장 항목 예시:** 임대료(지연 임대 처리 리스)<br>
**출금:** 임대 비용 XXX<br>
**입금:** 지연 임대 부채 XXX<br>
**입금:** 공급업체 지불/임대료 XXX

## <a name="impairment-expense"></a>손상 비용

임대가 손상된 경우 계정이 게시됩니다. 이 계정은 출금되는 반면 ROU 자산 계정은 직접 입금됩니다.

**분개장 항목 예시:** 임대료<br>
**출금:** 손상 비용 XXX<br>
**입금:** ROU 자산 XXX

## <a name="lease-payment"></a>임대료

**공급업체에 지불** 매개 변수가 꺼져 있는 경우 계정이 게시됩니다. 이 계정은 매개 변수가 꺼져 있는 경우 지불해야 하는 공급업체 대신에 입금됩니다.

**분개장 항목 예시:** 임대료<br>
**출금:** 임대 부채 XXX<br>
**입금:** 임대료 XXX

## <a name="expense-type-postings"></a>비용 유형 게시

각 비용 유형에 대해 선택된 계정은 해당 비용 유형에 대한 지불이 생성될 때 출금됩니다. 예를 들어 **보험** 비용 유형에 대해 지정된 계정은 보험 비용에 대한 집행 비용 일정에서 송장 또는 지불 분개장 항목이 생성될 때마다 출금됩니다.

**분개장 항목 예시:** 보험료 지불<br>
**출금:** 보험료 비용 유형 계정 XXX<br>
**입금:** 상쇄 계정 XXX

> [!NOTE]
> 상쇄 계정은 집행 비용 지급 일정에 대한 라인의 임대 수준에서 선택됩니다. 이 상계 계정은 공급업체 또는 원장 계정과 연관될 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
