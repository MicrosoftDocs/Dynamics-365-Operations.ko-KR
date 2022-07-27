---
title: 재고 가시성 앱
description: 이 토픽에서는 재고 가시성 앱을 사용하는 방법에 대해 설명합니다.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 359f89f98ca6954a0bbafd63fffa1d505a43f0c8
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8449809"
---
# <a name="use-the-inventory-visibility-app"></a>재고 가시성 앱 사용하기

[!include [banner](../includes/banner.md)]


이 토픽에서는 재고 가시성 앱을 사용하는 방법에 대해 설명합니다.

재고 가시성은 시각화를 위한 모델 기반 앱을 제공합니다. 앱에는 **구성**, **운영 가시성** 및 **재고 요약** 의 세 페이지가 포함되어 있습니다. 다음 기능이 있습니다.

- 직접 구성 및 소프트 예약 구성을 위한 사용자 인터페이스(UI)를 제공합니다.
- 다양한 차원 조합에 대한 실시간 재고 조회를 지원합니다.
- 예약 요청 전기를 위한 UI를 제공합니다.
- 그것은 모든 차원과 함께 제품에 대한 재고의 사용자 정의 보기를 제공합니다.

## <a name="prerequisites"></a>전제 조건

시작하기 전에 [재고 가시성 설치 및 설정](inventory-visibility-setup.md)에 설명된 대로 재고 가시성 추가 기능을 설치 및 설정합니다.

## <a name="open-the-inventory-visibility-app"></a>재고 가시성 앱 열기

재고 가시성 앱을 열려면 Power Apps 환경에 로그인하고 **재고 가시성** 을 엽니다.

## <a name="configuration"></a><a name="configuration"></a>구성

재고 가시성 앱의 **구성** 페이지는 현재 구성 및 소프트 예약 구성을 설정하는 데 도움이 됩니다. 추가 기능이 설치된 후 기본 구성에는 Microsoft Dynamics 365 Supply Chain Management(`fno` 데이터 원본)에 대한 기본 설정이 포함됩니다. 기본 설정을 검토할 수 있습니다. 이후에는 비즈니스 요구 사항 및 외부 시스템의 재고 게시 요구 사항을 기반으로 구성을 수정하여 여러 시스템에서 재고 변경 사항을 게시, 구성 및 쿼리할 수 있는 방법을 표준화할 수 있습니다.

솔루션 구성 방법에 대한 자세한 내용은 [재고 가시성 구성](inventory-visibility-configuration.md)을 참조하세요.

## <a name="operational-visibility"></a>운영 가시성

**운영 가시성** 페이지는 다양한 차원 조합을 기반으로 한 실시간 현재고 쿼리 결과를 제공합니다. *OnHandReservation* 기능이 켜져 있으면 **운영 가시성** 페이지에서 예약 요청을 게시할 수도 있습니다.

### <a name="on-hand-query"></a>보유 재고 쿼리

**현재고 조회** 탭에는 실시간 현재고 조회 결과가 표시됩니다.

선택하면 **현재고 쿼리** 탭을 선택하면 시스템에서 재고 가시성 서비스를 쿼리하는 데 필요한 전달자 토큰을 가져올 수 있도록 자격 증명을 요청합니다. 전달자 토큰을 **전달자 토큰** 필드에 붙여넣고 대화 상자를 닫으면 됩니다. 그런 다음 현재 쿼리 요청을 게시할 수 있습니다.

전달자 토큰이 유효하지 않거나 만료된 경우 **BearerToken** 필드에 새 토큰을 붙여넣어야 합니다. 올바른 **클라이언트 ID**, **테넌트 ID**, **클라이언트 암호** 값을 입력한 다음 **새로 고침** 을 선택합니다. 시스템은 자동으로 새롭고 유효한 전달자 토큰을 얻습니다.

현재 쿼리를 게시하려면 요청 본문에 쿼리를 입력합니다. [post 메서드를 사용하여 쿼리](inventory-visibility-api.md#query-with-post-method)에 설명된 패턴을 사용합니다.

![보유 재고 쿼리 설정](media/inventory-visibility-query-settings.png "보유 재고 쿼리 설정")

### <a name="reservation-posting"></a>예약 게시

**예약 게시** 탭을 사용하여 예약 요청을 게시합니다. 예약 요청을 게시하기 전에 *OnHandReservation* 기능을 켜야 합니다. 이 기능에 대한 자세한 내용은 [재고 가시성 예약](inventory-visibility-reservations.md)을 참조하세요.

예약 요청을 게시하려면 요청 본문에 값을 입력해야 합니다. 하나의 [예약 이벤트 생성](inventory-visibility-api.md#create-one-reservation-event)에 설명된 패턴을 사용합니다. 그런 다음 **전기** 를 선택합니다. 요청 응답 세부 정보를 보려면 **세부 정보 표시** 를 선택합니다. 응답 세부 정보에서 `reservationId` 값을 가져올 수도 있습니다.

## <a name="inventory-summary"></a><a name="inventory-summary"></a>재고 요약

**재고 요약** 은 *재고 보유 합계* 엔터티에 대한 사용자 지정된 보기입니다. 모든 차원과 함께 제품에 대한 재고 요약을 제공합니다. 재고 요약 데이터는 재고 가시성에서 주기적으로 동기화됩니다. **재고 요약** 탭에서 데이터를 보려면 먼저 **기능 관리** 탭에서 *OnHandMostSpecificBackgroundService* 기능을 켜야 합니다.

Dataverse에서 제공하는 **고급 필터** 를 사용하여 중요한 행을 표시하는 개인 보기를 만들 수 있습니다. 고급 필터 옵션을 사용하면 단순한 것부터 복잡한 것까지 다양한 보기를 만들 수 있습니다. 또한 필터에 그룹화 및 중첩 조건을 추가할 수 있습니다. **고급 필터** 를 사용하는 방법에 대한 자세한 내용은 [고급 그리드 필터를 사용하여 개인 보기 편집 또는 만들기](/powerapps/user/grid-filters-advanced)를 참조하세요.

사용자 지정된 보기의 상단에는 **기본 차원**, **사용자 지정 차원** 및 **측정** 의 세 가지 필드가 있습니다. 이러한 필드를 사용하여 표시되는 열을 제어할 수 있습니다.

열 머리글을 선택하여 현재 결과를 필터링하거나 정렬할 수 있습니다.

사용자 지정 보기 하단에는 "50개 레코드(29개 선택됨)" 또는 "50개 레코드"와 같은 정보가 표시됩니다. 이 정보는 **고급 필터** 결과에서 현재 로드된 레코드를 나타냅니다. "29개 선택됨" 텍스트는 로드된 레코드에 대해 열 헤더 필터를 사용하여 선택된 레코드 수를 나타냅니다.

보기 하단에는 Dataverse에서 더 많은 레코드를 로드하는 데 사용할 수 있는 **추가 로드** 단추가 있습니다. 로드되는 기본 레코드 수는 50개입니다. **추가 로드** 를 선택하면 다음 1,000개의 사용 가능한 레코드가 보기에 로드됩니다. **추가 로드** 단추의 숫자는 현재 로드된 레코드와 **고급 필터** 결과에 대한 총 레코드 수를 나타냅니다.

![인벤토리 요약](media/inventory-visibility-onhand-list.png "인벤토리 요약")
