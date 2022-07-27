---
title: 고급 은행 조정 개요
description: 이 문서에서는 고급 은행 조정 프로세스의 흐름을 설명합니다. 고급 은행 조정 기능을 사용하면 은행 거래 내에서 자동으로 조정될 수 있는 은행 거래 내역서를 가져올 수 있습니다.
author: panolte
ms.date: 06/20/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "22104"
- intro-internal
ms.assetid: b0705653-1fa6-4d94-9728-bcf9fb387ad1
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ebddf6c77df227f896e6f275f741ea69fb68474
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8451393"
---
# <a name="advanced-bank-reconciliation-overview"></a>고급 은행 조정 개요

[!include [banner](../includes/banner.md)]

이 문서에서는 고급 은행 조정 프로세스의 흐름을 설명합니다. 고급 은행 조정 기능을 사용하면 은행 거래 내에서 자동으로 조정될 수 있는 은행 거래 내역서를 가져올 수 있습니다.

고급 은행 조정 기능을 사용하면 은행 거래 내역서를 가져올 수 있습니다. 가져온 은행 거래 내역서는 은행 거래 내에서 자동으로 조정될 수 있습니다. 다음은 고급 은행 조정 흐름의 단계입니다.

1.  은행 거래 내역서 가져오기를 설정합니다.
    -   데이터 항목 프레임워크를 통해 은행 거래 내역서를 가져옵니다.
    -   ISO20022, BAI2 및 MT940이라는 세 가지 일반적인 은행 거래 내역서 형식이 내장되어 있습니다.
    -   기능을 모든 형식으로 확장할 수 있습니다.

2.  고급 은행 조정에 사용할 번호 시퀀스를 설정하고 은행 조정 대응 규칙을 정의합니다.
    -   조정 매칭 규칙은 조정 프로세스 중에 은행 거래 내역서 라인 및 Microsoft Dynamics 365 Finance 은행 거래 라인을 필터링하는 데 사용되는 기준 세트입니다. 비즈니스 관행에 따라 둘 이상의 일치 규칙을 설정하여 조정 프로세스를 자동화하고 최적화할 수 있습니다.

3.  은행 거래 내역서와 금융 은행 거래를 조정합니다.
    -   자동 매칭 및 조정 분개 생성을 수행합니다.
    -   은행 거래 내역과 금융 은행 거래를 나란히 봅니다.
    -   금융 거래가 은행 거래 명세서에는 표시되지만 금융 앱에는 표시되지 않는 경우 자동으로 게시됩니다.
    -   조정 명세서를 생성합니다.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]