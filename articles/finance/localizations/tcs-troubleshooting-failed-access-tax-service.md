---
title: 세금 서비스에 액세스하지 못함
description: 이 항목에서는 세금 계산 서비스에 액세스하지 못하는 문제를 해결하는 방법을 설명합니다.
author: hangwan
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 02/16/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 48a75cd0c1d91c3b3d9c3fb2e6cab93a76756532
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8451735"
---
# <a name="failed-to-access-tax-service"></a>세금 서비스에 액세스하지 못함

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

이 항목에서는 세금 계산 서비스의 "세금 서비스에 액세스하지 못했습니다" 오류를 수정하는 방법을 설명합니다.

## <a name="symptoms"></a>증상

Microsoft Dynamics 365 Finance에서 **세금** \> **설정** \> **세금 구성** \> **세금 서비스 매개 변수** 로 이동합니다. **일반** 탭에서 **세금 계산 활성화** 옵션을 활성화합니다. 그런 다음 **기능 설정 이름** 필드에서 값을 선택하려고 하면 오류가 발생합니다. 오류 메시지는 "세금 서비스에 액세스하지 못했습니다"라고 나옵니다.

## <a name="cause"></a>원인

이 오류는 Finance에서 세금 계산 서비스에 액세스할 수 없기 때문에 발생합니다.

## <a name="resolution"></a>해결 

1. Microsoft Dynamics Lifecycle Services(LCS)에 로그인합니다.
2. **환경** 페이지의 **환경 추가 기능** 탭에서 **세금 계산** 항목을 찾고 상태를 검토합니다. 상태가 **설치 중** 또는 **설치됨** 일 것입니다. 세금 계산 서비스 추가 기능이 설치되어 있지 않으면 오류가 표시됩니다.

## <a name="mitigation"></a>완화

1. LCS의 **Finance** 페이지에 있는 **Power Platform 통합** 섹션에서 **새 추가 기능 설치** 를 선택합니다.
2. 페이지 하단으로 스크롤하여 **세금 계산** 추가 기능을 설치합니다.
3. Finance 환경으로 돌아가 세금 계산 서비스에 액세스해봅니다.

> [!NOTE]
> 세금 계산 서비스를 설치하기 전에 [세금 계산 서비스 전제 조건](global-get-started-with-tax-calculation-service.md#prerequisites)을 검토하세요.
> 
> **Power Platform 통합** 섹션이 없어 추가 기능을 설치할 수 없는 경우 [추가 기능 개요](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md)를 참조하세요. 추가 기능을 설치한 후에도 오류가 계속 발생하면 시스템 관리자에게 문의하세요.
