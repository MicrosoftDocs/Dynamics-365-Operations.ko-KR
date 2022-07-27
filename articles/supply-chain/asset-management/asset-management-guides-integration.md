---
title: Dynamics 365 Supply Chain Management(자산 관리)와 Dynamics 365 Guides 통합
description: 이 항목에서는 Microsoft Dynamics 365 Supply Chain Management의 자산 관리 모듈을 Dynamics 365 Guides와 통합하여 일상적인 서비스 및 유지 관리 워크플로에서 혼합 현실 가이드를 활용하는 방법을 설명합니다.
author: johanhoffmann
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 4132992eb5f4b42d43d9ff72cada616fe0573c2f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448096"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a>Dynamics 365 Supply Chain Management(자산 관리)와 Dynamics 365 Guides 통합

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management의 **자산 관리** 모듈을 Dynamics 365 Guides와 통합하여 일상적인 서비스 및 유지 관리 워크플로에서 혼합 현실 가이드를 활용할 수 있습니다. 가이드가 자산 관리 작업 주문과 연결된 경우 Supply Chain Management(Dynamics 365) 모바일 앱에서 작업 주문의 유지 관리 체크리스트를 여는 작업자는 가이드를 사용할 수 있음을 확인합니다. 작업자는 Dynamics 365 Guides HoloLens 앱에서 가이드를 찾아 열 수 있습니다.

## <a name="prerequisites"></a>전제 조건

자산 관리 작업 주문에 가이드를 첨부하려면 먼저 다음 전제 조건을 완료해야 합니다.

- [Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) 버전 10.0.9 이상 설정.
- [Supply Chain Management 앱용 이중 쓰기 켜기](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).
- **MRGuidesFeature** 기능에 대해 [플라이트 설정](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features). (생산 환경의 경우 먼저 지원 티켓을 제출하여 테넌트를 플라이트 그룹에 추가해야 합니다.)
- **라이선스 구성** 페이지에서 [다음 구성 키 설정](/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference):

    - 자산 관리 \> 자산 관리 혼합 현실
    - 혼합 현실 \> 혼합 현실 가이드

- [Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) 버전 200.0.0.96 이상 설정.

## <a name="use-dynamics-365-guides-with-asset-management"></a>자산 관리에 Dynamics 365 Guides 사용

가이드를 연결하려면 자산 관리에서 유지 관리 체크리스트 라인을 사용합니다. 유지 관리 체크리스트 템플릿, 유지 관리 작업 유형 또는 작업 주문을 통해 연결을 만들 수 있습니다. 세 가지 모두 유지 관리 체크리스트 행을 포함하기 때문입니다. 템플릿을 사용하는 모든 유지 관리 작업 유형과 템플릿을 연결할 수 있으므로 템플릿을 사용하면 시간을 절약할 수 있습니다. 예를 들어 유지 관리 작업 유형과 연결된 가이드는 해당 작업 유형을 지정하는 모든 작업 주문과 자동으로 연결됩니다. 반면에 작업 주문과 직접 연결된 가이드는 해당 작업 주문에 대해서만 존재합니다.

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a>가이드를 유지 관리 체크리스트 템플릿과 연결

가이드를 유지 관리 체크리스트 템플릿과 연결하려면 다음 단계를 따르세요.

1. Dynamics 365 Guides PC와 HoloLens 앱을 사용하여 가이드를 만듭니다. 안내서를 만드는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.

    - [PC 앱을 사용하여 가이드 만들기](/dynamics365/mixed-reality/guides/pc-app-overview)
    - [HoloLens 앱을 사용하여 홀로그램 배치](/dynamics365/mixed-reality/guides/hololens-app-overview)

