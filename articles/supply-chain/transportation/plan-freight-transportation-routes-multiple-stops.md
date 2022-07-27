---
title: 여러 기착지가 있는 화물 운송 경로 계획
description: 이 문서에서는 Dynamics 365 Supply Chain Management에서 운송 경로를 계획하는 데 사용하는 다양한 요소에 대해 설명합니다.
author: Henrikan
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSHubMaster, TMSLoadBuildTemplates, TMSRateRouteWorkbench, TMSRouteGuide, TMSRoutePlan, TMSRouteWorkbench, WHSLoadTemplate, TMSRouteSchedule, TMSRouteRateDetail
audience: Application User
ms.reviewer: kamaybac
ms.custom: 90013
ms.assetid: 50d6f58c-f1c8-4321-9e83-8445cec57a85
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eff1efd7530c410b392646e39325b58cbd8bcf78
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8448393"
---
# <a name="plan-freight-transportation-routes-with-multiple-stops"></a>여러 기착지가 있는 화물 운송 경로 계획

[!include [banner](../includes/banner.md)]

이 문서에서는 Dynamics 365 Supply Chain Management에서 운송 경로를 계획하는 데 사용하는 다양한 요소에 대해 설명합니다.

여러 기착지가 있는 복잡한 운송 경로에 대해 경로 계획 및 경로 안내를 사용할 수 있습니다. 동일한 경로를 정기적으로 사용하는 경우 예약된 경로를 설정할 수 있습니다.

## <a name="route-plans"></a>경로 계획
경로 계획에는 경로에서 방문한 기착지와 각 구간에 사용되는 운송업체에 대한 정보를 제공하는 경로 구간이 포함됩니다. 경로의 기착지를 허브로 정의해야 합니다. 허브는 공급업체, 창고, 고객 또는 운송업체를 변경하는 재적재 장소일 수 있습니다. 각 세그먼트에 대해 다양한 요금에 대한 "현물 환율"을 정의할 수 있습니다. 여기 예시들이 있습니다 :

-   지정된 구간으로 이동하는 요금
-   상품 픽업 요금
-   상품 반출 요금

각 경로 계획은 경로 가이드와 연결되어야 합니다.

## <a name="route-guides"></a>경로 가이드
경로 가이드는 특정 경로 계획에 로드를 일치시키는 기준을 정의합니다. 예를 들어, 출발지 허브와 목적지 허브, 컨테이너 부피 또는 중량 제한, 운송업체, 서비스 또는 그룹을 지정할 수 있습니다. 경로 가이드는 **평가 경로 워크벤치** 페이지에서 로드를 수동 또는 자동으로 경로에 일치시킬 수 있습니다. 경로 가이드가 예정된 경로에 대한 것이라면 **로드 빌드 워크벤치** 페이지에서도 사용할 수 있습니다.

## <a name="scheduled-routes"></a>예정된 경로
예정된 경로는 배송 날짜에 대한 일정이 있는 미리 정의된 경로 계획입니다. 예정된 경로와 예정되지 않은 경로는 로드가 할당되는 방식이 다릅니다. 평가 경로 워크벤치를 사용하여 예정되지 않은 경로를 지정하면 로드와 경로 가이드만 검증됩니다. 예약된 경로를 지정하면 주문 및 허브의 날짜와 주소, 경로 계획의 날짜도 고려됩니다. 예약된 경로에 로드를 수동으로 할당하기 위해 평가 경로 워크벤치 페이지를 사용할 필요가 없습니다. 대신, 로드 빌드 워크벤치를 사용하여 고객 주소 및 지정된 예약된 경로에 대한 판매 주문의 배송 날짜를 기반으로 로드 빌드를 제안할 수 있습니다. 예약된 경로의 경우 경로 계획에는 고정된 출발지 및 목적지 허브가 있습니다. 일반적으로 운송업체와 서비스는 모든 구간에서 동일하지만 다를 수 있습니다. 목적지 허브는 경로에서 방문한 고객의 우편 번호를 사용하여 생성됩니다. 하나의 경로 계획에 대해 여러 경로 일정을 정의할 수 있습니다. 경로 계획은 경로 가이드와 연결되어야 합니다. 그러나 예약된 경로의 경우 계획은 하나의 경로 가이드에만 연결될 수 있습니다. 경로 예약은 **경로 예약** 페이지에서 실제 경로를 생성하는 데만 사용됩니다. 로드 빌드 워크벤치에서 로드를 제안할 때 기본 로드 템플릿을 사용할 수 있습니다.

## <a name="load-building-workbench"></a>로드 빌드 워크벤치
로드 빌드 워크벤치는 판매 주문의 고객 주소와 배송 날짜, 사용 가능한 예약 경로를 사용하여 로드를 제안합니다. 기본적으로 경로의 값은 워크벤치에 입력됩니다. 그러나 경로의 "시작" 날짜보다 빠른 "시작" 날짜를 선택할 수 있습니다. 로드가 제안되면 열려 있는 모든 판매 주문의 배송 주소와 배송 날짜를 확인합니다. 배송 주소의 우편번호가 경로 계획에 있는 허브의 우편번호와 일치하고 배송 날짜가 기준에서 선택한 범위 내인 경우 로드에 대한 판매 주문이 제안됩니다. 로드 템플릿의 용량도 고려됩니다. 한 번에 하나의 로드만 제안됩니다. 포함되지 않은 판매 주문이 있는 경우 다른 로드 템플릿(예: 더 큰 트럭 또는 컨테이너의 로드 템플릿)을 사용하거나 추가 배송을 계획해야 할 수 있습니다.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]