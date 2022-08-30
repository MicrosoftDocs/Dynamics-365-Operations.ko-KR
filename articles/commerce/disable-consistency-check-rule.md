---
title: 거래 유효성 검사 프로세스에 사용된 규칙 사용 안 함
description: 이 문서에서는 Microsoft Dynamics 365 Commerce에서 거래 유효성 검사 규칙을 비활성화하는 기능에 대해 설명합니다.
author: analpert
ms.date: 12/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7d566aa3b829dad281528925a341382f9637fdba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884880"
---
# <a name="disable-rules-used-in-the-transaction-validation-process"></a>거래 유효성 검사 프로세스에 사용된 규칙 사용 안 함

[!include [banner](../includes/banner.md)]

소매업체는 저마다 고유한 비즈니스 시나리오와 프로세스를 가질 수 있습니다. 따라서 상거래의 거래 유효성 검사 프로세스에 포함된 모든 규칙이 모든 소매업체에 적용되는 것은 아닙니다. 차이점을 수용하기 위해 Microsoft Dynamics 365 Commerce는 적용할 수 없는 규칙을 비활성화하는 데 사용할 수 있는 기능을 제공합니다.

사용자 환경의 거래 유효성 검사 프로세스에서 사용할 수 있는 규칙 목록을 보고 각 규칙의 상태를 보려면 **Retail 및 Commerce \> Headquarters 설정 \> 매개 변수 \> Commerce 매개 변수** 로 이동하여 **거래 확인** 탭을 선택하십시오. 활성화된 모든 규칙은 **매장 거래 확인** 프로세스 진행 중 거래의 유효성을 검증하는 데 사용되며 거래 정보를 수집하여 거래 명세서에 게시하려면 검증을 통과해야 합니다.

모든 규칙의 상태는 기본적으로 **사용함** 으로 설정됩니다. 따라서 모든 규칙은 상거래 명세서로 가져올 거래의 유효성을 사전에 검증하는 데 사용됩니다. 하나의 규칙을 사용하지 않으려면 그 상태를 **사용 안 함** 으로 변경하십시오. **매장 거래 확인** 프로세스 중에 거래 유효성을 검사할 때 비활성화된 규칙은 고려되지 않습니다.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
