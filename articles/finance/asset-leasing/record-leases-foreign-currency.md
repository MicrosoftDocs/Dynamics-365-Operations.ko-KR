---
title: 외화로 임대 기록
description: 이 항목에서는 임대를 회계 또는 보고 통화가 아닌 다른 통화로 기록하는 방법을 설명합니다.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 91bf3f91614f0dd4835c253456128c9ced046749c0e13383590e01dfd436c921
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450691"
---
# <a name="record-leases-in-foreign-currencies"></a>외화로 임대 기록

[!include [banner](../includes/banner.md)]

회계 통화 또는 보고 통화 이외의 통화인 임대에 대한 자산 임대 계정은 **원장 설정** 페이지에서 설정합니다. 모든 임대는 해당 트랜잭션 통화로 입력해야 합니다. 즉, 임대 계약에 명시된 통화로 입력해야 합니다. 이 항목에서는 임대를 회계 또는 보고 통화가 아닌 다른 통화로 기록하는 방법을 설명합니다.

임대를 외화로 입력하는 경우 ROU(사용 권리) 자산은 회계 통화와 보고 통화로 모두 감가상각됩니다. 이러한 통화는 **원장 설정** 페이지에서 구성됩니다. 이 방식은 고정 자산에서도 사용됩니다. 외화 임대를 생성할 때 **통화** 필드에서 트랜잭션 통화를 선택합니다.

회계 통화의 환율은 **회계 통화 환율** 필드의 기본값입니다. 보고 통화의 환율은 **보고 통화 환율** 필드의 기본값입니다. 이러한 환율은 임대 개시일에 효력을 가집니다. **회계 통화 환율** 및 **보고 통화 환율** 필드는 **임대 세부 정보** 페이지의 **재무 및 보고 환율 정보** FastTab에 있습니다.

1. **고정 환율** 확인란을 선택하여 자동으로 입력된 환율을 재정의한 다음 새 환율을 입력합니다.
2. 다른 필드에 임대에 필요한 정보를 입력한 다음 **예약 생성** 을 선택합니다.
3. 새 **임대 세부 정보** 페이지에서 **장부** 를 선택합니다.
4. **임대 장부** 페이지의 **재무 및 보고 환율 정보** 탭에서 **회계 통화 초기 사용 권한 자산** 및 **보고 통화 초기 사용 권한 자산** 필드의 값을 확인합니다. 이러한 각 필드는 환산된 ROU 자산 잔액을 해당 통화로 표시합니다. 이러한 필드는 재무 정보를 변경할 때마다 업데이트됩니다. 지급 일정을 확인하기 전에 **일정 만들기** 를 선택합니다.

    초기 인식 저널 항목은 임대에 나열된 통화 환율을 사용하는 ROU 자산을 기록합니다. 저널 항목에는 **회계 통화 초기 사용 권한 자산** 및 **보고 통화 초기 사용 권한 자산** 필드의 값도 포함됩니다.

## <a name="subsequent-measurement-for-foreign-currency-leases"></a>외화 임대에 대한 후속 측정

감가상각 일정에는 보고 통화, 회계 통화 및 트랜잭션 통화로 예상되는 감가상각 금액이 표시됩니다.

보고 통화 또는 회계 통화로 ROU 자산 잔액 및 감가상각 금액을 보려면 **자산 감가상각 예약** 페이지를 열고 **회계 통화 금액 표시** 또는 **보고 통화 금액 표시** 확인란을 선택합니다.

외화로 표시된 임대에 대해 감가상각 비용 저널 항목을 생성하면 해당 항목은 임대에 나열된 환율을 사용합니다. 또한 **회계 통화 초기 사용 권리 자산** 및 **보고 통화 초기 사용 권리 자산** 필드의 값도 사용합니다.

최종 감가상각 금액은 약간 다른 환율을 사용하여 계산할 수 있으므로, ROU 자산이 회계 통화와 보고 통화 모두에서 완전히 감가상각될 수 있습니다.

임대가 **지연 임대** 로 재분류된 경우, 시스템은 회계 및 보고 통화가 이미 정의된 경우 자동으로 환율을 지웁니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
