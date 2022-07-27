---
title: 판매 내역 정리 실적 개선
description: 이 토픽에서는 판매 내역 정리 성능 개선 기능과 사용 설정 방법에 대해 설명합니다.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3c8ad7b0bd46c49fc989be091f44630a6a3eebc1
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2022
ms.locfileid: "8449767"
---
# <a name="sales-history-cleanup-performance-improvements"></a>판매 내역 정리 실적 개선

[!include [banner](../includes/banner.md)]

**판매 업데이트 기록 정리** 주기적인 배치 작업은 판매 업데이트가 많은 환경에서 자주 실행되지 않는 경우 시간이 오래 걸릴 수 있습니다. 이러한 상황에서 *판매 내역 정리 성능 향상* 기능은 실행 기간을 줄이고 안정성을 향상시키는 데 도움이 될 수 있습니다.

이 기능은 다음과 같은 방식으로 기존 정리 작업을 개선합니다.

- 정리를 배치로 분할합니다(사용자 정의를 통해 배치 크기를 변경할 수 있음).
- 최대 2시간 동안 진행됩니다(사용자 지정을 통해 기간 변경 가능).
- 가능한 경우 데이터베이스 기능을 활용하여 잠금 경합을 최소화하고 정리 중 트랜잭션 테이블 조인을 방지합니다.

기능을 활성화하면 **판매 업데이트 내역 정리** 배치 작업(**영업 및 마케팅 \> 기간 태스크 \> 정리 \> 판매 업데이트 내역 정리**)이 이전과 같이 실행되지만 더 나은 성능과 최대 2시간 동안 실행됩니다. 즉, 특정 보존 기간 동안 모든 데이터를 정리하기 위해 여러 번 실행해야 할 수 있습니다.

## <a name="turn-on-the-sales-history-cleanup-performance-improvements-feature"></a>판매 내역 정리 실적 개선 기능 켜기

이 기능을 사용하려면 먼저 시스템에서 켜져 있어야 합니다. 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 설정을 사용하여 기능의 상태를 확인하고 켤 수 있습니다. **기능 관리** 작업 영역에서 기능은 다음과 같은 방식으로 나열됩니다.

- **모듈:** *영업 및 마케팅*
- **기능 이름:** *판매 내역 정리 성능 개선*
