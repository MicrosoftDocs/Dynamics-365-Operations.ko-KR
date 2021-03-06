---
title: 지불 및 약속 어음에 대한 TDS 계산
description: 이 토픽에서는 원천공제세(TDS)가 계산되는 다양한 지불 트랜잭션에 대한 참조 정보를 제공합니다.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: d5c9822c2e4f71fb89776d1c1c76056bad85d484
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8451792"
---
# <a name="tds-calculation-on-payments-and-promissory-notes"></a>지불 및 약속 어음에 대한 TDS 계산

[!include [banner](../includes/banner.md)]

이 토픽에서는 원천공제세(TDS)가 계산되는 다양한 지불 트랜잭션에 대한 참조 정보를 제공합니다.

| 일련 번호 | 트랜잭션 유형 | 트랜잭션 금액 | 페이지 이름 및 경로 | 계정 유형 및 상쇄 계정 유형 |
|---------------|------------------|--------------------|--------------------|--------------------------------------|
| 1             | 선지급/송장에 대한 지급(TDS 미지급) | 차변 또는 대변 | <ul><li>일반 분개장(**총계정원장 \> 분개장 항목 \> 일반 분개장**)</li><li>인보이스 분개장(**지급 계정 \> 송장 \> 송장 분개장**)</li><li>지불 분개장(**지급 계정 \> 지불 \> 공급업체 지불 분개장**)</li></ul> | 공급업체(Dr.), 은행(Cr.) |
| 2             | 선지급/인보이스 지불(고객 구매 – TDS 미지급) | 차변 또는 대변 | <ul><li>일반 분개장(**총계정원장 \> 분개장 항목 \> 일반 분개장**)</li><li>인보이스 분개장(**지급 계정 \> 송장 \> 송장 분개장**)</li><li>지불 분개장(**지급 계정 \> 지불 \> 공급업체 지불 분개장**)</li></ul> | 고객(Dr.), 은행(Cr.) |
| 3             | 약속 어음 | 차변 | 인출 약속 어음 분개장(**지급 계정 \> 지불 \> 약속 어음 \> 인출 약속 어음 분개장**) | 공급업체(Dr.), 원장(Cr.) |
| 4             | 기타 소득(TDS 미수금) | 차변 또는 대변 | 일반 분개장(**총계정원장 \> 분개장 항목 \> 일반 분개장**) | 은행(Dr.), 원장(Cr.) |
| 5             | 기타 비용(TDS 미지급) | 차변 또는 대변 | 일반 분개장(**총계정원장 \> 분개장 항목 \> 일반 분개장**) | 은행(Dr.), 원장(Cr.) |

지불 및 약속 어음에 대한 TDS를 계산하려면 다음 단계를 따르십시오.

1. 분개장 페이지에서 분개 라인을 만듭니다. 계정 유형 및 상쇄 계정 유형을 선택합니다.
2. **기능 \> 정산** 을 선택하여 **미결 트랜잭션 편집** 페이지를 엽니다. 그런 다음 정산해야 하는 특정 송장을 선택합니다. TDS가 이미 송장 수준에서 계산된 경우 **금액 출처** 필드에 TDS가 계산된 기본 금액이 표시됩니다. **TDS 금액** 필드는 트랜잭션에 대해 계산된 TDS 금액을 보여줍니다. **금액** 필드에는 순 지불 금액(즉, TDS를 공제한 후 지불 금액)이 표시됩니다.

    > [!NOTE]
    > 송장에 대해 이루어진 지불의 경우 다음 조건이 적용됩니다.
    >
    > - 지불 금액과 송장 금액이 동일한 경우 이미 송장 수준에서 계산되었다면 TDS는 계산되지 않습니다.
    > - TDS 금액을 공제한 후의 송장 금액이 지불 금액보다 많을 경우 TDS가 계산되지 않습니다.
    > - TDS 금액을 공제한 후의 송장 금액이 지불 금액보다 적은 경우 송장 금액을 초과하는 금액에 대해 TDS를 계산합니다.

