---
title: 비용 개체 컨트롤러에 대한 액세스 권한
description: 이 토픽에서는 비용 개체 컨트롤러에 대한 액세스 권한에 대한 정보를 제공합니다.
author: AndersGirke
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c30a7c2765647aad17a475ba8705b8e688d166593adf242fcd15d90e49334189
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8450334"
---
# <a name="access-rights-for-cost-object-controllers"></a>비용 개체 컨트롤러에 대한 액세스 권한

[!include [banner](../includes/banner.md)]

**비용 관리** 작업 영역은 관리자가 비용 개체의 성과를 볼 수 있는 중심 지점입니다. 이 작업 영역을 통해 관리자는 원가 회계사가 아니더라도 원가 회계 데이터를 사용할 수 있습니다. 보안상의 이유로 관리자는 자신이 담당하는 특정 원가 개체와 관련된 원가 회계 데이터만 볼 수 있어야 합니다.

원가 회계에는 네 가지 고유한 역할이 있습니다.

| 역할 이름               | 라이선스      |
|-------------------------|--------------|
| 원가 회계 관리자 | 활동     |
| 원가 회계사         | Operations   |
| 원가 회계 직원   | Operations   |
| 비용 개체 컨트롤러  | 팀 구성원 |

이 토픽에서는 **비용 개체 컨트롤러** 역할을 관리자에게 할당하는 방법에 대해 설명합니다.

**비용 개체 컨트롤러** 역할이 관리자에게 할당되면 관리자는 다음 작업을 수행할 수 있습니다.

- **비용 관리** 작업 영역(클라이언트에서)에 액세스합니다.

    - 드릴스루 및 드릴스루 환경을 지원하는 페이지에 대한 보기 액세스 권한이 있습니다.

- **비용 관리** 작업 영역(모바일 애플리케이션에서)에 액세스합니다.

> [!NOTE]
> **비용 개체 컨트롤러** 역할은 사용자가 데이터에 액세스하고 볼 수 있는 비용 개체를 제어하지 않습니다. 행 수준 보안은 차원 계층 및 액세스 목록 계층을 통해 제공됩니다.

## <a name="grant-access-rights"></a>액세스 권한 허용
다음 예는 차원 계층 구조가 어떤 모습일 수 있는지 보여줍니다.

**차원 계층 세부 정보**

| 차원 계층 이름 | 차원    | 차원 계층 유형 이름      | 액세스 목록 계층 |
|--------------------------|--------------|------------------------------------|-----------------------|
| 조직             | 비용 센터 | 차원 분류 계층 | **예**               |

계층 디자이너에서 **사용자** 빠른 탭을 사용하여 각 노드에 하나 이상의 사용자 ID를 삽입할 수 있습니다.

|             노드                 | 사용자            | 차원 구성원에서     |   차원 구성원으로   |
|-----------------------------------|------------------|---------------------------|-------------------------|
| 조직                      | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;관리자                 | 4월            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finance   | Alicia           | CC002                     | CC003                   |
|                                   |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;HR        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;생산            | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;포장 | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;조립  | Chris            | CC006                     | CC006                   |

> [!NOTE]
> 비용 회계는 비용 회계의 모든 항목을 표시할 수 있도록 계층의 최상위 수준에 할당해야 합니다.

액세스 목록 계층 구조 및 해당 보안 설정을 적용하기 전에 **원가 개체 차원 구성원에 대한 보기 액세스 사용** 옵션을 **원가 회계 매개 변수** 페이지(**원가 회계** > **설정** > **매개 변수**)의 **일반** 탭에서 **예** 로 설정해야 합니다.

액세스 목록 계층 설정은 다음 영역에 표시되는 데이터를 제어하기 위해 사용됩니다.

- **비용 관리** 작업 영역(클라이언트에서):

    - 드릴스루에 사용되는 페이지의 데이터

- **비용 제어** 작업 영역(모바일 애플리케이션에서):

    - 카드 잔액

- Microsoft Power BI:

    - Power BI 시각화에 표시되는 데이터
    - Dynamics 365 Finance 클라이언트에 내장된 데이터 Power BI 시각화

> [!IMPORTANT]
> - 액세스 목록 계층이 Power BI의 데이터에 영향을 미치기 전에 Power BI의 액세스 목록 계층과 행 수준 보안이 쌍을 이루어야 합니다. 자세한 내용은 [비용 회계 콘텐츠 팩을 위한 보안 설정](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)을 참조하십시오.
> - 이 토픽에서는 **비용 제어** 작업 영역을 사용하기 전에 준비해야 하는 사전 요구 사항을 보여줍니다.

추가 리소스

- [비용 관리 작업 영역](cost-control-workspace.md)
- [차원 계층](dimension-hierarchy.md)
- [비용 회계 콘텐츠 팩에 대한 보안 설정](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
