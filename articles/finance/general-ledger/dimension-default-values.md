---
title: 재무 분개장의 기본 재무 차원
description: 이 항목에서는 재무 분개장을 통해 입력된 거래 건에서 재무 차원 값이 설정되는 방법을 정의하는 규칙에 대해 설명합니다. 또한 고정 차원이 사용되는 시나리오에 대한 세부 정보도 제공합니다.
author: kweekley
ms.date: 09/04/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransDaily, LedgerJournalTransVendInvoice, LedgerJournalTransVendPaym, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 327bc27f068e1f9eefacc6b5defa27044cb1a77e
ms.sourcegitcommit: d420b96d37093c26f0e99c548f036eb49a15ec30
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2021
ms.locfileid: "8452887"
---
# <a name="default-financial-dimensions-on-financial-journals"></a>재무 분개장의 기본 재무 차원

[!include [banner](../includes/banner.md)]

이 항목에서는 (재고 분개장 또는 프로젝트 분개장이 아닌) 재무 분개장을 통해 입력된 거래 건에서 재무 차원 값이 설정되는 방법을 정의하는 규칙에 대해 설명합니다. 또한 고정 차원이 사용되는 시나리오에 대한 세부 정보도 제공합니다.

## <a name="symptom"></a>증상

재무 차원 값이 재무 분개장 내 계정 또는 상쇄 계정에서 예상대로 설정되지 않았습니다. 다음 시나리오는 두 가지 예를 소개합니다.

쿠폰이 일반 분개장에 입력됩니다. 계정은 공급업체 계정이며 상쇄 계정은 은행 계정에 속합니다. 공급업체의 재무 차원은 기본적으로 계정에 입력되지만 은행의 재무 차원은 상쇄 계정에 기본적으로 입력되지 않습니다. 그 대신, 계정의 차원 값이 기본적으로 상쇄 계정에 입력됩니다.

고객에게는 기본 재무 차원 값이 할당되며 수익 주 계정에는 부서 재무 차원에 대한 고정 차원 값이 할당됩니다. 쿠폰이 일반 분개장에 입력됩니다.  계정은 고객이고 상쇄 계정은 원장 계정, 특히 고정 차원 값이 있는 수익 계정입니다. 고정 차원은 수익 주 계정의 상쇄 계정에 설정되어 있지 않습니다. 그 대신, 고객에게서 가져온 계정의 부서 차원 값으로 설정됩니다.  쿠폰을 기장한 후 기장된 회계 항목에 고정 차원 값이 사용되지만 해당 쿠폰은 여전히 수익 계정에서 고객의 부서 값을 표시합니다. 

분개장 내 쿠폰에 설정된 재무 차원 값에 대해서는 어떤 규칙을 따르나요?

## <a name="resolution"></a>해결책

일반 분개장 또는 공급업체 송장 분개장 같은 재무 분개장에서 쿠폰 라인에 기본적으로 재무 차원 값을 입력하려면 다음 규칙을 따릅니다. 

1. **분개장 헤더**

   - 분개장 헤더 차원은 기본적으로 저널 이름 차원에서 입력됩니다.

2. **분개장 항목 계정**

   - 분개장 항목 계정 차원은 기본적으로 저널 헤더 차원에서 입력됩니다.
   - 재무 차원이 비어 있는 경우, 해당 값은 기본적으로 고객, 공급업체, 은행, 고정 자산, 프로젝트 또는 원장 차원에서 입력됩니다.

     - 계정 유형이 **원장** 일 경우, 원장 계정의 고정 차원은 거래 내역 입력 시 기본 차원으로 처리됩니다.
     - 계정 유형이 **고객**, **공급업체**, **은행**, **고정 자산** 또는 **프로젝트** 일 경우, 주 계정은 아직 결정할 수 없습니다. 따라서 해당 계정에 대해 고정 차원이 기본적으로 입력되지 않습니다.

