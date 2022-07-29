---
title: 일반 분개장 처리
description: 이 항목에서는 일반 분개장을 쉽게 처리하고 올바른 데이터를 캡처하며 내부 제어가 손상되지 않도록 하는 데 도움이 되는 Microsoft Dynamics 365 Finance의 기능에 관해 설명합니다.
author: kweekley
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7096d8576cf124e5e1d814c360d96639f66a742a
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2022
ms.locfileid: "8451660"
---
# <a name="general-journal-processing"></a>일반 분개장 처리

[!include [banner](../includes/banner.md)]

이 항목에서는 일반 분개장을 쉽게 처리하고 올바른 데이터를 캡처하며 내부 제어가 손상되지 않도록 하는 데 도움이 되는 기능에 관해 설명합니다.  

## <a name="journal-names"></a>분개장 이름

설정해야 할 가장 중요한 영역 중 하나는 분개장 이름입니다. 분개장 이름은 회사 간, 발생 조정 및 오류 수정과 같이 각 목적에 맞게 특정하게 정의하는 것이 좋습니다. 각 분개장 이름을 맞춤화하여 각 목적에 맞는 데이터를 쉽고 안전하게 입력할 수 있습니다. 

**분개장 이름** 페이지에서 다음 요소를 설정할 수 있습니다.

-   **워크플로 승인** – 내부 통제를 강화하기 위해 총 출금 금액과 같은 기준을 기반으로 검토 및 승인 단계에 대한 중요성 한계를 설정하는 분개장 워크플로를 정의합니다. 일반 분개장에 대한 워크플로는 **총계정원장 워크플로** 페이지에서 설정합니다.
-   **기본값** – 상쇄 계정, 통화 및 재무 차원에 대한 기본값을 선택합니다.
-   **분개장 제어** – 회사 및 계정 유형과 세그먼트 값에 대한 제한을 설정할 수 있습니다. 

**예**

분개장 이름은 조정에만 사용할 수 있습니다. 이 경우 **원장** 계정 유형만 모든 회사에서 유효하도록 지정할 수 있습니다. 

[![분개장 제어 계정 유형.](./media/journal-control-account-types1.png)](./media/journal-control-account-types1.png)

분개장 이름은 특정 세그먼트 또는 주 계정의 범위에만 사용할 수 있습니다. 

[![분개장 제어 세그먼트.](./media/journal-control-segment1.png)](./media/journal-control-segment1.png)

**자동 취소** 옵션은 일반 분개장에서 사용할 수 있습니다. 예를 들어 다음 그림과 같이 실제 문서가 아직 처리되지 않은 발생 조정이 있습니다.
[![일반 분개장 취소.](./media/general-journal-reversing1.png)](./media/general-journal-reversing1.png) 

분개장 기입용 Microsoft Excel 추가 기능은 자동화 수준을 높이고 데이터를 더 쉽게 입력할 수 있게 해줍니다. **일반 분개장** 및 **분개장 바우처** 페이지에서 **Excel에서 라인 열기** 작업을 사용할 수 있습니다. 

**정기 분개장** 페이지에서 정기 분개장을 설정하여 분개장 처리를 자동화할 수 있습니다. 

바우처 템플릿은 언제든지 사용할 수 있습니다. **일반 분개장** 페이지에서 **저장** 및 **바우처 템플릿 선택** 작업은 바우처 라인의 **기능** 아래의 **분개장 바우처** 페이지에 있습니다.

## <a name="related-setup"></a>관련 설정
다음 설정은 일반 분개장에만 적용되는 것은 아니지만 데이터 입력이 정확하고 쉬운지 확인하는 데 도움이 됩니다.

### <a name="main-account"></a>주 계정

주 계정 설정은 일반 분개장 처리를 위한 다양한 옵션을 제공합니다.

-   **DC/CR 요구 사항** – 주 계정이 출금 또는 입금 거래로 제한된 경우 이 옵션을 사용합니다. 분개장이 확인되거나 게시되면 설정이 확인됩니다.

-   **기본 상쇄 계정**
-   **일시 중단** – 모든 회사 또는 특정 회사/법인에 대한 주 계정의 데이터 입력을 일시 중단합니다.
-   **수동 입력을 허용하지 않음** – 사용자가 분개장의 계정 값을 수동으로 입력하는 것을 방지합니다.
-   **기본/통화 유효성 검사**
-   **법인 재정의** – 이 설정은 정의된 회사/법인에만 적용됩니다.
    -   **기본/판매세 유효성 검사**
    -   **기본 차원** – **고정되지 않음** 또는 **고정 가치**. **고정 가치** 는 이 주 계정에 대한 모든 게시가 **고정** 으로 설정된 모든 차원 값을 항상 사용하도록 보장합니다.
