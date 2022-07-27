---
title: 현금 흐름 예측 활성화
description: 이 항목에서는 Finance Insights에서 현금흐름 예측 기능을 설정하는 방법에 대해 설명합니다.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 763818f70095964d77ff82cf02178367d05eaf23
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8451534"
---
# <a name="enable-cash-flow-forecasting"></a>현금 흐름 예측 활성화

[!include [banner](../includes/banner.md)]

이 항목에서는 Finance Insights에서 현금흐름 예측 기능을 설정하는 방법에 대해 설명합니다.

> [!NOTE]
> 현금 흐름에서 지급 예측을 사용하려면 [고객 지급 예측 활성화](enable-cust-paymnt-prediction.md)에 설명된 대로 고객 지급 예측 기능을 설정해야 합니다.
  
1. **기능 관리** 작업 공간을 열고 다음 단계를 수행하십시오.

    1. **업데이트 확인** 을 선택합니다.
    2. **모두** 탭에서 **현금 흐름 예측** 을 검색합니다. 해당 기능을 찾을 수 없으면 **(미리 보기) 현금 흐름 예측** 을 검색하십시오. 
    3. 기능을 켭니다.

2. **현금 및 은행 관리 \> 현금 흐름 예측 설정** 으로 이동하여 예측에 포함되어야 할 유동성 계정을 추가합니다. 또한 **지급 계정** 및 **수취 계정** 탭에서 지불에 대한 유동성 계정을 설정합니다. 현금 흐름 예측을 다시 계산해야 합니다.

    > [!NOTE]
    > 유동성 계정이 설정되어 있지 않으면 현금 흐름을 생성할 수 없습니다.
    >
    > 현금 흐름 예측 설정 방법에 대한 자세한 내용은 [현금 흐름 예측](../cash-bank-management/cash-flow-forecasting.md)을 참조하십시오.

3. **현금 및 은행 관리 \> 설정 \> Finance Insights(미리 보기) \> 현금흐름 예측(미리 보기)** 으로 이동하여 다음 단계를 수행하십시오.

    1. **현금 흐름 예측** 탭에서 **기능 사용** 을 선택합니다.
    2. **예측 모델 생성** 을 선택합니다.

> [!NOTE]
> **현금 흐름 예측** 모델 교육은 1년 이상에 걸쳐 100건 이상의 거래가 있는 데이터가 필요하다. 1,000건 이상의 트랜잭션이 있는 데이터를 최소 2년 이상 보유하는 것이 좋습니다.

현금 흐름 예측 기능에 대한 자세한 내용은 [현금 흐름 예측](cash-flow-forecast-intro.md)을 참조하십시오.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