3. **분개장 항목 상쇄 계정**

 - 먼저 분개장 항목 상쇄 계정 차원은 기본적으로 분개장 항목 계정 차원에서 입력됩니다.

 - 재무 차원이 비어 있는 경우, 다음 기본 항목은 고객, 공급업체, 은행, 고정 자산, 프로젝트 또는 원장의 기본 차원에서 가져옵니다.
   1. 상쇄 계정 유형이 **원장** 일 경우, 원장 계정의 고정 차원은 거래 내역 입력 시 기본 차원으로 처리됩니다. 차원 값이 계정에서 이미 기본적으로 입력된 경우, 주 계정의 기본 또는 고정 차원 값은 기존 값을 재정의하지 않습니다.
   2. 상쇄 계정 유형이 **고객**, **공급업체**, **은행**, **고정 자산** 또는 **프로젝트** 일 경우, 주 계정은 아직 알려지지 않았으므로 고정 차원은 상쇄 계정의 기본값으로 설정되지 않습니다.

4. **기장**

    1. 기장하는 동안 회계 항목의 각 라인에 대한 주 계정(계정 및 상쇄 계정 모두에 대해)은 고정 차원 값이 있는지 여부를 결정하기 위해 평가됩니다. 고정 차원이 정의되면 기존 값이나 공백 값은 해당 고정 차원 값으로 대체됩니다.

        고정 차원 값은 기장 후 분개장 항목에 표시되지 **않습니다**. 그 대신, 게시된 쿠폰을 볼 때 회계 항목에 표시됩니다.

    2. 페니 반올림 계정 및 회사 간 대금 거래 계정과 같이 기장 시 추가될 수 있는 추가 원장 계정을 포함해 기장 중에 기본적으로 다른 차원 값이 입력되지 않습니다. 추가 원장 계정에 대한 기본 차원 항목은 계정 또는 상쇄 계정에서 가져옵니다.

기본적으로 차원 값을 입력하기 위한 목적상, 분개장 기본 프로세스는 빈 차원 값이 의도적으로 비워둔 것인지 아니면 기본 항목을 입력하지 않았는지 여부를 판단할 수 없습니다. 차원 값을 의도적으로 비워 둔 경우, 앞서 설명한 기본값 설정 순서를 사용하여 기본적으로 값을 계속 입력할 수 있습니다. 하나의 차원에 빈 값이 있어야 하는 경우, 빈 차원 대신 사용할 수 있도록 값이 **0**(영) 또는 **Blank** 인 차원을 생성해야 할 수 있습니다.

재무 차원 기본값 설정 순서의 예는 다음 시나리오를 검토하십시오.

### <a name="scenario-1"></a>시나리오 1

**총계정원장 \> 분개장 설정 \> 분개장 이름** 으로 이동해 **GenJrn** 분개장 이름을 선택합니다. 그런 다음, **재무 차원** 빠른 탭에서 기본 재무 차원에 대해 다음 값을 정의합니다.

- **BUSINESSUNIT:** 001
- **DEPARTMENT:** 024

[![분개장 이름 페이지](./media/financial-dimension-defaulting-jrnl-names-01.png)](./media/financial-dimension-defaulting-jrnl-names-01.png)

**총계정원장 \> 분개장 기입 \> 일반 분개장** 으로 이동하여 **GenJrn** 분개장 이름을 사용하는 새 일반 분개장을 만듭니다. 차원은 **재무 차원** 탭에 표시된 대로 기본적으로 분개장 이름(LedgerJournalName 테이블)에서 분개장 헤더(LedgerJournalTable 테이블)까지 입력됩니다.

[![일반 분개장 페이지의 재무 차원 탭](./media/financial-dimension-defaulting-genrl-jrnl-02.png)](./media/financial-dimension-defaulting-genrl-jrnl-02.png)

**라인** 으로 이동합니다. **계정 유형** 필드에서 **원장** 을 선택한 다음, **계정** 필드에 **170150** 을 입력합니다. 그런 다음, **탭** 키를 선택해 필드 밖으로 이동합니다. 해당 차원은 기본적으로 분개장 헤더에서 입력됩니다. 따라서 **계정** 값은 **170150-001-024** 로 표시됩니다.

