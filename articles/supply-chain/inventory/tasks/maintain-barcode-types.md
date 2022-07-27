---
title: 바코드 유형 유지
description: 이 절차에서는 불출 목록 보고서의 일부로 사용할 수 있는 새 바코드 정의를 설정하는 방법을 보여줍니다.
author: yufeihuang
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b689d1fc85d59ac87efa1903fd7122ae5ff011da
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448378"
---
# <a name="maintain-bar-code-types"></a>바코드 유형 유지

[!include [banner](../../includes/banner.md)]

이 절차에서는 불출 목록 보고서의 일부로 사용할 수 있는 새 바코드 정의를 설정하는 방법을 보여줍니다. 데모 데이터 회사 USMF에서 이 절차를 수행하거나 자신의 데이터를 사용할 수 있습니다. USMF를 사용하는 경우 표시된 예제 값을 사용할 수 있습니다. 이러한 작업은 일반적으로 창고 관리자가 수행합니다.

1. **바코드** 로 이동합니다.
1. **새로 만들기** 를 선택합니다.
1. **바코드 설정** 필드에 값을 입력합니다.
1. **설명** 필드에 값을 입력합니다.
1. **바코드 유형** 필드에서 옵션을 선택합니다.
    * USMF를 사용하는 경우 '코드 39'를 선택할 수 있습니다.
1. **마스크 ID** 필드에서 바코드 마스크 ID를 지정합니다. 바코드 마스크는 바코드를 생성하고 POS(Point of Sale) 시스템으로 스캔되는 바코드를 빠르게 식별하는 데 사용됩니다. 자세한 내용은 [바코드 마스크 설정](../../../commerce/set-up-bar-code-masks.md)을 참조하세요.
1. **크기** 필드에 숫자를 입력합니다.
1. **최대 길이** 필드에 숫자를 입력합니다.
1. **저장** 을 선택합니다.
1. 페이지를 닫습니다
1. **재고 및 창고 관리 매개 변수** 로 이동합니다.
1. **바코드 설정** 필드에 값을 입력하거나 선택합니다.
    * 이전에 생성한 바코드 설정을 선택하지만 바코드 형식은 프로세스에 사용된 레코드 유형의 고유 식별자 형식과 일치해야 합니다. 예를 들어 피킹 경로의 경우 바코드 형식은 일반적으로 숫자 시퀀스인 피킹 경로 참조 형식과 일치해야 합니다.  
1. **저장** 을 선택합니다.
1. 페이지를 닫습니다



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
