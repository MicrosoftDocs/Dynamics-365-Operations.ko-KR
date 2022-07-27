---
title: Global Inventory Accounting의 Power BI 활성화
description: 이 토픽에서는 Global Inventory Accounting의 Microsoft Power BI을 활성화하는 방법에 대해 설명합니다.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f0a8f5948d9e30eb220aa8177a4b9718223a4f9d
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2022
ms.locfileid: "8449791"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a>Global Inventory Accounting의 Power BI 활성화

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!--KFM: Preview until 4/30/2022 -->

[PowerBI.com](https://powerbi.com/) 계정의 타일, 대시보드 및 보고서를 Microsoft Dynamics 365 애플리케이션 작업 영역에 고정할 수 있습니다.

## <a name="prerequisites"></a>전제 조건

Power BI 보고를 활성화하려면 다음 사전 요구 사항이 충족되어야 합니다.

- Dynamics 365 애플리케이션의 시스템 관리자여야 합니다.
- [PowerBI.com](https://powerbi.com/) 계정이 있어야 합니다.
- Power BI 계정에 최소한 하나의 대시보드와 하나의 보고서가 있어야 합니다.
- Azure AD(Azure Active Directory) 계정의 관리자여야 합니다.
- Azure AD 도메인은 [PowerBI.com](https://powerbi.com/) 계정에 사용한 것과 동일한 도메인이어야 합니다.

## <a name="setup"></a>설정

Power BI 통합을 설정하려면 다음 단계를 따르세요.

1. [Microsoft Dynamics LCS(Lifecycle Services)](https://lcs.dynamics.com/Logon/Index)에 로그인합니다.
1. **공유 자산 라이브러리** 로 이동하여 자산 유형으로 **Power BI 보고서 모델** 을 선택하고 **Global Inventory Accounting** 패키지를 다운로드합니다. 
1. [PowerBI.com](https://app.powerbi.com/)에 로그인하고 다음 단계에 따라 **Global Inventory Accounting** Power BI 보고서 파일을 업로드합니다.

    1. **새로 만들기** 를 선택합니다.
    1. **파일 업로드** 를 선택합니다.
    1. **Global Inventory Accounting** Power BI 보고서 파일을 선택합니다.

1. 다음 단계에 따라 **Global Inventory Accounting** Power BI 보고서를 구성합니다.

    1. **내 작업 영역** 으로 이동하여 Global Inventory Accounting에 대한 데이터 세트를 찾은 다음 **옵션** 메뉴에서 **설정** 을 선택합니다.
    1. **Global Inventory Accounting 설정** 에서 **매개 변수** 를 확장하고 필요에 따라 모든 매개변수를 업데이트합니다. 특히 다음 설정을 확인하세요.
        1. LCS(**Power Platform 통합** 섹션)의 **Power Platform 환경 정보** 에서 찾은 값을 사용하여 기본 **Dataverse URL** 값을 덮어씁니다.
        1. LCS의 **환경 세부 정보**(**환경 관리** 섹션)에 있는 값을 사용하여 기본 **환경 ID** 값을 덮어씁니다.
        1. **데이터 원본 자격 증명** 섹션의 **CDS** 레이블 옆에 있는 **자격 증명 편집** 링크를 선택합니다. 그런 다음 **OAuth2** 인증 방법을 사용하여 Dataverse 계정에 로그인합니다.
    1. **내 작업 영역 \> 보고서 \> Global Inventory Accounting** 에서 찾은 Power BI 보고서가 이제 올바르게 작동하고 시스템의 콘텐츠를 표시하는지 확인하세요.

1. [PowerBI.com 통합 구성](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process)에 설명된 대로 애플리케이션을 등록합니다.
1. 다음 단계에 따라 **Global Inventory Accounting** Power BI 보고서 파일을 Dynamics 365 Supply Chain Management에 통합합니다.

    1. **시스템 관리 \> 설정 \> PowerBI.com 구성** 으로 이동합니다.
    1. **편집** 을 선택합니다.
    1. **PowerBI.Com 통합 활성화** 를 선택합니다.
    1. **애플리케이션 ID** 필드에 애플리케이션 ID를 입력합니다.
    1. **애플리케이션 키** 필드에 애플리케이션 키를 입력합니다.
    1. **저장** 을 선택합니다.

1. Power BI 로그인 대화 상자가 나타나도록 페이지를 새로 고칩니다.
1. **옵션** 탭에서 보고서 **카탈로그 열기** 를 선택한 다음 이전에 업로드한 **Global Inventory Accounting** Power BI 보고서 파일을 선택합니다.
1. 페이지를 새로 고칩니다. 보고서가 추가되었는지 확인해야 합니다.
1. **Power BI 보고서** 에서 **Global Inventory Accounting** 링크를 선택합니다.

자세한 내용은 [PowerBI.com 통합 구성](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md)을 참조하세요.
