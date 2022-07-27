---
title: 세금 계산 매개 변수의 빈 세금 기능 목록
description: 이 항목에서는 세금 계산 매개 변수 페이지의 세금 기능 목록이 비어 있는 문제를 해결하는 방법을 설명합니다.
author: wangchen
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 5b87499042c9c4bfe76e182b170adf4f1cfeac4b
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8451741"
---
# <a name="empty-tax-feature-list-in-tax-calculation-parameters"></a>세금 계산 매개 변수의 빈 세금 기능 목록

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="symptom"></a>증상

Microsoft Dynamics 365 Finance에서 사용할 수 있도록 Regulatory Configuration Service(RCS)에 기능을 게시했습니다. 그러나 Finance를 열고 **세금** \> **설정** \> **세금 구성** \> **세금 계산 매개 변수** 로 이동해보면 **기능 설정 이름** 필드에 값을 선택하려고 하면 값 목록이 비어 있습니다.

## <a name="reason"></a>이유

이 문제는 일반적으로 Finance 환경과 RCS 환경이 같은 테넌트에 있지 않기 때문에 발생합니다.

### <a name="rcs-tenant"></a>RCS 테넌트

다음 단계에 따라 RCS 테넌트의 ID를 찾습니다.

1. 전체 RCS URL을 복사합니다. URL은 `https://rcs-rts-sf-ed22b5aeea8-int-westus2.configure.global.int.dynamics.com/namespaces/817ff7a0-0d77-4aba-9360-3c9749e2c5de/?cmp=dat&mi=RCSFeatureDomainsWorkspace`와 비슷합니다.
2. InPrivate 브라우저 창을 열고 주소 표시줄에 RCS URL을 붙여넣은 다음 **Enter** 를 선택합니다. RCS 테넌트 ID를 찾을 수 있는 로그인 페이지로 이동됩니다. 예를 들어 로그인 페이지의 URL이 `https://login.microsoftonline.com/d335a570-a05b-4bc5-8eb3-c42c65f9560d`인 경우 테넌트 ID는 `https://login.microsoftonline.com/` 다음에 나오는 내용, 즉 **d335a570-a05b-4bc5-8eb3-c42c65f9560d** 입니다.

### <a name="finance-environment-tenant-id"></a>Finance 환경 테넌트 ID

Finance 환경에 대한 테넌트 ID를 찾으려면 RCS 테넌트를 찾기 위해 수행한 것과 같은 단계를 따르세요. 그러나 전체 RCS URL 대신 Finance 환경의 전체 URL을 복사하여 붙여넣습니다.

## <a name="resolution"></a>해결

두 테넌트 ID가 다른 경우 이 항목에서 설명하는 문제가 발생한 것입니다. 같다면 관련 없는 문제가 발생한 것입니다. 이 경우 Microsoft 지원에 문의하는 것이 좋습니다.

### <a name="solution-1"></a>해결 방법 1

Finance 환경이 로그인된 동일한 테넌트에 RCS 환경에 로그인합니다. 그런 다음 세금 기능을 만들고 게시합니다.

### <a name="solution-2"></a>해결 방법 2

RCS의 Finance 테넌트와 세금 기능을 공유합니다.

1. RCS에서 **세계화 기능** \> **세금 계산** 으로 이동합니다.
2. 공유할 기능을 선택한 다음 **조직** 탭에서 **공유 대상** 을 선택합니다.
3. **조직 도메인 이름** 필드에 이름을 입력합니다. 예를 들어 **contoso.onmicrosoft.com** 을 입력합니다.
4. **공유** 를 선택합니다.

![외부 조직과 공유 드롭다운 대화 상자.](media/ShareTaxFeature.png)
