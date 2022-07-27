---
title: 정기 신용 관리 업무
description: 이 토픽에서는 고객의 신용 한도를 관리하는 프로세스의 필수 부분인 정기 작업에 대해 설명합니다.
author: JodiChristiansen
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 398fcd9d45ce0ddfb1f7189e0712f9dac2db012f
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451147"
---
# <a name="periodic-credit-management-tasks"></a>정기 신용 관리 업무

[!include [banner](../includes/banner.md)]

이 토픽에서는 고객의 신용 한도를 관리하는 프로세스의 필수 부분인 정기 작업에 대해 설명합니다.

## <a name="update-risk-scores"></a>위험 점수 업데이트

비즈니스가 발전하고 상황이 변화함에 따라 해당 고객의 신용 위험도 변경될 수 있습니다. 고객에 대한 적절한 신용 한도를 유지하려면 각 위험 점수에 대한 기준을 정기적으로 검토하고 각 고객에 대한 점수를 업데이트해야 합니다. **위험 점수 업데이트** 페이지(**신용 및 수금 \> 정기 작업 \> 신용 관리 \> 위험 점수 업데이트**)를 사용하여 다음 점수를 업데이트할 수 있습니다. 모든 사용자 정의 계산도 처리됩니다.

- **평균 지불일** – 이 점수는 고객이 송장을 지불하는 데 걸리는 평균 일 수입니다.
- **고객 기간** – 이 점수는 고객이 조직의 고객이었던 기간입니다.
- **사업 기간** – 이 점수는 고객이 사업을 해온 연수입니다. **고객** 페이지의 **비즈니스 시작** 필드 값을 사용합니다.
- **미결제 판매 일 수** – 이 점수는 수취 계정 잔액, 판매 수익 및 이전 12개월 기간의 일 수를 기반으로 합니다.
- **평균 잔액** – 이 점수는 이전 12개월 동안의 수취 계정 잔액을 기준으로 합니다.
- **신용 관리 그룹**, **계정 상태** 및 **국가** – 이 점수는 고객의 정보를 사용합니다.

## <a name="update-customer-balance-statistics"></a>고객 잔액 통계 업데이트

**고객 잔액 통계 업데이트** 프로세스를 실행하여 **잔액 통계 조회** 페이지에 표시되는 잔액 통계 계산을 업데이트할 수 있습니다. 이 정보는 **고객** 페이지의 신용 통계 팩트 상자에 표시되는 위험 점수 및 값을 계산하는 데 사용됩니다.

프로세스를 실행하면 단일 고객에 대한 고객 잔액 통계가 업데이트됩니다. 여러 고객에 대해 프로세스를 실행하도록 일괄 작업을 설정하려면 **잔액 통계 계산** 페이지(**신용 관리 \> 정기 작업 \> 잔액 통계 계산**)를 사용할 수 있습니다.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