-   **게시 유효성 검사**
    -   **사용자 유효성 검사** – 이 옵션은 주 계정에 게시할 수 있는 사용자를 통제합니다.
    -   **게시 유형 유효성 검사** – 이 옵션은 주 계정에 허용되는 게시 유형을 통제합니다.

### <a name="accounting-structures-and-advanced-rules-structures"></a>회계 구조 및 고급 규칙 구조

회계 구조 및 고급 규칙 구조는 Financial Reporting 및 성과 추적에 필요한 데이터가 일반 분개장 처리와 설명서에서 캡처되도록 하는 데 매우 중요합니다. 회계 구조 및 고급 규칙 구조를 통해 데이터 입력 환경을 맞춤화할 수 있습니다. 각 상황에 맞는 재무 차원의 데이터만 입력을 허용할 수 있으며 항상 정확한 데이터가 캡처되어야 한다는 요구 사항을 적용할 수도 있습니다.

자세한 내용은 다음 항목을 참조하세요.
- [계정 차트 계획](plan-chart-of-accounts.md) 
- [분개장에 대한 고급 규칙 만들기](tasks/create-advanced-rules-journals.md)
- [템플릿을 사용하여 분개장 기입 만들기](tasks/create-journal-entry-template.md)
- [저널 만들기 및 유효성 검사](tasks/create-validate-journals.md)
- [정기 분개장 게시](tasks/post-periodic-journals.md)
- [원장 할당 분개장 처리](tasks/process-ledger-allocation-journal.md)

## <a name="simulate-posting"></a>게시 시뮬레이션
대부분 분개장의 **유효성 검사** 메뉴에서 **게시 시뮬레이션** 을 찾을 수 있습니다. **유효성 검사** 기능을 사용하여 분개장의 유효성을 검사하면 시스템은 특정 오류 조건에 따라 분개장을 테스트합니다. **게시 시뮬레이션** 기능을 사용하면 실제로 분개장을 게시하지 않고 게시 중에 실행되는 동일한 프로세스를 모두 실행합니다. 그런 다음 표시되는 게시 메시지를 검토하고 발견한 오류를 수정한 다음 **게시** 메뉴를 열어 분개장을 게시할 수 있습니다. 

일괄 처리에는 **게시 시뮬레이션** 을 사용할 수 없습니다. 그러나 게시의 일괄 처리를 시뮬레이션할 수 있는 코드가 있으며 개발자는 이 코드를 확장하여 해당 기능을 추가할 수 있습니다.  

## <a name="journal-unlock"></a>분개장 잠금 해제
분개장 페이지에서 "시스템에 의해 잠김" 상태가 예로 설정된 분개장을 잠금 해제하는 버튼을 사용할 수 있습니다. 시스템 관리자는 실행 중인 배치 작업을 분석하고 이 분개장이 더는 일괄 처리 작업에 의해 적극적으로 처리되지 않는다는 것을 확인하고 이 잠금 해제를 수행할 수 있습니다. 이 버튼은 **기능 관리** 페이지의 **분개장 잠금 해제 버튼** 이라는 기능으로 활성화됩니다. 

## <a name="workflow-recall"></a>워크플로 회수 
워크플로에서 상태가 "복구 불가"인 분개장을 회수하는 이 기능은 분개장의 **워크플로** 버튼과 **워크플로 기록** 페이지를 사용하여 활성화됩니다. 이 기능은 **기능 관리** 페이지의 **분개장의 워크플로 상태 재설정** 이라는 기능으로 활성화합니다.

## <a name="delete-journal-lines"></a>분개장 라인 삭제
모든 분개장 라인을 빠르게 삭제하는 기능이며 분개장의 **기능** > **분개장 라인 삭제** 에서 활성화합니다. 이 기능을 활성화하려면 **기능 관리** 에서 **저널 성능 최적화 삭제** 를 선택합니다. 이 기능은 각 라인의 **Delete** 메서드를 호출하지 않고 라인 집합을 제거하므로 **LedgerJournalTrans** 테이블의 확장과 **Delete** 메서드에 영향을 줍니다. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]