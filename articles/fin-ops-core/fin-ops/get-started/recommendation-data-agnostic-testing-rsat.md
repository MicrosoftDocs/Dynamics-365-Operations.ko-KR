---
title: Regression Suite Automation Tool를 사용한 데이터 불가지론적 테스트
description: 이 항목에서는 Regression Suite Automation Tool를 사용하여 데이터 진단 테스트를 수행하기 위한 권장 사항을 설명합니다.
author: kfend
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2019-09-11
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: d9a5bce1cc56dfdf66b2ce58c2e740b7c4b3bdfc7f4e75396fe5dc7cb931b6d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "8460968"
---
# <a name="data-agnostic-testing-using-the-regression-suite-automation-tool"></a>Regression Suite Automation Tool를 사용한 데이터 불가지론적 테스트

[!include [banner](../includes/banner.md)]

ERP 응용 프로그램의 기능 검증은 데이터에 대해 완전히 독립적일 수는 없지만 테스트를 위한 여러 단계와 접근 방식이 있습니다. 이러한 테스트 단계에는 다음이 포함됩니다.  

- SysTest 프레임워크
- ATL 프레임워크
- Regression Suite Automation Tool(RSAT)

[![테스트 분류 피라미드.](./media/rsat-data-agnostic-testing-01.PNG)](./media/rsat-data-agnostic-testing-01.PNG)

## <a name="overview"></a>개요
-   **SysTest 프레임워크** – SysTest 프레임워크는 단위 테스트 작성에 안정적입니다. 단위 테스트는 일반적으로 방법이나 기능을 테스트하기 때문에 항상 데이터에 구애받지 않고 테스트의 일부로 제공되는 입력 데이터에만 의존해야 합니다.
-   **ATL 프레임워크** – Microsoft는 SysTest 프레임워크의 추상화인 ATL 프레임워크를 보유하고 있으며 기능 테스트 작성을 훨씬 더 간단하고 안정적으로 만듭니다. 이 프레임워크는 구성 요소 테스트 또는 간단한 통합 테스트를 작성하는 데 사용해야 합니다.
-   **RSAT** – RSAT는 통합 테스트 및 비즈니스 주기 테스트에 사용됩니다. 회귀 검증 테스트라고도 하는 비즈니스 주기 테스트는 기존 데이터에 종속됩니다. 그러나 이러한 테스트는 추가 요소를 고려하면 데이터에 구애받지 않을 수 있습니다. 

    - O 단위 테스트 및 구성 요소 테스트가 낮은 수준이고 완전히 데이터에 구애받지 않을 수 있는 경우(기존 데이터 세트에 종속되지 않음), 비즈니스 주기 또는 회귀 검증 테스트는 일부 기존 데이터에 종속됩니다. 이 데이터에는 설정, 구성 설정(매개변수) 및 마스터 데이터(고객, 공급업체, 품목 등)가 포함되지만 트랜잭션 데이터는 포함되지 않습니다. 테스트 중에 이러한 항목이 변경되는 경우 최종 테스트의 일부로 되돌려졌는지 확인합니다.
    - 특정 레코드를 선택하는 대신 특정 기준에 따라 마스터 데이터를 선택합니다. 예를 들어 차원 값과 재고 가용성을 기반으로 항목을 선택하려면 해당 값으로 제품 목록을 필터링하고 첫 번째 항목을 선택한 다음 향후 테스트에 사용할 번호를 복사합니다. 고객, 공급업체 또는 품목과 같은 단순한 마스터 데이터 라인인 경우 자동화의 일부로 생성하고 체인을 통해 향후 테스트에 사용할 수 있습니다. 
    - o 송장 번호와 같은 고유 식별자를 번호 순서를 통해 입력하거나 =TEXT(NOW(),"yyyymmddhhmm")와 같은 Microsoft Excel 함수를 사용하여 고유 식별자를 입력합니다. 이 기능은 1분마다 고유한 번호를 제공하여 작업이 발생한 시간을 추적할 수 있습니다. 이는 제품 영수증 번호 및 공급업체 송장 번호와 같은 변수에 사용할 수 있습니다. 이러한 테스트는 복원할 필요 없이 동일한 데이터베이스에서 계속해서 계속 작동합니다.
    - 항상 환경의 **편집 모드** 를 첫 테스트 케이스로 **읽기** 또는 **편집** 으로 설정하세요. 기본 옵션이 **자동** 이기 때문입니다. **자동** 옵션은 항상 이전 설정을 사용하며 신뢰할 수 없는 테스트를 유발할 수 있습니다. 
 
    [![옵션 페이지, 성능 탭.](./media/rsat-data-agnostic-testing-02.PNG)](./media/rsat-data-agnostic-testing-02.PNG)
 
    - 일반 유효성 검사 대신 특정 트랜잭션을 필터링한 후에만 유효성을 검사하세요. 예를 들어 레코드 수의 경우 유효성 검사에서 다른 모든 트랜잭션이 제외되도록 트랜잭션 번호 또는 트랜잭션 날짜를 필터링합니다. 
    - 고객 잔액 또는 예산 확인을 확인하는 경우 고정 예상 값을 검증하는 대신 먼저 값을 저장한 다음 거래 값을 추가하여 예상 결과를 검증하세요. 
 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]