[![분개장 쿠폰 페이지의 일반 분개장에 대한 분개장 항목](./media/financial-dimension-defaulting-jrnl-vchr-03.png)](./media/financial-dimension-defaulting-jrnl-vchr-03.png)

**계정** 값을 **170150-001-023** 으로 변경합니다. 차변 금액 또는 대변 금액을 입력합니다. **상쇄 계정 유형** 필드에서 **원장** 을 선택한 다음, **상쇄 계정** 필드에 **600150** 을 입력합니다. 차원 값은 기본적으로 계정에서 입력됩니다. 따라서 **상쇄 계정** 값은 **600150-001-023** 으로 표시됩니다.

### <a name="scenario-2"></a>시나리오 2

시나리오 1에서 분개장 이름에 대해 정의한 것과 동일한 재무 차원을 사용합니다. 그런 다음, **수취 계정 \> 고객 \> 모든 고객** 으로 이동하여 고객 US-001에 대한 기본 재무 차원 값을 정의합니다. 해당 고객을 선택하여 고객 세부 정보를 엽니다. **재무 차원** 탭에서 **BUSINESSUNIT** 차원에 대한 기본값(**001**)을 유지합니다. **COSTCENTER** 차원을 추가한 후, **007** 을 값으로 입력합니다.

**GenJrn** 분개장 이름을 사용하는 새 일반 분개장을 만듭니다. **재무 차원** 탭에서 **BUSINESSUNIT** 기본값을 **001** 에서 **002** 로 변경합니다.

**라인** 으로 이동합니다. **계정 유형** 필드에서 **고객** 을 선택한 다음, **계정** 필드에 **US-001** 을 입력합니다. 원장 외 계정 유형에 대한 재무 차원을 보려면 **재무 차원 \> 계정** 을 선택합니다. 재무 차원 값에 대해 다음과 같은 기본 항목이 입력됩니다.

- **BUSINESSUNIT:** 002 – 기본 항목은 분개장 헤더에서 가져옵니다. 기본값이 이미 입력되었으므로 값 **001** 은 기본적으로 고객 US-001에서 입력되지 않습니다.
- **COSTCENTER:** 007 – 기본 항목은 고객 US-001 설정에서 가져옵니다.
- **DEPARTMENT:** 024 – 기본 항목은 분개장 헤더에서 가져옵니다.

라인으로 돌아가 **상쇄 계정 유형** 에서 **원장** 을 선택한 다음, **상쇄 계정** 필드에 **600150** 을 입력합니다. 다음과 같은 기본 재무 차원 값이 라인에 입력됩니다.

- **BUSINESSUNIT:** 002 – 계정의 재무 차원에서 기본 항목을 가져옵니다. (원래는 분개장 헤더에서 기본적으로 입력되었습니다.)
- **DEPARTMENT:** 024 – 계정의 재무 차원에서 기본 항목을 가져옵니다. (원래는 분개장 헤더에서 기본적으로 입력되었습니다.)
- **COSTCENTER:** 007 – 계정의 재무 차원에서 기본 항목을 가져옵니다. (원래는 고객으로부터 기본적으로 입력되었습니다.)

### <a name="scenario-3"></a>시나리오 3

시나리오 2에 사용한 것과 동일한 분개장에 새 라인을 추가합니다. **계정 유형** 필드에서 **원장** 을 선택한 다음, **계정** 필드에 **170150** 을 입력합니다. 주 계정 170150만 남도록 기본 차원 값을 지웁니다. **상쇄 계정 유형** 필드에서 **고객** 을 선택한 다음, **상쇄 계정** 필드에 **US-001** 을 입력합니다. 재무 차원 값에 대해 다음과 같은 기본 항목이 입력됩니다.

