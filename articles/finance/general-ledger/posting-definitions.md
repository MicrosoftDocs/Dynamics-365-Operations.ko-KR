---
title: 게시 정의
description: 이 항목에서는 게시 정의에 대한 정보와 정의 및 연결 방법에 대해 설명합니다. 지원되는 게시 유형 및 문서의 경우 프로필 대신 게시 정의를 사용하여 계정 항목의 기본 계정 및 재무 차원을 분류할 수 있습니다.
author: kweekley
ms.date: 09/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d409f154823a74e032adb71253ce97f8e3b2f101
ms.sourcegitcommit: 4f8465729d7ae0bf5150a2785a6140c984c7030e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2021
ms.locfileid: "8451132"
---
# <a name="posting-definitions"></a>게시 정의

[!include [banner](../includes/banner.md)]

이 항목에서는 게시 정의에 대한 정보와 정의 및 연결 방법에 대해 설명합니다.
지원되는 게시 유형 및 문서의 경우 프로필 대신 게시 정의를 사용하여 계정 항목의 기본 계정 및 재무 차원을 분류할 수 있습니다. **트랜잭션 게시 정의** 페이지에서 지원되는 문서 및 게시 유형을 볼 수 있습니다. 

게시 정의 사용을 시작하려면 **총계정원장 매개 변수** 페이지에서 **게시 정의 사용** 옵션을 선택합니다. 게시 정의를 사용하는 경우에도 원본 항목과 지원되지 않는 게시 유형 및 문서에 대한 게시 프로파일을 정의해야 합니다. 

구매 주문에 대한 지불부담 회계를 가능하게 하고 구매 요청에 대한 지불부담 전 회계를 가능하게 하려면 게시 정의를 사용해야 합니다.

## <a name="defining-posting-definitions"></a>게시 정의의 정의
**게시 정의** 페이지를 사용하여 일치 기준을 지정하고 일치가 발생할 때 생성되어야 하는 항목을 정의합니다. 일치 기준은 회계 분포로서 원본 항목에 대해 평가됩니다. 

또한 **게시 정의** 페이지에서 입력 라인에 우선순위 번호를 할당하여 라인이 평가되는 순서를 제어할 수 있습니다. 우선순위 번호가 가장 낮은 라인이 먼저 평가됩니다. 예를 들어 우선순위가 1인 모든 라인이 평가되고 우선순위가 2인 라인이 평가됩니다. 일치하는 항목이 발견되면 다른 일치 기준은 무시됩니다. 또한 원본 트랜잭션과 일치하는 그룹의 기준만 생성된 항목을 생성합니다. 

**게시 정의 테스트** 마법사를 사용하여 게시 정의의 유효성을 검사할 수 있습니다. 게시 정의에 대한 샘플 시작 항목을 정의하면 생성된 항목이 표시됩니다. 

게시 정의 버전을 유효 날짜와 함께 사용할 수 있습니다. 예를 들어, 새로운 회계 연도에 다른 원장 계정에 게시할 게시 정의의 미래 버전을 생성할 수 있습니다. 

**트랜잭션 게시 정의** 페이지를 사용하여 게시 정의를 트랜잭션 유형에 할당합니다.

## <a name="linking-posting-definitions"></a>게시 정의 연결
게시 정의를 만들 때 한 게시 정의에서 다른 게시 정의로 연결할 수 있습니다. 그러면 연결된 정의의 기준이 현재 게시 정의의 기준과 함께 고려됩니다. 이 기능은 다른 정의에 이미 입력한 경우 현재 게시 정의에 대한 **게시 정의** 페이지의 **항목** FastTab에 기준을 다시 입력할 필요가 없으므로 시간을 절약하는 데 도움이 됩니다. 

다이어그램 또는 표에 사용할 수 있는 모든 링크를 포함합니다. 현재 게시 정의와 충돌을 방지하려면 연결하는 게시 정의의 라인이 고유해야 합니다. 

게시 정의에서 링크를 생성할 때는 다음과 같은 제한이 적용됩니다.

-   지정된 게시 정의는 다른 게시 정의에 연결하거나 다른 게시 정의에서 연결할 수 있지만 둘 다 연결할 수는 없습니다. 그러나 게시 정의는 여러 게시 정의에 연결할 수 있습니다.
-   동일한 모듈에 있는 게시 정의 간의 링크만 설정할 수 있습니다.
-   모든 트랜잭션 유형에 게시 정의를 할당할 수 있지만 트랜잭션 유형은 게시 정의와 동일한 모듈에 있어야 합니다. **트랜잭션 게시 정의** 페이지를 사용하여 트랜잭션 유형이 어떤 모듈에 있는지 확인합니다.


자세한 내용은 [게시 정의 예제](example-posting-definitions.md)를 참조하십시오. 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]