1. Supply Chain Management에서 [유지 관리 체크리스트 템플릿 만들기](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).
1. 생성한 가이드를 새 유지 관리 체크리스트 템플릿의 유지 관리 체크리스트 라인과 연결합니다.

    1. **유지 관리 체크리스트 라인** 빠른 탭에서 가이드를 연결할 라인을 선택합니다.
    1. **관련 가이드** 빠른 탭에서 **가이드 추가** 를 선택합니다.

        ![가이드를 유지 관리 체크리스트 라인과 연결.](media/am-guides-integration-add-guide.png "가이드를 유지 관리 체크리스트 라인과 연결")

    1. **이름** 필드에서 가이드를 선택한 다음 **저장** 을 선택합니다.

        ![이름 필드에서 가이드를 선택합니다.](media/am-guides-integration-select-guide.png "이름 필드에서 가이드 선택")

1. 유지 관리 체크리스트 템플릿을 작업 유형과 연결:

    1. [유지 관리 작업 유형을 만들거나](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) 기존 유지 관리 작업 유형을 선택합니다.
    1. 작업 창에서 **유지 관리 작업 유형 기본값** 을 선택합니다.

        ![유지 관리 작업 유형 기본값 버튼.](media/am-guides-integration-job-defaults.png "유지 관리 작업 유형 기본값 버튼")

    1. 라인을 만든 다음 **저장** 을 선택합니다.

        ![라인을 생성합니다.](media/am-guides-integration-add-line.png "라인 만들기")

    1. 작업 창에서 **유지 관리 체크리스트** 를 선택합니다.

        ![유지 관리 체크리스트 버튼.](media/am-guides-integration-maintenance-checklist.png "유지 관리 체크리스트 버튼")

    1. **유지 관리 체크리스트 라인** 빠른 탭에서 라인을 추가한 다음 **유형** 필드의 값을 **템플릿** 으로 변경합니다.

        ![유형 값 변경.](media/am-guides-integration-checklist-lines.png "유형 값 변경")

    1. **라인 세부 정보** 빠른 탭의 **템플릿** 필드에서 가이드를 연결한 템플릿을 선택한 다음 **저장** 을 선택합니다.

        ![템플릿 선택.](media/am-guides-integration-checklist-line-details.png "템플릿 선택")

1. [작업 주문을 생성](work-orders/manually-created-workorders.md#create-work-order)한 다음 가이드를 연결한 유지 관리 체크리스트 템플릿을 사용하는 유지 관리 작업 유형을 선택합니다. 가이드는 작업 주문과 자동으로 연결됩니다.

    ![유지 관리 작업 유형을 선택합니다.](media/am-guides-integration-create-work-order.png "유지 관리 작업 유형 선택")

1. 작업 주문 및 작업자와 연결된 가이드 보기:

    1. [자산 관리 모바일 작업 영역](asset-management-mobile-workspace.md)을 열어 작업 주문에 액세스합니다.
    1. 작업 주문의 [지 관리 체크리스트를 엽니다](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job).
    1. 관련 가이드를 보려면 체크리스트 라인을 선택합니다.

        ![체크리스트 라인과 관련된 가이드.](media/am-guides-integration-show-guide.png "체크리스트 라인과 관련된 가이드")

    1. HoloLens에서 가이드를 엽니다.

        ![HoloLens에서 가이드를 엽니다.](media/am-guides-integration-hololens-select.png "HoloLens에서 가이드 열기")

> [!NOTE]
> 작업 주문 또는 작업 유형의 유지 관리 체크리스트에서 가이드를 직접 연결할 수도 있습니다.

> [!IMPORTANT]
> 유지 관리 체크리스트 템플릿을 기본 유지 관리 작업 유형과 연결할 때 **유지 관리 작업 유형 기본값** 페이지의 **관련 가이드** 빠른 탭에 템플릿에 연결된 가이드가 표시되지 않는 알려진 문제가 있습니다. 그러나 해당 작업 유형이 **관련 가이드** 빠른 탭의 작업 주문에 적용된 후에 가이드가 나타납니다.

## <a name="see-also"></a>참고 항목

- [이중 쓰기 개요](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [자산 관리 개요](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]