- **BUSINESSUNIT:** 002 – 계정 차원 값이 비어 있기 때문에 기본 항목은 분개장 헤더에서 가져옵니다. 기본값은 이미 분개장 헤더에서 가져왔으므로 값 **001** 은 기본적으로 고객 US-001에서 입력되지 않습니다. 만약 **BUSINESSUNIT** 값을 의도적으로 비워두었다면 상쇄 계정에서 재무 차원도 제거해야 합니다.
- **COSTCENTER:** 007 – 계정 차원 값과 분개장 헤더 차원 값이 비어 있기 때문에 기본 항목은 고객 US-001에서 가져옵니다. 만약 **COSTCENTER** 값을 의도적으로 비워두었다면 상쇄 계정에서 재무 차원도 제거해야 합니다.
- **DEPARTMENT:** 024 – 계정 차원 값이 비어 있기 때문에 기본 항목은 분개장 헤더에서 가져옵니다. 만약 **DEPARTMENT** 값을 의도적으로 비워두었다면 상쇄 계정에서 재무 차원도 제거해야 합니다.

### <a name="scenario-4"></a>시나리오 4

시나리오 1과 2에서 분개장 이름과 고객에 대해 정의한 것과 동일한 기본 재무 차원 값을 사용합니다. 그런 다음, 주 계정 170150의 **BUSINESSUNIT** 차원에 대해 고정된 차원 값을 정의합니다. **총계정원장 \> 계정 차트 \> 계정 \> 주 계정** 으로 이동합니다. **주 계정** 필드에서 **170150** 을 선택한 다음, **법인 재정의** 탭에서 **추가** 를 선택합니다. **USMF** 를 법인으로 선택한 다음, **추가** 를 선택합니다. 해당 레코드를 선택한 다음, **기본 차원** 을 선택합니다. **BUSINESSUNIT** 차원을 **고정 값** 으로 변경한 다음, **003** 을 값으로 입력합니다.

**GenJrn** 분개장 이름을 사용하는 새 일반 분개장을 만듭니다. **재무 차원** 탭에서 모든 기본 차원 값을 제거합니다.

**라인** 으로 이동합니다. **계정 유형** 필드에서 **원장** 을 선택한 다음, **계정** 필드에 **170150** 을 입력합니다. 그런 다음, **탭** 키를 선택해 필드 밖으로 이동합니다. 차원 값은 기본적으로 계정 170150에 대한 주 계정 설정에서 입력됩니다. 따라서 **계정** 값은 **170150-003-** 으로 표시됩니다.

**계정** 값을 **170150-004-** 로 변경합니다. **분개장 기능은 고정 차원 값이 변경되는 것을 방지하지 않습니다.** 차변 금액 또는 대변 금액을 입력합니다. **상쇄 계정 유형** 필드에서 **원장** 을 선택한 다음, **상쇄 계정** 필드에 **170250** 을 입력합니다. 재무 차원 값 004는 계정에서 기본값으로 입력됩니다. 그런 다음, 문서를 기장합니다. 분개장에서 **쿠폰** 을 선택합니다. 기장을 진행하는 중 **BUSINESSUNIT** 값이 고정 차원 값인 **003** 으로 되돌아갔습니다.

분개장의 쿠폰으로 돌아가면 **BUSINESSUNIT** 차원이 고정 차원 값을 반영하지 **않습니다**. 이것은 기장하기 전에 화면에 표시된 값을 항상 갖습니다. 기장 프로세스는 쿠폰에 입력된 어떠한 내용도 변경하지 않습니다. 기장 중에는 회계 항목만 변경됩니다.

## <a name="developer-notes"></a>개발자 노트

개발자로서 기본 프로세스에 대한 코드를 보고 싶다면 다음과 같은 메서드를 검토하십시오.

- **LedgerJournalEngine.accountModified()** – 이 메서드는 모든 분개장에 대해 표준에 해당되는 기본 계정 차원 기본값 설정 프로세스의 주 진입점입니다.
- **LedgerJournalEngine.offsetAccountModified()** – 이 메서드는 상쇄 계정 차원 기본값 설정 프로세스의 주 진입점입니다.