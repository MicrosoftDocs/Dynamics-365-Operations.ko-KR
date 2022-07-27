---
title: 자유 텍스트 송장 수정
description: 이 문서에서는 전기된 자유 텍스트 송장을 수정하고 수정된 송장으로 재발행하는 방법에 대해 설명합니다.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf4503e3d4b200219d6b444b69c866871d21787d
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2021
ms.locfileid: "8451156"
---
# <a name="correct-a-free-text-invoice"></a>자유 텍스트 송장 수정

[!include [banner](../includes/banner.md)]

이 문서에서는 전기된 자유 텍스트 송장을 수정하고 수정된 송장으로 재발행하는 방법에 대해 설명합니다.

이미 전기된 자유 텍스트 송장을 수정하려면 전기된 무료 텍스트 송장을 엽니다. **송장** 페이지에서 **취소** 를 선택한 다음 **송장 수정** 을 선택합니다. 이유 코드를 선택하고 설명을 추가한 다음 수정된 새 송장의 날짜를 선택합니다. 수정된 송장을 수정하고 전기할 수 있습니다. 

수정된 송장을 전기하면 원본 송장 금액과 동일한 대변 금액에 대해 취소 송장이 생성됩니다. 따라서 원본 송장과 취소 송장의 합산 잔액은 0입니다. 취소 송장은 원본 송장에 대해 정산됩니다. 

수정된 송장을 전기하면 3개의 송장이 생성됩니다.

-   **원본 송장** – 수정하는 정보가 포함된 송장.
-   **취소 송장** – 가장 최근에 수정된 송장을 취소하기 위해 생성된 시스템 생성 대변 송장입니다.
-   **수정된 송장** – 수정된 송장 정보가 포함된 송장.

다음 두 가지 방법으로 취소 송장 및 수정 송장을 식별할 수 있습니다.

-   **모든 무료 텍스트 송장** 페이지에는 **수정** 열이 있어 어떤 송장이 취소된 송장과 수정된 송장인지 확인할 수 있습니다.
-   자유 텍스트 송장의 헤더는 **취소 송장 '\[송장 번호\]'** 또는 **수정된 송장 '\[송장 번호\]'** 의 상태를 보여줍니다.

> [!NOTE]
> 이 기능은 **자유 텍스트 송장 수정** 구성 키를 선택한 경우에만 사용할 수 있습니다. 구성 키를 활성화하는 방법에 대한 자세한 내용은 [유지 관리 모드](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) 토픽의 구성 키 활성화(또는 비활성화) 섹션을 참조하십시오. 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
