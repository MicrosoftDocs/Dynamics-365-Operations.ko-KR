---
title: 단기 피킹 항목 재할당 설정
description: 이 토픽에서는 창고 작업자가 이동한 위치에 인벤토리가 충분하지 않은 경우 대체 위치를 빠르게 찾을 수 있도록 하는 방법을 보여줍니다.
author: Mirzaab
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7fe17246037a35e44d12476f184af3bd4c806022
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/29/2021
ms.locfileid: "8447790"
---
# <a name="set-up-short-picking-item-reallocation"></a>단기 피킹 항목 재할당 설정

[!include [banner](../../includes/banner.md)]

이 절차에서는 창고 작업자가 이동한 위치에 인벤토리가 충분하지 않은 경우 대체 위치를 빠르게 찾을 수 있도록 하는 방법을 보여줍니다. 

재할당 프로세스는 **작업 예외** 에 의해 제어되고 창고 **작업자** 가 사용합니다.

자동, 수동 또는 두 가지 재할당 프로세스를 모두 사용할 수 있습니다.

- 자동 재할당 - 위치 지시문은 상품이 다른 위치에서 사용 가능한지 확인하는 데 사용됩니다. 가능한 경우 작업이 업데이트되고 창고 사용자는 대체 위치로 안내됩니다.
- 수동 재할당 - 창고 사용자가 예약되지 않은 수량의 상품이 있는 하나 이상의 위치에서 선택할 수 있습니다. 
- 자동 및 수동 - 시스템이 자동 재할당을 수행할 수 없고 위치가 예약되지 않은 수량으로 사용 가능한 경우 사용자에게 위치를 선택하라는 메시지가 표시됩니다.

## <a name="set-up-work-exceptions"></a>작업 예외 설정
창고 작업자가 처리 중인 발송물의 요구 사항에 따라 선택할 수 있도록 다양한 항목 재할당 정책으로 여러 작업 예외를 정의할 수 있습니다.

USMF 데모 데이터 회사가 이 절차를 만드는 데 사용되었습니다.

1. **탐색 창** 에서 **창고 관리 > 설정 > 작업 > 작업 예외** 로 이동합니다.
2. **새로 만들기** 를 클릭합니다. 
3. **작업 예외 코드** 필드에 값을 입력합니다. 이것은 이 예외의 제목이 됩니다. 예를 들어 단기 선택 매뉴얼입니다.
4. **설명** 필드에 값을 입력합니다. 이것은 이 예외의 사용법에 대한 간단한 설명입니다. 예를 들어, 단기 선택 - 항목을 사용할 수 없습니다.
5. **예외** 유형 필드에서 **단기 선택** 을 선택합니다.
6. **인벤토리 조정** 확인란을 선택합니다. 선택하면 단기 선택 위치에서 인벤토리가 자동으로 0으로 조정됩니다.
7. **기본 조정 유형 코드** 필드에서 값을 입력하거나 선택합니다. 예를 들어 USMF에서 **Res Adj Out 제거** 를 선택할 수 있습니다. 각 조정 유형 코드에는 이름, 설명, 인벤토리 분개장 이름 및 **예약 제거** 의 네 가지 특성이 있습니다. **예약 제거** 가 사용 설정되면 단기 선택 주문 라인의 예약이 제거됩니다.  
8. **항목 재할당** 필드에서 수동과 같은 값을 선택합니다. 수동 또는 자동 및 수동을 선택하는 경우 창고 작업자는 수동 재할당을 사용할 수 있어야 합니다.

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>항목 수동 재할당을 사용하도록 작업자 설정

USMF 데모 데이터 회사가 이 절차를 만드는 데 사용되었습니다.

1. 페이지를 닫습니다.
2. **탐색 창** 에서 **창고 관리 > 설정 > 작업자** 로 이동합니다.
3. **편집** 을 클릭합니다.
4. 목록에서 작업자를 선택합니다. 예를 들어 Julia Funderburg입니다.
5. **사용자** 빠른 탭을 펼칩니다.
6. 목록에서 **사용자 ID** 를 선택합니다. 예를 들어 24를 입력합니다.
7. **작업** 빠른 탭을 확장합니다.
8. **항목 수동 재할당 허용** 필드에서 **예** 를 선택합니다.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]