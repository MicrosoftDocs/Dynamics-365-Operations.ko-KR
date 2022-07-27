---
title: 글로벌 모바일 디바이스 매개 변수
description: 이 항목에서는 창고 관리 매개 변수 페이지에서 모바일 디바이스 설정을 지정하는 방법에 대해 설명합니다.
author: HuberIvan
ms.date: 08/13/2021
ms.topic: article
ms.search.form: WHS
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-huberivan
ms.search.validFrom: 2021-08-13
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 03c10232d55c99c73e625170797f89f6c77e812b
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2021
ms.locfileid: "8447712"
---
# <a name="global-mobile-device-parameters"></a>글로벌 모바일 디바이스 매개 변수

[!include [banner](../includes/banner.md)]

이 항목에서는 시스템이 모바일 디바이스와 상호 작용하는 방식에 영향을 미치는 글로벌 창고 관리 매개 변수를 설정하는 방법에 대해 설명합니다.

창고 작업자를 설정하는 방법에 대한 자세한 내용은 [창고 작업자 관리](manage-warehouse-workers.md)를 참조하세요. 모바일 디바이스에서 번호판 처리에 대한 자세한 내용은 [Warehouse Management 모바일 앱을 통해 번호판 받기](warehousing-mobile-device-app-license-plate-receiving.md)를 참조하세요. 순환 재고 프로세스에 대한 자세한 내용은 [순환 재고](cycle-counting.md) 및 [순환 재고 예시 시나리오](cycle-counting-scenarios.md)를 참조하세요.

## <a name="open-the-warehouse-management-parameters-page"></a>창고 관리 매개 변수 페이지 열기

**창고 관리 매개 변수** 페이지를 열려면 **창고 관리 \> 설정 \> 창고 관리 매개 변수** 로 이동합니다. 그런 다음 이 항목의 다음 섹션에 설명된 대로 모바일 디바이스 작업과 관련된 필드를 설정할 수 있습니다.

## <a name="mobile-device-fasttab-on-the-general-tab"></a>일반 탭의 모바일 디바이스 빠른 탭

글로벌 모바일 디바이스 설정은 **창고 관리 매개 변수** 페이지의 **일반** 탭에 있는 **모바일 디바이스** 빠른 탭에서 찾을 수 있습니다. 다음 필드를 사용할 수 있습니다.

| 필드 | 설명 |
|---|---|
| 모바일 디바이스 메모 유형 | 판매 주문 피킹 중 작업자에게 표시되는 정보 유형을 선택합니다. |
| 스캔 수량 제한 | 작업자가 각 세션 동안 스캔할 수 있는 최대 항목 수량을 *조정* 의 **작업 생성 프로세스** 값이 있는 모바일 디바이스 메뉴 항목을 사용하여 입력합니다. 이 필드는 다른 유형의 메뉴 항목을 사용하여 수행되는 스캔에 영향을 미치지 않습니다. |
| 모바일 디바이스 세션 로깅 사용 | 이 옵션을 *예* 로 설정하여 작업자 로그인 기록의 로그를 유지합니다. 로그를 보려면 **작업 사용자 세션 \> 문의 및 신고 \> 모바일 디바이스 로그 \>작업 사용자 세션** 으로 이동합니다. |
| 저장된 오류 수 | 시스템이 저장해야 하는 최대 오류 레코드 수를 입력합니다. 오류 로그를 보려면 **작업 사용자 세션 \> 문의 및 신고 \> 모바일 디바이스 로그 \>작업 사용자 세션** 으로 이동합니다. |
| 기본 웨어하우스 전송 분개장 | 작업자가 모바일 디바이스를 사용하여 한 창고에서 다른 창고로 제품을 이동할 때 사용되는 분개장을 선택합니다. |
| 외부 검토 시 구매 주문 라인 등록 허용 | 작업자가 모바일 디바이스를 사용하여 **승인 상태** 값이 *외부 검토 중* 인 구매 주문에 대한 주문 라인을 등록할 수 있어야 하는 경우 이 옵션을 *예* 로 설정합니다. 작업자가 외부 검토 중인 구매 주문에 대한 라인을 등록하지 못하도록 하려면 이 옵션을 *아니요* 로 설정합니다. |
| RSAT 지원 활성화 | 이 필드는 앱이 수행하는 각 단계를 기록하고 유효성을 검사하는 Warehouse Management 모바일 앱 작업 유효성 검사기를 활성화합니다. 이 프로세스는 시스템 성능을 크게 저하시킬 수 있으므로 테스트 중에만 유효성 검사기를 활성화해야 합니다. 프로덕션 환경에서는 절대로 활성화하면 안 됩니다. |
