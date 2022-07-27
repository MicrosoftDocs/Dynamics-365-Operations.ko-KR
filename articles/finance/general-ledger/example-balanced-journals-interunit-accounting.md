---
title: 부서 간 회계를 위한 균형 잡힌 분개장
description: 이 문서에서는 원장 페이지에서 균형 잡힌 재무 차원을 선택할 때 분개장이 자동으로 균형 조정되는 방법을 보여줍니다.
author: kweekley
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f6ffccb2ee504f182250dbf6d316823efafddf5
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2021
ms.locfileid: "8451126"
---
# <a name="balanced-journals-for-interunit-accounting"></a>부서 간 회계를 위한 균형 잡힌 분개장

[!include [banner](../includes/banner.md)]

이 문서에서는 원장 페이지에서 균형 잡힌 재무 차원을 선택할 때 분개장이 자동으로 균형 조정되는 방법을 보여줍니다. 

계정 항목이 재무 차원 값 수준에서 균형을 이루지 않으면 분개장 균형을 맞추기 위해 추가 계정 항목이 자동으로 생성됩니다. 이러한 계정 항목은 **자동 거래용 계정** 페이지의 **부서 간 - 출금** 및 **부서 간 - 입금** 게시 유형을 사용하여 주 계정을 결정합니다. 예를 들어, 원장 계정의 두 번째 세그먼트인 사업부가 균형 잡힌 재무 차원으로 선택되고 다음과 같은 회계 항목이 생성될 예정이라고 가정해보겠습니다.

| &nbsp;               | &nbsp;    |
|----------------------|-----------|
| 6100 – MSP – OU\_256 | 100.00 DR |
| 6100 – NY – OU\_249  | 100.00 DR |
| 2100 – MSP – OU\_256 | 200.00 CR |

이 경우 다음과 같이 균형이 결정됩니다.

-   사업부 MSP의 경우 = 100.00 CR
-   사업부 NY의 경우 = 100.00 DR

따라서 재무 차원 값 수준에서 분개장 균형을 맞추기 위해 다음 회계 항목이 자동으로 생성됩니다.

| &nbsp;                            | &nbsp;    |
|-----------------------------------|-----------|
| (부서 간 출금) – MSP – OU\_256 | 100.00 DR |
| (부서 간 입금) – NY – OU\_249 | 100.00 CR |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
