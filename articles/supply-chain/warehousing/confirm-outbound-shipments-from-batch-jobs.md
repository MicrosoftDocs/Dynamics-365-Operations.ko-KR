---
title: 일괄 작업에서 아웃바운드 배송 확인
description: 이 항목에서는 출하 준비 로드에 대한 아웃바운드 이전 주문 배송을 자동으로 확인하는 배치 작업을 설정하는 방법에 대해 설명합니다.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: f68dcfc0c1454ee5b095e186c52faa6c83bf8dc6
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2022
ms.locfileid: "8450049"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a>일괄 작업에서 아웃바운드 배송 확인

[!include [banner](../includes/banner.md)]

이 항목에서는 출하 준비 로드에 대한 아웃바운드 이전 주문 배송을 자동으로 확인하는 배치 작업을 설정하는 방법에 대해 설명합니다. 여기에 설명된 배치 작업은 판매 주문이 아닌 이전 주문 배송에만 적용됩니다.

## <a name="turn-the-confirm-outbound-shipments-from-batch-jobs-feature-on-or-off"></a>일괄 작업에서 아웃바운드 배송 확인 기능을 켜거나 끕니다.

이 항목에서 설명하는 기능을 사용하려면 *일괄 작업의 아웃바운드 배송 확인* 기능이 시스템에 대해 켜져 있어야 합니다. Supply Chain Management 버전 10.0.21부터 이 기능은 기본적으로 켜져 있습니다. Supply Chain Management 10.0.25부터 이 기능은 필수이며 끌 수 없습니다. 10.0.25 이전 버전을 실행 중인 경우 관리자는 [기능 관리](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) 작업 영역에서 *일괄 작업의 아웃바운드 배송 확인* 기능을 검색하여 이 기능을 켜거나 끌 수 있습니다.

## <a name="process-outbound-shipments"></a>아웃바운드 배송 처리

배송 준비가 된 로드에 대해 아웃바운드 배송 확인을 실행하도록 예약된 배치 작업을 설정하려면:

1. **창고 관리 \> 정기 작업 \> 아웃바운드 배송 처리** 로 이동합니다.
1. **배송 확인** 대화 상자가 열립니다. **포함할 레코드** 빠른 탭에서 **필터** 를 선택합니다.
1. 쿼리 편집기 대화 상자가 열립니다. **범위** 탭에서 다음 값이 있는 행을 추가합니다.
    - **테이블** - *로드*
    - **파생 테이블** - *로드*
    - **필드** - *로드 상태*
    - **기준** - *로드됨*
1. **확인** 을 선택하여 **배송 확인** 대화 상자로 돌아갑니다.
1. **백그라운드에서 실행** 빠른 탭에서 **일괄 처리** 를 **예** 로 설정합니다.
1. **백그라운드에서 실행** 빠른 탭에서 **되풀이** 를 선택합니다.
1. **반복 정의** 대화 상자가 열립니다. 비즈니스에 필요한 실행 일정을 설정합니다.
1. **확인** 을 선택하여 **배송 확인** 대화 상자로 돌아갑니다.
1. **배송 확인** 대화 상자에서 **확인** 을 선택하여 일괄 작업을 일괄 대기열에 추가합니다.

자세한 내용은 [일괄 처리 개요](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md)를 참조하세요.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]