3. **분개장 바우처** 페이지, **개요** 탭의 **TDS 그룹** 필드에서 공급업체 또는 고객에 대해 정의된 기본 TDS 그룹을 검토하거나 변경합니다. 분개장 라인에서 계산되는 TDS는 TDS 그룹의 TDS 세금 코드에 대해 정의된 공식을 기반으로 합니다.

    > [!NOTE]
    > TDS는 **공급업체** 페이지에서 공급업체에 대해 **원천징수세 계산** 옵션이 **예** 로 설정된 경우에만 계산됩니다.

4. **세금 정보** 탭의 **회사 정보** 섹션의 **이름** 필드에서 회사에 대해 설정된 대체 주소의 회사 이름을 선택할 수 있습니다.

    **원천징수세** 섹션에서 **피납세자 특성** 필드는 공급업체 또는 고객의 피납세자 범주의 특성을 보여줍니다. **세금 계정 번호(TAN)** 필드는 선택한 회사의 세금 계정 번호(TAN)를 보여줍니다.

5. **원천징수세 버튼 \> 원천징수세** 를 선택하여 **임시 원천징수세 트랜잭션** 페이지를 엽니다. 이 페이지의 상단에는 다음 필드가 있습니다.

    - **원천징수세 총액** – TDS 그룹에 대한 트랜잭션에 대해 계산된 총 TDS입니다.
    - **값** – 트랜잭션에 대한 TDS를 계산하는 데 사용된 총 백분율입니다. 총 백분율은 TDS 세금 코드에 대해 정의되고 TDS 그룹에 첨부된 공식을 기반으로 합니다.
    - **조정된 원천징수세 총액** – TDS 그룹의 모든 세금 코드에 대해 조정된 총 TDS 금액입니다.
    - **TDS** – 체크박스가 선택되어 있으면 TDS 그룹이 트랜잭션에 연결되었음을 나타냅니다.

    **개요** 필드의 **일반** 및 **조정** 탭에는 TDS 그룹에 연결된 각 TDS 세금 코드에 대해 계산된 TDS 금액과 조정된 TDS 금액의 세부 정보가 표시됩니다.

6. **임계값** 을 선택하여 **임계값** 페이지를 엽니다. 여기에서 특정 TDS 세금 코드에 첨부된 TDS 세금 구성요소에 대해 정의된 임계값 한도를 검토할 수 있습니다.
7. **공식 디자이너** 를 선택하여 **공식 디자이너** 페이지를 엽니다. 여기에서 특정 TDS 세금 코드에 대해 정의된 공식을 검토할 수 있습니다.
8. **공식 디자이너** 및 **임시 원천징수세 트랜잭션** 페이지를 닫고 **분개장 바우처** 페이지로 돌아갑니다.
9. 분개장을 확인하고 전기합니다. 계산된 TDS 금액은 TDS 그룹의 각 TDS 세금 코드에 대해 정의된 미지급 계정에 전기됩니다. TDS 세금 코드의 미수금 계정은 **원천징수세 코드** 페이지에 정의되어 있습니다.
10. **전기된 원천징수세** 를 선택하여 **원천징수세 트랜잭션** 페이지를 엽니다. **값** 필드는 트랜잭션에 대한 TDS를 계산하는 데 사용된 총 백분율을 보여줍니다.

    **개요** 필드의 **일반** 및 **금액** 탭에는 트랜잭션에 연결된 TDS 그룹에 대해 계산된 TDS 금액이 표시됩니다.

11. TDS 그룹에 첨부된 각 TDS 세금 코드에 대한 TDS 계산 정보를 검토합니다.

## <a name="generate-payments"></a>지불 생성

지불을 생성하려면 다음 단계를 따르세요.

1. 다음 단계 중 하나를 따르십시오.

    - **지급 계정 \> 지불 \> 공급업체 지불 분개장** 으로 이동합니다.
    - **수취 계정 \> 지불 \> 고객 지불 분개장** 으로 이동합니다.
    - **지급 계정 \> 지불 \> 약속 어음 \> 인출 약속 어음 분개장** 으로 이동합니다.
    - **수취 계정 \> 지불 \> 환어음 \> 인출 환어음 분개장** 으로 이동합니다.
    - **수취 계정 \> 지불 \> 환어음 \> 재인출 환어음 분개장** 으로 이동합니다.

2. **라인** 을 선택합니다.
3. **기능 \> 지불 생성** 을 선택합니다.
